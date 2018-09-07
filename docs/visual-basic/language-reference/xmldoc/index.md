---
title: Doporučené značky XML pro dokumentační komentáře (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 3b2dec4224006d35fb9add11e170b9dcbeeafcf3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881278"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="c0d9a-102">Doporučené značky XML pro dokumentační komentáře (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0d9a-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>
<span data-ttu-id="c0d9a-103">Kompilátor jazyka Visual Basic můžete zpracovat dokumentační komentáře v kódu do souboru XML.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="c0d9a-104">Další nástroje můžete použít ke zpracování souboru XML do dokumentace ke službě.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="c0d9a-105">Komentáře XML jsou povolené konstrukcí jako jsou typy a členy typu.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="c0d9a-106">Pro částečné typy mají pouze jednu část typu komentáře XML, ačkoli neexistuje žádné omezení komentování jejích členů.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0d9a-107">Dokumentační komentáře nelze použít pro obory názvů.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="c0d9a-108">Důvodem je, že jeden obor názvů může zahrnovat několik sestavení, a ne všechna sestavení mají být načteny současně.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="c0d9a-109">Kompilátor zpracovává všechny značky, který je platný kód XML.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="c0d9a-110">Následující značky poskytuje běžně používané funkce v dokumentaci pro uživatele.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[<span data-ttu-id="c0d9a-111">\<c ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-111">\<c></span></span>](../../../visual-basic/language-reference/xmldoc/c.md)|[<span data-ttu-id="c0d9a-112">\<kód ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-112">\<code></span></span>](../../../visual-basic/language-reference/xmldoc/code.md)|[<span data-ttu-id="c0d9a-113">\<Příklad ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-113">\<example></span></span>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|<span data-ttu-id="c0d9a-114">[\<Výjimka >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-114">[\<exception>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup></span></span>|<span data-ttu-id="c0d9a-115">[\<Zahrnout >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-115">[\<include>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup></span></span>|[<span data-ttu-id="c0d9a-116">\<Seznam ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-116">\<list></span></span>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[<span data-ttu-id="c0d9a-117">\<para ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-117">\<para></span></span>](../../../visual-basic/language-reference/xmldoc/para.md)|<span data-ttu-id="c0d9a-118">[\<Param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-118">[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup></span></span>|[<span data-ttu-id="c0d9a-119">\<paramref ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-119">\<paramref></span></span>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|<span data-ttu-id="c0d9a-120">[\<oprávnění >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-120">[\<permission>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup></span></span>|[<span data-ttu-id="c0d9a-121">\<REMARKS ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-121">\<remarks></span></span>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[<span data-ttu-id="c0d9a-122">\<Vrátí ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-122">\<returns></span></span>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|<span data-ttu-id="c0d9a-123">[\<Zobrazit >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-123">[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup></span></span>|<span data-ttu-id="c0d9a-124">[\<SeeAlso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-124">[\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup></span></span>|[<span data-ttu-id="c0d9a-125">\<Summary ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-125">\<summary></span></span>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|<span data-ttu-id="c0d9a-126">[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c0d9a-126">[\<typeparam>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup></span></span>|[<span data-ttu-id="c0d9a-127">\<Hodnota ></span><span class="sxs-lookup"><span data-stu-id="c0d9a-127">\<value></span></span>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 <span data-ttu-id="c0d9a-128">(<sup>1</sup> kompilátor ověří syntaxi.)</span><span class="sxs-lookup"><span data-stu-id="c0d9a-128">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c0d9a-129">Pokud chcete ostré závorky se zobrazí v textu Dokumentační komentář, použijte `&lt;` a `&gt;`.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-129">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="c0d9a-130">Například řetězec `"&lt;text in angle brackets&gt;"` se zobrazí jako `<text in angle brackets>`.</span><span class="sxs-lookup"><span data-stu-id="c0d9a-130">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0d9a-131">Viz také</span><span class="sxs-lookup"><span data-stu-id="c0d9a-131">See Also</span></span>  
 [<span data-ttu-id="c0d9a-132">Dokumentace kódu s XML</span><span class="sxs-lookup"><span data-stu-id="c0d9a-132">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="c0d9a-133">/doc</span><span class="sxs-lookup"><span data-stu-id="c0d9a-133">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [<span data-ttu-id="c0d9a-134">Postupy: Vytvoření dokumentace XML</span><span class="sxs-lookup"><span data-stu-id="c0d9a-134">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)