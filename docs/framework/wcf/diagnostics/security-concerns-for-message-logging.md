---
title: "Zajištění zabezpečení pro protokolování zpráv"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 21f513f2-815b-47f3-85a6-03c008510038
caps.latest.revision: "17"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 1f3d62e8b6771666dd3a55855ca0c5e41853f439
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="security-concerns-for-message-logging"></a><span data-ttu-id="e41f4-102">Zajištění zabezpečení pro protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="e41f4-102">Security Concerns for Message Logging</span></span>
<span data-ttu-id="e41f4-103">Toto téma popisuje, jak můžete chránit citlivá data vystavení v protokolů zpráv, jakož i událostí generovaných protokolování zpráv.</span><span class="sxs-lookup"><span data-stu-id="e41f4-103">This topic describes how you can protect sensitive data from being exposed in message logs, as well as events generated by message logging.</span></span>  
  
## <a name="security-concerns"></a><span data-ttu-id="e41f4-104">Aspekty zabezpečení</span><span class="sxs-lookup"><span data-stu-id="e41f4-104">Security Concerns</span></span>  
  
### <a name="logging-sensitive-information"></a><span data-ttu-id="e41f4-105">Protokolování citlivé informace.</span><span class="sxs-lookup"><span data-stu-id="e41f4-105">Logging Sensitive Information</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="e41f4-106">všechna data v záhlaví konkrétní aplikace a tělo nelze změnit.</span><span class="sxs-lookup"><span data-stu-id="e41f4-106"> does not modify any data in application-specific headers and body.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="e41f4-107">také nesleduje osobní údaje v záhlaví konkrétní aplikace a data textu.</span><span class="sxs-lookup"><span data-stu-id="e41f4-107"> also does not track personal information in application-specific headers or body data.</span></span>  
  
 <span data-ttu-id="e41f4-108">Když je povoleno protokolování zpráv, osobní údaje v hlavičkách specifické pro aplikace, jako je řetězec dotazu; a body informace, například číslo platební karty, se může stát viditelné v protokolech.</span><span class="sxs-lookup"><span data-stu-id="e41f4-108">When message logging is enabled, personal information in application-specific headers, such as, a query string; and body information, such as, a credit card number, can become visible in the logs.</span></span> <span data-ttu-id="e41f4-109">Nástroje pro nasazení aplikace je zodpovědná za prosadit řízení přístupu na soubory konfigurace a protokolu.</span><span class="sxs-lookup"><span data-stu-id="e41f4-109">The application deployer is responsible for enforcing access control on the configuration and log files.</span></span> <span data-ttu-id="e41f4-110">Pokud nechcete, aby tento druh informací viditelný, měli vypnout protokolování nebo odfiltrovat část dat, pokud chcete sdílet v protokolech.</span><span class="sxs-lookup"><span data-stu-id="e41f4-110">If you do not want this kind of information to be visible, you should disable logging, or filter out part of the data if you want to share the logs.</span></span>  
  
 <span data-ttu-id="e41f4-111">Následující tipy vám může pomoct zabránit neúmyslnému zveřejnění obsahu souboru protokolu:</span><span class="sxs-lookup"><span data-stu-id="e41f4-111">The following tips can help you to prevent the content of a log file from being exposed unintentionally:</span></span>  
  
-   <span data-ttu-id="e41f4-112">Zajistěte, aby v protokolu, které soubory jsou chráněné pomocí řízení přístupu jsou uvedené (ACL) v webového hostitele i scénáře hostování na vlastním serveru.</span><span class="sxs-lookup"><span data-stu-id="e41f4-112">Ensure that the log files are protected by Access Control Lists (ACL) both in Web-host and self-host scenarios.</span></span>  
  
