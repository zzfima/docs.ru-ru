---
title: "Службы WCF и средство отслеживания событий для Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb8924cc04442e3b9eda5e251e6dcdc57f5660c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="0d6fa-102">Службы WCF и средство отслеживания событий для Windows</span><span class="sxs-lookup"><span data-stu-id="0d6fa-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="0d6fa-103">Этот образец демонстрирует использование аналитического отслеживания в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для передачи событий в средство отслеживания событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="0d6fa-103">This sample demonstrates how to use the analytic tracing in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="0d6fa-104">Аналитические трассировки представляют собой события, возникающие в ключевых точках стека [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и позволяющие отлаживать службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-104">The analytic traces are events emitted at key points in the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stack that allow troubleshooting of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services in production environment.</span></span>  
  
 <span data-ttu-id="0d6fa-105">Аналитическое отслеживание служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] можно включить в рабочей среде, оказывая минимальное воздействие на производительность.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-105">Analytic trace in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="0d6fa-106">Отслеживаемые события передаются в сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-106">These traces are emitted as events to an ETW session.</span></span>  
  
 <span data-ttu-id="0d6fa-107">Данный образец включает базовую службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], события из которой передаются в журнал событий, который можно просмотреть с помощью средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-107">This sample includes a basic [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="0d6fa-108">Можно также запустить выделенный сеанс трассировки событий Windows, который будет прослушивать события от этой службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d6fa-108">It is also possible to start a dedicated ETW session that listens for events from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="0d6fa-109">Данный образец включает скрипт для создания выделенного сеанса трассировки событий Windows, хранящего события в двоичном файле, который можно прочесть с помощью средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="0d6fa-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="0d6fa-110">To use this sample</span></span>  
  
1.  <span data-ttu-id="0d6fa-111">Откройте в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] файл решения EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-111">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the EtwAnalyticTraceSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="0d6fa-112">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-112">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="0d6fa-113">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-113">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="0d6fa-114">В веб-браузере, щелкните **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="0d6fa-115">В браузере должен появиться URI WSDL-документа для службы.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="0d6fa-116">Скопируйте этот URI.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-116">Copy that URI.</span></span>  
  
     <span data-ttu-id="0d6fa-117">По умолчанию служба начинает прослушивание запросов на порту 1378 (http://localhost:1378/Calculator.svc).</span><span class="sxs-lookup"><span data-stu-id="0d6fa-117">By default, the service starts listening for requests on port 1378 (http://localhost:1378/Calculator.svc).</span></span>  
  
4.  <span data-ttu-id="0d6fa-118">Запустите тестовый клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="0d6fa-118">Run the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe).</span></span>  
  
     <span data-ttu-id="0d6fa-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Тестовый клиент (WcfTestClient.exe) расположен в \< [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] каталог установки > \Common7\IDE\ WcfTestClient.exe (по умолчанию [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] каталог установки — C:\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="0d6fa-119">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] Install Dir>\Common7\IDE\ WcfTestClient.exe (default [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] install dir is C:\Program Files\Microsoft Visual Studio 10.0).</span></span>  
  
5.  <span data-ttu-id="0d6fa-120">В пределах [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] тестовый клиент, добавить службу, указав **файл**, а затем **добавить службу**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-120">Within the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client, add the service by selecting **File**, and then **Add Service**.</span></span>  
  
     <span data-ttu-id="0d6fa-121">Добавьте адрес конечной точки в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-121">Add the endpoint address in the input box.</span></span> <span data-ttu-id="0d6fa-122">Значение по умолчанию равно http://localhost:1378/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-122">The default is http://localhost:1378/Calculator.svc.</span></span>  
  
