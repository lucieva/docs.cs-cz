---
title: "Řešení externím prostředkům během zpracování XSLT"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 3a59d31c-0ec5-4de6-a2a9-558531c8116e
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8921321191a68899e114613f8469e1552fff34bf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="resolving-external-resources-during-xslt-processing"></a><span data-ttu-id="83eeb-102">Řešení externím prostředkům během zpracování XSLT</span><span class="sxs-lookup"><span data-stu-id="83eeb-102">Resolving External Resources During XSLT Processing</span></span>
<span data-ttu-id="83eeb-103">Existují několikrát během transformace XSLT, kdy budete muset vyřešit externím prostředkům.</span><span class="sxs-lookup"><span data-stu-id="83eeb-103">There are several times during an XSLT transformation when you may need to resolve external resources.</span></span>  
  
## <a name="using-the-xmlresolver-class"></a><span data-ttu-id="83eeb-104">Používání třídy objekt XmlResolver</span><span class="sxs-lookup"><span data-stu-id="83eeb-104">Using the XmlResolver Class</span></span>  
 <span data-ttu-id="83eeb-105"><xref:System.Xml.XmlResolver> Třída se používá k překladu externím prostředkům.</span><span class="sxs-lookup"><span data-stu-id="83eeb-105">The <xref:System.Xml.XmlResolver> class is used to resolve external resources.</span></span> <span data-ttu-id="83eeb-106">Následující tabulka popisuje, kdy <xref:System.Xml.XmlResolver> spojené se stane při zpracování XSLT.</span><span class="sxs-lookup"><span data-stu-id="83eeb-106">The following table describes when the <xref:System.Xml.XmlResolver> becomes involved during XSLT processing.</span></span>  
  
|<span data-ttu-id="83eeb-107">Úloha XSLT</span><span class="sxs-lookup"><span data-stu-id="83eeb-107">XSLT task</span></span>|<span data-ttu-id="83eeb-108">Co objekt XmlResolver se používá pro</span><span class="sxs-lookup"><span data-stu-id="83eeb-108">What the XmlResolver is used for</span></span>|  
|---------------|--------------------------------------|  
|<span data-ttu-id="83eeb-109">Zkompilujte šablony stylů.</span><span class="sxs-lookup"><span data-stu-id="83eeb-109">Compile the style sheet.</span></span>|<span data-ttu-id="83eeb-110">Vyřešte identifikátor URI šablony stylů.</span><span class="sxs-lookup"><span data-stu-id="83eeb-110">Resolve the URI of the style sheet.</span></span><br /><br /> <span data-ttu-id="83eeb-111">- a -</span><span class="sxs-lookup"><span data-stu-id="83eeb-111">-and-</span></span><br /><br /> <span data-ttu-id="83eeb-112">Vyřešit odkazy na URI v žádném `xsl:import` nebo `xsl:include` elementy.</span><span class="sxs-lookup"><span data-stu-id="83eeb-112">Resolve URI references in any `xsl:import` or `xsl:include` elements.</span></span>|  
|<span data-ttu-id="83eeb-113">Spusťte šablony stylů.</span><span class="sxs-lookup"><span data-stu-id="83eeb-113">Execute the style sheet.</span></span>|<span data-ttu-id="83eeb-114">Identifikátor URI dokumentu kontextu přeložit.</span><span class="sxs-lookup"><span data-stu-id="83eeb-114">Resolve the URI of the context document.</span></span><br /><br /> <span data-ttu-id="83eeb-115">- a -</span><span class="sxs-lookup"><span data-stu-id="83eeb-115">-and-</span></span><br /><br /> <span data-ttu-id="83eeb-116">Vyřešit odkazy na URI ve všech XSLT `document()` funkce.</span><span class="sxs-lookup"><span data-stu-id="83eeb-116">Resolve URI references in any XSLT `document()` functions.</span></span>|  
  
 <span data-ttu-id="83eeb-117"><xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> a <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> metody patří přetížení, které provést <xref:System.Xml.XmlResolver> objektu jako jeden z jeho argumenty.</span><span class="sxs-lookup"><span data-stu-id="83eeb-117">The <xref:System.Xml.Xsl.XslCompiledTransform.Load%2A> and <xref:System.Xml.Xsl.XslCompiledTransform.Transform%2A> methods include overloads that take an <xref:System.Xml.XmlResolver> object as one of its arguments.</span></span> <span data-ttu-id="83eeb-118">Pokud <xref:System.Xml.XmlResolver> není určena, výchozí <xref:System.Xml.XmlUrlResolver> bez pověření se používá.</span><span class="sxs-lookup"><span data-stu-id="83eeb-118">If an <xref:System.Xml.XmlResolver> is not specified, a default <xref:System.Xml.XmlUrlResolver> with no credentials is used.</span></span>  
  
 <span data-ttu-id="83eeb-119">Následující seznam popisuje, pokud chcete zadat <xref:System.Xml.XmlResolver> objektu:</span><span class="sxs-lookup"><span data-stu-id="83eeb-119">The following list describes when you may want to specify an <xref:System.Xml.XmlResolver> object:</span></span>  
  
