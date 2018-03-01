---
title: AutoResetEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 71933d0be804fdf68b0dc602902343f2d88b8c82
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="6a400-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="6a400-102">AutoResetEvent</span></span>
<span data-ttu-id="6a400-103">Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания.</span><span class="sxs-lookup"><span data-stu-id="6a400-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="6a400-104">Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="6a400-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="6a400-105">Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="6a400-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="6a400-106">Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="6a400-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="6a400-107">Если ожидающих потоков нет, состояние объекта события остается сигнальным.</span><span class="sxs-lookup"><span data-stu-id="6a400-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="6a400-108"><xref:System.Threading.AutoResetEvent> соответствует вызову Win32 `CreateEvent`, где указано значение `false` для аргумента `bManualReset`.</span><span class="sxs-lookup"><span data-stu-id="6a400-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="6a400-109">Пример использования <xref:System.Threading.AutoResetEvent> см. в описании [класса Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="6a400-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a400-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6a400-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="6a400-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="6a400-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="6a400-112">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="6a400-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="6a400-113">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="6a400-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="6a400-114">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="6a400-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
