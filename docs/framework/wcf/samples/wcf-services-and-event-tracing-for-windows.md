---
title: Службы WCF и средство отслеживания событий для Windows
ms.date: 03/30/2017
ms.assetid: eda4355d-0bd0-4dc9-80a2-d2c832152272
ms.openlocfilehash: b8a1f30f20aa2c541a574a070b3644569d633ca2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183214"
---
# <a name="wcf-services-and-event-tracing-for-windows"></a><span data-ttu-id="aacad-102">Службы WCF и средство отслеживания событий для Windows</span><span class="sxs-lookup"><span data-stu-id="aacad-102">WCF Services and Event Tracing for Windows</span></span>
<span data-ttu-id="aacad-103">В этом примере показано, как использовать аналитический розыск в Фонде связи Windows (WCF) для испускания событий в отслеживании событий для Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="aacad-103">This sample demonstrates how to use the analytic tracing in Windows Communication Foundation (WCF) to emit events in Event Tracing for Windows (ETW).</span></span> <span data-ttu-id="aacad-104">Аналитические следы — это события, испускаемые в ключевых точках стека WCF, которые позволяют улавливать проблемы служб WCF в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="aacad-104">The analytic traces are events emitted at key points in the WCF stack that allow troubleshooting of WCF services in production environment.</span></span>

 <span data-ttu-id="aacad-105">Аналитический след в службах WCF отслеживает, который может быть включен в производственной среде с минимальным влиянием на производительность.</span><span class="sxs-lookup"><span data-stu-id="aacad-105">Analytic trace in WCF services is tracing that can be turned on in a production environment with minimal impact on performance.</span></span> <span data-ttu-id="aacad-106">Отслеживаемые события передаются в сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="aacad-106">These traces are emitted as events to an ETW session.</span></span>

 <span data-ttu-id="aacad-107">Этот пример включает базовую службу WCF, в которой события излучаются из службы в журнал событий, который можно просматривать с помощью Event Viewer.</span><span class="sxs-lookup"><span data-stu-id="aacad-107">This sample includes a basic WCF service in which events are emitted from the service to the event log, which can be viewed using Event Viewer.</span></span> <span data-ttu-id="aacad-108">Также можно начать специальную сессию ETW, которая слушает события из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="aacad-108">It is also possible to start a dedicated ETW session that listens for events from the WCF service.</span></span> <span data-ttu-id="aacad-109">Данный образец включает скрипт для создания выделенного сеанса трассировки событий Windows, хранящего события в двоичном файле, который можно прочесть с помощью средства просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="aacad-109">The sample includes a script to create a dedicated ETW session that stores events in a binary file that can be read using Event Viewer.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="aacad-110">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="aacad-110">To use this sample</span></span>

1. <span data-ttu-id="aacad-111">Используя Visual Studio 2012, откройте файл решений EtwAnalyticTraceSample.sln.</span><span class="sxs-lookup"><span data-stu-id="aacad-111">Using Visual Studio 2012, open the EtwAnalyticTraceSample.sln solution file.</span></span>

2. <span data-ttu-id="aacad-112">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="aacad-112">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="aacad-113">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="aacad-113">To run the solution, press CTRL+F5.</span></span>

     <span data-ttu-id="aacad-114">В веб-браузере нажмите **Calculator.svc**.</span><span class="sxs-lookup"><span data-stu-id="aacad-114">In the Web browser, click **Calculator.svc**.</span></span> <span data-ttu-id="aacad-115">В браузере должен появиться URI WSDL-документа для службы.</span><span class="sxs-lookup"><span data-stu-id="aacad-115">The URI of the WSDL document for the service should appear in the browser.</span></span> <span data-ttu-id="aacad-116">Скопируйте этот URI.</span><span class="sxs-lookup"><span data-stu-id="aacad-116">Copy that URI.</span></span>

     <span data-ttu-id="aacad-117">По умолчанию служба начинает прослушивать запросы `http://localhost:1378/Calculator.svc`в порту 1378 .</span><span class="sxs-lookup"><span data-stu-id="aacad-117">By default, the service starts listening for requests on port 1378 `http://localhost:1378/Calculator.svc`.</span></span>

