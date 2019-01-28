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
ms.openlocfilehash: f3e44b81b519bcae42c2e69eff46e73b1ae631a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490808"
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
