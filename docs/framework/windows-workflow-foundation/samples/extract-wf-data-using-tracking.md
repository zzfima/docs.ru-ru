---
title: Извлечение данных WF с использованием отслеживания
ms.date: 03/30/2017
ms.assetid: e30c68f5-8c6a-495a-bd20-667a4364c68e
ms.openlocfilehash: 22b147521d4ce0c72fadfb7adc81e05f10ce52b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="extract-wf-data-using-tracking"></a><span data-ttu-id="30645-102">Извлечение данных WF с использованием отслеживания</span><span class="sxs-lookup"><span data-stu-id="30645-102">Extract WF Data using Tracking</span></span>
<span data-ttu-id="30645-103">Этот образец демонстрирует использование отслеживания рабочего процесса для получения переменных и аргументов рабочего процесса из действий.</span><span class="sxs-lookup"><span data-stu-id="30645-103">This sample demonstrates how to use workflow tracking to extract workflow variables and arguments from activities.</span></span> <span data-ttu-id="30645-104">Также показывается добавление заметок к записям отслеживания и извлечение полезной нагрузки данных из пользовательских записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-104">It also shows the addition of annotations to tracking records and the extraction of data payload within custom tracking records.</span></span> <span data-ttu-id="30645-105">В этом образце для извлечения данных из рабочего процесса используется участник отслеживания трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="30645-105">The sample uses the Event Tracing for Windows (ETW) tracking participant to extract data from the workflow.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="30645-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="30645-106">Sample Details</span></span>  
 <span data-ttu-id="30645-107">Windows Workflow Foundation (WF) предоставляет отслеживание для обеспечения видимости выполнения экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="30645-107">Windows Workflow Foundation (WF) provides tracking to gain visibility into the execution of a workflow instance.</span></span> <span data-ttu-id="30645-108">Среда выполнения отслеживания выдает записи отслеживания рабочего процесса в ходе его выполнения.</span><span class="sxs-lookup"><span data-stu-id="30645-108">The tracking runtime emits workflow tracking records during the execution of the workflow.</span></span> <span data-ttu-id="30645-109">Помимо записей отслеживания рабочего процесса, из рабочего процесса можно извлекать данные, имеющиеся в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="30645-109">Along with the workflow tracking records, data within the workflow instance can be extracted from the workflow.</span></span> <span data-ttu-id="30645-110">В следующем списке приводятся сведения о типах данных, которые могут быть извлечены из записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-110">The following list details the types of data that can be extracted from tracking records:</span></span>  
  
