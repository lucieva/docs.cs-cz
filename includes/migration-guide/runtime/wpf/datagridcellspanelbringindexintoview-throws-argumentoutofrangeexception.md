### <a name="datagridcellspanelbringindexintoview-throws-argumentoutofrangeexception"></a><span data-ttu-id="8fab8-101">DataGridCellsPanel.BringIndexIntoView vyvolá výjimka ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="8fab8-101">DataGridCellsPanel.BringIndexIntoView throws ArgumentOutOfRangeException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8fab8-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="8fab8-102">Details</span></span>|<span data-ttu-id="8fab8-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> bude fungovat asynchronně, když je povolena virtualizace sloupec, ale nebyly dosud stanoveny šířku sloupců.</span><span class="sxs-lookup"><span data-stu-id="8fab8-103"><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> will work asynchronously when column virtualization is enabled but the column widths have not yet been determined.</span></span>  <span data-ttu-id="8fab8-104">Pokud sloupce jsou odebrány, než se stane asynchronní práce, <xref:System.ArgumentOutOfRangeException?displayProperty=name> situace může nastat.</span><span class="sxs-lookup"><span data-stu-id="8fab8-104">If columns are removed before the asynchronous work happens, an <xref:System.ArgumentOutOfRangeException?displayProperty=name> can occur.</span></span>|
|<span data-ttu-id="8fab8-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="8fab8-105">Suggestion</span></span>|<span data-ttu-id="8fab8-106">Kterákoli z následujících akcí:</span><span class="sxs-lookup"><span data-stu-id="8fab8-106">Any one of the following:</span></span><ol><li><span data-ttu-id="8fab8-107">Upgrade na rozhraní .NET Framework 4.7.</span><span class="sxs-lookup"><span data-stu-id="8fab8-107">Upgrade to .NET Framework 4.7.</span></span></li><li><span data-ttu-id="8fab8-108">Nainstalujte nejnovější údržby opravy pro rozhraní .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="8fab8-108">Install the latest servicing patch for .NET Framework 4.6.2.</span></span></li><li><span data-ttu-id="8fab8-109">Nedošlo k odebrání sloupce dokud asynchronní odpověď na <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> byla dokončena.</span><span class="sxs-lookup"><span data-stu-id="8fab8-109">Avoid removing columns until the asynchronous response to <xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)> has completed.</span></span></li></ol>|
|<span data-ttu-id="8fab8-110">Rozsah</span><span class="sxs-lookup"><span data-stu-id="8fab8-110">Scope</span></span>|<span data-ttu-id="8fab8-111">Edge</span><span class="sxs-lookup"><span data-stu-id="8fab8-111">Edge</span></span>|
|<span data-ttu-id="8fab8-112">Version</span><span class="sxs-lookup"><span data-stu-id="8fab8-112">Version</span></span>|<span data-ttu-id="8fab8-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="8fab8-113">4.6.2</span></span>|
|<span data-ttu-id="8fab8-114">Typ</span><span class="sxs-lookup"><span data-stu-id="8fab8-114">Type</span></span>|<span data-ttu-id="8fab8-115">Modul runtime</span><span class="sxs-lookup"><span data-stu-id="8fab8-115">Runtime</span></span>|
|<span data-ttu-id="8fab8-116">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="8fab8-116">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object)?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.ScrollIntoView(System.Object,System.Windows.Controls.DataGridColumn)?displayProperty=nameWithType></li></ul>|
