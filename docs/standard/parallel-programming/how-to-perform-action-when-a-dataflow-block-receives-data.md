---
title: 'Postupy: Provádění akcí po přijetí dat do bloku toku dat'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- TPL dataflow library, receiving data
ms.assetid: fc2585dc-965e-4632-ace7-73dd02684ed3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd5963fee985633d843cc60f521b66000b84e55e
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/08/2018
ms.locfileid: "44217188"
---
# <a name="how-to-perform-action-when-a-dataflow-block-receives-data"></a>Postupy: Provádění akcí po přijetí dat do bloku toku dat
*Blok toku dat provádění* typy volat uživatelského delegáta, pokud obdrží data. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, A <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType> třídy jsou typy bloků toku dat provádění. Můžete použít `delegate` – klíčové slovo (`Sub` v jazyce Visual Basic), <xref:System.Action%601>, <xref:System.Func%602>, nebo výraz lambda, když poskytují pracovní funkce, která se z bloku toku dat provádění. Tento dokument popisuje způsob použití <xref:System.Func%602> a lambda výrazy k provedení akce v blocích po spuštění.  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]

## <a name="example"></a>Příklad  
 Následující příklad používá tok dat pro čtení souboru z disku a vypočítá počet bajtů v tomto souboru, které jsou si rovny hodnotě nula. Používá <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> ke čtení souboru a vypočítat počet nula bajtů a <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> tisknout číslo nula bajtů do konzoly. <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> Určuje objekt <xref:System.Func%602> objekt pro provedení práce po bloky přijímat data. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> Objektu používá výraz lambda k tisku ke konzole číslo nula bajtů, které jsou pro čtení.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#1)]
 [!code-vb[TPLDataflow_ExecutionBlocks#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#1)]  
  
 I když můžete zadat výraz lambda definoval se <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objektů, v tomto příkladu <xref:System.Func%602> povolit další kódu pro použití `CountBytes` metoda. <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> Objektu používá lambda výraz, protože práce, která musí provést, je specifická pro tuto úlohu a není mohly být užitečné z jiného kódu. Další informace o tom, jak fungují výrazy lambda v knihovně Task Parallel Library najdete v tématu [výrazy Lambda v PLINQ a TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).  
  
 V části Souhrn delegovat typy v [toku dat](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) dokument shrnuje typy delegátů, které můžete poskytnout <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602>, a <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> objekty. Tabulka také určuje, zda typ delegáta pracuje synchronně nebo asynchronně.  
  
## <a name="compiling-the-code"></a>Probíhá kompilace kódu  
 Zkopírujte ukázkový kód a vložte ho do projektu sady Visual Studio nebo vložit do souboru s názvem `DataflowExecutionBlocks.cs` (`DataflowExecutionBlocks.vb` v jazyce Visual Basic), a pak spusťte následující příkaz v okně Příkazový řádek sady Visual Studio.  
  
 Visual C#  
  
 **csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.cs**  
  
 Visual Basic  
  
 **Vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowExecutionBlocks.vb**  
  
## <a name="robust-programming"></a>Robustní programování  
 V tomto příkladu obsahuje delegát typu <xref:System.Func%602> k <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objekt pro provedení úlohy bloku toku dat synchronně. Pokud chcete povolit bloku toku dat chovat asynchronně, zadejte delegát typu <xref:System.Func%601> do bloku toku dat. Při bloku toku dat chová asynchronně, úloha bloku toku dat je kompletní jenom v případě vrácený <xref:System.Threading.Tasks.Task%601> objekt dokončí. Následující příklad upravuje `CountBytes` metody a použije [asynchronní](~/docs/csharp/language-reference/keywords/async.md) a [await](~/docs/csharp/language-reference/keywords/await.md) operátory ([asynchronní](~/docs/visual-basic/language-reference/modifiers/async.md) a [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) v Visual Basic) asynchronně vypočítat celkový počet bajtů, které mají hodnotu nula do zadaného souboru. <xref:System.IO.FileStream.ReadAsync%2A> Metoda provádí asynchronní operace čtení souboru.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#2)]
 [!code-vb[TPLDataflow_ExecutionBlocks#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#2)]  
  
 Asynchronní lambda výrazy můžete použít také k provedení akce z bloku toku dat provádění. Následující příklad upravuje <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objekt, který se používá v předchozím příkladu tak, aby používala výrazu lambda a provádí práci asynchronně.  
  
 [!code-csharp[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_executionblocks/cs/dataflowexecutionblocks.cs#3)]
 [!code-vb[TPLDataflow_ExecutionBlocks#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_executionblocks/vb/dataflowexecutionblocks.vb#3)]  
  
## <a name="see-also"></a>Viz také:

- [Tok dat](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
