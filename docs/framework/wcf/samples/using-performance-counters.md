---
title: Использование счетчиков производительности
ms.date: 03/30/2017
ms.assetid: 00a787af-1876-473c-a48d-f52b51e28a3f
ms.openlocfilehash: 3e0a0199e93abe1218f7d9c052807cb94e911140
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716703"
---
# <a name="using-performance-counters"></a><span data-ttu-id="43b8c-102">Использование счетчиков производительности</span><span class="sxs-lookup"><span data-stu-id="43b8c-102">Using Performance Counters</span></span>
<span data-ttu-id="43b8c-103">В этом образце показано, как получить доступ к счетчикам производительности Windows Communication Foundation (WCF) и как создавать определяемые пользователем счетчики производительности.</span><span class="sxs-lookup"><span data-stu-id="43b8c-103">This sample demonstrates how to access Windows Communication Foundation (WCF) performance counters and how to create user-defined performance counters.</span></span> <span data-ttu-id="43b8c-104">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="43b8c-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="43b8c-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="43b8c-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="43b8c-106">В этом образце клиент вызывает четыре метода службы `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="43b8c-106">In this sample, the client calls the four methods of the `ICalculator` service.</span></span> <span data-ttu-id="43b8c-107">Вызов данных методов осуществляется клиентом до тех пор, пока не будет прерван пользователем.</span><span class="sxs-lookup"><span data-stu-id="43b8c-107">The client continues to do this until it is interrupted by the user.</span></span> <span data-ttu-id="43b8c-108">Служба остается неизменной.</span><span class="sxs-lookup"><span data-stu-id="43b8c-108">The service remains unchanged.</span></span>  
  
 <span data-ttu-id="43b8c-109">Счетчики производительности включаются в разделе diagnostics файла Web.config службы, как показано в следующем образце конфигурации.</span><span class="sxs-lookup"><span data-stu-id="43b8c-109">Performance counters are enabled in the diagnostics section of the Web.config file for the service, as shown in the following sample configuration.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics performanceCounters="All" />   
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="43b8c-110">Эту задачу можно также выполнить с помощью [средства редактора конфигурации (SvcConfigEditor. exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="43b8c-110">This task can also be done using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).</span></span>  
  
 <span data-ttu-id="43b8c-111">Если счетчики производительности включены, для службы включается весь набор счетчиков производительности WCF.</span><span class="sxs-lookup"><span data-stu-id="43b8c-111">When performance counters are enabled, the entire suite of WCF performance counters is enabled for the service.</span></span> <span data-ttu-id="43b8c-112">Платформа .NET Framework автоматически поддерживает данные о производительности на трех уровнях: `ServiceModelService`, `ServiceModelEndpoint` и `ServiceModelOperation`.</span><span class="sxs-lookup"><span data-stu-id="43b8c-112">The .NET Framework automatically maintains performance data at three levels: `ServiceModelService`, `ServiceModelEndpoint` and `ServiceModelOperation`.</span></span> <span data-ttu-id="43b8c-113">На каждом из этих уровней имеются счетчики производительности, например "Calls", "Calls per Second" и "Security Calls Not Authorized".</span><span class="sxs-lookup"><span data-stu-id="43b8c-113">Each of these levels has performance counters such as "Calls", "Calls per Second", and "Security Calls Not Authorized".</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="43b8c-114">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="43b8c-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="43b8c-115">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="43b8c-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="43b8c-116">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="43b8c-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="43b8c-117">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="43b8c-117">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
### <a name="to-view-performance-data"></a><span data-ttu-id="43b8c-118">Просмотр данных о производительности</span><span class="sxs-lookup"><span data-stu-id="43b8c-118">To view performance data</span></span>  
  
1. <span data-ttu-id="43b8c-119">Запустите средство "монитор производительности", нажав кнопку **Пуск**, **выполните...** , введите `perfmon` и нажмите кнопку **ОК,** а затем на панели управления выберите пункт **Администрирование** и дважды щелкните элемент **производительность**.</span><span class="sxs-lookup"><span data-stu-id="43b8c-119">Start the Performance Monitor Tool by clicking **Start**, **Run…**, enter `perfmon` and click **OK,** or from Control Panel, select **Administrative Tools** and double-click **Performance**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43b8c-120">Пока не начнется выполнение кода образца, добавить счетчики невозможно.</span><span class="sxs-lookup"><span data-stu-id="43b8c-120">You cannot add counters until the sample code is running.</span></span>  
  
2. <span data-ttu-id="43b8c-121">Удалите доступные счетчики производительности, выбирая их и нажимая клавишу DELETE.</span><span class="sxs-lookup"><span data-stu-id="43b8c-121">Remove the performance counters that are listed by selecting them and pressing the Delete key.</span></span>  
  
3. <span data-ttu-id="43b8c-122">Добавьте счетчики WCF, щелкнув правой кнопкой мыши панель графа и выбрав пункт **Добавить счетчики**.</span><span class="sxs-lookup"><span data-stu-id="43b8c-122">Add WCF counters by right-clicking the graph pane and selecting **Add Counters**.</span></span> <span data-ttu-id="43b8c-123">В диалоговом окне **Добавление счетчиков** выберите **Сервицемоделоператион 3.0.0.0, Сервицемоделендпоинт 3.0.0.0 или сервицемоделсервице 3.0.0.0** в раскрывающемся списке Объект производительности.</span><span class="sxs-lookup"><span data-stu-id="43b8c-123">In the **Add Counters** dialog box, select **ServiceModelOperation 3.0.0.0, ServiceModelEndpoint 3.0.0.0, or ServiceModelService 3.0.0.0** in the Performance object drop down list box.</span></span> <span data-ttu-id="43b8c-124">Выберите в списке нужные счетчики.</span><span class="sxs-lookup"><span data-stu-id="43b8c-124">Select the counters you want to view from the list.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="43b8c-125">Нет счетчиков производительности WCF для службы, если на компьютере не выполняются службы WCF.</span><span class="sxs-lookup"><span data-stu-id="43b8c-125">There are no WCF performance counters for a service if there are no WCF services running on the computer.</span></span>  
  
### <a name="to-use-the-configuration-editor-to-enable-counters"></a><span data-ttu-id="43b8c-126">Включение счетчиков с помощью редактора конфигураций</span><span class="sxs-lookup"><span data-stu-id="43b8c-126">To use the Configuration Editor to enable counters</span></span>  
  
1. <span data-ttu-id="43b8c-127">Откройте экземпляр программы SvcConfigEditor.exe.</span><span class="sxs-lookup"><span data-stu-id="43b8c-127">Open an instance of the SvcConfigEditor.exe.</span></span>  
  
2. <span data-ttu-id="43b8c-128">В меню Файл выберите команду **Открыть** , а затем щелкните **файл конфигурации.** ...</span><span class="sxs-lookup"><span data-stu-id="43b8c-128">On the File menu, click **Open** and then click **Config file…**.</span></span>  
  
3. <span data-ttu-id="43b8c-129">Перейдите в папку службы примера приложения и откройте файл Web.config.</span><span class="sxs-lookup"><span data-stu-id="43b8c-129">Navigate to the sample application's service folder and open the Web.config file.</span></span>  
  
4. <span data-ttu-id="43b8c-130">Щелкните **Диагностика** в дереве конфигурации.</span><span class="sxs-lookup"><span data-stu-id="43b8c-130">Click **Diagnostics** on the Configuration tree.</span></span>  
  
5. <span data-ttu-id="43b8c-131">Чтобы отобразить "все", переключите **Счетчик производительности** в окне " **Диагностика** ".</span><span class="sxs-lookup"><span data-stu-id="43b8c-131">Toggle **Performance Counter** in the **Diagnostics** window to show 'All'.</span></span>  
  
6. <span data-ttu-id="43b8c-132">Сохраните файл конфигурации и закройте редактор.</span><span class="sxs-lookup"><span data-stu-id="43b8c-132">Save the configuration file and exit the editor.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="43b8c-133">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="43b8c-133">The samples may already be installed on your computer.</span></span> <span data-ttu-id="43b8c-134">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="43b8c-134">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="43b8c-135">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="43b8c-135">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="43b8c-136">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="43b8c-136">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\PerfCounters`  
  
## <a name="see-also"></a><span data-ttu-id="43b8c-137">См. также:</span><span class="sxs-lookup"><span data-stu-id="43b8c-137">See also</span></span>

- [<span data-ttu-id="43b8c-138">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="43b8c-138">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
