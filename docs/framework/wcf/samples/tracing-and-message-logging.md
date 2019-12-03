---
title: Трассировка и ведение журнала сообщений
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: f6f2fd0bbbc191d466ac600bd9639c8955d5b7fe
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715682"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="f77d2-102">Трассировка и ведение журнала сообщений</span><span class="sxs-lookup"><span data-stu-id="f77d2-102">Tracing and Message Logging</span></span>
<span data-ttu-id="f77d2-103">В этом образце показано, как включить трассировку и ведение журнала сообщений.</span><span class="sxs-lookup"><span data-stu-id="f77d2-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="f77d2-104">Результирующие трассировки и журналы сообщений просматриваются с помощью [средства Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="f77d2-105">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f77d2-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="f77d2-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="f77d2-107">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f77d2-107">Tracing</span></span>  
 <span data-ttu-id="f77d2-108">Windows Communication Foundation (WCF) использует механизм трассировки, определенный в пространстве имен <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="f77d2-108">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="f77d2-109">В этой модели трассировки данные трассировки создаются источниками трассировки, реализуемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="f77d2-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="f77d2-110">Каждый источник определяется именем.</span><span class="sxs-lookup"><span data-stu-id="f77d2-110">Each source is identified by a name.</span></span> <span data-ttu-id="f77d2-111">Потребители трассировки создают прослушиватели трассировки для источников трассировки, для которых необходимо извлечь информацию.</span><span class="sxs-lookup"><span data-stu-id="f77d2-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="f77d2-112">Чтобы получить данные трассировки, необходимо создать прослушиватель для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="f77d2-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="f77d2-113">В WCF это можно сделать, добавив следующий код в файл конфигурации службы или клиента путем установки `switchValue`источника трассировки модели службы:</span><span class="sxs-lookup"><span data-stu-id="f77d2-113">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="f77d2-114">Дополнительные сведения об источниках трассировки см. в разделе Источник трассировки статьи [Настройка трассировки](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="f77d2-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="f77d2-115">Трассировка и распространение действий</span><span class="sxs-lookup"><span data-stu-id="f77d2-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="f77d2-116">Если `ActivityTracing` включены и `propagateActivity` задано значение `true` в источниках трассировки `system.ServiceModel` для клиента и службы предоставляют корреляцию трассировок в логических единицах обработки (действиях), между действиями в конечных точках (посредством передачи действий) и между действиями, охватывающими несколько конечных точек (с помощью распространения идентификатора действия).</span><span class="sxs-lookup"><span data-stu-id="f77d2-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="f77d2-117">Эти три механизма (действия, перенаправление и распространение) могут помочь быстрее найти первопричину ошибки с использованием программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="f77d2-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="f77d2-118">Дополнительные сведения см. [в разделе Использование Service Trace Viewer для просмотра коррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="f77d2-119">Возможно расширить трассировку, предоставляемую ServiceModel, создав пользовательские трассировки действий.</span><span class="sxs-lookup"><span data-stu-id="f77d2-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="f77d2-120">Пользовательская трассировка действий позволяет пользователю создавать действия трассировки для следующих целей.</span><span class="sxs-lookup"><span data-stu-id="f77d2-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="f77d2-121">Группирование трассировок в логические блоки обработки.</span><span class="sxs-lookup"><span data-stu-id="f77d2-121">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="f77d2-122">Корреляция действий путем перенаправления и распространения.</span><span class="sxs-lookup"><span data-stu-id="f77d2-122">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="f77d2-123">Снижение затрат на производительность трассировки WCF (например, стоимость дискового пространства в файле журнала).</span><span class="sxs-lookup"><span data-stu-id="f77d2-123">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="f77d2-124">Дополнительные сведения о трассировке действий, определяемых пользователем, см. в примере [расширенной трассировки](../../../../docs/framework/wcf/samples/extending-tracing.md) .</span><span class="sxs-lookup"><span data-stu-id="f77d2-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="f77d2-125">Ведение журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="f77d2-125">Message Logging</span></span>  
 <span data-ttu-id="f77d2-126">Ведение журнала сообщений можно включить как на клиенте, так и в службе любого приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="f77d2-126">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="f77d2-127">Чтобы включить ведение журнала сообщений, необходимо добавить следующий код в клиент или службу.</span><span class="sxs-lookup"><span data-stu-id="f77d2-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="f77d2-128">При записи сообщения тип трассировки зависит от того, трассируется оно на стороне клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="f77d2-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="f77d2-129">Например, сообщение "Добавить", отправленное клиенту, трассируется в категории "TransportWrite" на стороне клиента, в то время как то же сообщение трассируется в категории "TransportRead" на стороне службы.</span><span class="sxs-lookup"><span data-stu-id="f77d2-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="f77d2-130">Настройте прослушиватель трассировки, добавив следующий код в раздел <xref:System.Diagnostics> файла App.config клиента или файла Web.config службы.</span><span class="sxs-lookup"><span data-stu-id="f77d2-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 <span data-ttu-id="f77d2-131">Сообщения записываются в журнал в формате XML в целевом каталоге, указанном в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f77d2-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f77d2-132">Файлы трассировки невозможно создать, если не создан каталог журнала.</span><span class="sxs-lookup"><span data-stu-id="f77d2-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="f77d2-133">Убедитесь, что каталог C:\logs\ существует или укажите альтернативный каталог ведения журнала в конфигурации прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="f77d2-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="f77d2-134">Дополнительные сведения см. в первоначальных инструкциях по настройке, приведенных в конце данного документа.</span><span class="sxs-lookup"><span data-stu-id="f77d2-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="f77d2-135">Дополнительные сведения о ведении журнала сообщений см. в разделе [Настройка ведения журнала сообщений](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="f77d2-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f77d2-136">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="f77d2-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f77d2-137">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f77d2-138">Перед выполнением образца трассировки и ведения журнала сообщений создайте каталог C:\logs\, чтобы служба записывала данные в файлы с расширением SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="f77d2-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="f77d2-139">Имя этого каталога определяется в файле конфигурации как путь для трассировок и сообщений для записи в журнал, и его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="f77d2-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="f77d2-140">Предоставьте сетевой службе пользователя доступ к записи в каталог журналов.</span><span class="sxs-lookup"><span data-stu-id="f77d2-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="f77d2-141">Чтобы создать выпуск C#решения C++, или Visual Basic .NET, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="f77d2-142">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f77d2-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f77d2-143">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f77d2-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="f77d2-144">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="f77d2-144">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="f77d2-145">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="f77d2-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f77d2-146">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="f77d2-146">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="f77d2-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="f77d2-147">See also</span></span>

- [<span data-ttu-id="f77d2-148">Трассировка</span><span class="sxs-lookup"><span data-stu-id="f77d2-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [<span data-ttu-id="f77d2-149">Примеры мониторинга AppFabric</span><span class="sxs-lookup"><span data-stu-id="f77d2-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
