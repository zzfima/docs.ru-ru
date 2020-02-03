---
title: Трассировка ETW
ms.date: 03/30/2017
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
ms.openlocfilehash: a62403e61e0566d5e7b753ff951bf4b316209b6f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742109"
---
# <a name="etw-tracing"></a><span data-ttu-id="30d42-102">Трассировка ETW</span><span class="sxs-lookup"><span data-stu-id="30d42-102">ETW Tracing</span></span>
<span data-ttu-id="30d42-103">В этом примере показано, как реализовать сквозную трассировку (E2E) с помощью трассировки событий для Windows (трассировка событий Windows) и `ETWTraceListener`, предоставляемого с этим примером.</span><span class="sxs-lookup"><span data-stu-id="30d42-103">This sample demonstrates how to implement End-to-End (E2E) tracing using Event Tracing for Windows (ETW) and the `ETWTraceListener` that is provided with this sample.</span></span> <span data-ttu-id="30d42-104">Образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает трассировку ETW.</span><span class="sxs-lookup"><span data-stu-id="30d42-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes ETW tracing.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30d42-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="30d42-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="30d42-106">В этом примере предполагается, что вы знакомы с [трассировкой и ведением журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="30d42-106">This sample assumes that you are familiar with [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="30d42-107">Каждый источник трассировки в модели трассировки <xref:System.Diagnostics> может иметь несколько прослушивателей трассировки, которые определяют место и способ трассировки данных.</span><span class="sxs-lookup"><span data-stu-id="30d42-107">Each trace source in the <xref:System.Diagnostics> tracing model can have multiple trace listeners that determine where and how the data is traced.</span></span> <span data-ttu-id="30d42-108">Тип прослушивателя определяет формат записи данных трассировки в журнал.</span><span class="sxs-lookup"><span data-stu-id="30d42-108">The type of listener defines the format in which trace data is logged.</span></span> <span data-ttu-id="30d42-109">В следующем образце кода показано, как добавить прослушиватель в конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="30d42-109">The following code sample shows how to add the listener to configuration.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 <span data-ttu-id="30d42-110">Перед использованием этого прослушивателя необходимо запустить сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="30d42-110">Before using this listener, an ETW Trace Session must be started.</span></span> <span data-ttu-id="30d42-111">Этот сеанс может быть запущен с помощью программ Logman.exe или Tracelog.exe.</span><span class="sxs-lookup"><span data-stu-id="30d42-111">This session can be started by using Logman.exe or Tracelog.exe.</span></span> <span data-ttu-id="30d42-112">В этот образец включен файл SetupETW.bat, поэтому можно настроить сеанс трассировки событий Windows вместе с файлом CleanupETW.bat для закрытия сеанса и завершения выполнения файла журнала.</span><span class="sxs-lookup"><span data-stu-id="30d42-112">A SetupETW.bat file is included with this sample so that you can set up the ETW Trace Session along with a CleanupETW.bat file for closing the session and completing the log file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="30d42-113">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="30d42-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span> <span data-ttu-id="30d42-114">Дополнительные сведения об этих средствах см. в разделе <https://go.microsoft.com/fwlink/?LinkId=56580></span><span class="sxs-lookup"><span data-stu-id="30d42-114">For more information about these tools, see <https://go.microsoft.com/fwlink/?LinkId=56580></span></span>  
  
 <span data-ttu-id="30d42-115">При использовании ETWTraceListener трассировки заносятся в журнал в двоичных файлах с расширением ETL.</span><span class="sxs-lookup"><span data-stu-id="30d42-115">When using the ETWTraceListener, traces are logged in binary .etl files.</span></span> <span data-ttu-id="30d42-116">Если трассировка ServiceModel включена, все созданные трассировки отображаются в одном и том же файле.</span><span class="sxs-lookup"><span data-stu-id="30d42-116">With ServiceModel tracing turned on, all generated traces appear in the same file.</span></span> <span data-ttu-id="30d42-117">Используйте [средство Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра файлов журнала ETL и SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="30d42-117">Use [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) for viewing .etl and .svclog log files.</span></span> <span data-ttu-id="30d42-118">Средство просмотра создает сквозное представление системы, позволяющее выполнять трассировку сообщения на пути от источника в место назначения и точку потребления.</span><span class="sxs-lookup"><span data-stu-id="30d42-118">The viewer creates an end-to-end view of the system that makes it possible to trace a message from its source to its destination and point of consumption.</span></span>  
  
 <span data-ttu-id="30d42-119">Прослушиватель трассировки событий Windows поддерживает циклическое ведение журнала.</span><span class="sxs-lookup"><span data-stu-id="30d42-119">The ETW Trace Listener supports circular logging.</span></span> <span data-ttu-id="30d42-120">Чтобы включить эту функцию, последовательно выберите **Пуск**, **выполнить** и введите `cmd`, чтобы запустить консоль командной строки.</span><span class="sxs-lookup"><span data-stu-id="30d42-120">To enable this feature, go to **Start**, **Run** and type `cmd` to start a command console.</span></span> <span data-ttu-id="30d42-121">В следующей команде замените параметр `<logfilename>` на имя требуемого файла журнала.</span><span class="sxs-lookup"><span data-stu-id="30d42-121">In the following command, replace the `<logfilename>` parameter with the name of your log file.</span></span>  
  
```console  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 <span data-ttu-id="30d42-122">Коммутаторы `-f` и `-max` необязательны.</span><span class="sxs-lookup"><span data-stu-id="30d42-122">The `-f` and `-max` switches are optional.</span></span> <span data-ttu-id="30d42-123">Они указывают двоичный циклический формат и максимальный размер журнала (1000 МБ) соответственно.</span><span class="sxs-lookup"><span data-stu-id="30d42-123">They specify the binary circular format and max log size of 1000MB respectively.</span></span> <span data-ttu-id="30d42-124">Коммутатор `-p` используется для указания поставщика трассировки.</span><span class="sxs-lookup"><span data-stu-id="30d42-124">The `-p` switch is used to specify the trace provider.</span></span> <span data-ttu-id="30d42-125">В этом примере `"{411a0819-c24b-428c-83e2-26b41091702e}"` является идентификатором GUID для примера поставщика трассировки событий Windows XML.</span><span class="sxs-lookup"><span data-stu-id="30d42-125">In our example, `"{411a0819-c24b-428c-83e2-26b41091702e}"` is the GUID for "XML ETW Sample Provider".</span></span>  
  
 <span data-ttu-id="30d42-126">Для запуска сеанса введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="30d42-126">To start the session, type in the following command.</span></span>  
  
```console  
logman start Wcf  
```  
  
 <span data-ttu-id="30d42-127">По завершении ведения журнала можно остановить сеанс с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="30d42-127">After you have finished logging, you can stop the session with the following command.</span></span>  
  
```console  
logman stop Wcf  
```  
  
 <span data-ttu-id="30d42-128">Этот процесс создает двоичные циклические журналы, которые можно обработать с помощью выбранного инструмента, включая [средство Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) или Tracerpt.</span><span class="sxs-lookup"><span data-stu-id="30d42-128">This process generates binary circular logs that you can process with your tool of choice, including [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) or Tracerpt.</span></span>  
  
 <span data-ttu-id="30d42-129">Вы также можете ознакомиться с примером [циклической трассировки](../../../../docs/framework/wcf/samples/circular-tracing.md) для получения дополнительных сведений о альтернативном прослушивателе для выполнения циклического ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="30d42-129">You can also review the [Circular Tracing](../../../../docs/framework/wcf/samples/circular-tracing.md) sample for more information on an alternative listener to perform circular logging.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="30d42-130">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="30d42-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="30d42-131">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30d42-131">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="30d42-132">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30d42-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="30d42-133">Для запуска команд RegisterProvider.bat, SetupETW.bat и CleanupETW.bat необходимо использовать учетную запись локального администратора.</span><span class="sxs-lookup"><span data-stu-id="30d42-133">To use the RegisterProvider.bat, SetupETW.bat and CleanupETW.bat commands, you must run under a local administrator account.</span></span> <span data-ttu-id="30d42-134">При использовании Windows Vista или более поздней версии необходимо также запустить командную строку с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="30d42-134">If you are using Windows Vista or later, you must also run the command prompt with elevated privileges.</span></span> <span data-ttu-id="30d42-135">Для этого щелкните правой кнопкой мыши значок командной строки и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="30d42-135">To do so, right-click the command prompt icon, then click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="30d42-136">Перед выполнением примера запустите файл RegisterProvider.bat на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="30d42-136">Before running the sample, run RegisterProvider.bat on the client and server.</span></span> <span data-ttu-id="30d42-137">При этом выполняется настройка получаемого файла ETWTracingSampleLog.etl для создания трассировок, которые можно считать с помощью программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="30d42-137">This sets up the resulting ETWTracingSampleLog.etl file to generate traces that can be read by the Service Trace Viewer.</span></span> <span data-ttu-id="30d42-138">Этот файл можно найти в папке C:\logs.</span><span class="sxs-lookup"><span data-stu-id="30d42-138">This file can be found in the C:\logs folder.</span></span> <span data-ttu-id="30d42-139">Если эта папка не существует, ее необходимо создать, в противном случае трассировки создаваться не будут.</span><span class="sxs-lookup"><span data-stu-id="30d42-139">If this folder does not exist, it must be created or no traces are generated.</span></span> <span data-ttu-id="30d42-140">Затем запустите файл SetupETW.bat на клиентском и серверном компьютерах, чтобы начать сеанс трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="30d42-140">Then, run SetupETW.bat on the client and server computers to begin the ETW Trace Session.</span></span> <span data-ttu-id="30d42-141">Файл SetupETW.bat можно найти в папке CS\Client.</span><span class="sxs-lookup"><span data-stu-id="30d42-141">The SetupETW.bat file can be found under the CS\Client folder.</span></span>  
  
4. <span data-ttu-id="30d42-142">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="30d42-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
5. <span data-ttu-id="30d42-143">По завершении образца запустите файл CleanupETW.bat, чтобы завершить создание файла ETWTracingSampleLog.etl.</span><span class="sxs-lookup"><span data-stu-id="30d42-143">When the sample is completed, run CleanupETW.bat to complete the creation of the ETWTracingSampleLog.etl file.</span></span>  
  
6. <span data-ttu-id="30d42-144">Откройте файл ETWTracingSampleLog.etl с помощью программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="30d42-144">Open the ETWTracingSampleLog.etl file from within the Service Trace Viewer.</span></span> <span data-ttu-id="30d42-145">Будет предложено сохранить двоичный файл как файл с расширением SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="30d42-145">You will be prompted to save the binary formatted file as a .svclog file.</span></span>  
  
7. <span data-ttu-id="30d42-146">Откройте только что созданный файл с расширением SVCLOG с помощью программы Service Trace Viewer, чтобы просмотреть трассировки событий Windows и трассировки ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="30d42-146">Open the newly created .svclog file from within the Service Trace Viewer to view the ETW and ServiceModel traces.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="30d42-147">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="30d42-147">The samples may already be installed on your computer.</span></span> <span data-ttu-id="30d42-148">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="30d42-148">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="30d42-149">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="30d42-149">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="30d42-150">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="30d42-150">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a><span data-ttu-id="30d42-151">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="30d42-151">See also</span></span>

- <span data-ttu-id="30d42-152">[Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="30d42-152">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
