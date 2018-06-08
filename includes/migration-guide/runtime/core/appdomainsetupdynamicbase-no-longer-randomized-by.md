### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a><span data-ttu-id="c6605-101">AppDomainSetup.DynamicBase už náhodně mění podle userandomizedstringhashalgorithm –</span><span class="sxs-lookup"><span data-stu-id="c6605-101">AppDomainSetup.DynamicBase is no longer randomized by UseRandomizedStringHashAlgorithm</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c6605-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="c6605-102">Details</span></span>|<span data-ttu-id="c6605-103">Před rozhraní .NET Framework 4.6, hodnota <xref:System.AppDomainSetup.DynamicBase> by se náhodně mění, mezi doménami aplikací, nebo mezi procesy, pokud bylo userandomizedstringhashalgorithm – povolené v konfiguračním souboru aplikace.</span><span class="sxs-lookup"><span data-stu-id="c6605-103">Prior to the .NET Framework 4.6, the value of <xref:System.AppDomainSetup.DynamicBase> would be randomized between application domains, or between processes, if UseRandomizedStringHashAlgorithm was enabled in the app's config file.</span></span> <span data-ttu-id="c6605-104">Od verze rozhraní .NET Framework 4.6 <xref:System.AppDomainSetup.DynamicBase> vrátí výsledku stabilní mezi různými instancemi spuštění aplikace a mezi doménami jinou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="c6605-104">Beginning in the .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> will return a stable result between different instances of an app running, and between different app domains.</span></span> <span data-ttu-id="c6605-105">Dynamické základů budou stále lišit pro různé aplikace; Tato změna pouze odebere náhodných pojmenování element pro různé instance stejné aplikaci.</span><span class="sxs-lookup"><span data-stu-id="c6605-105">Dynamic bases will still differ for different apps; this change only removes the random naming element for different instances of the same app.</span></span>|
|<span data-ttu-id="c6605-106">Návrh</span><span class="sxs-lookup"><span data-stu-id="c6605-106">Suggestion</span></span>|<span data-ttu-id="c6605-107">Uvědomte si, že povolení <code>UseRandomizedStringHashAlgorithm</code> nebude mít za následek <xref:System.AppDomainSetup.DynamicBase> se náhodně mění.</span><span class="sxs-lookup"><span data-stu-id="c6605-107">Be aware that enabling <code>UseRandomizedStringHashAlgorithm</code> will not result in <xref:System.AppDomainSetup.DynamicBase> being randomized.</span></span> <span data-ttu-id="c6605-108">V případě potřeby náhodných základní musí být vytvořeného v kódu aplikace a nikoli prostřednictvím toto rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="c6605-108">If a random base is needed, it must be produced in your app's code rather than via this API.</span></span>|
|<span data-ttu-id="c6605-109">Rozsah</span><span class="sxs-lookup"><span data-stu-id="c6605-109">Scope</span></span>|<span data-ttu-id="c6605-110">Edge</span><span class="sxs-lookup"><span data-stu-id="c6605-110">Edge</span></span>|
|<span data-ttu-id="c6605-111">Version</span><span class="sxs-lookup"><span data-stu-id="c6605-111">Version</span></span>|<span data-ttu-id="c6605-112">4.6</span><span class="sxs-lookup"><span data-stu-id="c6605-112">4.6</span></span>|
|<span data-ttu-id="c6605-113">Typ</span><span class="sxs-lookup"><span data-stu-id="c6605-113">Type</span></span>|<span data-ttu-id="c6605-114">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="c6605-114">Runtime</span></span>|
|<span data-ttu-id="c6605-115">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="c6605-115">Affected APIs</span></span>|<ul><li><xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|
