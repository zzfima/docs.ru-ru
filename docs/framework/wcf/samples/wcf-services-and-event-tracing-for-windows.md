---
title: Службы WCF и средство отслеживания событий для Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: 100f9c0ce71eedaa4061fc894521597074b21b00
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198293"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="f6403-102">Службы WCF и средство отслеживания событий для Windows</span><span class="sxs-lookup"><span data-stu-id="f6403-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="f6403-103">Этот образец демонстрирует использование аналитического отслеживания в Windows Communication Foundation (WCF) для передачи событий в Windows (Трассировка событий).</span><span class="sxs-lookup"><span data-stu-id="f6403-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="f6403-104">Аналитические трассировки — это события, возникающие в ключевых точках стека WCF, позволяющие отлаживать службы WCF в рабочей среде.</span><span class="sxs-lookup"><span data-stu-id="f6403-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="f6403-105">Трассировка аналитического отслеживания в службах WCF, которая может быть включен в рабочей среде с минимальным влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="f6403-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="f6403-106">Отслеживаемые события передаются в сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="f6403-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="f6403-107">Этот пример включает базовой службы WCF, в котором они выдаются из службы в журнал событий, который можно просмотреть с помощью средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6403-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="f6403-108">Можно также запустить выделенный сеанс ETW, который прослушивает события из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f6403-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="f6403-109">Данный образец включает скрипт для создания выделенного сеанса трассировки событий Windows, хранящего события в двоичном файле, который можно прочесть с помощью средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6403-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="f6403-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="f6403-110">To use this sample</span></span>

1.  <span data-ttu-id="f6403-111">С помощью Visual Studio 2012, откройте файл решения EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="f6403-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2.  <span data-ttu-id="f6403-112">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="f6403-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3.  <span data-ttu-id="f6403-113">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="f6403-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="f6403-114">В веб-браузере, щелкните **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="f6403-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="f6403-115">В браузере должен появиться URI WSDL-документа для службы.</span><span class="sxs-lookup"><span data-stu-id="f6403-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="f6403-116">Скопируйте этот URI.</span><span class="sxs-lookup"><span data-stu-id="f6403-116">Copy that URI.</span></span>

     <span data-ttu-id="f6403-117">По умолчанию служба начинает прослушивание запросов на порту 1378 `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="f6403-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4.  <span data-ttu-id="f6403-118">Запустите тестовый клиент WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="f6403-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="f6403-119">Тестовый клиент WCF (WcfTestClient.exe) расположен в `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span><span class="sxs-lookup"><span data-stu-id="f6403-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="f6403-120">Каталог установки Visual Studio 2012 по умолчанию является `C:\Program Files\Microsoft Visual Studio 10.0`.</span><span class="sxs-lookup"><span data-stu-id="f6403-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5.  <span data-ttu-id="f6403-121">В тестовом клиенте WCF, добавьте службу, выбрав **файл**, а затем **добавить службу**.</span><span class="sxs-lookup"><span data-stu-id="f6403-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="f6403-122">Добавьте адрес конечной точки в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="f6403-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="f6403-123">Значение по умолчанию — `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="f6403-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6.  <span data-ttu-id="f6403-124">Откройте приложение просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6403-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="f6403-125">Перед запуском службы запустите средство просмотра событий и убедитесь, что в журнал событий прослушивает событий отслеживания от службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f6403-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7.  <span data-ttu-id="f6403-126">Из **запустить** меню, выберите **Администрирование**, а затем **средство просмотра событий**.</span><span class="sxs-lookup"><span data-stu-id="f6403-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="f6403-127">Включить **аналитический** и **Отладка** журналы.</span><span class="sxs-lookup"><span data-stu-id="f6403-127">Enable the **Analytic** and **Debug** logs.</span></span>

8.  <span data-ttu-id="f6403-128">В представлении в виде дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="f6403-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f6403-129">Щелкните правой кнопкой мыши **Application Server-Applications**выберите **представление**, а затем **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="f6403-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="f6403-130">Убедитесь, что **Отобразить аналитический и отладочный журналы** флажок.</span><span class="sxs-lookup"><span data-stu-id="f6403-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="f6403-131">Включить **аналитический** журнала.</span><span class="sxs-lookup"><span data-stu-id="f6403-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="f6403-132">В представлении в виде дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="f6403-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f6403-133">Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="f6403-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="f6403-134">Проверка службы</span><span class="sxs-lookup"><span data-stu-id="f6403-134">To test the service</span></span>

1.  <span data-ttu-id="f6403-135">Вернитесь в тестовом клиенте WCF и дважды щелкните `Divide` и сохраните значения по умолчанию, в которых задано нулевое значение знаменателя 0.</span><span class="sxs-lookup"><span data-stu-id="f6403-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="f6403-136">Если знаменатель равен 0, служба выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="f6403-136">If the denominator is 0, then the service throws a fault.</span></span>

2.  <span data-ttu-id="f6403-137">Просмотрите события, переданные из службы.</span><span class="sxs-lookup"><span data-stu-id="f6403-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="f6403-138">Вернитесь в средство просмотра событий и перейдите к окну **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="f6403-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="f6403-139">Щелкните правой кнопкой мыши **аналитический** и выберите **обновить**.</span><span class="sxs-lookup"><span data-stu-id="f6403-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="f6403-140">События аналитического отслеживания WCF отображаются в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6403-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="f6403-141">Обратите внимание, что для возникшей ошибки в средстве просмотра событий отображается событие аналитического отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f6403-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3.  <span data-ttu-id="f6403-142">Повторите шаги 1 и 2, используя уже допустимые входные значения.</span><span class="sxs-lookup"><span data-stu-id="f6403-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="f6403-143">Значением параметра `N2` может быть любое число, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="f6403-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="f6403-144">Обновите канал аналитики, чтобы убедиться, что события WCF не включают событий, связанных с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="f6403-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="f6403-145">Образец иллюстрирует передачу событий аналитического отслеживания из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="f6403-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="f6403-146">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="f6403-146">To cleanup (Optional)</span></span>

1.  <span data-ttu-id="f6403-147">Откройте средство просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="f6403-147">Open Event Viewer.</span></span>

2.  <span data-ttu-id="f6403-148">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем  **Application-Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="f6403-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="f6403-149">Щелкните правой кнопкой мыши **аналитический** и выберите **отключить журнал**.</span><span class="sxs-lookup"><span data-stu-id="f6403-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3.  <span data-ttu-id="f6403-150">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, а затем  **Application-Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="f6403-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="f6403-151">Щелкните правой кнопкой мыши **аналитический** и выберите **очистить журнал**.</span><span class="sxs-lookup"><span data-stu-id="f6403-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4.  <span data-ttu-id="f6403-152">Выберите **снимите** параметр, чтобы удалить события.</span><span class="sxs-lookup"><span data-stu-id="f6403-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f6403-153">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f6403-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f6403-154">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f6403-154">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f6403-155">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="f6403-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f6403-156">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f6403-156">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="f6403-157">См. также</span><span class="sxs-lookup"><span data-stu-id="f6403-157">See Also</span></span>  
 [<span data-ttu-id="f6403-158">Образцы наблюдения за AppFabric</span><span class="sxs-lookup"><span data-stu-id="f6403-158">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