-   <span data-ttu-id="83eeb-120">Pokud proces XSLT potřebuje pro přístup k prostředkům sítě, který vyžaduje ověření, můžete použít <xref:System.Xml.XmlResolver> s potřebná pověření.</span><span class="sxs-lookup"><span data-stu-id="83eeb-120">If the XSLT process needs to access a network resource that requires authentication, you can use an <xref:System.Xml.XmlResolver> with the necessary credentials.</span></span>  
  
-   <span data-ttu-id="83eeb-121">Pokud chcete omezit prostředky, ke kterým mají přístup proces XSLT, můžete použít <xref:System.Xml.XmlSecureResolver> s oprávněním správné nastavení.</span><span class="sxs-lookup"><span data-stu-id="83eeb-121">If you want to restrict the resources that the XSLT process can access, you can use an <xref:System.Xml.XmlSecureResolver> with the correct permission set.</span></span> <span data-ttu-id="83eeb-122">Použití <xref:System.Xml.XmlSecureResolver> třídy, pokud je třeba otevřít prostředek není řídíte, nebo které není důvěryhodný.</span><span class="sxs-lookup"><span data-stu-id="83eeb-122">Use the <xref:System.Xml.XmlSecureResolver> class if you need to open a resource that you do not control, or that is untrusted.</span></span>  
  
-   <span data-ttu-id="83eeb-123">Pokud chcete přizpůsobit chování, můžete implementovat vlastní <xref:System.Xml.XmlResolver> třídy a použít ho k vyřešení prostředky.</span><span class="sxs-lookup"><span data-stu-id="83eeb-123">If you want to customize behavior, you can implement your own <xref:System.Xml.XmlResolver> class and use it to resolve resources.</span></span>  
  
-   <span data-ttu-id="83eeb-124">Pokud chcete zajistit, že žádné externí prostředky ke kterým se přistupuje, můžete zadat `null` pro <xref:System.Xml.XmlResolver> argument.</span><span class="sxs-lookup"><span data-stu-id="83eeb-124">If you want to ensure that no external resources are accessed, you can specify `null` for the <xref:System.Xml.XmlResolver> argument.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83eeb-125">Příklad</span><span class="sxs-lookup"><span data-stu-id="83eeb-125">Example</span></span>  
 <span data-ttu-id="83eeb-126">Následující příklad zkompiluje stylů, která je uložena na síťovém prostředku.</span><span class="sxs-lookup"><span data-stu-id="83eeb-126">The following example compiles a style sheet that is stored on a network resource.</span></span> <span data-ttu-id="83eeb-127"><xref:System.Xml.XmlUrlResolver> Objektu určuje přihlašovací údaje potřebné pro přístup k šabloně stylů.</span><span class="sxs-lookup"><span data-stu-id="83eeb-127">An <xref:System.Xml.XmlUrlResolver> object specifies the credentials necessary to access the style sheet.</span></span>  
  
 [!code-csharp[XslCompiledTransform.Load#11](../../../../samples/snippets/csharp/VS_Snippets_Data/XslCompiledTransform.Load/CS/Xslt_Load_v2.cs#11)]
 [!code-vb[XslCompiledTransform.Load#11](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XslCompiledTransform.Load/VB/Xslt_Load_v2.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="83eeb-128">Viz také</span><span class="sxs-lookup"><span data-stu-id="83eeb-128">See Also</span></span>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 <xref:System.Xml.Xsl.XsltSettings>  
 [<span data-ttu-id="83eeb-129">Transformace XSLT</span><span class="sxs-lookup"><span data-stu-id="83eeb-129">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)