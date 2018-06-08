### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="17276-101">Víceřádkový ASP.Net TextBox mezery změnit při použití AntiXSSEncoder</span><span class="sxs-lookup"><span data-stu-id="17276-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="17276-102">Podrobnosti</span><span class="sxs-lookup"><span data-stu-id="17276-102">Details</span></span>|<span data-ttu-id="17276-103">V rozhraní .NET Framework 4.0, další řádky byly vloženy mezi řádky Víceřádkový textové pole na zpětné volání, pokud se používá <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span><span class="sxs-lookup"><span data-stu-id="17276-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="17276-104">Rozhraní .NET Framework 4.5 tyto nadbytečné konce řádků nejsou zahrnuty, ale pouze v případě, že webová aplikace je cílení na rozhraní .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="17276-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="17276-105">Návrh</span><span class="sxs-lookup"><span data-stu-id="17276-105">Suggestion</span></span>|<span data-ttu-id="17276-106">Upozorňujeme, že změnit cíl na rozhraní .NET Framework 4.5 necílené 4.0 webové aplikace může mít více řádků textová pole vylepšené už vložit nadbytečné konce řádků.</span><span class="sxs-lookup"><span data-stu-id="17276-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="17276-107">Pokud to není žádoucí, aplikace může mít staré chování při spuštění v rozhraní .NET Framework 4.5 cílením rozhraní .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="17276-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="17276-108">Rozsah</span><span class="sxs-lookup"><span data-stu-id="17276-108">Scope</span></span>|<span data-ttu-id="17276-109">Vedlejší</span><span class="sxs-lookup"><span data-stu-id="17276-109">Minor</span></span>|
|<span data-ttu-id="17276-110">Version</span><span class="sxs-lookup"><span data-stu-id="17276-110">Version</span></span>|<span data-ttu-id="17276-111">4.5</span><span class="sxs-lookup"><span data-stu-id="17276-111">4.5</span></span>|
|<span data-ttu-id="17276-112">Typ</span><span class="sxs-lookup"><span data-stu-id="17276-112">Type</span></span>|<span data-ttu-id="17276-113">Změna orientace</span><span class="sxs-lookup"><span data-stu-id="17276-113">Retargeting</span></span>|
