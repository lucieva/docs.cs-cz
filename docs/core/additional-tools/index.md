---
title: "Další nástroje .NET core"
description: "Přehled další nástroje, které podporují a rozšiřovat funkce .NET Core."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: eac67285500e62501f3bb552deaf5b07db609d4e
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/20/2018
---
# <a name="net-core-additional-tools"></a><span data-ttu-id="004c7-103">Další nástroje .NET core</span><span class="sxs-lookup"><span data-stu-id="004c7-103">.NET Core additional tools</span></span>
<span data-ttu-id="004c7-104">Tato část zkompiluje o seznam nástrojů, které podporují a rozšířit funkci .NET Core kromě [.NET Core rozhraní příkazového řádku (CLI)](..\tools\index.md) nástroje.</span><span class="sxs-lookup"><span data-stu-id="004c7-104">This section compiles a list of tools that support and extend the .NET Core functionality, in addition to the [.NET Core command-line interface (CLI)](..\tools\index.md) tools.</span></span>

### <a name="wcf-web-service-reference-toolwcf-web-service-reference-guidemd"></a>[<span data-ttu-id="004c7-105">Nástroj odkaz na službu WCF webu</span><span class="sxs-lookup"><span data-stu-id="004c7-105">WCF Web Service Reference Tool</span></span>](wcf-web-service-reference-guide.md)
<span data-ttu-id="004c7-106">Odkaz na službu WCF Web je poskytovatel připojené služby Visual Studio, který provedené v jeho debut [Visual Studio 2017 verze 15,5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span><span class="sxs-lookup"><span data-stu-id="004c7-106">The WCF Web Service Reference is a Visual Studio connected service provider that made its debut in [Visual Studio 2017 version 15.5](https://www.visualstudio.com/news/releasenotes/vs2017-relnotes#WCFTools).</span></span> <span data-ttu-id="004c7-107">Tento nástroj získává metadata z webové služby v aktuálním řešení v umístění v síti, nebo ze souboru WSDL a vytvoří soubor kompatibilní zdroj .NET Core obsahující kód proxy serveru klienta Windows Communication Foundation (WCF), který můžete použít pro přístup k webu Služba.</span><span class="sxs-lookup"><span data-stu-id="004c7-107">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

### <a name="xml-serializer-generatorxmlserializergenerator-instructionsmd"></a>[<span data-ttu-id="004c7-108">Generátor serializátor XML</span><span class="sxs-lookup"><span data-stu-id="004c7-108">XML Serializer Generator</span></span>](xmlserializergenerator-instructions.md)
<span data-ttu-id="004c7-109">Podobně jako [generátor serializátor Xml (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) pro rozhraní .NET Framework [balíček Microsoft.XmlSerializer.Generator NuGet](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) je řešení pro knihovny .NET Core a .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="004c7-109">Like the [Xml Serializer Generator (sgen.exe)](../../standard/serialization/xml-serializer-generator-tool-sgen-exe.md) for the .NET Framework, the [Microsoft.XmlSerializer.Generator NuGet package](https://www.nuget.org/packages/Microsoft.XmlSerializer.Generator) is the solution for .NET Core and .NET Standard libraries.</span></span> <span data-ttu-id="004c7-110">Vytvoří sestavení serializace XML pro typy, které jsou součástí sestavení, které chcete zvýšit výkon při spuštění serializace XML při serializaci nebo zrušte serializaci objektů těchto typů pomocí <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="004c7-110">It creates an XML serialization assembly for types contained in an assembly to improve the startup performance of XML serialization when serializing or de-serializing objects of those types using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>