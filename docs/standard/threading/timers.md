---
title: Таймеры
description: Узнайте, какие таймеры .NET можно использовать в многопоточной среде.
ms.date: 07/03/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: d7d1fa13b02fe7425fa9b4cb81ba20297a23fe4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "73128955"
---
# <a name="timers"></a><span data-ttu-id="e69a2-103">Таймеры</span><span class="sxs-lookup"><span data-stu-id="e69a2-103">Timers</span></span>

<span data-ttu-id="e69a2-104">.NET предоставляет два таймера, которые можно использовать в многопоточной среде:</span><span class="sxs-lookup"><span data-stu-id="e69a2-104">.NET provides two timers to use in a multithreaded environment:</span></span>

- <span data-ttu-id="e69a2-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, который выполняет метод одного обратного вызова в потоке <xref:System.Threading.ThreadPool> с регулярными интервалами.</span><span class="sxs-lookup"><span data-stu-id="e69a2-105"><xref:System.Threading.Timer?displayProperty=nameWithType>, which executes a single callback method on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>
- <span data-ttu-id="e69a2-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, который по умолчанию порождает событие в потоке <xref:System.Threading.ThreadPool> с регулярными интервалами.</span><span class="sxs-lookup"><span data-stu-id="e69a2-106"><xref:System.Timers.Timer?displayProperty=nameWithType>, which by default raises an event on a <xref:System.Threading.ThreadPool> thread at regular intervals.</span></span>

> [!NOTE]
> <span data-ttu-id="e69a2-107">В некоторых реализациях .NET может содержать дополнительные таймеры:</span><span class="sxs-lookup"><span data-stu-id="e69a2-107">Some .NET implementations may include additional timers:</span></span>
>
> - <span data-ttu-id="e69a2-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType> — компонент Windows Forms, который вызывает событие через определенные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="e69a2-108"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: a Windows Forms component that fires an event at regular intervals.</span></span> <span data-ttu-id="e69a2-109">У этого компонента нет интерфейса пользователя. Он предназначен для однопоточной среды.</span><span class="sxs-lookup"><span data-stu-id="e69a2-109">The component has no user interface and is designed for use in a single-threaded environment.</span></span>  
> - <span data-ttu-id="e69a2-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType> — компонент ASP.NET, который выполняет асинхронную или синхронную обратную передачу веб-страницы с регулярными интервалами.</span><span class="sxs-lookup"><span data-stu-id="e69a2-110"><xref:System.Web.UI.Timer?displayProperty=nameWithType>: an ASP.NET component that performs asynchronous or synchronous web page postbacks at a regular interval.</span></span>
> - <span data-ttu-id="e69a2-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType> — таймер, интегрированный в очередь <xref:System.Windows.Threading.Dispatcher>, которая обрабатывается с заданными интервалом и приоритетом.</span><span class="sxs-lookup"><span data-stu-id="e69a2-111"><xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: a timer that is integrated into the <xref:System.Windows.Threading.Dispatcher> queue which is processed at a specified interval of time and at a specified priority.</span></span>

## <a name="the-systemthreadingtimer-class"></a><span data-ttu-id="e69a2-112">Класс System.Threading.Timer</span><span class="sxs-lookup"><span data-stu-id="e69a2-112">The System.Threading.Timer class</span></span>