6.  <span data-ttu-id="0d6fa-123">Откройте приложение просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-123">Open the Event Viewer application.</span></span>  
  
     <span data-ttu-id="0d6fa-124">Перед запуском службы запустите средство просмотра событий и убедитесь, что журнал событий прослушивает события отслеживания, создаваемые в службе [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d6fa-124">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span>  
  
7.  <span data-ttu-id="0d6fa-125">Из **запустить** последовательно выберите пункты **Администрирование**, а затем **средство просмотра событий**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-125">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="0d6fa-126">Включить **аналитический** и **отладки** журналы.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-126">Enable the **Analytic** and **Debug** logs.</span></span>  
  
8.  <span data-ttu-id="0d6fa-127">В представлении дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-127">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="0d6fa-128">Щелкните правой кнопкой мыши **сервер приложений-приложения**выберите **представление**, а затем **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-128">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="0d6fa-129">Убедитесь, что **Отобразить аналитический и отладочный журналы** флажок.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-129">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="0d6fa-130">Включить **аналитический** журнала.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-130">Enable the **Analytic** log.</span></span>  
  
     <span data-ttu-id="0d6fa-131">В представлении дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-131">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="0d6fa-132">Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-132">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
#### <a name="to-test-the-service"></a><span data-ttu-id="0d6fa-133">Проверка службы</span><span class="sxs-lookup"><span data-stu-id="0d6fa-133">To test the service</span></span>  
  
1.  <span data-ttu-id="0d6fa-134">Переключитесь в тестовый клиент [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], дважды щелкните `Divide` и сохраните значения по умолчанию, в которых задано нулевое значение знаменателя.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-134">Switch back to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>  
  
     <span data-ttu-id="0d6fa-135">Если знаменатель равен 0, служба выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-135">If the denominator is 0, then the service throws a fault.</span></span>  
  
2.  <span data-ttu-id="0d6fa-136">Просмотрите события, переданные из службы.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-136">Observe the events emitted from the service.</span></span>  
  
     <span data-ttu-id="0d6fa-137">Вернитесь в средство просмотра событий и перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-137">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="0d6fa-138">Щелкните правой кнопкой мыши **аналитический** и выберите **обновление**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-138">Right-click **Analytic** and select **Refresh**.</span></span>  
  
     <span data-ttu-id="0d6fa-139">События аналитического отслеживания WCF отображаются в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-139">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="0d6fa-140">Обратите внимание, что для возникшей ошибки в средстве просмотра событий отображается событие аналитического отслеживания.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-140">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>  
  
3.  <span data-ttu-id="0d6fa-141">Повторите шаги 1 и 2, используя уже допустимые входные значения.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-141">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="0d6fa-142">Значением параметра `N2` может быть любое число, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-142">The value of the `N2` parameter can be any number other than 0.</span></span>  
  
     <span data-ttu-id="0d6fa-143">Обновите канал аналитики, чтобы убедиться, что события WCF не включают событий, связанных с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-143">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>  
  
 <span data-ttu-id="0d6fa-144">Образец иллюстрирует передачу событий аналитического отслеживания из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-144">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>  
  
#### <a name="to-cleanup-optional"></a><span data-ttu-id="0d6fa-145">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="0d6fa-145">To cleanup (Optional)</span></span>  
  
1.  <span data-ttu-id="0d6fa-146">Откройте средство просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-146">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="0d6fa-147">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем  **Сервер приложений приложения**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-147">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="0d6fa-148">Щелкните правой кнопкой мыши **аналитический** и выберите **отключить журнал**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-148">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="0d6fa-149">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем  **Сервер приложений приложения**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-149">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="0d6fa-150">Щелкните правой кнопкой мыши **аналитический** и выберите **очистить журнал**.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-150">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
4.  <span data-ttu-id="0d6fa-151">Выберите **снимите** параметр, чтобы очистить события.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-151">Choose the **Clear** option to clear the events.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d6fa-152">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0d6fa-153">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0d6fa-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0d6fa-154">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d6fa-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0d6fa-155">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0d6fa-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="0d6fa-156">См. также</span><span class="sxs-lookup"><span data-stu-id="0d6fa-156">See Also</span></span>  
 [<span data-ttu-id="0d6fa-157">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="0d6fa-157">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
