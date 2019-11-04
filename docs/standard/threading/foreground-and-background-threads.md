---
title: Основные и фоновые потоки
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
ms.openlocfilehash: 9e93f07b3b84264373db0317919b6ee519c8127c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138055"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="28809-102">Основные и фоновые потоки</span><span class="sxs-lookup"><span data-stu-id="28809-102">Foreground and Background Threads</span></span>
<span data-ttu-id="28809-103">Управляемый поток может быть основным или фоновым.</span><span class="sxs-lookup"><span data-stu-id="28809-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="28809-104">Фоновые потоки отличаются от основных только в одном аспекте: фоновый поток не поддерживает работу управляемой среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="28809-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="28809-105">После того, как в управляемом процессе (где управляемой сборкой является файл EXE) остановятся все основные потоки, система принудительно останавливает все фоновые потоки и завершает работу процесса.</span><span class="sxs-lookup"><span data-stu-id="28809-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="28809-106">Когда в среде выполнения останавливается фоновый поток из-за завершения работы процесса, исключение в потоке не возникает.</span><span class="sxs-lookup"><span data-stu-id="28809-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="28809-107">Но если потоки останавливаются из-за выгрузки домена приложения в методе <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType>, во всех основных и фоновых потоках создается исключение <xref:System.Threading.ThreadAbortException>.</span><span class="sxs-lookup"><span data-stu-id="28809-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="28809-108">Свойство <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> позволяет определить, является ли поток основным или фоновым, а также изменить его статус.</span><span class="sxs-lookup"><span data-stu-id="28809-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="28809-109">Поток можно в любой момент сделать фоновым, задав в нем для свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="28809-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="28809-110">Основное или фоновое состояние потока не влияет на поведение необработанного исключения в потоке.</span><span class="sxs-lookup"><span data-stu-id="28809-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="28809-111">На платформе .NET Framework версии 2.0 необработанное исключение в основном или фоновом потоке приведет к завершению работы приложения.</span><span class="sxs-lookup"><span data-stu-id="28809-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="28809-112">См. также [Исключения в управляемых потоках](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span><span class="sxs-lookup"><span data-stu-id="28809-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="28809-113">Потоки, входящие в пул управляемых потоков (то есть потоки, в которых для свойства <xref:System.Threading.Thread.IsThreadPoolThread%2A> задано значение `true`), считаются фоновыми потоками.</span><span class="sxs-lookup"><span data-stu-id="28809-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="28809-114">Все потоки, которые включаются в управляемую среду выполнения из неуправляемого кода, помечаются как фоновые потоки.</span><span class="sxs-lookup"><span data-stu-id="28809-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="28809-115">Все потоки, созданные путем создания и запуска нового объекта <xref:System.Threading.Thread>, по умолчанию становятся основными потоками.</span><span class="sxs-lookup"><span data-stu-id="28809-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="28809-116">Если у вас есть поток, который отслеживает некоторое действие, например подключение через сокет, установите для его свойства <xref:System.Threading.Thread.IsBackground%2A> значение `true`, чтобы этот поток не мешал завершить процесс.</span><span class="sxs-lookup"><span data-stu-id="28809-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28809-117">См. также</span><span class="sxs-lookup"><span data-stu-id="28809-117">See also</span></span>

- <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>
- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadAbortException>
