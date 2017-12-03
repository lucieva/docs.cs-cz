---
title: "WIF relace správy"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98bce126-18a9-401b-b20d-67ee462a5f8a
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9c41b9c0c9abe3fc80d16dbd847c35c8b2da7038
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="wif-session-management"></a><span data-ttu-id="aecf9-102">WIF relace správy</span><span class="sxs-lookup"><span data-stu-id="aecf9-102">WIF Session Management</span></span>
<span data-ttu-id="aecf9-103">Když klient se poprvé pokusí o přístup k chráněnému prostředku, který je hostován předávající strana, klient musí je nejdřív ověřit samotné služby tokenů zabezpečení (STS), která je důvěryhodná předávající stranou.</span><span class="sxs-lookup"><span data-stu-id="aecf9-103">When a client first tries to access a protected resource that is hosted by a relying party, the client must first authenticate itself to a security token service (STS) that is trusted by the relying party.</span></span> <span data-ttu-id="aecf9-104">Služba tokenů zabezpečení pak vydá token zabezpečení do klienta.</span><span class="sxs-lookup"><span data-stu-id="aecf9-104">The STS then issues a security token to the client.</span></span> <span data-ttu-id="aecf9-105">Klient uvede tento token pro předávající stranu, která pak uděluje klientský přístup k chráněnému prostředku.</span><span class="sxs-lookup"><span data-stu-id="aecf9-105">The client presents this token to the relying party, which then grants the client access to the protected resource.</span></span> <span data-ttu-id="aecf9-106">Ale nechcete, aby klient tak, aby měl znovu provést ověření na službu STS pro každý požadavek zvlášť, protože i nemusí být ve stejném počítači nebo ve stejné doméně jako předávající strany.</span><span class="sxs-lookup"><span data-stu-id="aecf9-106">However, you don’t want the client to have to re-authenticate to the STS for each request, especially because it might not even be on the same computer or in the same domain as the relying party.</span></span> <span data-ttu-id="aecf9-107">Místo toho Windows Identity Foundation (WIF) má klienta a vytvořit relaci, ve které klient použije token zabezpečení relace k vlastnímu ověření předávající stranu pro všechny požadavky po prvním požadavku předávající strany.</span><span class="sxs-lookup"><span data-stu-id="aecf9-107">Instead, Windows Identity Foundation (WIF) has the client and relying party establish a session in which the client uses a session security token to authenticate itself to the relying party for all requests after the first request.</span></span> <span data-ttu-id="aecf9-108">Předávající strana můžete použít tento token zabezpečení relace, který je uložený v souboru cookie, k rekonstrukci klienta <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aecf9-108">The relying party can use this session security token, which is stored inside a cookie, to reconstruct the client’s <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="aecf9-109">Služba tokenů zabezpečení definuje ověření klient musí poskytnout.</span><span class="sxs-lookup"><span data-stu-id="aecf9-109">The STS defines what authentication the client must provide.</span></span> <span data-ttu-id="aecf9-110">Klient však může mít několik přihlašovací údaje, s nimiž se může ověřit sám na službu STS.</span><span class="sxs-lookup"><span data-stu-id="aecf9-110">However, the client might have multiple credentials with which it can authenticate itself to the STS.</span></span> <span data-ttu-id="aecf9-111">Například může mít tokenu z Windows Live, uživatelské jméno a heslo, certifikát a smartkey.</span><span class="sxs-lookup"><span data-stu-id="aecf9-111">For example, it might have a token from Windows Live, a user name and password, a certificate, and a smartkey.</span></span> <span data-ttu-id="aecf9-112">V takovém případě služba tokenů zabezpečení uděluje klienta několik identit s každou identitu odpovídající přihlašovací údaje, které představuje klienta.</span><span class="sxs-lookup"><span data-stu-id="aecf9-112">In that case, the STS grants the client several identities, with each identity corresponding to one of the credentials that the client presents.</span></span> <span data-ttu-id="aecf9-113">Předávající strana můžete použít jeden nebo více těchto identit, když rozhoduje, jakou úroveň přístupu k udělení klienta.</span><span class="sxs-lookup"><span data-stu-id="aecf9-113">The relying party can use one or more of these identities when it decides what level of access to grant the client.</span></span>  
  
 <span data-ttu-id="aecf9-114"><xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=nameWithType> Se používá k rekonstrukci klienta <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>, který obsahuje všechny identity klienta v <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A>.</span><span class="sxs-lookup"><span data-stu-id="aecf9-114">The <xref:System.IdentityModel.Tokens.SessionSecurityToken?displayProperty=nameWithType> is used to reconstruct the client’s <xref:System.Security.Claims.ClaimsPrincipal?displayProperty=nameWithType>, which contains all of the client’s identities in <xref:System.Security.Claims.ClaimsPrincipal.Identities%2A>.</span></span> <span data-ttu-id="aecf9-115">Každý <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> v kolekci obsahuje bootstrap tokeny, které jsou spojeny s danou identitu.</span><span class="sxs-lookup"><span data-stu-id="aecf9-115">Each <xref:System.Security.Claims.ClaimsIdentity?displayProperty=nameWithType> in the collection contains the bootstrap tokens that are associated with that identity.</span></span>  
  
 <span data-ttu-id="aecf9-116">Pokud se objeví token novou relaci s ID relace původní token relace <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=nameWithType> neaktualizuje token relace v mezipaměti v tokenu.</span><span class="sxs-lookup"><span data-stu-id="aecf9-116">If a new session token is issued with the session ID of the original session token, <xref:System.IdentityModel.Tokens.SessionSecurityTokenHandler?displayProperty=nameWithType> does not update the session token in the token cache.</span></span> <span data-ttu-id="aecf9-117">Měli vždycky vytvořit instanci token relace s ID jedinečný relace.</span><span class="sxs-lookup"><span data-stu-id="aecf9-117">You should always instantiate a session token with a unique session ID.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aecf9-118">Vyvolá Session.SecurityTokenHandler.ReadToken <xref:System.Xml.XmlException> výjimka, pokud obdrží neplatný vstup; například, pokud je poškozený soubor cookie, který obsahuje token relace.</span><span class="sxs-lookup"><span data-stu-id="aecf9-118">Session.SecurityTokenHandler.ReadToken throws a <xref:System.Xml.XmlException> exception if it receives invalid input; for example, if the cookie that contains the session token is corrupted.</span></span> <span data-ttu-id="aecf9-119">Doporučujeme, abyste tuto výjimku zachytit a zadejte specifické pro aplikaci chování.</span><span class="sxs-lookup"><span data-stu-id="aecf9-119">We recommend that you catch this exception and provide application-specific behavior.</span></span>  
  
 <span data-ttu-id="aecf9-120">Pokud chráněný webová stránka obsahuje velké množství prostředků (například malé grafické), které jsou i v chráněnou doménu, klient musí znovu ověří předávající strany ke stažení, každý z těchto prostředků.</span><span class="sxs-lookup"><span data-stu-id="aecf9-120">If a protected Web page contains lots of resources (such as small graphics) that are also in the protected domain, the client must re-authenticate itself to the relying party to download each of those resources.</span></span> <span data-ttu-id="aecf9-121">Použití ověřovací token relace nevyžaduje nutnost ověření služby tokenů zabezpečení pro každý požadavek, ale stále znamená, že mnoho soubory cookie jsou odesílány přes.</span><span class="sxs-lookup"><span data-stu-id="aecf9-121">Use of a session authentication token avoids the need to authenticate to the STS for each request, but it still means that many cookies are being sent over.</span></span> <span data-ttu-id="aecf9-122">Můžete chtít nastavit webové stránky tak, že důležitá data a prostředky jsou uloženy v chráněnou doménu při menší položky jsou uložené v doméně nechráněné a odkazované z hlavní webové stránky.</span><span class="sxs-lookup"><span data-stu-id="aecf9-122">You might want to set up the Web page so that the important data and resources are stored in the protected domain while minor items are stored in an unprotected domain and linked to from the main Web page.</span></span> <span data-ttu-id="aecf9-123">Také nastavte cestu k souboru cookie, chcete-li pouze chráněnou doménu.</span><span class="sxs-lookup"><span data-stu-id="aecf9-123">Also, set the cookie path to reference only the protected domain.</span></span>  
  
 <span data-ttu-id="aecf9-124">K provozu v režimu odkaz, Microsoft doporučuje poskytuje obslužnou rutinu pro <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated> událost v **global.asax.cs** souborů a nastavení **IsReferenceMode** předaná vlastnost na tokenu <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A> vlastnost.</span><span class="sxs-lookup"><span data-stu-id="aecf9-124">To operate in reference mode, Microsoft recommends providing a handler for the <xref:System.IdentityModel.Services.WSFederationAuthenticationModule.SessionSecurityTokenCreated> event in the **global.asax.cs** file and setting the **IsReferenceMode** property on the token passed in the <xref:System.IdentityModel.Services.SessionSecurityTokenCreatedEventArgs.SessionToken%2A> property.</span></span> <span data-ttu-id="aecf9-125">Tyto aktualizace zajišťují, že token relace pracuje v režimu odkaz pro každý požadavek a je podporuje přes nastavení jenom <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A> vlastnost modul relace ověřování.</span><span class="sxs-lookup"><span data-stu-id="aecf9-125">These updates will ensure that the session token operates in reference mode for every request and is favored over merely setting the  <xref:System.IdentityModel.Services.SessionAuthenticationModule.IsReferenceMode%2A> property on the Session Authentication Module.</span></span>  
  
