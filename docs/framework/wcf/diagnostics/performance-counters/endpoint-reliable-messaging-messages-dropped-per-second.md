---
title: 'Koncový bod: Počet zrušených spolehlivých zpráv za sekundu'
ms.date: 03/30/2017
ms.assetid: ea3c4fc0-1e0f-4863-8879-57bc6c113018
ms.openlocfilehash: 8f935bee06d175ce454bd7f58a1afbbe9ab505ad
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863501"
---
# <a name="endpoint-reliable-messaging-messages-dropped-per-second"></a>Koncový bod: Počet zrušených spolehlivých zpráv za sekundu
Název čítače: Relací spolehlivého zasílání zpráv za sekundu.  
  
## <a name="description"></a>Popis  
 Celkový počet spolehlivého zasílání zpráv, které byly vynechány v tomto koncovém bodu za sekundu.  
  
 Tento čítač je typ čítače výkonu [PERF_COUNTER_COUNTER](https://go.microsoft.com/fwlink/?LinkID=94649), jehož hodnota je vypočítána pomocí tohoto vzorce.  
  
 (N 1 - N 0) / ((D 1 - D 0) / F)
