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
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69d16e8c6491b4c66ab5a5452762e73172ebbb77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="autoresetevent"></a><span data-ttu-id="6e944-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="6e944-102">AutoResetEvent</span></span>
<span data-ttu-id="6e944-103"><xref:System.Threading.AutoResetEvent> Класс представляет событие дескриптора ожидания, которое сбрасывается автоматически при получении сигнала после освобождения одного ожидающего потока.</span><span class="sxs-lookup"><span data-stu-id="6e944-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="6e944-104">Этот класс представляет специальное использование базового класса, <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="6e944-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="6e944-105">Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="6e944-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="6e944-106"><xref:System.Threading.AutoResetEvent> Сбрасывается автоматически несигнальное системой после выпуска одного ожидающего потока.</span><span class="sxs-lookup"><span data-stu-id="6e944-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="6e944-107">Если ожидающих потоков нет, состояние объекта события остается сигнальным.</span><span class="sxs-lookup"><span data-stu-id="6e944-107">If no threads are waiting, the event object's state remains signaled.</span></span> <span data-ttu-id="6e944-108"><xref:System.Threading.AutoResetEvent>соответствует Win32 `CreateEvent` вызвать, указав `false` для `bManualReset` аргумент.</span><span class="sxs-lookup"><span data-stu-id="6e944-108"><xref:System.Threading.AutoResetEvent> corresponds to a Win32 `CreateEvent` call, specifying `false` for the `bManualReset` argument.</span></span>  
  
 <span data-ttu-id="6e944-109">Пример, использующий <xref:System.Threading.AutoResetEvent>, в разделе [монитора](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span><span class="sxs-lookup"><span data-stu-id="6e944-109">For an example that uses <xref:System.Threading.AutoResetEvent>, see [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e944-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6e944-110">See Also</span></span>  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [<span data-ttu-id="6e944-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="6e944-111">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [<span data-ttu-id="6e944-112">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="6e944-112">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="6e944-113">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="6e944-113">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
 [<span data-ttu-id="6e944-114">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="6e944-114">Wait Handles</span></span>](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