<span data-ttu-id="e69a2-113">Класс <xref:System.Threading.Timer?displayProperty=nameWithType> позволяет непрерывно вызывать делегат через определенные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="e69a2-113">The <xref:System.Threading.Timer?displayProperty=nameWithType> class enables you to continuously call a delegate at specified time intervals.</span></span> <span data-ttu-id="e69a2-114">Этот класс также можно использовать для планирования одного вызова к делегату через заданный интервал времени.</span><span class="sxs-lookup"><span data-stu-id="e69a2-114">You also can use this class to schedule a single call to a delegate in a specified time interval.</span></span> <span data-ttu-id="e69a2-115">Делегат выполняется в потоке <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-115">The delegate is executed on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="e69a2-116">При создании объекта <xref:System.Threading.Timer?displayProperty=nameWithType> вы указываете делегат <xref:System.Threading.TimerCallback>, который определяет метод обратного вызова, необязательный объект состояния, который передается обратному вызову, временную задержку до первого вызова обратного вызова и интервал времени между вызовами обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e69a2-116">When you create a <xref:System.Threading.Timer?displayProperty=nameWithType> object, you specify a <xref:System.Threading.TimerCallback> delegate that defines the callback method, an optional state object that is passed to the callback, the amount of time to delay before the first invocation of the callback, and the time interval between callback invocations.</span></span> <span data-ttu-id="e69a2-117">Чтобы отменить ожидающий таймер, вызовите метод <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-117">To cancel a pending timer, call the <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="e69a2-118">В следующем примере создается таймер, который вызывает предоставленный делегат в первый раз через одну секунду (1000 миллисекунд), а затем каждые две секунды.</span><span class="sxs-lookup"><span data-stu-id="e69a2-118">The following example creates a timer that calls the provided delegate for the first time after one second (1000 milliseconds) and then calls it every two seconds.</span></span> <span data-ttu-id="e69a2-119">Объект состояния в примере используется для подсчета вызовов делегата.</span><span class="sxs-lookup"><span data-stu-id="e69a2-119">The state object in the example is used to count how many times the delegate is called.</span></span> <span data-ttu-id="e69a2-120">Таймер останавливается после 10 вызовов.</span><span class="sxs-lookup"><span data-stu-id="e69a2-120">The timer is stopped when the delegate has been called at least 10 times.</span></span>

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

<span data-ttu-id="e69a2-121">Дополнительные сведения и примеры см. в разделе <xref:System.Threading.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-121">For more information and examples, see <xref:System.Threading.Timer?displayProperty=nameWithType>.</span></span>

## <a name="the-systemtimerstimer-class"></a><span data-ttu-id="e69a2-122">Класс System.Timers.Timer</span><span class="sxs-lookup"><span data-stu-id="e69a2-122">The System.Timers.Timer class</span></span>

<span data-ttu-id="e69a2-123">Еще один таймер, который может использоваться в многопоточной среде, — <xref:System.Timers.Timer?displayProperty=nameWithType>. По умолчанию он порождает событие в потоке <xref:System.Threading.ThreadPool>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-123">Another timer that can be used in a multithreaded environment is <xref:System.Timers.Timer?displayProperty=nameWithType> that by default raises an event on a <xref:System.Threading.ThreadPool> thread.</span></span>

<span data-ttu-id="e69a2-124">При создании объекта <xref:System.Timers.Timer?displayProperty=nameWithType> вы можете указать интервал времени, в котором порождается событие <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-124">When you create a <xref:System.Timers.Timer?displayProperty=nameWithType> object, you may specify the time interval in which to raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="e69a2-125">Используйте свойство <xref:System.Timers.Timer.Enabled%2A>, чтобы указать, должен ли таймер порождать событие <xref:System.Timers.Timer.Elapsed>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-125">Use the <xref:System.Timers.Timer.Enabled%2A> property to indicate if a timer should raise an <xref:System.Timers.Timer.Elapsed> event.</span></span> <span data-ttu-id="e69a2-126">Если вам нужно, чтобы событие <xref:System.Timers.Timer.Elapsed> вызывалось только один раз по истечении заданного интервала, установите для <xref:System.Timers.Timer.AutoReset%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e69a2-126">If you need an <xref:System.Timers.Timer.Elapsed> event to be raised only once after the specified interval has elapsed, set the <xref:System.Timers.Timer.AutoReset%2A> to `false`.</span></span> <span data-ttu-id="e69a2-127">Свойство <xref:System.Timers.Timer.AutoReset%2A> по умолчанию имеет значение `true`, то есть событие <xref:System.Timers.Timer.Elapsed> вызывается регулярно с интервалом, определенным в свойстве <xref:System.Timers.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-127">The default value of the <xref:System.Timers.Timer.AutoReset%2A> property is `true`, which means that an <xref:System.Timers.Timer.Elapsed> event is raised regularly at the interval defined by the <xref:System.Timers.Timer.Interval%2A> property.</span></span>

<span data-ttu-id="e69a2-128">Дополнительные сведения и примеры см. в разделе <xref:System.Timers.Timer?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e69a2-128">For more information and examples, see <xref:System.Timers.Timer?displayProperty=nameWithType>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e69a2-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e69a2-129">See also</span></span>

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [<span data-ttu-id="e69a2-130">Объекты и функциональные возможности работы с потоками</span><span class="sxs-lookup"><span data-stu-id="e69a2-130">Threading Objects and Features</span></span>](threading-objects-and-features.md)
