---
title: "Основные и фоновые потоки"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="4de15-102">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="4de15-102">Foreground and Background Threads</span></span>
<span data-ttu-id="4de15-103">Управляемый поток может в фоновом потоке или основной поток.</span><span class="sxs-lookup"><span data-stu-id="4de15-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="4de15-104">Фоновые потоки идентичны основные потоки с одним исключением: фоновый поток не поддерживает хранение в управляемую среду выполнения под управлением.</span><span class="sxs-lookup"><span data-stu-id="4de15-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="4de15-105">После управляемого процесса (где файл .exe — это управляемая сборка) были остановлены все основные потоки, система останавливает все фоновые потоки и завершает работу.</span><span class="sxs-lookup"><span data-stu-id="4de15-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4de15-106">Когда среда выполнения останавливает фоновый поток, так как происходит отключение процесс, исключение не возникает в потоке.</span><span class="sxs-lookup"><span data-stu-id="4de15-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="4de15-107">Тем не менее, когда потоки остановлены, так как <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> метод выгрузка домена приложения, <xref:System.Threading.ThreadAbortException> исключение в потоках переднего плана и фона.</span><span class="sxs-lookup"><span data-stu-id="4de15-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="4de15-108">Используйте <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> свойств, чтобы определить, является ли поток фоновый рисунок или основной поток, либо для изменения его статуса.</span><span class="sxs-lookup"><span data-stu-id="4de15-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="4de15-109">Поток может изменяться в фоновый поток в любое время, задав его <xref:System.Threading.Thread.IsBackground%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="4de15-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4de15-110">Основной или фоновой состояние потока не влияет на результат необработанное исключение в потоке.</span><span class="sxs-lookup"><span data-stu-id="4de15-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="4de15-111">В платформе .NET Framework версии 2.0 необработанное исключение в обычном или фоновом режиме потоков приведет к завершению работы приложения.</span><span class="sxs-lookup"><span data-stu-id="4de15-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="4de15-112">В разделе [исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="4de15-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="4de15-113">Потоки, относящиеся к группе управляемых потоков (то есть потоки которого <xref:System.Threading.Thread.IsThreadPoolThread%2A> свойство `true`) — это фоновые потоки.</span><span class="sxs-lookup"><span data-stu-id="4de15-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="4de15-114">Все потоки, которые входят в управляемую среду выполнения из неуправляемого кода, помечаются как фоновые потоки.</span><span class="sxs-lookup"><span data-stu-id="4de15-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="4de15-115">Все потоки, созданные путем создания и запуска нового <xref:System.Threading.Thread> объекта, по умолчанию переднего плана.</span><span class="sxs-lookup"><span data-stu-id="4de15-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="4de15-116">При использовании потока для отслеживания деятельности, такие как подключения через сокет, задать его <xref:System.Threading.Thread.IsBackground%2A> свойства `true` , чтобы поток не запрещает процесс завершается.</span><span class="sxs-lookup"><span data-stu-id="4de15-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4de15-117">См. также</span><span class="sxs-lookup"><span data-stu-id="4de15-117">See Also</span></span>  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
