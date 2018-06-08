### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="4a70f-101">Konstruktoru EncoderParameter je zastaralá</span><span class="sxs-lookup"><span data-stu-id="4a70f-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="4a70f-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="4a70f-102">Details</span></span>|<span data-ttu-id="4a70f-103"><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> Konstruktor je nyní zastaralý a zavádí sestavení upozornění, pokud se používá.</span><span class="sxs-lookup"><span data-stu-id="4a70f-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="4a70f-104">Návrh</span><span class="sxs-lookup"><span data-stu-id="4a70f-104">Suggestion</span></span>|<span data-ttu-id="4a70f-105">I když <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>konstruktor budou nadále fungovat, následující konstruktor musí být použit místo abyste se vyhnuli upozornění na zastaralé sestavení při znovu kompilování kódu nástroje pro rozhraní .NET Framework 4.5: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="4a70f-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="4a70f-106">Rozsah</span><span class="sxs-lookup"><span data-stu-id="4a70f-106">Scope</span></span>|<span data-ttu-id="4a70f-107">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="4a70f-107">Minor</span></span>|
|<span data-ttu-id="4a70f-108">Version</span><span class="sxs-lookup"><span data-stu-id="4a70f-108">Version</span></span>|<span data-ttu-id="4a70f-109">4.5</span><span class="sxs-lookup"><span data-stu-id="4a70f-109">4.5</span></span>|
|<span data-ttu-id="4a70f-110">Typ</span><span class="sxs-lookup"><span data-stu-id="4a70f-110">Type</span></span>|<span data-ttu-id="4a70f-111">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="4a70f-111">Retargeting</span></span>|
|<span data-ttu-id="4a70f-112">Ovlivněné rozhraní API</span><span class="sxs-lookup"><span data-stu-id="4a70f-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