-   <span data-ttu-id="e41f4-113">Zvolte příponu souboru, který nelze zpracovat snadno pomocí nějaké webové žádosti.</span><span class="sxs-lookup"><span data-stu-id="e41f4-113">Choose a file extension that cannot be easily served using a Web request.</span></span> <span data-ttu-id="e41f4-114">Například přípona souboru .xml není bezpečná volba.</span><span class="sxs-lookup"><span data-stu-id="e41f4-114">For example, the .xml file extension is not a safe choice.</span></span> <span data-ttu-id="e41f4-115">Můžete zkontrolovat v Průvodci správu Internetové informační služby (IIS) a podívejte se do seznamu přípon, které se dají obsluhovat.</span><span class="sxs-lookup"><span data-stu-id="e41f4-115">You can check the Internet Information Services (IIS) administration guide to see a list of extensions that can be served.</span></span>  
  
-   <span data-ttu-id="e41f4-116">Zadejte absolutní cestu k umístění souboru protokolu, které by měla být mimo webového hostitele vroot veřejné adresář, který chcete zabránit přistupuje externí strany pomocí webového prohlížeče.</span><span class="sxs-lookup"><span data-stu-id="e41f4-116">Specify an absolute path for the log file location, which should be outside of the Web host vroot public directory to prevent it from being accessed by an external party using a Web browser.</span></span>  
  
 <span data-ttu-id="e41f4-117">Ve výchozím nastavení klíče a identifikovatelné osobní údaje (PII), jako je například uživatelské jméno a heslo nejsou protokolovány v trasování a protokolovat zprávy.</span><span class="sxs-lookup"><span data-stu-id="e41f4-117">By default, keys and personally identifiable information (PII) such as username and password are not logged in traces and logged messages.</span></span> <span data-ttu-id="e41f4-118">Správce počítače, ale můžete použít `enableLoggingKnownPII` atribut `machineSettings` element tak, aby povolovala aplikace spuštěna v počítači do protokolu známé identifikovatelné osobní údaje (PII) v souboru Machine.config.</span><span class="sxs-lookup"><span data-stu-id="e41f4-118">A machine administrator, however, can use the `enableLoggingKnownPII` attribute in the `machineSettings` element of the Machine.config file to permit applications running on the machine to log known personally identifiable information (PII).</span></span> <span data-ttu-id="e41f4-119">Následující konfigurace ukazuje, jak to udělat:</span><span class="sxs-lookup"><span data-stu-id="e41f4-119">The following configuration demonstrates how to do this:</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel>  
      <machineSettings enableLoggingKnownPii="true"/>  
   </system.serviceModel>  
