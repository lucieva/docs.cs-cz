### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a><span data-ttu-id="b4d30-101">TabControl SelectionChanged událostí a SelectedContent vlastnost</span><span class="sxs-lookup"><span data-stu-id="b4d30-101">TabControl SelectionChanged event and SelectedContent property</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b4d30-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="b4d30-102">Details</span></span>|<span data-ttu-id="b4d30-103">Od verze rozhraní .NET Framework 4.7.1, <xref:System.Windows.Controls.TabControl> aktualizuje hodnotu jeho <xref:System.Windows.Controls.TabControl.SelectedContent> vlastnost než se vyvolá <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> událost, když se změní jeho výběr. V rozhraní .NET Framework 4.7 a starší verze aktualizace, která se SelectedContent došlo po události.</span><span class="sxs-lookup"><span data-stu-id="b4d30-103">Starting with the .NET Framework 4.7.1, a <xref:System.Windows.Controls.TabControl> updates the value of its <xref:System.Windows.Controls.TabControl.SelectedContent> property before raising the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event, when its selection changes.In the .NET Framework 4.7 and earlier versions, the update to SelectedContent happened after the event.</span></span>|
|<span data-ttu-id="b4d30-104">Návrh</span><span class="sxs-lookup"><span data-stu-id="b4d30-104">Suggestion</span></span>|<span data-ttu-id="b4d30-105">Aplikace, které cílí na rozhraní .NET Framework 4.7.1 nebo novější můžete zamítnutí to změnit a použijte starší verze chování přidáním následujícího <code>&lt;runtime&gt;</code> oddílu konfiguračního souboru aplikace:</span><span class="sxs-lookup"><span data-stu-id="b4d30-105">Apps that target the .NET Framework 4.7.1 or later can opt out of this change and use legacy behavior by adding the following to the <code>&lt;runtime&gt;</code> section of the application configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="b4d30-106">Aplikace, které cílí na rozhraní .NET Framework 4.7 nebo dřívější ale běží na rozhraní .NET Framework 4.7.1 nebo později můžete povolit nové chování přidáním následující řádek do <code>&lt;runtime&gt;</code> části souboru .configuration aplikace:</span><span class="sxs-lookup"><span data-stu-id="b4d30-106">Apps that target the .NET Framework 4.7 or earlier but are running on the .NET Framework 4.7.1 or later can enable the new behavior by adding the following line to the <code>&lt;runtime&gt;</code> section of the application .configuration file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="b4d30-107">Rozsah</span><span class="sxs-lookup"><span data-stu-id="b4d30-107">Scope</span></span>|<span data-ttu-id="b4d30-108">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="b4d30-108">Minor</span></span>|
|<span data-ttu-id="b4d30-109">Version</span><span class="sxs-lookup"><span data-stu-id="b4d30-109">Version</span></span>|<span data-ttu-id="b4d30-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="b4d30-110">4.7.1</span></span>|
|<span data-ttu-id="b4d30-111">Typ</span><span class="sxs-lookup"><span data-stu-id="b4d30-111">Type</span></span>|<span data-ttu-id="b4d30-112">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="b4d30-112">Retargeting</span></span>|
|<span data-ttu-id="b4d30-113">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="b4d30-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|
