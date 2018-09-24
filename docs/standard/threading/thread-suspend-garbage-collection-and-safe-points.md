---
title: Метод Thread.Suspend, сборка мусора и безопасные точки
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- suspending threads
- safe points
- threading [.NET Framework], suspending
- threading [.NET Framework], garbage collection
- garbage collection, threads
ms.assetid: e8f58e17-2714-4821-802a-f8eb3b2baa62
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc3af01167fe97b701bdb0c7bc37af02d8e8a77c
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46004183"
---
# <a name="threadsuspend-garbage-collection-and-safe-points"></a>Метод Thread.Suspend, сборка мусора и безопасные точки
Когда вы вызываете для потока <xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>, система фиксирует запрос на приостановку потока и позволяет ему продолжить работу до безопасной точки, а лишь затем выполняет приостановку. Безопасной точкой для потока считается такой этап выполнения, в котором можно безопасно выполнять сборку мусора.  
  
 После достижения безопасной точки среда выполнения гарантирует, что поток не выполняет никаких действий в управляемом коде. В потоке, выполняемом вне управляемого кода, всегда можно безопасно выполнить сборку мусора, поэтому его выполнение продолжается, пока он попытается возобновить выполнение управляемого кода.  
  
> [!NOTE]
>  Чтобы выполнить сборку мусора, среда выполнения приостанавливает все потоки, за исключением самого потока сборки мусора. Каждый поток должен достичь безопасной точки, чтобы его можно было приостановить.  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Thread>  
- <xref:System.GC>  
- [Работа с потоками](../../../docs/standard/threading/index.md)  
- [Автоматическое управление памятью](../../../docs/standard/automatic-memory-management.md)
