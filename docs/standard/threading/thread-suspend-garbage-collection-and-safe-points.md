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
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e47674ef8d1b1a7487e42765bcbce4b33cf98769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Метод Thread.Suspend, сборка мусора и безопасные точки
При вызове <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType> в потоке, система сообщает о был запрошен и позволяет потоку выполняться, пока он достигнет безопасной точки поступившем приостановку потока. Безопасные точки для потока является точкой, в ходе выполнения, на какие сборки мусора могут выполняться коллекции.  
  
 После достижения безопасной точки среды выполнения гарантирует, что поток не будет выполнять продолжить работу в управляемом коде. Поток выполняется вне управляемого кода всегда безопасно для сборки мусора, и его выполнение продолжается, пока он попытается возобновить выполнение управляемого кода.  
  
> [!NOTE]
>  Чтобы выполнить сборку мусора, среде выполнения необходимо приостановить все потоки, за исключением потока, отвечающего коллекции. Каждый поток должен достичь безопасной точки, прежде чем можно будет приостановить.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.Thread>  
 <xref:System.GC>  
 [Работа с потоками](../../../docs/standard/threading/index.md)  
 [Автоматическое управление памятью](../../../docs/standard/automatic-memory-management.md)
