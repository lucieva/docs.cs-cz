### <a name="tabcontrol-selectionchanged-event-and-selectedcontent-property"></a>TabControl – SelectionChanged události a SelectedContent vlastnost

|   |   |
|---|---|
|Podrobnosti|Od verze rozhraní .NET Framework 4.7.1, <xref:System.Windows.Controls.TabControl> aktualizuje hodnotu jeho <xref:System.Windows.Controls.TabControl.SelectedContent> vlastnost vyčkat, než se <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> událost, když se změní jeho výběr. V rozhraní .NET Framework 4.7 a dřívějších verzích aktualizace, která se SelectedContent došlo po skončení události.|
|Návrh|Aplikace, které se zaměřují rozhraní .NET Framework 4.7.1 nebo novější můžete zrušit to změnit a použít starší verzi chování přidáním následujícího <code>&lt;runtime&gt;</code> oddílu konfiguračního souboru aplikace:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Aplikace, které cílí na .NET Framework 4.7 nebo starší ale jsou spuštěny v rozhraní .NET Framework 4.7.1 nebo novější můžete povolit nové chování tak, že přidáte následující řádek, který <code>&lt;runtime&gt;</code> .configuration souboru aplikace:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Windows.Controls.TabControl.SelectionPropertiesCanLagBehindSelectionChangedEvent=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Rozsah|Vedlejší|
|Version|4.7.1|
|Typ|Mění se cílení|
|Ovlivněné rozhraní API|<ul><li><xref:System.Windows.Controls.TabControl.SelectedContent?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.Primitives.Selector.SelectionChanged?displayProperty=nameWithType></li></ul>|