</configuration>   
```  
  
 <span data-ttu-id="e41f4-120">Pak můžete použít modul pro nasazení aplikace `logKnownPii` atribut v souboru App.config nebo Web.config povolení protokolování PII následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="e41f4-120">An application deployer can then use the `logKnownPii` attribute in either the App.config or Web.config file to enable PII logging as follows:</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
      <source name="System.ServiceModel.MessageLogging"  
        logKnownPii="true">  
        <listeners>  
                 <add name="messages"  
                 type="System.Diagnostics.XmlWriterTraceListener"  
                 initializeData="c:\logs\messages.svclog" />  
          </listeners>  
      </source>  
    </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="e41f4-121">Pouze, pokud jsou obě nastavení `true` je povoleno protokolování PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-121">Only when both settings are `true` is PII logging enabled.</span></span> <span data-ttu-id="e41f4-122">Kombinace dva přepínače umožňuje flexibilně protokolu známé PII pro každou aplikaci.</span><span class="sxs-lookup"><span data-stu-id="e41f4-122">The combination of two switches allows the flexibility to log known PII for each application.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e41f4-123">V [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] `logEntireMessage` a `logKnownPii` příznaky musí být také nastaven na `true` v souboru Web.config nebo v souboru App.config PII protokolování, tak, jak zobrazit v následujícím příkladu `<system.serviceModel><messageLogging logEntireMessage="true" logKnownPii="true" …`.</span><span class="sxs-lookup"><span data-stu-id="e41f4-123">In [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] the `logEntireMessage` and `logKnownPii` flags must also be set to `true` in the Web.config file or the App.config file to enable PII logging, as show in the following example `<system.serviceModel><messageLogging logEntireMessage="true" logKnownPii="true" …`.</span></span>  
  
 <span data-ttu-id="e41f4-124">Je třeba si uvědomit, že pokud zadáte dva nebo více vlastních zdrojů v konfiguračním souboru, se čtou jenom atributy první zdroje.</span><span class="sxs-lookup"><span data-stu-id="e41f4-124">You should be aware that if you specify two or more custom sources in a configuration file, only the attributes of the first source are read.</span></span> <span data-ttu-id="e41f4-125">Další se ignorují.</span><span class="sxs-lookup"><span data-stu-id="e41f4-125">The others are ignored.</span></span> <span data-ttu-id="e41f4-126">To znamená, že pro následující App.config souboru PII se neprotokolují pro oba zdroje i když druhý zdroj je výslovně povoleno protokolování PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-126">This means that, for the following App.config, file, PII is not logged for both sources even though PII logging is explicitly enabled for the second source.</span></span>  
  
```xml  
<system.diagnostics>  
   <sources>  
      <source name="System.ServiceModel.MessageLogging"  
              logKnownPii="false">  
              <listeners>  
                 <add name="messages"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\messages.svclog" />  
              </listeners>  
            </source>  
      <source name="System.ServiceModel"   
              logKnownPii="true">  
              <listeners>  
                 <add name="traces"  
                      type="System.Diagnostics.XmlWriterTraceListener"  
                      initializeData="c:\logs\traces.svclog" />  
              </listeners>  
      </source>  
   </sources>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="e41f4-127">Pokud `<machineSettings enableLoggingKnownPii="Boolean"/>` element existuje mimo souboru Machine.config, vyvolá systému <xref:System.Configuration.ConfigurationErrorsException>.</span><span class="sxs-lookup"><span data-stu-id="e41f4-127">If the `<machineSettings enableLoggingKnownPii="Boolean"/>` element exists outside the Machine.config file, the system throws a <xref:System.Configuration.ConfigurationErrorsException>.</span></span>  
  
 <span data-ttu-id="e41f4-128">Změny jsou platné jenom v případě, že spuštění nebo restartování aplikace.</span><span class="sxs-lookup"><span data-stu-id="e41f4-128">The changes are effective only when the application starts or restarts.</span></span> <span data-ttu-id="e41f4-129">Při spuštění se zaprotokoluje událost, když oba atributy jsou nastaveny na `true`.</span><span class="sxs-lookup"><span data-stu-id="e41f4-129">An event is logged at startup when both attributes are set to `true`.</span></span> <span data-ttu-id="e41f4-130">Pokud se taky zaznamená událost `logKnownPii` je nastaven na `true` ale `enableLoggingKnownPii` je `false`.</span><span class="sxs-lookup"><span data-stu-id="e41f4-130">An event is also logged if `logKnownPii` is set to `true` but `enableLoggingKnownPii` is `false`.</span></span>  
  
 <span data-ttu-id="e41f4-131">Správce počítače a nástroje pro nasazení aplikace by měla vykonávat extrémně opatrní při používání těchto dva přepínače.</span><span class="sxs-lookup"><span data-stu-id="e41f4-131">The machine administrator and application deployer should exercise extreme caution when using these two switches.</span></span> <span data-ttu-id="e41f4-132">Pokud je povoleno protokolování PII, jsou protokolovány zabezpečení klíčů a PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-132">If PII logging is enabled, security keys and PII are logged.</span></span> <span data-ttu-id="e41f4-133">Pokud je zakázaná, specifické pro aplikaci a citlivá data protokolovány v záhlaví zprávy a obsah.</span><span class="sxs-lookup"><span data-stu-id="e41f4-133">If it is disabled, sensitive and application-specific data is still logged in message headers and bodies.</span></span> <span data-ttu-id="e41f4-134">Podrobnější informace o ochranu osobních údajů a ochrana PII vystavení, naleznete v [ochraně osobních údajů uživatelů](http://go.microsoft.com/fwlink/?LinkID=94647).</span><span class="sxs-lookup"><span data-stu-id="e41f4-134">For a more thorough discussion about privacy and protecting PII from being exposed, see [User Privacy](http://go.microsoft.com/fwlink/?LinkID=94647).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e41f4-135">V poškozených zpráv není skryté PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-135">PII is not hidden in malformed messages.</span></span> <span data-ttu-id="e41f4-136">Například messaged se zaznamenávají jako-je bez nutnosti jakékoli úpravy.</span><span class="sxs-lookup"><span data-stu-id="e41f4-136">Such messaged are logged as-is without any modification.</span></span> <span data-ttu-id="e41f4-137">Atributy uvedeno dříve mít žádný vliv na to.</span><span class="sxs-lookup"><span data-stu-id="e41f4-137">Attributes mentioned previously have no effect on this.</span></span>  
  