1.  <span data-ttu-id="30645-111">Переменные рабочего процесса из действия и записей отслеживания во время выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="30645-111">Workflow variables within an activity and tracking records during activity execution.</span></span>  
  
     <span data-ttu-id="30645-112">Для извлечения переменных рабочего процесса все переменные, подлежащие извлечению, указываются в профиле.</span><span class="sxs-lookup"><span data-stu-id="30645-112">To extract workflow variables, the variables to be extracted are specified in a profile.</span></span> <span data-ttu-id="30645-113">Извлекаемые переменные могут быть указаны только с использованием `ActivityStateQueries`.</span><span class="sxs-lookup"><span data-stu-id="30645-113">Variables to be extracted can only be specified with `ActivityStateQueries`.</span></span> <span data-ttu-id="30645-114">Следующий пример кода показывает профиль отслеживания, используемый для извлечения переменной рабочего процесса из действия.</span><span class="sxs-lookup"><span data-stu-id="30645-114">The following code example demonstrates a tracking profile used to extract the workflow variable from an activity.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="StockPriceService">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <variables>  
              <variable name="symbol"/>  
         </variables>  
    </activityStateQuery>  
    ```  
  
2.  <span data-ttu-id="30645-115">Аргументы действия и записи отслеживания состояния действия.</span><span class="sxs-lookup"><span data-stu-id="30645-115">Activity arguments and activity state tracking records.</span></span>  
  
     <span data-ttu-id="30645-116">Аргументы определяют то, как данные попадают в действие и выходят из него.</span><span class="sxs-lookup"><span data-stu-id="30645-116">Arguments define the way data flows in or out of an activity.</span></span> <span data-ttu-id="30645-117">Извлекаемые аргументы задаются с использованием <xref:System.Activities.Tracking.ActivityStateQuery>. Следующий пример кода является профилем отслеживания, извлекающим аргумент `Value`.</span><span class="sxs-lookup"><span data-stu-id="30645-117">Arguments to be extracted are specified using an <xref:System.Activities.Tracking.ActivityStateQuery>.The following code example is a tracking profile that extracts the `Value` argument.</span></span>  
  
    ```xml  
    <activityStateQuery activityName="GetStockPrice">  
         <states>  
              <state name="Closed"/>  
         </states>  
         <arguments>  
              <argument name="Value"/>  
         </arguments>  
    </activityStateQuery>  
    ```  
  
3.  <span data-ttu-id="30645-118">Заметки - это пары «ключ-значение», которые можно добавить к любой выдаваемой записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-118">Annotations are key/value pairs that can be added to any tracking record that is emitted.</span></span>  
  
     <span data-ttu-id="30645-119">С помощью заметок записи отслеживания помечаются.</span><span class="sxs-lookup"><span data-stu-id="30645-119">Annotations serve as a tagging mechanism for tracking records.</span></span> <span data-ttu-id="30645-120">Заметки добавляются к записям отслеживания через профиль отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-120">Annotations are added to tracking records through a tracking profile.</span></span> <span data-ttu-id="30645-121">Заметки можно добавлять к запросу отслеживания рабочего процесса любого типа.</span><span class="sxs-lookup"><span data-stu-id="30645-121">Annotations can be added to any type of a workflow tracking query.</span></span> <span data-ttu-id="30645-122">Следующий пример кода является профилем отслеживания, показывающим добавление заметки к записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-122">The following code example is a tracking profile that shows how an annotation can be added to a tracking record.</span></span>  
  
    ```xml  
    <workflowInstanceQuery>  
         <states>  
              <state name="Started"/>  
         </states>  
         <annotations>  
              <annotation name="StockPriceWorkflow" value="Begin"/>  
         </annotations>  
    </workflowInstanceQuery>  
    ```  
  
4.  <span data-ttu-id="30645-123">Пользовательские записи отслеживания выдаются пользовательскими действиями.</span><span class="sxs-lookup"><span data-stu-id="30645-123">Custom tracking records are emitted from user-defined activities.</span></span>  
  
     <span data-ttu-id="30645-124">Пользовательские записи отслеживания могут переносить полезные данные, определенные в этом действии.</span><span class="sxs-lookup"><span data-stu-id="30645-124">Custom tracking records can carry payload data defined within this activity.</span></span> <span data-ttu-id="30645-125">Подписка на пользовательские записи отслеживания в профиле отслеживания позволяет извлекать полезные данные из записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="30645-125">Subscribing for custom tracking records in a tracking profile allows the extraction of the payload within the tracking record.</span></span> <span data-ttu-id="30645-126">Пользовательские записи отслеживания могут быть извлечены с помощью пользовательского запроса <xref:System.Activities.Tracking.TrackingQuery>.</span><span class="sxs-lookup"><span data-stu-id="30645-126">The custom tracking records can be extracted with custom a <xref:System.Activities.Tracking.TrackingQuery>.</span></span> <span data-ttu-id="30645-127">Следующий пример кода - это профиль отслеживания, извлекающий пользовательскую запись отслеживания вместе с ее полезными данными.</span><span class="sxs-lookup"><span data-stu-id="30645-127">The following code example is a tracking profile that extracts a custom tracking record along with its payload.</span></span>  
  
    ```xml  
    <customTrackingQuery name="QuoteLookupEvent" activityName="GetStockPrice"/>  
    ```  
  
 <span data-ttu-id="30645-128">Этот образец демонстрирует извлечение переменных, аргументов, пользовательских записей, а также добавление заметок с помощью профиля, заданного в файле Web.config. Отслеживание включается в образце службы рабочего процесса путем добавления элемента поведения `<etwTracking>`.</span><span class="sxs-lookup"><span data-stu-id="30645-128">The sample demonstrates the extraction of a variables, arguments, custom records and adding annotations using a profile specified in a Web.config. Tracking is enabled on the sample workflow service by adding an `<etwTracking>` behavior element.</span></span> <span data-ttu-id="30645-129">Следующий пример кода включает отслеживание для профиля отслеживания `ExtractWorkflowVariables`.</span><span class="sxs-lookup"><span data-stu-id="30645-129">The following code example enables tracking for the `ExtractWorkflowVariables` tracking profile.</span></span>  
  
```xml  
<serviceBehaviors>  
     <behavior>  
               <etwTracking profileName="ExtractWorkflowVariables"/>  
     </behavior>  
