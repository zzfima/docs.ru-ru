---
title: contextSwitchDeadlock MDA
ms.date: 03/30/2017
helpviewer_keywords:
- deadlocks [.NET Framework]
- pumping messages
- STA message pumping
- single-threaded COM components
- MDAs (managed debugging assistants), context switching deadlocks
- managed debugging assistants (MDAs), context switching deadlocks
- ContextSwitchDeadlock MDA
- message pumping
- context switching deadlocks
ms.assetid: 26dfaa15-9ddb-4b0a-b6da-999bba664fa6
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43404ba24f6308d8da17b03df9997e893799c8d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643147"
---
# <a name="contextswitchdeadlock-mda"></a><span data-ttu-id="c9043-102">contextSwitchDeadlock MDA</span><span class="sxs-lookup"><span data-stu-id="c9043-102">contextSwitchDeadlock MDA</span></span>

<span data-ttu-id="c9043-103">Помощник отладки управляемого кода `contextSwitchDeadlock` (MDA) активируется при обнаружении взаимоблокировки во время попытки перехода к контексту COM.</span><span class="sxs-lookup"><span data-stu-id="c9043-103">The `contextSwitchDeadlock` managed debugging assistant (MDA) is activated when a deadlock is detected during an attempted COM context transition.</span></span>

## <a name="symptoms"></a><span data-ttu-id="c9043-104">Признаки</span><span class="sxs-lookup"><span data-stu-id="c9043-104">Symptoms</span></span>

<span data-ttu-id="c9043-105">Наиболее распространенный признак заключается в том, что вызов неуправляемого компонента COM из управляемого кода не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="c9043-105">The most common symptom is that a call on an unmanaged COM component from managed code does not return.</span></span>  <span data-ttu-id="c9043-106">Еще одним признаком является постепенное увеличение объема используемой памяти.</span><span class="sxs-lookup"><span data-stu-id="c9043-106">Another symptom is memory usage increasing over time.</span></span>

## <a name="cause"></a><span data-ttu-id="c9043-107">Причина</span><span class="sxs-lookup"><span data-stu-id="c9043-107">Cause</span></span>

<span data-ttu-id="c9043-108">Наиболее вероятная причина заключается в том, что поток однопотокового подразделения (STA) не выдает сообщения.</span><span class="sxs-lookup"><span data-stu-id="c9043-108">The most probable cause is that a single-threaded apartment (STA) thread is not pumping messages.</span></span> <span data-ttu-id="c9043-109">Поток однопотокового подразделения либо ожидает без выдачи сообщений, либо выполняет продолжительные операции и не позволяет очереди сообщений выдавать их.</span><span class="sxs-lookup"><span data-stu-id="c9043-109">The STA thread is either waiting without pumping messages or is performing lengthy operations and is not allowing the message queue to pump.</span></span>

<span data-ttu-id="c9043-110">Постепенное увеличение объема используемой памяти вызвано тем, что поток метода завершения пытается вызвать `Release` для неуправляемого компонента COM, и этот компонент не возвращает данные.</span><span class="sxs-lookup"><span data-stu-id="c9043-110">Memory usage increasing over time is caused by the finalizer thread attempting to call `Release` on an unmanaged COM component and that component is not returning.</span></span>  <span data-ttu-id="c9043-111">Это не позволяет методу завершения освободить другие объекты.</span><span class="sxs-lookup"><span data-stu-id="c9043-111">This prevents the finalizer from reclaiming other objects.</span></span>

<span data-ttu-id="c9043-112">По умолчанию потоковой моделью для основного потока консольных приложений Visual Basic является однопотоковое подразделение.</span><span class="sxs-lookup"><span data-stu-id="c9043-112">By default, the threading model for the main thread of Visual Basic console applications is STA.</span></span> <span data-ttu-id="c9043-113">Помощник отладки управляемого кода активируется, если поток однопотокового подразделения использует взаимодействие с COM напрямую либо косвенно посредством среды CLR или стороннего элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c9043-113">This MDA is activated if an STA thread uses COM interoperability either directly or indirectly through the common language runtime or a third-party control.</span></span>  <span data-ttu-id="c9043-114">Чтобы предотвратить активацию помощника отладки управляемого кода в консольном приложении Visual Basic, примените атрибут <xref:System.MTAThreadAttribute> для основного метода или измените приложение, чтобы оно выдавало сообщения.</span><span class="sxs-lookup"><span data-stu-id="c9043-114">To avoid activating this MDA in a Visual Basic console application, apply the <xref:System.MTAThreadAttribute> attribute to the main method or modify the application to pump messages.</span></span>

