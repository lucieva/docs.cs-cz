---
title: "Přístup k důrazně zadali pomocí objektem XPathNavigator nastaveným na Data XML"
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
ms.assetid: 898e0f52-8a7c-4d1f-afcd-6ffb28b050b4
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 61c78adff541ac2ba261d31776478a0468e21d4f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-strongly-typed-xml-data-using-xpathnavigator"></a><span data-ttu-id="87897-102">Přístup k důrazně zadali pomocí objektem XPathNavigator nastaveným na Data XML</span><span class="sxs-lookup"><span data-stu-id="87897-102">Accessing Strongly Typed XML Data Using XPathNavigator</span></span>
<span data-ttu-id="87897-103">Jako instance datového modelu XPath 2.0 <xref:System.Xml.XPath.XPathNavigator> třídy může obsahovat data silného typu, který se mapuje na běžné typy language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="87897-103">As an instance of the XPath 2.0 data model, the <xref:System.Xml.XPath.XPathNavigator> class can contain strongly-typed data that maps to common language runtime (CLR) types.</span></span> <span data-ttu-id="87897-104">Podle modelu dat XPath 2.0 může obsahovat pouze elementy a atributy data silného typu.</span><span class="sxs-lookup"><span data-stu-id="87897-104">According to the XPath 2.0 data model, only elements and attributes can contain strongly-typed data.</span></span> <span data-ttu-id="87897-105"><xref:System.Xml.XPath.XPathNavigator> Třída poskytuje mechanismus pro přístup k datům v rámci <xref:System.Xml.XPath.XPathDocument> nebo <xref:System.Xml.XmlDocument> jako silného typu dat, jakož i mechanismy pro převod z jednoho datového typu na jiný objekt.</span><span class="sxs-lookup"><span data-stu-id="87897-105">The <xref:System.Xml.XPath.XPathNavigator> class provides mechanisms for accessing data within an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object as strongly-typed data as well as mechanisms for converting from one data type to another.</span></span>  
  
## <a name="type-information-exposed-by-xpathnavigator"></a><span data-ttu-id="87897-106">Informace o typu vystavené objektem XPathNavigator nastaveným na</span><span class="sxs-lookup"><span data-stu-id="87897-106">Type Information Exposed by XPathNavigator</span></span>  
 <span data-ttu-id="87897-107">Data XML 1.0 je technicky bez typu, pokud zpracování s DTD, XML schéma definition language (XSD) schématu nebo jinému kontrolnímu mechanismu.</span><span class="sxs-lookup"><span data-stu-id="87897-107">XML 1.0 data is technically without type, unless processed with a DTD, XML schema definition language (XSD) schema, or other mechanism.</span></span> <span data-ttu-id="87897-108">Existuje několik kategorií informace o typu, který může být přidružen elementu XML nebo atributu.</span><span class="sxs-lookup"><span data-stu-id="87897-108">There are a number of categories of type information that can be associated with an XML element or attribute.</span></span>  
  