4. <span data-ttu-id="aacad-118">Выполнить тестовый клиент WCF (WcfTestClient.exe).</span><span class="sxs-lookup"><span data-stu-id="aacad-118">Run the WCF test client (WcfTestClient.exe).</span></span>

     <span data-ttu-id="aacad-119">Тестовый клиент WCF (WcfTestClient.exe) `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`находится по адресу .</span><span class="sxs-lookup"><span data-stu-id="aacad-119">The WCF test client (WcfTestClient.exe) is located at `\<Visual Studio 2012 Install Dir>\Common7\IDE\WcfTestClient.exe`.</span></span>  <span data-ttu-id="aacad-120">По умолчанию Visual Studio 2012 установить dir является `C:\Program Files\Microsoft Visual Studio 10.0`.</span><span class="sxs-lookup"><span data-stu-id="aacad-120">The default Visual Studio 2012 install dir is `C:\Program Files\Microsoft Visual Studio 10.0`.</span></span>

5. <span data-ttu-id="aacad-121">В тестовом клиенте WCF добавьте услугу, выбрав **файл,** а затем **добавьте услугу.**</span><span class="sxs-lookup"><span data-stu-id="aacad-121">Within the WCF test client, add the service by selecting **File**, and then **Add Service**.</span></span>

     <span data-ttu-id="aacad-122">Добавьте адрес конечной точки в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="aacad-122">Add the endpoint address in the input box.</span></span> <span data-ttu-id="aacad-123">Значение по умолчанию — `http://localhost:1378/Calculator.svc`.</span><span class="sxs-lookup"><span data-stu-id="aacad-123">The default is `http://localhost:1378/Calculator.svc`.</span></span>

6. <span data-ttu-id="aacad-124">Откройте приложение просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="aacad-124">Open the Event Viewer application.</span></span>

     <span data-ttu-id="aacad-125">Прежде чем выступить в службу, запустите Event Viewer и убедитесь, что журнал событий прослушивает события, испущенные из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="aacad-125">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the WCF service.</span></span>

7. <span data-ttu-id="aacad-126">Из меню **«Пуск»** выберите **Административные инструменты,** а затем **зритель событий.**</span><span class="sxs-lookup"><span data-stu-id="aacad-126">From the **Start** menu, select **Administrative Tools**, and then **Event Viewer**.</span></span>  <span data-ttu-id="aacad-127">Включить **журналы analytic** и **Debug.**</span><span class="sxs-lookup"><span data-stu-id="aacad-127">Enable the **Analytic** and **Debug** logs.</span></span>

8. <span data-ttu-id="aacad-128">В представлении дерева в Event Viewer перейдите в журналы **событий,** **приложения и службы,** **Microsoft,** **Windows,** а затем **приложения Server-Applications.**</span><span class="sxs-lookup"><span data-stu-id="aacad-128">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="aacad-129">Право нажмите **приложение Server-Приложения**, выберите **Просмотр**, а затем **показать аналитические и debug журналы**.</span><span class="sxs-lookup"><span data-stu-id="aacad-129">Right-click **Application Server-Applications**, select **View**, and then **Show Analytic and Debug Logs**.</span></span>

     <span data-ttu-id="aacad-130">Убедитесь, что **опция Show Analytic и Debug Logs проверена.**</span><span class="sxs-lookup"><span data-stu-id="aacad-130">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>

9. <span data-ttu-id="aacad-131">Включить **аналитический** журнал.</span><span class="sxs-lookup"><span data-stu-id="aacad-131">Enable the **Analytic** log.</span></span>

     <span data-ttu-id="aacad-132">В представлении дерева в Event Viewer перейдите в журналы **событий,** **приложения и службы,** **Microsoft,** **Windows,** а затем **приложения Server-Applications.**</span><span class="sxs-lookup"><span data-stu-id="aacad-132">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="aacad-133">Нажмите правой кнопкой **аналитический** и выберите **Включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="aacad-133">Right-click **Analytic** and select **Enable Log**.</span></span>

#### <a name="to-test-the-service"></a><span data-ttu-id="aacad-134">Проверка службы</span><span class="sxs-lookup"><span data-stu-id="aacad-134">To test the service</span></span>

1. <span data-ttu-id="aacad-135">Переключитесь на тестовый клиент `Divide` WCF и дважды щелкните и сохраните значения по умолчанию, которые указывают знаменатель 0.</span><span class="sxs-lookup"><span data-stu-id="aacad-135">Switch back to WCF test client and double-click `Divide` and keep the default values, which specify a denominator of 0.</span></span>

     <span data-ttu-id="aacad-136">Если знаменатель равен 0, служба выдает ошибку.</span><span class="sxs-lookup"><span data-stu-id="aacad-136">If the denominator is 0, then the service throws a fault.</span></span>

