### <a name="httpruntimeappdomainapppath-throws-a-nullreferenceexception"></a><span data-ttu-id="56d6d-101">HttpRuntime.AppDomainAppPath vyvolá výjimky NullReferenceException.</span><span class="sxs-lookup"><span data-stu-id="56d6d-101">HttpRuntime.AppDomainAppPath Throws a NullReferenceException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="56d6d-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="56d6d-102">Details</span></span>|<span data-ttu-id="56d6d-103">V rozhraní .NET Framework 4.6.2 modul runtime vyvolá <code>T:System.NullReferenceException</code> při načítání <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> hodnotu, která zahrnuje znaky null. V rozhraní .NET Framework 4.6.1 a dřívějších verzí, modul runtime vyvolá <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="56d6d-103">In the .NET Framework 4.6.2, the runtime throws a <code>T:System.NullReferenceException</code> when retrieving a <code>P:System.Web.HttpRuntime.AppDomainAppPath</code> value that includes null characters.In the .NET Framework 4.6.1 and earlier versions, the runtime throws an <code>T:System.ArgumentNullException</code>.</span></span>|
|<span data-ttu-id="56d6d-104">Návrh</span><span class="sxs-lookup"><span data-stu-id="56d6d-104">Suggestion</span></span>|<span data-ttu-id="56d6d-105">Můžete provést jeden z těchto kroků reagovat na tuto změnu:</span><span class="sxs-lookup"><span data-stu-id="56d6d-105">You can do either of the follow to respond to this change:</span></span><ul><li><span data-ttu-id="56d6d-106">Zpracování <code>T:System.NullReferenceException</code> Pokud je aplikace spuštěna v rozhraní .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="56d6d-106">Handle the <code>T:System.NullReferenceException</code> if you application is running on the .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="56d6d-107">Upgrade na 4.7 Framework .NET, která obnoví předchozí chování a způsobí výjimku, <code>T:System.ArgumentNullException</code>.</span><span class="sxs-lookup"><span data-stu-id="56d6d-107">Upgrade to the .NET Framework 4.7, which restores the previous behavior and throws an <code>T:System.ArgumentNullException</code>.</span></span></li></ul>|
|<span data-ttu-id="56d6d-108">Rozsah</span><span class="sxs-lookup"><span data-stu-id="56d6d-108">Scope</span></span>|<span data-ttu-id="56d6d-109">Edge</span><span class="sxs-lookup"><span data-stu-id="56d6d-109">Edge</span></span>|
|<span data-ttu-id="56d6d-110">Version</span><span class="sxs-lookup"><span data-stu-id="56d6d-110">Version</span></span>|<span data-ttu-id="56d6d-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="56d6d-111">4.6.2</span></span>|
|<span data-ttu-id="56d6d-112">Typ</span><span class="sxs-lookup"><span data-stu-id="56d6d-112">Type</span></span>|<span data-ttu-id="56d6d-113">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="56d6d-113">Retargeting</span></span>|
|<span data-ttu-id="56d6d-114">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="56d6d-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRuntime.AppDomainAppPath?displayProperty=nameWithType></li></ul>|