-   <span data-ttu-id="87897-109">Jednoduché typy CLR: Žádný z jazyků schématu XML nepodporuje typy Common Language Runtime (CLR) přímo.</span><span class="sxs-lookup"><span data-stu-id="87897-109">Simple CLR Types: None of the XML Schema languages support Common Language Runtime (CLR) types directly.</span></span> <span data-ttu-id="87897-110">Protože je užitečné, abyste mohli zobrazit jednoduché elementu a atributu obsah jako nejvhodnější typ CLR, všechny jednoduchým obsahem lze zadat jako <xref:System.String> chybí informace o schématu s žádným přidat informace o schématu potenciálně upřesnění tomuto obsahu uživateli více příslušného typu.</span><span class="sxs-lookup"><span data-stu-id="87897-110">Because it is useful to be able to view simple element and attribute content as the most appropriate CLR type, all simple content can be typed as <xref:System.String> in the absence of schema information with any added schema information potentially refining this content to a more appropriate type.</span></span> <span data-ttu-id="87897-111">Můžete najít nejlépe odpovídající typ CLR jednoduchým obsahem elementu a atributu pomocí <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="87897-111">You can find the best matching CLR type of simple element and attribute content by using the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property.</span></span> <span data-ttu-id="87897-112">Další informace o mapování z předdefinovaných typů schématu pro typy CLR najdete v tématu [podpora typu ve třídách System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87897-112">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="87897-113">Seznam typů jednoduché (CLR): elementu nebo atributu s jednoduchým obsahem může obsahovat seznam hodnot oddělených mezer.</span><span class="sxs-lookup"><span data-stu-id="87897-113">Lists of Simple (CLR) Types: An element or attribute with simple content can contain a list of values separated by white space.</span></span> <span data-ttu-id="87897-114">Hodnoty jsou určené schéma XML jako "typ seznamu".</span><span class="sxs-lookup"><span data-stu-id="87897-114">The values are specified by an XML Schema to be a "list type."</span></span> <span data-ttu-id="87897-115">Chybí schématu XML by takové jednoduchým obsahem považovány za jeden textový uzel.</span><span class="sxs-lookup"><span data-stu-id="87897-115">In the absence of an XML Schema, such simple content would be treated as a single text node.</span></span> <span data-ttu-id="87897-116">Pokud schéma XML je k dispozici, mohou být zpřístupněny tento jednoduchý obsah jako řadu atomic hodnoty, každý s jednoduchý typ, který se mapuje na kolekce objektů CLR.</span><span class="sxs-lookup"><span data-stu-id="87897-116">When an XML Schema is available, this simple content can be exposed as a series of atomic values each having a simple type that maps to a collection of CLR objects.</span></span> <span data-ttu-id="87897-117">Další informace o mapování z předdefinovaných typů schématu pro typy CLR najdete v tématu [podpora typu ve třídách System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87897-117">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="87897-118">Zadaná hodnota: Ověřit schéma atribut nebo element s jednoduchého typu obsahuje hodnotu typu.</span><span class="sxs-lookup"><span data-stu-id="87897-118">Typed Value: A schema-validated attribute or element with a simple type has a typed value.</span></span> <span data-ttu-id="87897-119">Tato hodnota je primitivní typ, například číselný, řetězce nebo typ datum.</span><span class="sxs-lookup"><span data-stu-id="87897-119">This value is a primitive type such as a numeric, string, or date type.</span></span> <span data-ttu-id="87897-120">Všechny předdefinované jednoduché typy v XSD lze mapovat na typy CLR, které poskytují přístup k hodnotě uzlu jako typ vhodnější místo stejně jako <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="87897-120">All the built-in simple types in XSD can be mapped to CLR types that provide access to the value of a node as a more appropriate type instead of just as a <xref:System.String>.</span></span> <span data-ttu-id="87897-121">Element s atributy nebo podřízené položky elementu se považuje za komplexního typu.</span><span class="sxs-lookup"><span data-stu-id="87897-121">An element with attributes or element children is considered to be a complex type.</span></span> <span data-ttu-id="87897-122">Typové hodnotu pro komplexní typ s jednoduchým obsahem (pouze textové uzly jako podřízené objekty) je stejný jako u jednoduchý typ část jeho obsahu.</span><span class="sxs-lookup"><span data-stu-id="87897-122">The typed value of a complex type with simple content (only text nodes as children) is the same as that of the simple type of its content.</span></span> <span data-ttu-id="87897-123">Hodnota typu komplexního typu se složitým obsahem (jeden nebo více podřízených prvků) je s řetězcovou hodnotou obsahující zřetězení všechny jeho podřízené textové uzly vrátí jako <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="87897-123">The typed value of a complex type with complex content (one or more child elements) is the string value of the concatenation of all its child text nodes returned as a <xref:System.String>.</span></span> <span data-ttu-id="87897-124">Další informace o mapování z předdefinovaných typů schématu pro typy CLR najdete v tématu [podpora typu ve třídách System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87897-124">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
-   <span data-ttu-id="87897-125">Schématu jazyk konkrétní název typu: Ve většině případů typů CLR, které jsou nastavené jako vedlejší účinek použití externí schéma, slouží k poskytování přístupu k hodnotě uzlu.</span><span class="sxs-lookup"><span data-stu-id="87897-125">Schema-Language Specific Type Name: In most cases, the CLR types, which are set as a side-effect of applying an external schema, are used to provide access to the value of a node.</span></span> <span data-ttu-id="87897-126">Mohou však nastat situace, místo zkontrolujte typ spojený s konkrétní schématu použitého pro dokument XML.</span><span class="sxs-lookup"><span data-stu-id="87897-126">However, there may be situations where you may want to examine the type associated with a particular schema applied to an XML document.</span></span> <span data-ttu-id="87897-127">Například můžete chtít hledání v dokumentu XML extrahování všechny elementy, které jsou určeny tak, aby měl obsah typu "PurchaseOrder" podle připojeného schématu.</span><span class="sxs-lookup"><span data-stu-id="87897-127">For example, you may wish to search through an XML document, extracting all elements that are determined to have content of type "PurchaseOrder" according to an attached schema.</span></span> <span data-ttu-id="87897-128">Tyto informace o typu lze nastavit pouze v důsledku ověřování schématu a tyto informace je přístupné přes <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> a <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> vlastnosti <xref:System.Xml.XPath.XPathNavigator> třídy.</span><span class="sxs-lookup"><span data-stu-id="87897-128">Such type information can be set only as a result of schema validation and this information is accessed through the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> and <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="87897-129">Další informace najdete v části informační Post schématu ověření sadu (PSVI) níže.</span><span class="sxs-lookup"><span data-stu-id="87897-129">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
-   <span data-ttu-id="87897-130">Reflexe konkrétní jazyk schématu: V ostatních případech můžete chtít získat další podrobnosti o konkrétní schématu typu u dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="87897-130">Schema-Language Specific Type Reflection: In other cases, you may want to obtain further details of the schema-specific type applied to an XML document.</span></span> <span data-ttu-id="87897-131">Například při čtení souboru XML, můžete k extrakci `maxOccurs` atribut pro každý uzel platný v dokumentu XML tak, aby bylo možné provést některé vlastní výpočet.</span><span class="sxs-lookup"><span data-stu-id="87897-131">For example, when reading an XML file, you may want to extract the `maxOccurs` attribute for each valid node in the XML document in order to perform some custom calculation.</span></span> <span data-ttu-id="87897-132">Protože tyto informace je nastavena pouze prostřednictvím ověřování schématu, je přístupné přes <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator> třídy.</span><span class="sxs-lookup"><span data-stu-id="87897-132">Because this information is set only through schema validation, it is accessed through the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span> <span data-ttu-id="87897-133">Další informace najdete v části informační Post schématu ověření sadu (PSVI) níže.</span><span class="sxs-lookup"><span data-stu-id="87897-133">For more information, see The Post Schema Validation Infoset (PSVI) section below.</span></span>  
  
## <a name="xpathnavigator-typed-accessors"></a><span data-ttu-id="87897-134">Objektem XPathNavigator nastaveným na silné přístupové objekty</span><span class="sxs-lookup"><span data-stu-id="87897-134">XPathNavigator Typed Accessors</span></span>  
 <span data-ttu-id="87897-135">Následující tabulka uvádí různé vlastnosti a metody <xref:System.Xml.XPath.XPathNavigator> třídu, která lze použít pro přístup k informacím typ o uzlu.</span><span class="sxs-lookup"><span data-stu-id="87897-135">The following table shows the various properties and methods of the <xref:System.Xml.XPath.XPathNavigator> class that can be used to access the type information about a node.</span></span>  
  
|<span data-ttu-id="87897-136">Vlastnost</span><span class="sxs-lookup"><span data-stu-id="87897-136">Property</span></span>|<span data-ttu-id="87897-137">Popis</span><span class="sxs-lookup"><span data-stu-id="87897-137">Description</span></span>|  
|--------------|-----------------|  
|<xref:System.Xml.XPath.XPathNavigator.XmlType%2A>|<span data-ttu-id="87897-138">Pokud je platná tato položka obsahuje informace o uzlu typ schématu XML.</span><span class="sxs-lookup"><span data-stu-id="87897-138">This contains the XML schema type information for the node if it is valid.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A>|<span data-ttu-id="87897-139">Tato položka obsahuje informační Post schématu ověření sadu uzlu, který bude přidán za ověření.</span><span class="sxs-lookup"><span data-stu-id="87897-139">This contains the Post Schema Validation Infoset of the node that is added after validation.</span></span> <span data-ttu-id="87897-140">To zahrnuje informace o typu schématu XML a také informace platnosti.</span><span class="sxs-lookup"><span data-stu-id="87897-140">This includes the XML schema type information, as well as validity information.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueType%2A>|<span data-ttu-id="87897-141">Typ CLR typové hodnotu uzlu.</span><span class="sxs-lookup"><span data-stu-id="87897-141">The CLR type of the typed value of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.TypedValue%2A>|<span data-ttu-id="87897-142">Obsah uzlu CLR jeden nebo více hodnot s typem je nejvíce odpovídá typ schématu XML uzlu.</span><span class="sxs-lookup"><span data-stu-id="87897-142">The content of the node as one or more CLR values whose type is the closest match to the XML schema type of the node.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsBoolean%2A>|<span data-ttu-id="87897-143"><xref:System.String> Hodnotu aktuální uzel přetypovat <xref:System.Boolean> hodnoty, podle pravidla přetypování XPath 2.0 pro `xs:boolean`.</span><span class="sxs-lookup"><span data-stu-id="87897-143">The <xref:System.String> value of the current node cast to a <xref:System.Boolean> value, according to the XPath 2.0 casting rules for `xs:boolean`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDateTime%2A>|<span data-ttu-id="87897-144"><xref:System.String> Hodnotu aktuální uzel přetypovat <xref:System.DateTime> hodnoty, podle pravidla přetypování XPath 2.0 pro `xs:datetime`.</span><span class="sxs-lookup"><span data-stu-id="87897-144">The <xref:System.String> value of the current node cast to a <xref:System.DateTime> value, according to the XPath 2.0 casting rules for `xs:datetime`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>|<span data-ttu-id="87897-145"><xref:System.String> Hodnotu aktuální uzel přetypovat <xref:System.Double> hodnoty, podle pravidla přetypování XPath 2.0 pro `xsd:double`.</span><span class="sxs-lookup"><span data-stu-id="87897-145">The <xref:System.String> value of the current node cast to a <xref:System.Double> value, according to the XPath 2.0 casting rules for `xsd:double`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>|<span data-ttu-id="87897-146"><xref:System.String> Hodnotu aktuální uzel přetypovat <xref:System.Int32> hodnoty, podle pravidla přetypování XPath 2.0 pro `xs:integer`.</span><span class="sxs-lookup"><span data-stu-id="87897-146">The <xref:System.String> value of the current node cast to a <xref:System.Int32> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A>|<span data-ttu-id="87897-147"><xref:System.String> Hodnotu aktuální uzel přetypovat <xref:System.Int64> hodnoty, podle pravidla přetypování XPath 2.0 pro `xs:integer`.</span><span class="sxs-lookup"><span data-stu-id="87897-147">The <xref:System.String> value of the current node cast to a <xref:System.Int64> value, according to the XPath 2.0 casting rules for `xs:integer`.</span></span>|  
|<xref:System.Xml.XPath.XPathNavigator.ValueAs%2A>|<span data-ttu-id="87897-148">Obsah uzlu přetypovat na typ cíle podle pravidel přetypování XPath 2.0.</span><span class="sxs-lookup"><span data-stu-id="87897-148">The contents of the node cast to the target type according to the XPath 2.0 casting rules.</span></span>|  
  
 <span data-ttu-id="87897-149">Další informace o mapování z předdefinovaných typů schématu pro typy CLR najdete v tématu [podpora typu ve třídách System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87897-149">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="the-post-schema-validation-infoset-psvi"></a><span data-ttu-id="87897-150">Informační Post schématu ověření sadu (PSVI)</span><span class="sxs-lookup"><span data-stu-id="87897-150">The Post Schema Validation Infoset (PSVI)</span></span>  
 <span data-ttu-id="87897-151">Procesor schématu XML přijímá informační sadu XML jako vstup a převede jej do schématu ověření informační sadu (PSVI Post).</span><span class="sxs-lookup"><span data-stu-id="87897-151">An XML Schema processor accepts an XML Infoset as input and converts it into a Post Schema Validation Infoset (PSVI).</span></span> <span data-ttu-id="87897-152">PSVI je původní vstupní XML informační sadu s přidat nové informace položky a nové vlastnosti, které jsou přidány do existujících položek informace.</span><span class="sxs-lookup"><span data-stu-id="87897-152">A PSVI is the original input XML infoset with new information items added and new properties added to existing information items.</span></span> <span data-ttu-id="87897-153">Existují tři obecné třídy informací zapisovaných do informační sadu XML v PSVI, které jsou vystavené <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="87897-153">There are three broad classes of information added to the XML Infoset in the PSVI that are exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
1.  <span data-ttu-id="87897-154">Ověření výstupy: Informace o tom, jestli elementu nebo atributu byl úspěšně ověřen nebo ne.</span><span class="sxs-lookup"><span data-stu-id="87897-154">Validation Outcomes: Information as to whether an element or attribute was successfully validated or not.</span></span> <span data-ttu-id="87897-155">To je zveřejněný prostřednictvím <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator> třídy.</span><span class="sxs-lookup"><span data-stu-id="87897-155">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.Validity%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
2.  <span data-ttu-id="87897-156">Informace o výchozí: Označení, zda hodnota elementu nebo atributu byl získán prostřednictvím výchozí hodnoty zadané ve schématu, nebo ne.</span><span class="sxs-lookup"><span data-stu-id="87897-156">Default Information: Indications as to whether the value of the element or attribute was obtained via default values specified in the schema or not.</span></span> <span data-ttu-id="87897-157">To je zveřejněný prostřednictvím <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator> třídy.</span><span class="sxs-lookup"><span data-stu-id="87897-157">This is exposed by the <xref:System.Xml.Schema.IXmlSchemaInfo.IsDefault%2A> property of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
3.  <span data-ttu-id="87897-158">Typ poznámky: Odkazy na komponenty schématu, které mohou být definic typů nebo elementu a atributu deklarace.</span><span class="sxs-lookup"><span data-stu-id="87897-158">Type Annotations: References to schema components that may be type definitions or element and attribute declarations.</span></span> <span data-ttu-id="87897-159"><xref:System.Xml.XPath.XPathNavigator.XmlType%2A> Vlastnost <xref:System.Xml.XPath.XPathNavigator> obsahuje informace o konkrétní typ uzlu, pokud je platná.</span><span class="sxs-lookup"><span data-stu-id="87897-159">The <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property of the <xref:System.Xml.XPath.XPathNavigator> contains the specific type information of the node if it is valid.</span></span> <span data-ttu-id="87897-160">Pokud platnost uzel neznámý, například když se ověřila pak následně upravit.</span><span class="sxs-lookup"><span data-stu-id="87897-160">If the validity of a node is unknown, such as when it was validated then subsequently edited.</span></span> <span data-ttu-id="87897-161">pak se <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> je nastavena na `null` , ale stále k dispozici v různé vlastnosti informací o typu <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator> třídy.</span><span class="sxs-lookup"><span data-stu-id="87897-161">then the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property is set to `null` but type information is still available from the various properties of the <xref:System.Xml.XPath.XPathNavigator.SchemaInfo%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
 <span data-ttu-id="87897-162">Následující příklad ilustruje, pomocí informací v vystavené informační Post schématu ověření sadu <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="87897-162">The following example illustrates using information in the Post Schema Validation Infoset exposed by the <xref:System.Xml.XPath.XPathNavigator>.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("books.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("published", "http://www.contoso.com/books")  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name)  
Console.WriteLine(navigator.SchemaInfo.Validity)  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "books.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("books.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("published", "http://www.contoso.com/books");  
  
Console.WriteLine(navigator.SchemaInfo.SchemaType.Name);  
Console.WriteLine(navigator.SchemaInfo.Validity);  
Console.WriteLine(navigator.SchemaInfo.SchemaElement.MinOccurs);  
```  
  
 <span data-ttu-id="87897-163">V příkladu trvá `books.xml` souboru jako vstup.</span><span class="sxs-lookup"><span data-stu-id="87897-163">The example takes the `books.xml` file as input.</span></span>  
  
```xml  
<books xmlns="http://www.contoso.com/books">  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="87897-164">Tento příklad také trvá `books.xsd` schématu jako vstup.</span><span class="sxs-lookup"><span data-stu-id="87897-164">The example also takes the `books.xsd` schema as input.</span></span>  
  
```xml  
<xs:schema xmlns="http://www.contoso.com/books"   
attributeFormDefault="unqualified" elementFormDefault="qualified"   
targetNamespace="http://www.contoso.com/books"   
xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:simpleType name="publishedType">  
        <xs:restriction base="xs:date">  
            <xs:minInclusive value="2003-01-01" />  
            <xs:maxInclusive value="2003-12-31" />  
        </xs:restriction>  
    </xs:simpleType>  
    <xs:complexType name="bookType">  
        <xs:sequence>  
            <xs:element name="title" type="xs:string"/>  
            <xs:element name="price" type="xs:decimal"/>  
            <xs:element name="published" type="publishedType"/>  
        </xs:sequence>  
    </xs:complexType>  
    <xs:complexType name="booksType">  
        <xs:sequence>  
            <xs:element name="book" type="bookType" />  
        </xs:sequence>  
    </xs:complexType>  
    <xs:element name="books" type="booksType" />  
</xs:schema>  
```  
  
## <a name="obtain-typed-values-using-valueas-properties"></a><span data-ttu-id="87897-165">Získat zadávaných hodnot pomocí vlastnosti ValueAs</span><span class="sxs-lookup"><span data-stu-id="87897-165">Obtain Typed Values Using ValueAs Properties</span></span>  
 <span data-ttu-id="87897-166">Hodnota typu uzlu může načíst přístup k <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> vlastnost <xref:System.Xml.XPath.XPathNavigator>.</span><span class="sxs-lookup"><span data-stu-id="87897-166">The typed value of a node can be retrieved by accessing the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property of the <xref:System.Xml.XPath.XPathNavigator>.</span></span> <span data-ttu-id="87897-167">V některých případech můžete chtít převést hodnotu typu uzlu na jiný typ.</span><span class="sxs-lookup"><span data-stu-id="87897-167">In certain cases you may want to convert the typed value of a node to a different type.</span></span> <span data-ttu-id="87897-168">Běžným příkladem jsou k získání číselné hodnoty z uzlu XML.</span><span class="sxs-lookup"><span data-stu-id="87897-168">A common example is to get a numeric value from an XML node.</span></span> <span data-ttu-id="87897-169">Zvažte například následující neověřený a bez typu dokumentu XML.</span><span class="sxs-lookup"><span data-stu-id="87897-169">For example, consider the following unvalidated and untyped XML document.</span></span>  
  
```xml  
<books>  
    <book>  
        <title>Title</title>  
        <price>10.00</price>  
        <published>2003-12-31</published>  
    </book>  
</books>  
```  
  
 <span data-ttu-id="87897-170">Pokud <xref:System.Xml.XPath.XPathNavigator> je umístěn na `price` element <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> by vlastnost `null`, <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> by vlastnost <xref:System.String>a <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> vlastnost bude řetězec `10.00`.</span><span class="sxs-lookup"><span data-stu-id="87897-170">If the <xref:System.Xml.XPath.XPathNavigator> is positioned on the `price` element the <xref:System.Xml.XPath.XPathNavigator.XmlType%2A> property would be `null`, the <xref:System.Xml.XPath.XPathNavigator.ValueType%2A> property would be <xref:System.String>, and the <xref:System.Xml.XPath.XPathNavigator.TypedValue%2A> property would be the string `10.00`.</span></span>  
  
 <span data-ttu-id="87897-171">Je však stále možné rozbalte hodnotu jako číselná hodnota pomocí <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>, nebo <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> metody a vlastnosti.</span><span class="sxs-lookup"><span data-stu-id="87897-171">However, it is still possible to extract the value as a numeric value using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsDouble%2A>, <xref:System.Xml.XPath.XPathNavigator.ValueAsInt%2A>, or <xref:System.Xml.XPath.XPathNavigator.ValueAsLong%2A> method and properties.</span></span> <span data-ttu-id="87897-172">Následující příklad ilustruje, provádění takových přetypování pomocí <xref:System.Xml.XPath.XPathItem.ValueAs%2A> metoda.</span><span class="sxs-lookup"><span data-stu-id="87897-172">The following example illustrates performing such a cast using the <xref:System.Xml.XPath.XPathItem.ValueAs%2A> method.</span></span>  
  
```vb  
Dim document As New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
navigator.MoveToChild("books", "")  
navigator.MoveToChild("book", "")  
navigator.MoveToChild("price", "")  
  
Dim price = navigator.ValueAs(GetType(Decimal))  
Dim discount As Decimal = 0.2  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * discount))  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
navigator.MoveToChild("books", "");  
navigator.MoveToChild("book", "");  
navigator.MoveToChild("price", "");  
  
Decimal price = (decimal)navigator.ValueAs(typeof(decimal));  
  
Console.WriteLine("The price of the book has been dropped 20% from {0:C} to {1:C}", navigator.Value, (price - price * (decimal)0.20));  
```  
  
 <span data-ttu-id="87897-173">Další informace o mapování z předdefinovaných typů schématu pro typy CLR najdete v tématu [podpora typu ve třídách System.Xml](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span><span class="sxs-lookup"><span data-stu-id="87897-173">For more information about the mapping from schema built-in types to CLR types, see [Type Support in the System.Xml Classes](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87897-174">Viz také</span><span class="sxs-lookup"><span data-stu-id="87897-174">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="87897-175">Podpora typu v System.Xml třídy</span><span class="sxs-lookup"><span data-stu-id="87897-175">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)  
 [<span data-ttu-id="87897-176">Zpracování kódu XML dat pomocí jazyka XPath datový Model</span><span class="sxs-lookup"><span data-stu-id="87897-176">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="87897-177">Uzel navigační sady pomocí objektem XPathNavigator nastaveným na</span><span class="sxs-lookup"><span data-stu-id="87897-177">Node Set Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/node-set-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="87897-178">Atribut a Namespace uzlu navigace pomocí objektem XPathNavigator nastaveným na</span><span class="sxs-lookup"><span data-stu-id="87897-178">Attribute and Namespace Node Navigation Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/attribute-and-namespace-node-navigation-using-xpathnavigator.md)  
 [<span data-ttu-id="87897-179">Extrahovat pomocí objektem XPathNavigator nastaveným na Data XML</span><span class="sxs-lookup"><span data-stu-id="87897-179">Extract XML Data Using XPathNavigator</span></span>](../../../../docs/standard/data/xml/extract-xml-data-using-xpathnavigator.md)