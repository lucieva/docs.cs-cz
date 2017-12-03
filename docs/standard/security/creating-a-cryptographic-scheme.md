---
title: "Vytváření šifrovacích schémat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e3c4a832f70fae7808bf71016cb9f6648332f01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="90bec-102">Vytváření šifrovacích schémat</span><span class="sxs-lookup"><span data-stu-id="90bec-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="90bec-103">K vytvoření různých schémat k šifrování a dešifrování dat mohou být kombinovány kryptografické součásti rozhraní .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90bec-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="90bec-104">Jednoduchý kryptografických sloužící k šifrování a dešifrování dat může určit následující kroky:</span><span class="sxs-lookup"><span data-stu-id="90bec-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="90bec-105">Každá strana vygeneruje pár veřejného a privátního klíče.</span><span class="sxs-lookup"><span data-stu-id="90bec-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="90bec-106">Strany vyměňují své veřejné klíče.</span><span class="sxs-lookup"><span data-stu-id="90bec-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="90bec-107">Každá strana vygeneruje tajný klíč pro šifrování TripleDES, například a nově vytvořený klíč zašifruje pomocí veřejného klíče druhé strany.</span><span class="sxs-lookup"><span data-stu-id="90bec-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="90bec-108">Každá strana odesílá data na druhý a kombinují jiný tajný klíč s vlastní, v konkrétní pořadí, chcete-li vytvořit nový tajný klíč.</span><span class="sxs-lookup"><span data-stu-id="90bec-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="90bec-109">Strany poté zahájit konverzaci pomocí symetrického šifrování.</span><span class="sxs-lookup"><span data-stu-id="90bec-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="90bec-110">Vytvoření kryptografických schémat není jednoduchý úkol.</span><span class="sxs-lookup"><span data-stu-id="90bec-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="90bec-111">Další informace o používání šifrování najdete v tématu Kryptografie v dokumentaci platformy sady SDK na http://msdn.microsoft.com/library.</span><span class="sxs-lookup"><span data-stu-id="90bec-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90bec-112">Viz také</span><span class="sxs-lookup"><span data-stu-id="90bec-112">See Also</span></span>  
 [<span data-ttu-id="90bec-113">Kryptografické služby</span><span class="sxs-lookup"><span data-stu-id="90bec-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)