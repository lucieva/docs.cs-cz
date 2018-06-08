### <a name="aspnet-mvc-now-escapes-spaces-in-strings-passed-in-via-route-parameters"></a><span data-ttu-id="8c99a-101">ASP.NET MVC řídicí sekvence nyní mezery v řetězcích předaná prostřednictvím parametry trasy</span><span class="sxs-lookup"><span data-stu-id="8c99a-101">ASP.NET MVC now escapes spaces in strings passed in via route parameters</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8c99a-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="8c99a-102">Details</span></span>|<span data-ttu-id="8c99a-103">K dosažení souladu s RFC 2396, jsou prostory v trasy cesty uvozený teď při naplňování parametry akce z trasy.</span><span class="sxs-lookup"><span data-stu-id="8c99a-103">In order to conform to RFC 2396, spaces in route paths are now escaped when populating action parameters from a route.</span></span> <span data-ttu-id="8c99a-104">Ano zatímco <code>/controller/action/some data</code> dříve odpovídá trasy <code>/controller/action/{data}</code> a zadejte <code>some data</code> jako parametr dat bude nyní poskytovat <code>some%20data</code> místo.</span><span class="sxs-lookup"><span data-stu-id="8c99a-104">So, whereas  <code>/controller/action/some data</code> would previously match the route <code>/controller/action/{data}</code> and provide <code>some data</code> as the data parameter, it will now provide <code>some%20data</code> instead.</span></span>|
|<span data-ttu-id="8c99a-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="8c99a-105">Suggestion</span></span>|<span data-ttu-id="8c99a-106">Kód se musí aktualizovat na unescape parametrů řetězce z trasy.</span><span class="sxs-lookup"><span data-stu-id="8c99a-106">Code should be updated to unescape string parameters from a route.</span></span> <span data-ttu-id="8c99a-107">V případě potřeby původní URI lze přistupovat pomocí <xref:System.Net.HttpWebRequest.RequestUri>. OriginalString rozhraní API.</span><span class="sxs-lookup"><span data-stu-id="8c99a-107">If the original URI is needed, it can be accessed with the <xref:System.Net.HttpWebRequest.RequestUri>.OriginalString API.</span></span>|
|<span data-ttu-id="8c99a-108">Rozsah</span><span class="sxs-lookup"><span data-stu-id="8c99a-108">Scope</span></span>|<span data-ttu-id="8c99a-109">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="8c99a-109">Minor</span></span>|
|<span data-ttu-id="8c99a-110">Version</span><span class="sxs-lookup"><span data-stu-id="8c99a-110">Version</span></span>|<span data-ttu-id="8c99a-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="8c99a-111">4.5.2</span></span>|
|<span data-ttu-id="8c99a-112">Typ</span><span class="sxs-lookup"><span data-stu-id="8c99a-112">Type</span></span>|<span data-ttu-id="8c99a-113">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="8c99a-113">Runtime</span></span>|
|<span data-ttu-id="8c99a-114">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="8c99a-114">Affected APIs</span></span>|<ul><li><xref:System.Web.Mvc.RouteAttribute.%23ctor(System.String)?displayProperty=nameWithType></li></ul>|
