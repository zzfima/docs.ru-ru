---
title: "Метод Thread.Suspend, сборка мусора и безопасные точки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fdd56763712dee9c6fa1f292eb3bbb2f0ccbf505
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Метод Thread.Suspend, сборка мусора и безопасные точки
Когда вы вызываете для потока <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>, система фиксирует запрос на приостановку потока и позволяет ему продолжить работу до безопасной точки, а лишь затем выполняет приостановку. Безопасной точкой для потока считается такой этап выполнения, в котором можно безопасно выполнять сборку мусора.  
  
 После достижения безопасной точки среда выполнения гарантирует, что поток не выполняет никаких действий в управляемом коде. В потоке, выполняемом вне управляемого кода, всегда можно безопасно выполнить сборку мусора, поэтому его выполнение продолжается, пока он попытается возобновить выполнение управляемого кода.  
  
> [!NOTE]
>  Чтобы выполнить сборку мусора, среда выполнения приостанавливает все потоки, за исключением самого потока сборки мусора. Каждый поток должен достичь безопасной точки, чтобы его можно было приостановить.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Автоматическое управление памятью](../../../docs/standard/automatic-memory-management.md)