### <a name="custom-trace-listener"></a><span data-ttu-id="e41f4-138">Vlastní naslouchací</span><span class="sxs-lookup"><span data-stu-id="e41f4-138">Custom Trace Listener</span></span>  
 <span data-ttu-id="e41f4-139">Přidání vlastní naslouchací na protokolování zpráv zdroj trasování je oprávnění, která by měla být omezeno na správce.</span><span class="sxs-lookup"><span data-stu-id="e41f4-139">Adding a custom trace listener on the Message Logging trace source is a privilege that should be restricted to the administrator.</span></span> <span data-ttu-id="e41f4-140">Důvodem je, že škodlivý vlastní naslouchací procesy je možné nakonfigurovat na odesílání zpráv vzdáleně, což vede k citlivým informacím.</span><span class="sxs-lookup"><span data-stu-id="e41f4-140">This is because malicious custom listeners can be configured to send messages remotely, which leads to sensitive information disclosure.</span></span> <span data-ttu-id="e41f4-141">Kromě toho pokud nakonfigurujete vlastní naslouchací proces pro odesílání zpráv v drátové síti, jako je třeba pro vzdálenou databázi, by měl vynutit řízení správné přístupu na protokolů zpráv ve vzdáleném počítači.</span><span class="sxs-lookup"><span data-stu-id="e41f4-141">In addition, if you configure a custom listener to send messages on the wire, such as, to a remote database, you should enforce proper access control on the message logs in the remote machine.</span></span>  
  
## <a name="events-triggered-by-message-logging"></a><span data-ttu-id="e41f4-142">Události aktivované protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="e41f4-142">Events Triggered by Message Logging</span></span>  
 <span data-ttu-id="e41f4-143">V následujícím seznamu uvedeny všechny události vysílaných protokolování zpráv.</span><span class="sxs-lookup"><span data-stu-id="e41f4-143">The following lists all the events emitted by message logging.</span></span>  
  
-   <span data-ttu-id="e41f4-144">Zpráva přihlašování: Tato událost je vygenerované, pokud je povoleno protokolování zpráv v konfiguraci, nebo prostřednictvím rozhraní WMI.</span><span class="sxs-lookup"><span data-stu-id="e41f4-144">Message logging on: This event is emitted when message logging is enabled in configuration, or through WMI.</span></span> <span data-ttu-id="e41f4-145">Obsah této události je "zpráva protokolování je zapnutý.</span><span class="sxs-lookup"><span data-stu-id="e41f4-145">The content of the event is "Message logging has been turned on.</span></span> <span data-ttu-id="e41f4-146">Citlivé informace může být zaznamenána ve formátu prostého textu, i v případě, že byly šifrované v drátové síti, například obsah zpráv."</span><span class="sxs-lookup"><span data-stu-id="e41f4-146">Sensitive information may be logged in clear text, even if they were encrypted on the wire, for example, message bodies."</span></span>  
  
