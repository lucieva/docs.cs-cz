---
title: Vytváření sloupců výrazů
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0af3bd64-92a2-4b47-ae62-f5df35f131a6
ms.openlocfilehash: 9c7a656e82198568c39b9bb58f8708f563d6caa2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2018
ms.locfileid: "43520824"
---
# <a name="creating-expression-columns"></a>Vytváření sloupců výrazů
Výraz pro sloupec můžete definovat, díky tomu se může obsahovat hodnotu počítá z jiných hodnot sloupců na stejném řádku nebo z hodnoty ve sloupcích více řádků v tabulce. Chcete-li definovat výraz, který má být vyhodnocen, použijte <xref:System.Data.DataColumn.Expression%2A> vlastnost cílového sloupce a jeho používání <xref:System.Data.DataColumn.ColumnName%2A> vlastnost k odkazování na ostatní sloupce ve výrazu. <xref:System.Data.DataColumn.DataType%2A> Sloupec musí být výraz odpovídající hodnotu, která vrací výraz.  
  
 Následující tabulka uvádí několik možných použití výrazu sloupce v tabulce.  
  
|Typ výrazu|Příklad|  
|---------------------|-------------|  
|Srovnání|"Celkový > = 500"|  
|Výpočet|"UnitPrice * Quantity"|  
|Agregace|Výraz sum(price)|  
  
 Můžete nastavit **výraz** vlastnost na existující **DataColumn** objektu, nebo můžete zahrnout vlastnost jako třetí argument předaný do <xref:System.Data.DataColumn> konstruktoru, jak je znázorněno v následujícím příkladu.  
  
```vb  
workTable.Columns.Add("Total",Type.GetType("System.Double"))  
workTable.Columns.Add("SalesTax", Type.GetType("System.Double"), _  
  "Total * 0.086")  
```  
  
```csharp  
workTable.Columns.Add("Total", typeof(Double));  
workTable.Columns.Add("SalesTax", typeof(Double), "Total * 0.086");  
```  
  
 Výrazy mohou odkazovat na jiné sloupce výrazu; Cyklický odkaz, ve kterém dvou výrazů odkazovat na sebe navzájem, ale bude generovat výjimku. Pravidla týkající se vytváření výrazů, najdete v článku <xref:System.Data.DataColumn.Expression%2A> vlastnost **DataColumn** třídy.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.Data.DataColumn>  
 <xref:System.Data.DataSet>  
 <xref:System.Data.DataTable>  
 [Definice schématu datové tabulky](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)  
 [Datové tabulky](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [ADO.NET spravovaných zprostředkovatelích a datové sady pro vývojáře](https://go.microsoft.com/fwlink/?LinkId=217917)