</serviceBehaviors>  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="30645-130">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="30645-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="30645-131">Откройте файл решения WFStockPriceApplication.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30645-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="30645-132">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="30645-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="30645-133">Чтобы запустить решение, нажмите клавишу F5.</span><span class="sxs-lookup"><span data-stu-id="30645-133">To run the solution, press F5.</span></span>  
  
     <span data-ttu-id="30645-134">Откроется окно браузера со списком каталогов для приложения.</span><span class="sxs-lookup"><span data-stu-id="30645-134">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="30645-135">Щелкните файл StockPriceService.xamlx в браузере.</span><span class="sxs-lookup"><span data-stu-id="30645-135">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="30645-136">В браузере отображается страница StockPriceService, содержащая адрес WSDL локальной службы.</span><span class="sxs-lookup"><span data-stu-id="30645-136">The browser displays the StockPriceService page, which contains the local service WSDL address.</span></span> <span data-ttu-id="30645-137">Скопируйте этот адрес.</span><span class="sxs-lookup"><span data-stu-id="30645-137">Copy this address.</span></span>  
  
     <span data-ttu-id="30645-138">В следующем примере показывается адрес WSDL локальной службы.</span><span class="sxs-lookup"><span data-stu-id="30645-138">The following example shows a local service WSDL address.</span></span> `http://localhost:53797/StockPriceService.xamlx?wsdl`  
  
6.  <span data-ttu-id="30645-139">Перед запуском службы запустите средство просмотра событий и убедитесь, что журнал событий ожидает получение событий отслеживания от службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="30645-139">Before invoking the service, start Event Viewer and ensure that the event log is listening for tracking events emitted from the workflow service.</span></span>  
  
7.  <span data-ttu-id="30645-140">Из **запустить** последовательно выберите пункты **Администрирование** и затем **средство просмотра событий**.</span><span class="sxs-lookup"><span data-stu-id="30645-140">From the **Start** menu, select **Administrative Tools** and then **Event Viewer**.</span></span>  
  
8.  <span data-ttu-id="30645-141">В представлении дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, и **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="30645-141">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, and **Microsoft**.</span></span> <span data-ttu-id="30645-142">Щелкните правой кнопкой мыши **Microsoft** и выберите **представление** и затем **Отобразить аналитический и отладочный журналы**.</span><span class="sxs-lookup"><span data-stu-id="30645-142">Right-click **Microsoft** and select **View** and then **Show Analytic and Debug Logs**.</span></span>  
  
     <span data-ttu-id="30645-143">Убедитесь, что **Отобразить аналитический и отладочный журналы** флажок.</span><span class="sxs-lookup"><span data-stu-id="30645-143">Ensure that the **Show Analytic and Debug Logs** option is checked.</span></span>  
  
9. <span data-ttu-id="30645-144">В представлении дерева в средстве просмотра событий перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**,  **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="30645-144">In the tree view in Event Viewer, navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="30645-145">Щелкните правой кнопкой мыши **аналитический** и выберите **включить журнал**.</span><span class="sxs-lookup"><span data-stu-id="30645-145">Right-click **Analytic** and select **Enable Log**.</span></span>  
  