-   <span data-ttu-id="e41f4-147">Zpráva odhlašování: Tato událost je vygenerované při protokolování zpráv je zakázán prostřednictvím rozhraní WMI.</span><span class="sxs-lookup"><span data-stu-id="e41f4-147">Message logging off: This event is emitted when message logging is disabled through WMI.</span></span> <span data-ttu-id="e41f4-148">Obsah této události je "Zpráva protokolování vypnuté."</span><span class="sxs-lookup"><span data-stu-id="e41f4-148">The content of the event is "Message logging has been turned off."</span></span>  
  
-   <span data-ttu-id="e41f4-149">Protokol známé PII na: Tato událost je vygenerované, pokud je povoleno protokolování známé PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-149">Log Known PII On: This event is emitted when logging of known PII is enabled.</span></span> <span data-ttu-id="e41f4-150">K tomu dojde při `enableLoggingKnownPii` atribut `machineSettings` element souboru Machine.config je nastaven na `true`a `logKnownPii` atribut `source` element v souboru App.config nebo Web.config je nastaven na hodnotu `true`.</span><span class="sxs-lookup"><span data-stu-id="e41f4-150">This happens when the `enableLoggingKnownPii` attribute in the `machineSettings` element of the Machine.config file is set to `true`, and the `logKnownPii` attribute of the `source` element in either the App.config or Web.config file is set to `true`.</span></span>  
  
-   <span data-ttu-id="e41f4-151">Protokolu známé PII nejsou povoleny: Tato událost je vygenerované, pokud není povoleno protokolování známé PII.</span><span class="sxs-lookup"><span data-stu-id="e41f4-151">Log Known PII Not Allowed: This event is emitted when logging of known PII is not allowed.</span></span> <span data-ttu-id="e41f4-152">K tomu dojde při `logKnownPii` atribut `source` element v souboru App.config nebo Web.config je nastaven na hodnotu `true`, ale `enableLoggingKnownPii` atribut `machineSettings` element souboru Machine.config je nastaven na `false`.</span><span class="sxs-lookup"><span data-stu-id="e41f4-152">This happens when the `logKnownPii` attribute of the `source` element in either the App.config or Web.config file is set to `true`, but the `enableLoggingKnownPii` attribute in the `machineSettings` element of the Machine.config file is set to `false`.</span></span> <span data-ttu-id="e41f4-153">Nedojde k výjimce.</span><span class="sxs-lookup"><span data-stu-id="e41f4-153">No exception is thrown.</span></span>  
  
 <span data-ttu-id="e41f4-154">Tyto události lze zobrazit v nástroji Prohlížeč událostí, která se dodává s Windows.</span><span class="sxs-lookup"><span data-stu-id="e41f4-154">These events can be viewed in the Event Viewer tool that comes with Windows.</span></span> <span data-ttu-id="e41f4-155">Další informace najdete v tématu [protokolování událostí](../../../../docs/framework/wcf/diagnostics/event-logging/index.md).</span><span class="sxs-lookup"><span data-stu-id="e41f4-155">For more information on this, see [Event Logging](../../../../docs/framework/wcf/diagnostics/event-logging/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e41f4-156">Viz také</span><span class="sxs-lookup"><span data-stu-id="e41f4-156">See Also</span></span>  
 [<span data-ttu-id="e41f4-157">Protokolování zpráv</span><span class="sxs-lookup"><span data-stu-id="e41f4-157">Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/message-logging.md)  
 [<span data-ttu-id="e41f4-158">Otázky zabezpečení a užitečné tipy pro trasování</span><span class="sxs-lookup"><span data-stu-id="e41f4-158">Security Concerns and Useful Tips for Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)