## <a name="extensibility"></a><span data-ttu-id="aecf9-126">Rozšiřitelnost</span><span class="sxs-lookup"><span data-stu-id="aecf9-126">Extensibility</span></span>  
 <span data-ttu-id="aecf9-127">Můžete rozšířit mechanismus správy relace.</span><span class="sxs-lookup"><span data-stu-id="aecf9-127">You can extend the session management mechanism.</span></span> <span data-ttu-id="aecf9-128">Jedním z důvodů může být zlepšit výkon.</span><span class="sxs-lookup"><span data-stu-id="aecf9-128">One reason for this would be to improve the performance.</span></span> <span data-ttu-id="aecf9-129">Můžete například vytvořit vlastní soubor cookie obslužnou rutinu, která transformuje nebo optimalizuje token zabezpečení relace mezi jeho stav v paměti a co do souboru cookie.</span><span class="sxs-lookup"><span data-stu-id="aecf9-129">For example, you could create a custom cookie handler that transforms or optimizes the session security token between its in-memory state and what goes into the cookie.</span></span> <span data-ttu-id="aecf9-130">Chcete-li to provést, můžete nakonfigurovat <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=nameWithType> vlastnost <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=nameWithType> použít vlastní soubor cookie obslužnou rutinu, která je odvozena z <xref:System.IdentityModel.Services.CookieHandler?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="aecf9-130">To do so, you can configure the <xref:System.IdentityModel.Services.SessionAuthenticationModule.CookieHandler%2A?displayProperty=nameWithType> property of the <xref:System.IdentityModel.Services.SessionAuthenticationModule?displayProperty=nameWithType> to use a custom cookie handler that derives from <xref:System.IdentityModel.Services.CookieHandler?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aecf9-131"><xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=nameWithType>je výchozí popisovač souboru cookie, protože soubory cookie překročil povolenou velikost pro protokol HTTP (Hypertext Transfer); Pokud chcete místo toho použít vlastní soubor cookie obslužnou rutinu, je nutné implementovat rozdělování.</span><span class="sxs-lookup"><span data-stu-id="aecf9-131"><xref:System.IdentityModel.Services.ChunkedCookieHandler?displayProperty=nameWithType> is the default cookie handler because the cookies exceed the allowable size for Hypertext Transfer Protocol (HTTP); if you use a custom cookie handler instead, you must implement chunking.</span></span>  
  
 <span data-ttu-id="aecf9-132">Další informace najdete v tématu [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) ukázkové (http://go.microsoft.com/fwlink/?LinkID=248408).</span><span class="sxs-lookup"><span data-stu-id="aecf9-132">For more information, see [ClaimsAwareWebFarm](http://go.microsoft.com/fwlink/?LinkID=248408) (http://go.microsoft.com/fwlink/?LinkID=248408) sample.</span></span> <span data-ttu-id="aecf9-133">Tento příklad ukazuje mezipaměti připravené relace farmy (na rozdíl od tokenreplycache) tak, že používáte relací odkazem místo výměna big soubory cookie. Tento příklad také znázorňuje jednodušší způsob zabezpečení soubory cookie ve farmě.</span><span class="sxs-lookup"><span data-stu-id="aecf9-133">This sample shows a farm ready session cache (as opposed to a tokenreplycache) so that you can use sessions by reference instead of exchanging big cookies; this sample also demonstrates an easier way of securing cookies in a farm.</span></span> <span data-ttu-id="aecf9-134">Mezipaměť relace je založený na WCF.</span><span class="sxs-lookup"><span data-stu-id="aecf9-134">The session cache is WCF-based.</span></span> <span data-ttu-id="aecf9-135">S ohledem na relaci, zabezpečení ukázka představuje novou funkci ve verzi WIF 4.5 transformačního souboru cookie podle MachineKey, což může být aktivovaný jednoduše vložením odpovídající fragment kódu v souboru web.config. Ukázka samotné není "pronájem", ale ukazuje, co je potřeba pro vytvoření aplikace připravené pro farmy.</span><span class="sxs-lookup"><span data-stu-id="aecf9-135">With regard to session securing, the sample demonstrates a new capability in WIF 4.5 of a cookie transform based on MachineKey, which can be activated by simply pasting the appropriate snippet in the web.config. The sample itself is not "farmed", but it demonstrates what you need for making your app farm-ready.</span></span>