10. <span data-ttu-id="30645-146">С помощью [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] откройте тестовый клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="30645-146">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], open the WCF test client.</span></span>  
  
     <span data-ttu-id="30645-147">Тестовый клиент WCF (WcfTestClient.exe) расположен в \< [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] папка установки > \Common7\IDE\ папки.</span><span class="sxs-lookup"><span data-stu-id="30645-147">The WCF test client (WcfTestClient.exe) is located in the \<[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder>\Common7\IDE\ folder.</span></span>  
  
     <span data-ttu-id="30645-148">По умолчанию папка установки [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] имеет вид C:\Program Files\Microsoft Visual Studio 10.0.</span><span class="sxs-lookup"><span data-stu-id="30645-148">The default [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] installation folder is C:\Program Files\Microsoft Visual Studio 10.0.</span></span>  
  
11. <span data-ttu-id="30645-149">В тестовом клиенте WCF выберите **добавить службу** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="30645-149">In WCF test client, select **Add Service** from the **File** menu.</span></span>  
  
     <span data-ttu-id="30645-150">Вставьте скопированный ранее адрес WSDL локальной службы в поле ввода.</span><span class="sxs-lookup"><span data-stu-id="30645-150">Add the local service WSDL address you copied earlier in the input box.</span></span>  
  
12. <span data-ttu-id="30645-151">В тестовом клиенте WCF дважды щелкните `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="30645-151">In WCF test client, double-click `GetStockPrice`.</span></span>  
  
     <span data-ttu-id="30645-152">Откроется метод `GetStockPrice`.</span><span class="sxs-lookup"><span data-stu-id="30645-152">This opens the `GetStockPrice` method.</span></span> <span data-ttu-id="30645-153">Запрос принимает один параметр.</span><span class="sxs-lookup"><span data-stu-id="30645-153">The request accepts one parameter.</span></span> <span data-ttu-id="30645-154">Используйте значение **Contoso**.</span><span class="sxs-lookup"><span data-stu-id="30645-154">Use the value **Contoso**.</span></span>  
  
13. <span data-ttu-id="30645-155">Нажмите кнопку **вызова**.</span><span class="sxs-lookup"><span data-stu-id="30645-155">Click **Invoke**.</span></span>  
  
14. <span data-ttu-id="30645-156">Вернитесь в средство просмотра событий и перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**,  **Сервер приложений-приложения**.</span><span class="sxs-lookup"><span data-stu-id="30645-156">Switch back to Event Viewer and navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="30645-157">Щелкните правой кнопкой мыши **аналитический** и выберите **обновление**.</span><span class="sxs-lookup"><span data-stu-id="30645-157">Right-click **Analytic** and select **Refresh**.</span></span> <span data-ttu-id="30645-158">События рабочего процесса находятся в диапазонах идентификатора события 100–199.</span><span class="sxs-lookup"><span data-stu-id="30645-158">The workflow events are in the event ID ranges 100-199.</span></span>  
  
     <span data-ttu-id="30645-159">События содержат заметки, переменные, аргументы и пользовательские записи отслеживания, которые можно просматривать в средстве просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="30645-159">The events contain the annotations, variables, arguments and custom tracking records that can be viewed in the event viewer.</span></span>  
  
## <a name="cleaning-up-in-the-event-viewer"></a><span data-ttu-id="30645-160">Очистка в средстве просмотра событий</span><span class="sxs-lookup"><span data-stu-id="30645-160">Cleaning up in the Event Viewer</span></span>  
 <span data-ttu-id="30645-161">Канал аналитики в журнале событий можно очистить в средстве просмотра событий с помощью следующих действий.</span><span class="sxs-lookup"><span data-stu-id="30645-161">The analytic channel in the event log can be cleaned up in the Event Viewer by doing the following.</span></span>  
  
#### <a name="to-clean-up-optional"></a><span data-ttu-id="30645-162">Очистка (необязательно)</span><span class="sxs-lookup"><span data-stu-id="30645-162">To clean up (Optional)</span></span>  
  
1.  <span data-ttu-id="30645-163">Откройте средство просмотра событий.</span><span class="sxs-lookup"><span data-stu-id="30645-163">Open Event Viewer.</span></span>  
  
2.  <span data-ttu-id="30645-164">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, **приложения Серверные приложения**.</span><span class="sxs-lookup"><span data-stu-id="30645-164">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="30645-165">Щелкните правой кнопкой мыши **аналитический** и выберите **отключить журнал**.</span><span class="sxs-lookup"><span data-stu-id="30645-165">Right-click **Analytic** and select **Disable Log**.</span></span>  
  
3.  <span data-ttu-id="30645-166">Перейдите к **средство просмотра событий**, **журналы приложений и служб**, **Microsoft**, **Windows**, **приложения Серверные приложения**.</span><span class="sxs-lookup"><span data-stu-id="30645-166">Navigate to **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="30645-167">Щелкните правой кнопкой мыши **аналитический** и выберите **очистить журнал**.</span><span class="sxs-lookup"><span data-stu-id="30645-167">Right-click **Analytic** and select **Clear Log**.</span></span>  
  
     <span data-ttu-id="30645-168">Выберите **снимите** параметр, чтобы очистить события.</span><span class="sxs-lookup"><span data-stu-id="30645-168">Choose the **Clear** option to clear the events.</span></span>  
  
## <a name="known-issue"></a><span data-ttu-id="30645-169">Известная проблема</span><span class="sxs-lookup"><span data-stu-id="30645-169">Known Issue</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30645-170">В средстве просмотра событий есть известная проблема, связанная с ошибкой декодирования событий трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="30645-170">There is a known issue in the Event Viewer where it may fail to decode ETW events.</span></span> <span data-ttu-id="30645-171">Может выводиться следующее сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="30645-171">You may see an error message that looks like the following.</span></span>  
>   
>  `The description for Event ID <id> from source Microsoft-Windows-Application Server-Applications cannot be found. Either the component that raises this event is not installed on your local computer or the installation is corrupted. You can install or repair the component on the local computer.`  
>   
>  <span data-ttu-id="30645-172">Если эта ошибка возникает, нажмите кнопку **обновление** в области действия.</span><span class="sxs-lookup"><span data-stu-id="30645-172">If you encounter this error, click **Refresh** in the actions pane.</span></span> <span data-ttu-id="30645-173">Теперь декодирование события должно выполняться правильно.</span><span class="sxs-lookup"><span data-stu-id="30645-173">The event should now decode properly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30645-174">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="30645-174">The samples may already be installed on your computer.</span></span> <span data-ttu-id="30645-175">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="30645-175">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="30645-176">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="30645-176">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="30645-177">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="30645-177">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\ExtractWfData`  
  
## <a name="see-also"></a><span data-ttu-id="30645-178">См. также</span><span class="sxs-lookup"><span data-stu-id="30645-178">See Also</span></span>  
 [<span data-ttu-id="30645-179">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="30645-179">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
