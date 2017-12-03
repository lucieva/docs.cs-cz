---
title: "Základní komunikace: Přenosové kanály pojmenovaného kanálu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 14ab8f84-ab3e-47cd-8ac5-dd68af940175
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31e10bade2b467b01b47f01f894fee438f523e44
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="core-communications-named-pipe-transport-channels"></a><span data-ttu-id="18a36-102">Základní komunikace: Přenosové kanály pojmenovaného kanálu</span><span class="sxs-lookup"><span data-stu-id="18a36-102">Core Communications: Named Pipe Transport Channels</span></span>
<span data-ttu-id="18a36-103">Toto téma uvádí všechny výjimky generované přenosové kanály pojmenovaný kanál.</span><span class="sxs-lookup"><span data-stu-id="18a36-103">This topic lists all exceptions generated by the Named Pipe Transport Channels.</span></span>  
  
## <a name="exception-list"></a><span data-ttu-id="18a36-104">Seznam výjimek</span><span class="sxs-lookup"><span data-stu-id="18a36-104">Exception List</span></span>  
  
|<span data-ttu-id="18a36-105">Kód prostředku</span><span class="sxs-lookup"><span data-stu-id="18a36-105">Resource Code</span></span>|<span data-ttu-id="18a36-106">Řetězec prostředku</span><span class="sxs-lookup"><span data-stu-id="18a36-106">Resource String</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="18a36-107">PipeCantCloseWithPendingWrite</span><span class="sxs-lookup"><span data-stu-id="18a36-107">PipeCantCloseWithPendingWrite</span></span>|<span data-ttu-id="18a36-108">Kanálu nelze uzavřít během operace zápisu do kanálu čeká na vyřízení.</span><span class="sxs-lookup"><span data-stu-id="18a36-108">The pipe cannot be closed while a write operation to the pipe is pending.</span></span>|  
|<span data-ttu-id="18a36-109">PipeReadPending</span><span class="sxs-lookup"><span data-stu-id="18a36-109">PipeReadPending</span></span>|<span data-ttu-id="18a36-110">Operace čtení probíhá u tohoto kanálu.</span><span class="sxs-lookup"><span data-stu-id="18a36-110">A read operation is in progress for the pipe.</span></span>|  
|<span data-ttu-id="18a36-111">PipeShutdownReadError</span><span class="sxs-lookup"><span data-stu-id="18a36-111">PipeShutdownReadError</span></span>|<span data-ttu-id="18a36-112">Operace čtení ukazatele kanálu 'vypnutí' se nezdařilo.</span><span class="sxs-lookup"><span data-stu-id="18a36-112">The read operation of the pipe 'shutdown' indicator failed.</span></span>|  
|<span data-ttu-id="18a36-113">PipeShutdownWriteError</span><span class="sxs-lookup"><span data-stu-id="18a36-113">PipeShutdownWriteError</span></span>|<span data-ttu-id="18a36-114">Operace zápisu indikátoru, vypnutí' kanálu se nezdařila.</span><span class="sxs-lookup"><span data-stu-id="18a36-114">The write operation of the pipe 'shutdown' indicator failed.</span></span>|  
|<span data-ttu-id="18a36-115">PipeWritePending</span><span class="sxs-lookup"><span data-stu-id="18a36-115">PipeWritePending</span></span>|<span data-ttu-id="18a36-116">Operace zápisu probíhá u tohoto kanálu.</span><span class="sxs-lookup"><span data-stu-id="18a36-116">A write operation is in progress for the pipe.</span></span>|