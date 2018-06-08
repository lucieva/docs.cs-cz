### <a name="incorrect-implementation-of-memberdescriptorequals"></a><span data-ttu-id="830fb-101">Nesprávné implementace MemberDescriptor.Equals</span><span class="sxs-lookup"><span data-stu-id="830fb-101">Incorrect implementation of MemberDescriptor.Equals</span></span>

|   |   |
|---|---|
|<span data-ttu-id="830fb-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="830fb-102">Details</span></span>|<span data-ttu-id="830fb-103">Původní implementace <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> metoda porovná dvě vlastnosti jiný řetězec z porovnávaných objektů: název kategorie a řetězec popisu.</span><span class="sxs-lookup"><span data-stu-id="830fb-103">The original implementation of the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method compares two different string properties from the objects being compared: the category name and the description string.</span></span> <span data-ttu-id="830fb-104">Potíže se má porovnat <xref:System.ComponentModel.MemberDescriptor.Category> z první objekt, který má <xref:System.ComponentModel.MemberDescriptor.Category> z druhý a <xref:System.ComponentModel.MemberDescriptor.Description> prvního k <xref:System.ComponentModel.MemberDescriptor.Description> druhého.</span><span class="sxs-lookup"><span data-stu-id="830fb-104">The fix is to compare the <xref:System.ComponentModel.MemberDescriptor.Category> of the first object to the <xref:System.ComponentModel.MemberDescriptor.Category> of the second one, and the <xref:System.ComponentModel.MemberDescriptor.Description> of the first to the <xref:System.ComponentModel.MemberDescriptor.Description> of the second.</span></span>|
|<span data-ttu-id="830fb-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="830fb-105">Suggestion</span></span>|<span data-ttu-id="830fb-106">Pokud je aplikace závislá na <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> někdy vrácení <code>false</code> při popisovače jsou ekvivalentní a cílení rozhraní .NET Framework 4.6.2 nebo novější, máte několik možností:</span><span class="sxs-lookup"><span data-stu-id="830fb-106">If your application depends on <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> sometimes returning <code>false</code> when descriptors are equivalent, and you are targeting the .NET Framework 4.6.2 or later, you have several options:</span></span><ol><li><span data-ttu-id="830fb-107">Provádět změny kódu k porovnání <xref:System.ComponentModel.MemberDescriptor.Category> a <xref:System.ComponentModel.MemberDescriptor.Description> pole ručně kromě volání <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> metoda.</span><span class="sxs-lookup"><span data-stu-id="830fb-107">Make code changes to compare the <xref:System.ComponentModel.MemberDescriptor.Category> and <xref:System.ComponentModel.MemberDescriptor.Description> fields manually in addition to calling the <xref:System.ComponentModel.MemberDescriptor.Equals%2A?displayProperty=nameWithType> method.</span></span></li><li><span data-ttu-id="830fb-108">Vyjádření výslovného nesouhlasu tuto změnu přidáním následující hodnotu do souboru app.config:</span><span class="sxs-lookup"><span data-stu-id="830fb-108">Opt out of this change by adding the following value to the app.config file:</span></span></li></ol><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="830fb-109">Pokud aplikace cílí rozhraní .NET Framework 4.6.1 nebo starší a běží na rozhraní .NET Framework 4.6.2 nebo novější a chcete, aby tato změna povolené, přepínač kompatibility můžete nastavit, aby <code>false</code> přidáním následující hodnotu do souboru app.config:</span><span class="sxs-lookup"><span data-stu-id="830fb-109">If your application targets .NET Framework 4.6.1 or earlier and is running on the .NET Framework 4.6.2 or later and you want this change enabled, you can set the compatibility switch to <code>false</code> by adding the following value to the app.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.MemberDescriptorEqualsReturnsFalseIfEquivalent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="830fb-110">Rozsah</span><span class="sxs-lookup"><span data-stu-id="830fb-110">Scope</span></span>|<span data-ttu-id="830fb-111">Edge</span><span class="sxs-lookup"><span data-stu-id="830fb-111">Edge</span></span>|
|<span data-ttu-id="830fb-112">Version</span><span class="sxs-lookup"><span data-stu-id="830fb-112">Version</span></span>|<span data-ttu-id="830fb-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="830fb-113">4.6.2</span></span>|
|<span data-ttu-id="830fb-114">Typ</span><span class="sxs-lookup"><span data-stu-id="830fb-114">Type</span></span>|<span data-ttu-id="830fb-115">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="830fb-115">Retargeting</span></span>|
|<span data-ttu-id="830fb-116">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="830fb-116">Affected APIs</span></span>|<ul><li><xref:System.ComponentModel.MemberDescriptor.Equals(System.Object)?displayProperty=nameWithType></li></ul>|
