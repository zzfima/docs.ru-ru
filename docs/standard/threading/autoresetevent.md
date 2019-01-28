---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70af739bdb90a70a1319354b4964c261e432912b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54729961"
---
# <a name="autoresetevent"></a><span data-ttu-id="7b8e6-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="7b8e6-102">AutoResetEvent</span></span>
<span data-ttu-id="7b8e6-103">Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания.</span><span class="sxs-lookup"><span data-stu-id="7b8e6-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="7b8e6-104">Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="7b8e6-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="7b8e6-105">Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="7b8e6-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="7b8e6-106">Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="7b8e6-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="7b8e6-107">Если ожидающих потоков нет, состояние объекта события остается сигнальным.</span><span class="sxs-lookup"><span data-stu-id="7b8e6-107">If no threads are waiting, the event object's state remains signaled.</span></span>
  
 <span data-ttu-id="7b8e6-108">Пример использования <xref:System.Threading.AutoResetEvent> см. в разделе <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="7b8e6-108">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b8e6-109">См. также</span><span class="sxs-lookup"><span data-stu-id="7b8e6-109">See also</span></span>

- <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType>
- <xref:System.Threading.WaitHandle?displayProperty=nameWithType>
- [<span data-ttu-id="7b8e6-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="7b8e6-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)
- [<span data-ttu-id="7b8e6-111">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="7b8e6-111">Threading objects and features</span></span>](threading-objects-and-features.md)
- [<span data-ttu-id="7b8e6-112">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="7b8e6-112">Threading</span></span>](index.md)
