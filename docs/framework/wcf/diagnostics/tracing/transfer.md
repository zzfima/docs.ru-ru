---
title: Transfer
ms.date: 03/30/2017
ms.assetid: dfcfa36c-d3bb-44b4-aa15-1c922c6f73e6
ms.openlocfilehash: e0ebfff97cd33e7a588a1ab92399a97a0fbec039
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185708"
---
# <a name="transfer"></a><span data-ttu-id="d14e0-102">Transfer</span><span class="sxs-lookup"><span data-stu-id="d14e0-102">Transfer</span></span>
<span data-ttu-id="d14e0-103">Эта тема описывает передачу в модели отслеживания активности Фонда связи Windows (WCF).</span><span class="sxs-lookup"><span data-stu-id="d14e0-103">This topic describes transfer in the Windows Communication Foundation (WCF) activity tracing model.</span></span>  
  
## <a name="transfer-definition"></a><span data-ttu-id="d14e0-104">Определение перенаправления</span><span class="sxs-lookup"><span data-stu-id="d14e0-104">Transfer Definition</span></span>  
 <span data-ttu-id="d14e0-105">Перенаправления между действиями передают причинно-следственную связь между событиями в связанных действиях внутри конечных точек.</span><span class="sxs-lookup"><span data-stu-id="d14e0-105">Transfers between activities represent causal relationships between events in the related activities within endpoints.</span></span> <span data-ttu-id="d14e0-106">Два действия связываются перенаправлениями при потоке управления от одного из этих действий к другому, например когда вызов метода пересекает границы действия.</span><span class="sxs-lookup"><span data-stu-id="d14e0-106">Two activities are related with transfers when control flows between these activities, for example, a method call crossing activity boundaries.</span></span> <span data-ttu-id="d14e0-107">В WCF, когда байты входят в службу, действие Listen At is передается в действие Receive Bytes, где создается объект сообщения.</span><span class="sxs-lookup"><span data-stu-id="d14e0-107">In WCF, when bytes are incoming on the service, the Listen At activity is transferred to the Receive Bytes activity where the message object is created.</span></span> <span data-ttu-id="d14e0-108">Список сценариев сквозного отслеживания и их соответствующей деятельности и проектирования трассировки можно узнать в [сценариях отслеживания от end-to-End.](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="d14e0-108">For a list of end-to-end tracing scenarios, and their respective activity and tracing design, see [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md).</span></span>  
  
 <span data-ttu-id="d14e0-109">Для выдачи трассировки перенаправлений задайте параметр `ActivityTracing` в источнике трассировки, как показано в предыдущем примере кода.</span><span class="sxs-lookup"><span data-stu-id="d14e0-109">To emit transfer traces, use the `ActivityTracing` setting on the trace source as demonstrated by the following configuration code.</span></span>  
  
```xml  
<source name="System.ServiceModel" switchValue="Verbose,ActivityTracing">  
```  
  
## <a name="using-transfer-to-correlate-activities-within-endpoints"></a><span data-ttu-id="d14e0-110">Использование перенаправления для корреляции действий внутри конечных точек</span><span class="sxs-lookup"><span data-stu-id="d14e0-110">Using Transfer to Correlate Activities Within Endpoints</span></span>  
 <span data-ttu-id="d14e0-111">Действия и перенаправления позволяют пользователю с определенной вероятностью найти первопричину ошибки.</span><span class="sxs-lookup"><span data-stu-id="d14e0-111">Activities and transfers permit the user to probabilistically locate the root cause of an error.</span></span> <span data-ttu-id="d14e0-112">Например, если при перенаправлении от действия M на действие N и обратно (в компонентах M и N соответственно) сразу же после перенаправления обратно на M происходит сбой, можно сделать вывод, что это скорее всего связано с передачей действием N данных обратно действию M.</span><span class="sxs-lookup"><span data-stu-id="d14e0-112">For example, if we transfer back and forth between activities M and N respectively in components M and N, and a crash happens in N right after the transfer back to M, we can draw the conclusion that it is likely due to N’s passing data back to M.</span></span>  
  
 <span data-ttu-id="d14e0-113">Трассировка перенаправления выдается от действия M на действие N при передаче управления от M к N. Например, N выполняет некоторую обработку для M в связи с тем, что вызов метода пересекает границы действий.</span><span class="sxs-lookup"><span data-stu-id="d14e0-113">A transfer trace is emitted from activity M to activity N when there is a flow of control between M and N. For example, N performs some work for M because of a method call crossing the activities’ boundaries.</span></span> <span data-ttu-id="d14e0-114">Действие N может уже существовать или быть создано.</span><span class="sxs-lookup"><span data-stu-id="d14e0-114">N may already exist or has been created.</span></span> <span data-ttu-id="d14e0-115">Действие N порождается действием M, когда N представляет собой новое действие, выполняющее некоторую обработку для M.</span><span class="sxs-lookup"><span data-stu-id="d14e0-115">N is spawned by M when N is a new activity that performs some work for M.</span></span>  
  
 <span data-ttu-id="d14e0-116">За перенаправлением от M на N не обязательно следует перенаправление обратно от N на M. Это связано с тем, что M может породить некоторую обработку в N и не следит за тем, когда N завершит эту обработку.</span><span class="sxs-lookup"><span data-stu-id="d14e0-116">A transfer from M to N may not be followed by a transfer back from N to M. This is because M can spawn some work in N and do not track when N completes that work.</span></span> <span data-ttu-id="d14e0-117">Фактически действие M может быть прекращено до того, как N завершит свою задачу.</span><span class="sxs-lookup"><span data-stu-id="d14e0-117">In fact, M can terminate before N completes its task.</span></span> <span data-ttu-id="d14e0-118">Это происходит в "Open ServiceHost" деятельности (M), которая порождает действия слушателя (N), а затем завершает.</span><span class="sxs-lookup"><span data-stu-id="d14e0-118">This happens in the "Open ServiceHost" activity (M) that spawns Listener activities (N) and then terminates.</span></span> <span data-ttu-id="d14e0-119">Перенаправление обратно от N на M означает, что действие N завершило обработку, относящуюся к действию M.</span><span class="sxs-lookup"><span data-stu-id="d14e0-119">A transfer back from N to M means that N completed the work related to M.</span></span>  
  
 <span data-ttu-id="d14e0-120">Действие N может продолжать выполнять другую обработку, не относящуюся к действию M, например существующее действие структуры проверки подлинности (N) продолжит получать запросы на вход (M) от других действий входа.</span><span class="sxs-lookup"><span data-stu-id="d14e0-120">N can continue performing other processing unrelated to M, for example, an existing authenticator activity (N) that keeps receiving login requests (M) from different login activities.</span></span>  
  
 <span data-ttu-id="d14e0-121">Между действиями M и N необязательно должно существовать отношение вложенности. Это может произойти по двум причинам.</span><span class="sxs-lookup"><span data-stu-id="d14e0-121">A nesting relationship does not necessarily exist between activities M and N. This can happen due to two reasons.</span></span> <span data-ttu-id="d14e0-122">Первая — когда действие M не осуществляет мониторинг обработки, выполняемой действием N, даже хотя действие M инициировало действие N. Вторая — когда действия N уже существует.</span><span class="sxs-lookup"><span data-stu-id="d14e0-122">First, when activity M does not monitor the actual processing performed in N although M initiated N. Second, when N already exists.</span></span>  
  
## <a name="example-of-transfers"></a><span data-ttu-id="d14e0-123">Пример перенаправления</span><span class="sxs-lookup"><span data-stu-id="d14e0-123">Example of Transfers</span></span>  
 <span data-ttu-id="d14e0-124">Ниже приведено два примера перенаправления.</span><span class="sxs-lookup"><span data-stu-id="d14e0-124">The following lists two transfer examples.</span></span>  
  
- <span data-ttu-id="d14e0-125">При создании узла службы конструктор получает управление от вызывающего кода, или вызывающий код выполняет перенаправление на конструктор.</span><span class="sxs-lookup"><span data-stu-id="d14e0-125">When you create a service host, the constructor gains control from the calling code, or the calling code transfers to the constructor.</span></span> <span data-ttu-id="d14e0-126">По завершении выполнения конструктор возвращает управление вызывающему коду, или конструктор выполняет перенаправление обратно на вызывающий код.</span><span class="sxs-lookup"><span data-stu-id="d14e0-126">When the constructor has finished executing, it returns control to the calling code, or the constructor transfers back to the calling code.</span></span> <span data-ttu-id="d14e0-127">Это случай отношения вложенности.</span><span class="sxs-lookup"><span data-stu-id="d14e0-127">This is the case of a nested relationship.</span></span>  
  
- <span data-ttu-id="d14e0-128">Когда прослушиватель начинает обрабатывать данные транспорта, он создает новый поток и передает действию Receive Bytes соответствующий контекст для обработки, т. е. передает управление и данные.</span><span class="sxs-lookup"><span data-stu-id="d14e0-128">When a listener starts processing transport data, it creates a new thread and hands to the Receive Bytes activity the appropriate context for processing, passing control and data.</span></span> <span data-ttu-id="d14e0-129">По завершении обработки запроса этим потоком действие Receive Bytes ничего не передает обратно прослушивателю.</span><span class="sxs-lookup"><span data-stu-id="d14e0-129">When that thread has finished processing the request, the Receive Bytes activity passes nothing back to the listener.</span></span> <span data-ttu-id="d14e0-130">В этом случае имеет место перенаправление на новое действие потока, однако перенаправления от действия потока не происходит.</span><span class="sxs-lookup"><span data-stu-id="d14e0-130">In this case, we have a transfer in but no transfer out of the new thread activity.</span></span> <span data-ttu-id="d14e0-131">Два действия связаны, но не являются вложенными.</span><span class="sxs-lookup"><span data-stu-id="d14e0-131">The two activities are related but not nested.</span></span>  
  
## <a name="activity-transfer-sequence"></a><span data-ttu-id="d14e0-132">Последовательность перенаправления между действиями</span><span class="sxs-lookup"><span data-stu-id="d14e0-132">Activity Transfer Sequence</span></span>  
 <span data-ttu-id="d14e0-133">Корректная последовательность перенаправления между действиями включает следующие шаги.</span><span class="sxs-lookup"><span data-stu-id="d14e0-133">A well-formed activity transfer sequence includes the following steps.</span></span>  
  
1. <span data-ttu-id="d14e0-134">Начало нового действия (заключается в выборе нового идентификатора gAId).</span><span class="sxs-lookup"><span data-stu-id="d14e0-134">Begin a new activity, which consists of selecting a new gAId.</span></span>  
  
2. <span data-ttu-id="d14e0-135">Выдача трассировки перенаправления на этот новый идентификатор gAId от текущего идентификатора действия.</span><span class="sxs-lookup"><span data-stu-id="d14e0-135">Emit a transfer trace to that new gAId from the current activity ID</span></span>  
  
3. <span data-ttu-id="d14e0-136">Задание нового идентификатора в локальной памяти потока.</span><span class="sxs-lookup"><span data-stu-id="d14e0-136">Set the new ID in TLS</span></span>  
  
4. <span data-ttu-id="d14e0-137">Выдача трассировки Start, обозначающей начало нового действия.</span><span class="sxs-lookup"><span data-stu-id="d14e0-137">Emit a start trace to indicate the beginning of the new activity by.</span></span>  
  
5. <span data-ttu-id="d14e0-138">Возврат к исходному действию заключается в следующем:</span><span class="sxs-lookup"><span data-stu-id="d14e0-138">Return to the original activity consists of the following:</span></span>  
  
6. <span data-ttu-id="d14e0-139">выдача трассировки перенаправления к исходному идентификатору gAId;</span><span class="sxs-lookup"><span data-stu-id="d14e0-139">Emit a transfer trace to the original gAId</span></span>  
  
7. <span data-ttu-id="d14e0-140">выдача трассировки Stop, обозначающей конец нового действия;</span><span class="sxs-lookup"><span data-stu-id="d14e0-140">Emit a Stop trace to indicate the end of the new activity</span></span>  
  
8. <span data-ttu-id="d14e0-141">присвоение локальной памяти потока старого идентификатора gAId.</span><span class="sxs-lookup"><span data-stu-id="d14e0-141">Set TLS to the old gAId.</span></span>  
  
 <span data-ttu-id="d14e0-142">В следующем примере кода показано, как это сделать.</span><span class="sxs-lookup"><span data-stu-id="d14e0-142">The following code example demonstrates how to do this.</span></span> <span data-ttu-id="d14e0-143">В этом примере предполагается, что при перенаправлении на новое действие совершается блокирующий вызов, и приводятся трассировки приостановки/возобновления.</span><span class="sxs-lookup"><span data-stu-id="d14e0-143">This sample assumes a blocking call is made when transferring to the new activity, and includes suspend/resume traces.</span></span>  
  
```csharp
// 0. Create a trace source  
TraceSource ts = new TraceSource("myTS");  

// 1. remember existing ("ambient") activity for clean up  
Guid oldGuid = Trace.CorrelationManager.ActivityId;  
// this will be our new activity  
Guid newGuid = Guid.NewGuid();

// 2. call transfer, indicating that we are switching to the new AID  
ts.TraceTransfer(667, "Transferring.", newGuid);  

// 3. Suspend the current activity.  
ts.TraceEvent(TraceEventType.Suspend, 667, "Suspend: Activity " + i-1);  

// 4. set the new AID in TLS  
Trace.CorrelationManager.ActivityId = newGuid;  

// 5. Emit the start trace  
ts.TraceEvent(TraceEventType.Start, 667, "Boundary: Activity " + i);  

// trace something  
ts.TraceEvent(TraceEventType.Information, 667, "Hello from activity " + i);  

// Perform Work  
// some work.  
// Return  
ts.TraceEvent(TraceEventType.Information, 667, "Work complete on activity " + i);

// 6. Emit the transfer returning to the original activity  
ts.TraceTransfer(667, "Transferring Back.", oldGuid);  

// 7. Emit the End trace  
ts.TraceEvent(TraceEventType.Stop, 667, "Boundary: Activity " + i);  

// 8. Change the tls variable to the original AID  
Trace.CorrelationManager.ActivityId = oldGuid;

// 9. Resume the old activity  
ts.TraceEvent(TraceEventType.Resume, 667, "Resume: Activity " + i-1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="d14e0-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d14e0-144">See also</span></span>

- [<span data-ttu-id="d14e0-145">Настройка трассировки</span><span class="sxs-lookup"><span data-stu-id="d14e0-145">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)
- [<span data-ttu-id="d14e0-146">Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок</span><span class="sxs-lookup"><span data-stu-id="d14e0-146">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)
- [<span data-ttu-id="d14e0-147">Сценарии сквозной трассировки</span><span class="sxs-lookup"><span data-stu-id="d14e0-147">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)
- [<span data-ttu-id="d14e0-148">Средство просмотра трассировки служб (SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="d14e0-148">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
