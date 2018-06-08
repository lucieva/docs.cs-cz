### <a name="ensure-systemuri-uses-a-consistent-reserved-character-set"></a><span data-ttu-id="01d31-101">Ujistěte se, že System.Uri používá konzistentní vyhrazené znakovou sadu</span><span class="sxs-lookup"><span data-stu-id="01d31-101">Ensure System.Uri uses a consistent reserved character set</span></span>

|   |   |
|---|---|
|<span data-ttu-id="01d31-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="01d31-102">Details</span></span>|<span data-ttu-id="01d31-103">V <xref:System.Uri?displayProperty=fullName>některé teď konzistentně vlevo zakódovaným procent kódování znaků, které byly někdy dekódovat.</span><span class="sxs-lookup"><span data-stu-id="01d31-103">In <xref:System.Uri?displayProperty=fullName>, certain percent-encoded characters that were sometimes decoded are now consistently left encoded.</span></span> <span data-ttu-id="01d31-104">K tomu dochází mezi vlastnosti a metody, které přístup k součástem cestu, query, fragment nebo informací o uživateli identifikátoru URI.</span><span class="sxs-lookup"><span data-stu-id="01d31-104">This occurs across the properties and methods that access the path, query, fragment, or userinfo components of the URI.</span></span> <span data-ttu-id="01d31-105">Chování se změní, pouze pokud obě z následujících jsou splněny:</span><span class="sxs-lookup"><span data-stu-id="01d31-105">The behavior will change only when both of the following are true:</span></span><ul><li><span data-ttu-id="01d31-106">Identifikátor URI obsahuje kódované podobě každého následující vyhrazené znaky: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> nebo <code>\*</code>.</span><span class="sxs-lookup"><span data-stu-id="01d31-106">The URI contains the encoded form of any of the following reserved characters: <code>:</code>, <code>'</code>, <code>(</code>, <code>)</code>, <code>!</code> or <code>\*</code>.</span></span></li><li><span data-ttu-id="01d31-107">Identifikátor URI obsahuje typu Unicode nebo kódovaný-vyhrazené znak.</span><span class="sxs-lookup"><span data-stu-id="01d31-107">The URI contains a Unicode or encoded non-reserved character.</span></span> <span data-ttu-id="01d31-108">Pokud jsou splněny obě výše, jsou zakódovány vlevo kódovaného vyhrazené znaky.</span><span class="sxs-lookup"><span data-stu-id="01d31-108">If both of the above are true, the encoded reserved characters are left encoded.</span></span> <span data-ttu-id="01d31-109">V předchozích verzích rozhraní .NET Framework se dekódovat.</span><span class="sxs-lookup"><span data-stu-id="01d31-109">In previous versions of the .NET Framework, they are decoded.</span></span></li></ul>|
|<span data-ttu-id="01d31-110">Návrh</span><span class="sxs-lookup"><span data-stu-id="01d31-110">Suggestion</span></span>|<span data-ttu-id="01d31-111">Pro aplikace, které cílové verze rozhraní .NET Framework počínaje 4.7.2 se ve výchozím nastavení zapnutá nové dekódování chování.</span><span class="sxs-lookup"><span data-stu-id="01d31-111">For applications that target versions of .NET Framework starting with 4.7.2, the new decoding behavior is enabled by default.</span></span> <span data-ttu-id="01d31-112">Pokud tato změna není žádoucí, můžete ji zakázat přidáním následující [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) přepnout <code>&lt;runtime&gt;</code> oddílu konfiguračního souboru aplikace:</span><span class="sxs-lookup"><span data-stu-id="01d31-112">If this change is undesirable, you can disable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the <code>&lt;runtime&gt;</code> section of the application configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="01d31-113">Pro aplikace, které cílí na starší verze rozhraní .NET Framework, ale jsou spuštěny v rozhraní .NET Framework 4.7.2 počínaje verzí nové chování dekódování ve výchozím nastavení vypnutá.</span><span class="sxs-lookup"><span data-stu-id="01d31-113">For applications that target earlier versions of the .NET Framework but are running under versions starting with .NET Framework 4.7.2, the new decoding behavior is disabled by default.</span></span> <span data-ttu-id="01d31-114">Můžete ji povolit přidáním následující [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) přepnout <code>&lt;runtime&gt;</code> oddílu konfiguračního souboru aplikace::</span><span class="sxs-lookup"><span data-stu-id="01d31-114">You can enable it by adding the following [AppContextSwitchOverrides](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) switch to the <code>&lt;runtime&gt;</code> section of the application configuration file::</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="01d31-115">Rozsah</span><span class="sxs-lookup"><span data-stu-id="01d31-115">Scope</span></span>|<span data-ttu-id="01d31-116">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="01d31-116">Minor</span></span>|
|<span data-ttu-id="01d31-117">Version</span><span class="sxs-lookup"><span data-stu-id="01d31-117">Version</span></span>|<span data-ttu-id="01d31-118">4.7.2</span><span class="sxs-lookup"><span data-stu-id="01d31-118">4.7.2</span></span>|
|<span data-ttu-id="01d31-119">Typ</span><span class="sxs-lookup"><span data-stu-id="01d31-119">Type</span></span>|<span data-ttu-id="01d31-120">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="01d31-120">Retargeting</span></span>|
|<span data-ttu-id="01d31-121">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="01d31-121">Affected APIs</span></span>|<ul><li><xref:System.Uri?displayProperty=nameWithType></li></ul>|
