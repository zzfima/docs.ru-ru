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
ms.openlocfilehash: 38efbe0ecd88c02752d610de4b1eec8b62eca1f8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2018
ms.locfileid: "46937553"
---
# <a name="autoresetevent"></a><span data-ttu-id="9ec73-102">AutoResetEvent</span><span class="sxs-lookup"><span data-stu-id="9ec73-102">AutoResetEvent</span></span>
<span data-ttu-id="9ec73-103">Класс <xref:System.Threading.AutoResetEvent> предоставляет событие локального дескриптора ожидания, которое автоматически сбрасывается после создания, освободив один поток ожидания.</span><span class="sxs-lookup"><span data-stu-id="9ec73-103">The <xref:System.Threading.AutoResetEvent> class represents a local wait handle event that resets automatically when signaled, after releasing a single waiting thread.</span></span> <span data-ttu-id="9ec73-104">Этот класс представляет отдельный сценарий применения базового класса <xref:System.Threading.EventWaitHandle>.</span><span class="sxs-lookup"><span data-stu-id="9ec73-104">This class represents a special case of its base class, <xref:System.Threading.EventWaitHandle>.</span></span> <span data-ttu-id="9ec73-105">Основную документацию по использованию и функциональным возможностям событий автоматического сброса см. в разделе [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).</span><span class="sxs-lookup"><span data-stu-id="9ec73-105">See the [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md) conceptual documentation for the use and features of automatic reset events.</span></span>  
  
 <span data-ttu-id="9ec73-106">Освободив один поток в состоянии ожидания, система автоматически сбрасывает сигнальное состояние объекта <xref:System.Threading.AutoResetEvent>.</span><span class="sxs-lookup"><span data-stu-id="9ec73-106">An <xref:System.Threading.AutoResetEvent> object is automatically reset to non-signaled by the system after a single waiting thread has been released.</span></span> <span data-ttu-id="9ec73-107">Если ожидающих потоков нет, состояние объекта события остается сигнальным.</span><span class="sxs-lookup"><span data-stu-id="9ec73-107">If no threads are waiting, the event object's state remains signaled.</span></span>
  
 <span data-ttu-id="9ec73-108">Пример использования <xref:System.Threading.AutoResetEvent> см. в разделе <xref:System.Threading.Monitor>.</span><span class="sxs-lookup"><span data-stu-id="9ec73-108">For an example that uses <xref:System.Threading.AutoResetEvent>, see <xref:System.Threading.Monitor>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec73-109">См. также</span><span class="sxs-lookup"><span data-stu-id="9ec73-109">See also</span></span>

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [<span data-ttu-id="9ec73-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span><span class="sxs-lookup"><span data-stu-id="9ec73-110">EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent</span></span>](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [<span data-ttu-id="9ec73-111">Работа с потоками</span><span class="sxs-lookup"><span data-stu-id="9ec73-111">Threading</span></span>](../../../docs/standard/threading/index.md)  
- [<span data-ttu-id="9ec73-112">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="9ec73-112">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)  
- [<span data-ttu-id="9ec73-113">Дескрипторы ожидания</span><span class="sxs-lookup"><span data-stu-id="9ec73-113">Wait Handles</span></span>](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
