### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="d52af-101">ObjectContext.Translate a ObjectContext.ExecuteStoreQuery teď podporují typ výčtu.</span><span class="sxs-lookup"><span data-stu-id="d52af-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d52af-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="d52af-102">Details</span></span>|<span data-ttu-id="d52af-103">V rozhraní .NET Framework 4.0, obecný parametr <code>T</code> z <code>ObjectContext.Translate</code> a <code>ObjectContext.ExecuteStoreQuery</code> metody nelze výčtu.</span><span class="sxs-lookup"><span data-stu-id="d52af-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="d52af-104">Tento scénář se teď podporuje.</span><span class="sxs-lookup"><span data-stu-id="d52af-104">That scenario is now supported.</span></span>|
|<span data-ttu-id="d52af-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="d52af-105">Suggestion</span></span>|<span data-ttu-id="d52af-106">Pokud přeložit nebo ExecuteStoreQuery byla volána na typu výčtu v rozhraní .NET Framework 4.0, byl vrácen '0'.</span><span class="sxs-lookup"><span data-stu-id="d52af-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="d52af-107">Pokud toto chování žádoucí, měl by být volání nahrazen konstanta 0 (nebo ekvivalentní výčtu je).</span><span class="sxs-lookup"><span data-stu-id="d52af-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>|
|<span data-ttu-id="d52af-108">Rozsah</span><span class="sxs-lookup"><span data-stu-id="d52af-108">Scope</span></span>|<span data-ttu-id="d52af-109">Edge</span><span class="sxs-lookup"><span data-stu-id="d52af-109">Edge</span></span>|
|<span data-ttu-id="d52af-110">Version</span><span class="sxs-lookup"><span data-stu-id="d52af-110">Version</span></span>|<span data-ttu-id="d52af-111">4.5</span><span class="sxs-lookup"><span data-stu-id="d52af-111">4.5</span></span>|
|<span data-ttu-id="d52af-112">Typ</span><span class="sxs-lookup"><span data-stu-id="d52af-112">Type</span></span>|<span data-ttu-id="d52af-113">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="d52af-113">Runtime</span></span>|
|<span data-ttu-id="d52af-114">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="d52af-114">Affected APIs</span></span>|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