2. <span data-ttu-id="aacad-137">Просмотрите события, переданные из службы.</span><span class="sxs-lookup"><span data-stu-id="aacad-137">Observe the events emitted from the service.</span></span>

     <span data-ttu-id="aacad-138">Вернитесь к Просмотру событий и перейдите к **журналу Event Viewer,** **приложениям и службам,** **Microsoft,** **Windows,** а затем **к приложениям Server-Applications.**</span><span class="sxs-lookup"><span data-stu-id="aacad-138">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application Server-Applications**.</span></span> <span data-ttu-id="aacad-139">Нажмите правой кнопкой **аналитический** и выберите **Обновить**.</span><span class="sxs-lookup"><span data-stu-id="aacad-139">Right-click **Analytic** and select **Refresh**.</span></span>

     <span data-ttu-id="aacad-140">События аналитического отслеживания WCF отображаются в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="aacad-140">The WCF analytic trace events are displayed in the event viewer.</span></span> <span data-ttu-id="aacad-141">Обратите внимание, что для возникшей ошибки в средстве просмотра событий отображается событие аналитического отслеживания.</span><span class="sxs-lookup"><span data-stu-id="aacad-141">Notice that because a fault was thrown by the service an error trace event is displayed in the event viewer.</span></span>

3. <span data-ttu-id="aacad-142">Повторите шаги 1 и 2, используя уже допустимые входные значения.</span><span class="sxs-lookup"><span data-stu-id="aacad-142">Repeat steps 1 and 2, but with valid inputs.</span></span> <span data-ttu-id="aacad-143">Значением параметра `N2` может быть любое число, отличное от 0.</span><span class="sxs-lookup"><span data-stu-id="aacad-143">The value of the `N2` parameter can be any number other than 0.</span></span>

     <span data-ttu-id="aacad-144">Обновите канал аналитики, чтобы убедиться, что события WCF не включают событий, связанных с ошибкой.</span><span class="sxs-lookup"><span data-stu-id="aacad-144">Refresh the analytic channel to view the WCF events do not include any error events.</span></span>

 <span data-ttu-id="aacad-145">Образец иллюстрирует передачу событий аналитического отслеживания из службы WCF.</span><span class="sxs-lookup"><span data-stu-id="aacad-145">The sample demonstrates the analytic trace events emitted from a WCF service.</span></span>

#### <a name="to-cleanup-optional"></a><span data-ttu-id="aacad-146">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="aacad-146">To cleanup (Optional)</span></span>

1. <span data-ttu-id="aacad-147">Откройте средство просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="aacad-147">Open Event Viewer.</span></span>

2. <span data-ttu-id="aacad-148">Перейдите к **просмотру событий,** **журналам приложений и служб,** **Microsoft,** **Windows,** а затем **application-Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="aacad-148">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="aacad-149">Нажмите правой кнопкой **аналитический** и выберите **отключить журнал**.</span><span class="sxs-lookup"><span data-stu-id="aacad-149">Right-click **Analytic** and select **Disable Log**.</span></span>

3. <span data-ttu-id="aacad-150">Перейдите к **просмотру событий,** **журналам приложений и служб,** **Microsoft,** **Windows,** а затем **application-Server-Applications**.</span><span class="sxs-lookup"><span data-stu-id="aacad-150">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, and then **Application-Server-Applications**.</span></span> <span data-ttu-id="aacad-151">Нажмите правой кнопкой **аналитический** и выберите **Clear Log**.</span><span class="sxs-lookup"><span data-stu-id="aacad-151">Right-click **Analytic** and select **Clear Log**.</span></span>

4. <span data-ttu-id="aacad-152">Выберите **опцию Clear,** чтобы очистить события.</span><span class="sxs-lookup"><span data-stu-id="aacad-152">Choose the **Clear** option to clear the events.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aacad-153">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="aacad-153">The samples may already be installed on your computer.</span></span> <span data-ttu-id="aacad-154">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="aacad-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="aacad-155">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="aacad-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="aacad-156">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="aacad-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ETWTracing`  
  
## <a name="see-also"></a><span data-ttu-id="aacad-157">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aacad-157">See also</span></span>

- <span data-ttu-id="aacad-158">[Образцы наблюдения за AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="aacad-158">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
