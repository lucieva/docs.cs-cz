### <a name="minfreememorypercentagetoactiveservice-is-now-respected"></a><span data-ttu-id="c2073-101">Nyní je dodržena MinFreeMemoryPercentageToActiveService</span><span class="sxs-lookup"><span data-stu-id="c2073-101">MinFreeMemoryPercentageToActiveService is now respected</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c2073-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="c2073-102">Details</span></span>|<span data-ttu-id="c2073-103">Toto nastavení určuje minimální velikost paměti, která musí být k dispozici na serveru před aktivací služby WCF.</span><span class="sxs-lookup"><span data-stu-id="c2073-103">This setting establishes the minimum memory that must be available on the server before a WCF service can be activated.</span></span> <span data-ttu-id="c2073-104">Je navržená tak, aby se zabránilo <xref:System.OutOfMemoryException?displayProperty=name> výjimky.</span><span class="sxs-lookup"><span data-stu-id="c2073-104">It is designed to prevent <xref:System.OutOfMemoryException?displayProperty=name> exceptions.</span></span> <span data-ttu-id="c2073-105">Toto nastavení v rozhraní .NET Framework 4.5, nemělo žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="c2073-105">In the .NET Framework 4.5, this setting had no effect.</span></span> <span data-ttu-id="c2073-106">V rozhraní .NET Framework 4.5.1 je zaznamenali nastavení.</span><span class="sxs-lookup"><span data-stu-id="c2073-106">In the .NET Framework 4.5.1, the setting is observed.</span></span>|
|<span data-ttu-id="c2073-107">Návrh</span><span class="sxs-lookup"><span data-stu-id="c2073-107">Suggestion</span></span>|<span data-ttu-id="c2073-108">Pokud volné paměti, které jsou dostupné na webovém serveru je nižší než procento definované nastavení konfigurace, dojde k výjimce.</span><span class="sxs-lookup"><span data-stu-id="c2073-108">An exception occurs if the free memory available on the web server is less than the percentage defined by the configuration setting.</span></span> <span data-ttu-id="c2073-109">Některé služby WCF, které úspěšně spuštěn a v prostředí omezené paměti se spustil teď může selhat.</span><span class="sxs-lookup"><span data-stu-id="c2073-109">Some WCF services that successfully started and ran in a constrained memory environment may now fail.</span></span>|
|<span data-ttu-id="c2073-110">Rozsah</span><span class="sxs-lookup"><span data-stu-id="c2073-110">Scope</span></span>|<span data-ttu-id="c2073-111">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="c2073-111">Minor</span></span>|
|<span data-ttu-id="c2073-112">Version</span><span class="sxs-lookup"><span data-stu-id="c2073-112">Version</span></span>|<span data-ttu-id="c2073-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="c2073-113">4.5.1</span></span>|
|<span data-ttu-id="c2073-114">Typ</span><span class="sxs-lookup"><span data-stu-id="c2073-114">Type</span></span>|<span data-ttu-id="c2073-115">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="c2073-115">Runtime</span></span>|
