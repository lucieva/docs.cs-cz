### <a name="xmlserializer-fails-while-serializing-a-type-that-hides-an-accessible-member-with-an-inaccessible-one"></a><span data-ttu-id="2b5c7-101">XmlSerializer selže při serializaci typ, který skryje člena přístupné pomocí některého nedostupné</span><span class="sxs-lookup"><span data-stu-id="2b5c7-101">XmlSerializer fails while serializing a type that hides an accessible member with an inaccessible one</span></span>

|   |   |
|---|---|
|<span data-ttu-id="2b5c7-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="2b5c7-102">Details</span></span>|<span data-ttu-id="2b5c7-103">Při serializaci odvozený typ <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> může selhat, pokud typ obsahuje nepřístupný pole nebo vlastnost, která skryje (prostřednictvím 'new' – klíčové slovo) pole nebo vlastnost se stejným názvem, který byl dříve přístupný (veřejné, např.) u základního typu.</span><span class="sxs-lookup"><span data-stu-id="2b5c7-103">When serializing a derived type, the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> can fail if the type contains an inaccessible field or property that hides (via the 'new' keyword) a field or property of the same name that was previously accessible (public, for example) on the base type.</span></span>|
|<span data-ttu-id="2b5c7-104">Návrh</span><span class="sxs-lookup"><span data-stu-id="2b5c7-104">Suggestion</span></span>|<span data-ttu-id="2b5c7-105">Tento problém lze vyřešit tak, že nový, neskrývá člen přístupné <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> (jeho označením veřejné, třeba). Můžete taky následující nastavení konfigurace se vrátí k 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> chování, které problém opravíme:</span><span class="sxs-lookup"><span data-stu-id="2b5c7-105">This problem can be solved by making the new, hiding member accessible to the <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> (by marking it public, for example).Alternatively, the following config setting will revert to 4.0 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=name> behavior, which will fix the problem:</span></span><pre><code class="lang-xml">&lt;system.xml.serialization&gt;&#13;&#10;&lt;xmlSerializer useLegacySerializerGeneration=&quot;true&quot; /&gt;&#13;&#10;&lt;/system.xml.serialization&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="2b5c7-106">Rozsah</span><span class="sxs-lookup"><span data-stu-id="2b5c7-106">Scope</span></span>|<span data-ttu-id="2b5c7-107">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="2b5c7-107">Minor</span></span>|
|<span data-ttu-id="2b5c7-108">Version</span><span class="sxs-lookup"><span data-stu-id="2b5c7-108">Version</span></span>|<span data-ttu-id="2b5c7-109">4.5</span><span class="sxs-lookup"><span data-stu-id="2b5c7-109">4.5</span></span>|
|<span data-ttu-id="2b5c7-110">Typ</span><span class="sxs-lookup"><span data-stu-id="2b5c7-110">Type</span></span>|<span data-ttu-id="2b5c7-111">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="2b5c7-111">Runtime</span></span>|
|<span data-ttu-id="2b5c7-112">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="2b5c7-112">Affected APIs</span></span>|<ul><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Object,System.Xml.Serialization.XmlSerializationWriter)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.Stream,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.IO.TextWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String)?displayProperty=nameWithType></li><li><xref:System.Xml.Serialization.XmlSerializer.Serialize(System.Xml.XmlWriter,System.Object,System.Xml.Serialization.XmlSerializerNamespaces,System.String,System.String)?displayProperty=nameWithType></li></ul>|
