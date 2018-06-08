### <a name="privatefontcollectionaddfontfile-method-releases-font-resources"></a><span data-ttu-id="0494d-101">Metoda PrivateFontCollection.AddFontFile uvolní prostředky písma</span><span class="sxs-lookup"><span data-stu-id="0494d-101">PrivateFontCollection.AddFontFile method releases Font resources</span></span>

|   |   |
|---|---|
|<span data-ttu-id="0494d-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="0494d-102">Details</span></span>|<span data-ttu-id="0494d-103">V rozhraní .NET Framework 4.7.1 a předchozích verzích <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> třída není uvolnění prostředků písma GDI + po <xref:System.Drawing.Text.PrivateFontCollection> uvolnění pro <xref:System.Drawing.Font> objekty, které jsou přidány do této kolekce pomocí <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> metoda.</span><span class="sxs-lookup"><span data-stu-id="0494d-103">In the .NET Framework 4.7.1 and previous versions, the <xref:System.Drawing.Text.PrivateFontCollection?displayProperty=nameWithType> class does not release the GDI+ font resources after the <xref:System.Drawing.Text.PrivateFontCollection> is disposed for <xref:System.Drawing.Font> objects that are added to this collection using the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)> method.</span></span> <span data-ttu-id="0494d-104">V rozhraní .NET Framework 4.7.2 a později <xref:System.Drawing.Text.FontCollection.Dispose%2A> uvolní písem GDI +, které byly přidány do kolekce jako soubory.</span><span class="sxs-lookup"><span data-stu-id="0494d-104">In the .NET Framework 4.7.2 and later <xref:System.Drawing.Text.FontCollection.Dispose%2A> releases the GDI+ fonts that were added to the collection as files.</span></span>|
|<span data-ttu-id="0494d-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="0494d-105">Suggestion</span></span>|<span data-ttu-id="0494d-106"><strong>Postup aktivování nebo zrušení těchto změn</strong>v pořadí pro aplikaci, abyste mohli využívat výhod tyto změny, musí běžet na rozhraní .NET Framework 4.7.2 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="0494d-106"><strong>How to opt in or out of these changes</strong>In order for an application to benefit from these changes, it must run on the .NET Framework 4.7.2 or later.</span></span> <span data-ttu-id="0494d-107">Aplikace můžete využít tyto změny v některém z následujících způsobů:</span><span class="sxs-lookup"><span data-stu-id="0494d-107">The application can benefit from these changes in either of the following ways:</span></span><ul><li><span data-ttu-id="0494d-108">Ho znovu zkompiluje cílí na rozhraní .NET Framework 4.7.2.</span><span class="sxs-lookup"><span data-stu-id="0494d-108">It is recompiled to target the .NET Framework 4.7.2.</span></span> <span data-ttu-id="0494d-109">Tuto změnu je povoleno ve výchozím nastavení v aplikacích Windows Forms cílených na rozhraní .NET Framework 4.7.2 nebo novější.</span><span class="sxs-lookup"><span data-stu-id="0494d-109">This change is enabled by default on Windows Forms applications that target the .NET Framework 4.7.2 or later.</span></span></li><li><span data-ttu-id="0494d-110">Ji používá starší verze nebo rozhraní .NET Framework 4.7.1 a výslovný nesouhlas chování starší verze usnadnění přidáním následující [AppContext přepínač](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) k <code>&lt;runtime&gt;</code> části souboru app.config a jeho nastavení na hodnotu <code>false</code>, jak ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="0494d-110">It targets the .NET Framework 4.7.1 or an earlier version and opts out of the legacy accessibility behaviors by adding the following [AppContext Switch](https://docs.microsoft.com/dotnet/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element) to the <code>&lt;runtime&gt;</code> section of the app.config file and setting it to <code>false</code>, as the following example shows.</span></span></li></ul><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Drawing.Text.DoNotRemoveGdiFontsResourcesFromFontCollection=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="0494d-111">Aplikace, které cílí na rozhraní .NET Framework 4.7.2 nebo novější a chcete zachovat starší verze chování můžete vyjádřit výslovný souhlas pro není explicitně nastavením tento přepínač AppContext na uvolnění prostředků písma <code>true</code>.</span><span class="sxs-lookup"><span data-stu-id="0494d-111">Applications that target the .NET Framework 4.7.2 or later, and want to preserve the legacy behavior can opt in to not release font resources by explicitly setting this AppContext switch to <code>true</code>.</span></span>|
|<span data-ttu-id="0494d-112">Rozsah</span><span class="sxs-lookup"><span data-stu-id="0494d-112">Scope</span></span>|<span data-ttu-id="0494d-113">Edge</span><span class="sxs-lookup"><span data-stu-id="0494d-113">Edge</span></span>|
|<span data-ttu-id="0494d-114">Version</span><span class="sxs-lookup"><span data-stu-id="0494d-114">Version</span></span>|<span data-ttu-id="0494d-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="0494d-115">4.7.2</span></span>|
|<span data-ttu-id="0494d-116">Typ</span><span class="sxs-lookup"><span data-stu-id="0494d-116">Type</span></span>|<span data-ttu-id="0494d-117">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="0494d-117">Retargeting</span></span>|
|<span data-ttu-id="0494d-118">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="0494d-118">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Text.PrivateFontCollection.AddFontFile(System.String)?displayProperty=nameWithType></li><li><xref:System.Drawing.Text.FontCollection.Dispose?displayProperty=nameWithType></li></ul>|
