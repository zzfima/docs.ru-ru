---
title: Отслеживание использования с помощью текстового файла
ms.date: 03/30/2017
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
ms.openlocfilehash: aa59ab8304c68873c938f42fc585be883b234ecc
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="tracking-using-a-text-file"></a><span data-ttu-id="48532-102">Отслеживание использования с помощью текстового файла</span><span class="sxs-lookup"><span data-stu-id="48532-102">Tracking Using a Text File</span></span>
<span data-ttu-id="48532-103">В этом примере показано, как расширить отслеживание в Windows Workflow Foundation (WF) путем создания настраиваемого участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="48532-103">This sample demonstrates how to extend tracking in Windows Workflow Foundation (WF) by creating a custom tracking participant.</span></span> <span data-ttu-id="48532-104">Участниками отслеживания являются классы платформы .NET Framework, которые получают записи отслеживания от среды выполнения при их передаче.</span><span class="sxs-lookup"><span data-stu-id="48532-104">Tracking participants are .NET Framework classes that receive tracking records from the runtime as they are emitted.</span></span> <span data-ttu-id="48532-105">Можно создать участника отслеживания для транспортировки событий отслеживания в место назначения, требуемое для сценария.</span><span class="sxs-lookup"><span data-stu-id="48532-105">You can create a tracking participant to transport the tracking events to whichever destination is required for your scenario.</span></span> <span data-ttu-id="48532-106">Например, участник отслеживания событий для Windows (ETW) предоставляется как часть [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48532-106">For example, ETW (Event Tracing for Windows) Tracking Participant is provided as part of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="48532-107">Участник отслеживания в этом образце записывает записи в текстовый файл в формате XML.</span><span class="sxs-lookup"><span data-stu-id="48532-107">The tracking participant in this sample writes the records in XML format to a text file.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="48532-108">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="48532-108">Sample details</span></span>  
 <span data-ttu-id="48532-109">Для оптимизации применимости и надежности участника отслеживания должны быть выполнены некоторые шаги для правильного подключения участника отслеживания в среду выполнения.</span><span class="sxs-lookup"><span data-stu-id="48532-109">To optimize the usefulness and robustness of your tracking participant, some additional steps must be completed to properly wire the tracking participant to the runtime.</span></span> <span data-ttu-id="48532-110">В следующей таблице описываются классы, используемые в образце для создания участника отслеживания, который соответствует рекомендациям.</span><span class="sxs-lookup"><span data-stu-id="48532-110">The following table describes the classes used in this sample to create a tracking participant that complies with best practices.</span></span>  
  
|<span data-ttu-id="48532-111">Класс</span><span class="sxs-lookup"><span data-stu-id="48532-111">Class</span></span>|<span data-ttu-id="48532-112">Описание</span><span class="sxs-lookup"><span data-stu-id="48532-112">Description</span></span>|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|<span data-ttu-id="48532-113">Элемент <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> используется для определения раздела конфигурации, используемого для настройки участника отслеживания текстового файла.</span><span class="sxs-lookup"><span data-stu-id="48532-113">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> is used to define the configuration section used to configure the text file tracking participant.</span></span> <span data-ttu-id="48532-114">Это позволяет пользователям указывать место назначения файла журнала с помощью обычных файлов конфигурации платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48532-114">This allows users to specify the destination of the log file using standard .NET Framework configuration files.</span></span>|  
|`TextFileTrackingBehavior`|<span data-ttu-id="48532-115">Поведения в WCF позволяют пользователям внедрять расширения в среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="48532-115">Behaviors in WCF allow users to inject extensions into the runtime.</span></span> <span data-ttu-id="48532-116">Это поведение добавляет участника отслеживания к службе при ее запуске.</span><span class="sxs-lookup"><span data-stu-id="48532-116">This behavior adds the tracking participant to the service when the service starts.</span></span>|  
|`TextFileTrackingParticipant`|<span data-ttu-id="48532-117">Участник отслеживания, который получает участников отслеживания во время выполнения и сохраняет их в файле журнала как XML.</span><span class="sxs-lookup"><span data-stu-id="48532-117">The tracking participant that receives tracking participants at runtime and stores them to a log file as XML.</span></span>|  
  
## <a name="behavior-extension-elements-configuration"></a><span data-ttu-id="48532-118">Конфигурация элементов расширения поведения</span><span class="sxs-lookup"><span data-stu-id="48532-118">Behavior Extension Elements Configuration</span></span>  
 <span data-ttu-id="48532-119">Для использования элемента расширения поведения, описанного ранее с помощью файлов конфигурации .NET Framework, требуется выполнить еще один шаг.</span><span class="sxs-lookup"><span data-stu-id="48532-119">One more step is required to make use of the behavior extension element previously described using .NET Framework configuration files.</span></span> <span data-ttu-id="48532-120">Если должно использоваться расширение, в файлы конфигурации необходимо внести следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="48532-120">The following configuration must be placed in configuration files where the extension is to be used.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  <span data-ttu-id="48532-121">См. файл Web.config в образце полного примера использования конфигурации элементов расширения поведения.</span><span class="sxs-lookup"><span data-stu-id="48532-121">See the Web.config file in the sample for a complete example usage of behavior extension elements configuration.</span></span>  
  
## <a name="custom-tracking-records"></a><span data-ttu-id="48532-122">Пользовательские записи отслеживания</span><span class="sxs-lookup"><span data-stu-id="48532-122">Custom Tracking Records</span></span>  
 <span data-ttu-id="48532-123">Файл GetStockPrices.cs демонстрирует способ создания пользовательских записей отслеживания в <xref:System.Activities.CodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="48532-123">The GetStockPrices.cs file demonstrates how to create custom tracking records from within a <xref:System.Activities.CodeActivity>.</span></span> <span data-ttu-id="48532-124">При выполнении образца найдите эту запись.</span><span class="sxs-lookup"><span data-stu-id="48532-124">Look for this record when running the sample.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="48532-125">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="48532-125">To use this sample</span></span>  
  
1.  <span data-ttu-id="48532-126">Откройте файл решения WFStockPriceApplication.sln в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48532-126">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the WFStockPriceApplication.sln solution file.</span></span>  
  
2.  <span data-ttu-id="48532-127">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="48532-127">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="48532-128">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="48532-128">To run the solution, press CTRL+F5.</span></span>  
  
     <span data-ttu-id="48532-129">Откроется окно браузера со списком каталогов для приложения.</span><span class="sxs-lookup"><span data-stu-id="48532-129">The browser window opens and shows the directory listing for the application.</span></span>  
  
4.  <span data-ttu-id="48532-130">Щелкните файл StockPriceService.xamlx в браузере.</span><span class="sxs-lookup"><span data-stu-id="48532-130">In the browser, click StockPriceService.xamlx.</span></span>  
  
5.  <span data-ttu-id="48532-131">В браузере отображается **StockPriceService** страницы, содержащей адрес wsdl локальной службы.</span><span class="sxs-lookup"><span data-stu-id="48532-131">The browser displays the **StockPriceService** page, which contains the local service wsdl address.</span></span> <span data-ttu-id="48532-132">Скопируйте этот адрес.</span><span class="sxs-lookup"><span data-stu-id="48532-132">Copy this address.</span></span>  
  
     <span data-ttu-id="48532-133">Примером адреса wsdl локальной службы является http://localhost:53797/StockPriceService.xamlx?wsdl.</span><span class="sxs-lookup"><span data-stu-id="48532-133">An example of the local service wsdl address is http://localhost:53797/StockPriceService.xamlx?wsdl.</span></span>  
  
6.  <span data-ttu-id="48532-134">В [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] перейдите в папку [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (по умолчанию папкой установки является папка %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span><span class="sxs-lookup"><span data-stu-id="48532-134">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], go to your [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] folder (the default installation folder is %SystemDrive%\Program Files\Microsoft Visual Studio 10.0).</span></span> <span data-ttu-id="48532-135">Затем перейдите в подпапку Common7\IDE\.</span><span class="sxs-lookup"><span data-stu-id="48532-135">Then locate the Common7\IDE\ subfolder.</span></span>  
  
7.  <span data-ttu-id="48532-136">Дважды щелкните файл, чтобы запустить тестовый клиент WCF.</span><span class="sxs-lookup"><span data-stu-id="48532-136">Double-click the WcfTestClient.exe file to launch the WCF Test Client.</span></span>  
  
8.  <span data-ttu-id="48532-137">В тестовом клиенте WCF выберите **добавить службу...**</span><span class="sxs-lookup"><span data-stu-id="48532-137">In the WCF Test Client, select **Add Service…**</span></span> <span data-ttu-id="48532-138">из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="48532-138">from the **File** menu.</span></span>  
  
9. <span data-ttu-id="48532-139">Вставьте в текстовое поле только что скопированный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="48532-139">Paste the URL you just copied into the text box.</span></span>  
  
10. <span data-ttu-id="48532-140">Нажмите кнопку **ОК** чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="48532-140">Click **OK** to close the dialog.</span></span>  
  
11. <span data-ttu-id="48532-141">Проверьте службу с помощью тестового клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="48532-141">Test the service using the WCF Test Client.</span></span>  
  
    1.  <span data-ttu-id="48532-142">В тестовом клиенте WCF дважды щелкните **GetStockPrice()** под **IStockPriceService** узла.</span><span class="sxs-lookup"><span data-stu-id="48532-142">In the WCF Test Client, double-click **GetStockPrice()** under the **IStockPriceService** node.</span></span>  
  
         <span data-ttu-id="48532-143">**GetStockPrice()** метод отображается в правой области с одним параметром.</span><span class="sxs-lookup"><span data-stu-id="48532-143">The **GetStockPrice()** method appears in the right pane, with one parameter.</span></span>  
  
    2.  <span data-ttu-id="48532-144">Введите Contoso в качестве значения параметра.</span><span class="sxs-lookup"><span data-stu-id="48532-144">Type in Contoso as the value for the parameter.</span></span>  
  
    3.  <span data-ttu-id="48532-145">Нажмите кнопку **вызова**.</span><span class="sxs-lookup"><span data-stu-id="48532-145">Click **Invoke**.</span></span>  
  
12. <span data-ttu-id="48532-146">Просмотрите отслеживаемые события в файле журнала, расположенном в каталоге данных приложения: %APPDATA%\trackingRecords.log.</span><span class="sxs-lookup"><span data-stu-id="48532-146">See the tracked events in the log file located in your application data directory at %APPDATA%\trackingRecords.log.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48532-147">% APPDATA % является переменной среды, которая разрешает %SystemDrive%\Users\\< имя_пользователя\>\AppData\Roaming в [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], или Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="48532-147">The %APPDATA% is an environment variable that resolves to %SystemDrive%\Users\\<username\>\AppData\Roaming in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], or Windows Server 2008.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="48532-148">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="48532-148">The samples may already be installed on your computer.</span></span> <span data-ttu-id="48532-149">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="48532-149">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="48532-150">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцов.</span><span class="sxs-lookup"><span data-stu-id="48532-150">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="48532-151">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="48532-151">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a><span data-ttu-id="48532-152">См. также</span><span class="sxs-lookup"><span data-stu-id="48532-152">See Also</span></span>  
 [<span data-ttu-id="48532-153">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="48532-153">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