<span data-ttu-id="c9043-115">Существует возможность ошибочной активации помощника отладки управляемого кода при соблюдении всех следующих условий:</span><span class="sxs-lookup"><span data-stu-id="c9043-115">It is possible for this MDA to be falsely activated when all of the following conditions are met:</span></span>

-   <span data-ttu-id="c9043-116">Приложение создает компоненты COM из потоков однопотокового подразделения напрямую или косвенно с помощью библиотек.</span><span class="sxs-lookup"><span data-stu-id="c9043-116">An application creates COM components from STA threads either directly or indirectly through libraries.</span></span>

-   <span data-ttu-id="c9043-117">Приложение было остановлено в отладчике, и пользователь либо продолжил выполнение приложения, либо выполнил его в пошаговом режиме.</span><span class="sxs-lookup"><span data-stu-id="c9043-117">The application was stopped in the debugger and the user either continued the application or performed a step operation.</span></span>

-   <span data-ttu-id="c9043-118">Отладка неуправляемого кода выключена.</span><span class="sxs-lookup"><span data-stu-id="c9043-118">Unmanaged debugging is not enabled.</span></span>

<span data-ttu-id="c9043-119">Чтобы определить, происходит ли ошибочная активация помощника отладки управляемого кода, отключите все точки останова, перезапустите приложение и позвольте ему выполняться без остановок.</span><span class="sxs-lookup"><span data-stu-id="c9043-119">To determine if the MDA is being falsely activated, disable all breakpoints, restart the application, and allow it to run without stopping.</span></span> <span data-ttu-id="c9043-120">Если помощник отладки управляемого кода не активируется, вероятно, первоначальная активация была ошибочной.</span><span class="sxs-lookup"><span data-stu-id="c9043-120">If the MDA is not activated, it is likely the initial activation was false.</span></span> <span data-ttu-id="c9043-121">В этом случае отключите помощник отладки управляемого кода, чтобы не нарушать работу сеанса отладки.</span><span class="sxs-lookup"><span data-stu-id="c9043-121">In this case, disable the MDA to avoid interference with the debugging session.</span></span>

> [!NOTE]
> <span data-ttu-id="c9043-122">Данный MDA находится в стандартный набор для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c9043-122">This MDA is in the default set for Visual Studio.</span></span> <span data-ttu-id="c9043-123">Сведения о том, как отключить MDA, см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span><span class="sxs-lookup"><span data-stu-id="c9043-123">For information about how to disable MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md#enable-and-disable-mdas).</span></span>

## <a name="resolution"></a><span data-ttu-id="c9043-124">Решение</span><span class="sxs-lookup"><span data-stu-id="c9043-124">Resolution</span></span>

<span data-ttu-id="c9043-125">Соблюдайте правила COM в отношении выдачи сообщений однопотокового подразделения.</span><span class="sxs-lookup"><span data-stu-id="c9043-125">Follow COM rules regarding STA message pumping.</span></span>

## <a name="effect-on-the-runtime"></a><span data-ttu-id="c9043-126">Влияние на среду выполнения</span><span class="sxs-lookup"><span data-stu-id="c9043-126">Effect on the Runtime</span></span>

<span data-ttu-id="c9043-127">Этот помощник отладки управляемого кода не оказывает никакого влияния на среду CLR.</span><span class="sxs-lookup"><span data-stu-id="c9043-127">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="c9043-128">Он только выводит данные о контекстах COM.</span><span class="sxs-lookup"><span data-stu-id="c9043-128">It only reports data about COM contexts.</span></span>

## <a name="output"></a><span data-ttu-id="c9043-129">Вывод</span><span class="sxs-lookup"><span data-stu-id="c9043-129">Output</span></span>

<span data-ttu-id="c9043-130">Сообщение с описанием текущего контекста и целевого контекста.</span><span class="sxs-lookup"><span data-stu-id="c9043-130">A message describing the current context and the target context.</span></span>

## <a name="configuration"></a><span data-ttu-id="c9043-131">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="c9043-131">Configuration</span></span>

```xml
<mdaConfig>
  <assistants>
    <contextSwitchDeadlock />
  </assistants>
</mdaConfig>
```

## <a name="see-also"></a><span data-ttu-id="c9043-132">См. также</span><span class="sxs-lookup"><span data-stu-id="c9043-132">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="c9043-133">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="c9043-133">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="c9043-134">Маршалинг взаимодействия</span><span class="sxs-lookup"><span data-stu-id="c9043-134">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
