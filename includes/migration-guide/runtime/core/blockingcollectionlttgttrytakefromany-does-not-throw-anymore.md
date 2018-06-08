### <a name="blockingcollectionlttgttrytakefromany-does-not-throw-anymore"></a><span data-ttu-id="d0b25-101">BlockingCollection&lt;T&gt;. TryTakeFromAny nevyvolá výjimku už</span><span class="sxs-lookup"><span data-stu-id="d0b25-101">BlockingCollection&lt;T&gt;.TryTakeFromAny does not throw anymore</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d0b25-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="d0b25-102">Details</span></span>|<span data-ttu-id="d0b25-103">Pokud jeden vstupní kolekcí je označena jako dokončená, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> už vrátí hodnotu -1 a <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> už vyvolá výjimku.</span><span class="sxs-lookup"><span data-stu-id="d0b25-103">If one of the input collections is marked completed, <xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer returns -1 and <xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)> no longer throws an exception.</span></span> <span data-ttu-id="d0b25-104">Tato změna umožňuje pracovat s kolekcemi, pokud je jedna z kolekcí prázdná nebo dokončená, ale další kolekce stále obsahuje položky, které lze načíst.</span><span class="sxs-lookup"><span data-stu-id="d0b25-104">This change makes it possible to work with collections when one of the collections is either empty or completed, but the other collection still has items that can be retrieved.</span></span>|
|<span data-ttu-id="d0b25-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="d0b25-105">Suggestion</span></span>|<span data-ttu-id="d0b25-106">Pokud vrátí hodnotu -1 nebo TakeFromAny vyvolání TryTakeFromAny používaly pro účely tok řízení v případech blokující kolekce jeho dokončení, takový kód by měl nyní změnit tak, aby použít <code>.Any(b =&gt; b.IsCompleted)</code> ke zjištění této podmínky.</span><span class="sxs-lookup"><span data-stu-id="d0b25-106">If TryTakeFromAny returning -1 or TakeFromAny throwing were used for control-flow purposes in cases of a blocking collection being completed, such code should now be changed to use <code>.Any(b =&gt; b.IsCompleted)</code> to detect that condition.</span></span>|
|<span data-ttu-id="d0b25-107">Rozsah</span><span class="sxs-lookup"><span data-stu-id="d0b25-107">Scope</span></span>|<span data-ttu-id="d0b25-108">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="d0b25-108">Minor</span></span>|
|<span data-ttu-id="d0b25-109">Version</span><span class="sxs-lookup"><span data-stu-id="d0b25-109">Version</span></span>|<span data-ttu-id="d0b25-110">4.5</span><span class="sxs-lookup"><span data-stu-id="d0b25-110">4.5</span></span>|
|<span data-ttu-id="d0b25-111">Typ</span><span class="sxs-lookup"><span data-stu-id="d0b25-111">Type</span></span>|<span data-ttu-id="d0b25-112">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="d0b25-112">Runtime</span></span>|
|<span data-ttu-id="d0b25-113">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="d0b25-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Threading.CancellationToken)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.Int32)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li><li><xref:System.Collections.Concurrent.BlockingCollection%601.TryTakeFromAny(System.Collections.Concurrent.BlockingCollection{%600}[],%600@,System.TimeSpan)?displayProperty=nameWithType></li></ul>|
