---
title: Трассировка и ведение журнала сообщений
ms.date: 03/30/2017
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
ms.openlocfilehash: 9ffb7a99540b953fc93a22d2296caf86f294d25d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79143828"
---
# <a name="tracing-and-message-logging"></a><span data-ttu-id="cbdfd-102">Трассировка и ведение журнала сообщений</span><span class="sxs-lookup"><span data-stu-id="cbdfd-102">Tracing and Message Logging</span></span>
<span data-ttu-id="cbdfd-103">В этом образце показано, как включить трассировку и ведение журнала сообщений.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-103">This sample demonstrates how to enable tracing and message logging.</span></span> <span data-ttu-id="cbdfd-104">Полученные следы и журналы сообщений просматриваются с помощью [инструмента просмотра служебного следа (SvcTraceViewer.exe).](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-104">The resulting traces and message logs are viewed using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="cbdfd-105">Этот пример основан на [получении начала](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="cbdfd-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbdfd-106">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="tracing"></a><span data-ttu-id="cbdfd-107">Трассировка</span><span class="sxs-lookup"><span data-stu-id="cbdfd-107">Tracing</span></span>  
 <span data-ttu-id="cbdfd-108">Фонд связи Windows (WCF) использует механизм <xref:System.Diagnostics> отслеживания, определяемый в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-108">Windows Communication Foundation (WCF) uses the tracing mechanism defined in the <xref:System.Diagnostics> namespace.</span></span> <span data-ttu-id="cbdfd-109">В этой модели трассировки данные трассировки создаются источниками трассировки, реализуемыми приложениями.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-109">In this tracing model, trace data is produced by trace sources that applications implement.</span></span> <span data-ttu-id="cbdfd-110">Каждый источник определяется именем.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-110">Each source is identified by a name.</span></span> <span data-ttu-id="cbdfd-111">Потребители трассировки создают прослушиватели трассировки для источников трассировки, для которых необходимо извлечь информацию.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-111">Trace consumers create trace listeners for the trace sources for which they want to retrieve information.</span></span> <span data-ttu-id="cbdfd-112">Чтобы получить данные трассировки, необходимо создать прослушиватель для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-112">To receive trace data, you must create a listener for the trace source.</span></span> <span data-ttu-id="cbdfd-113">В WCF это можно сделать, добавив следующий код в файл конфигурации службы или `switchValue`клиента, установив источник трассировки модели обслуживания:</span><span class="sxs-lookup"><span data-stu-id="cbdfd-113">In WCF, this can be done by adding the following code to either the service’s or client’s configuration file by setting the Service Model trace source `switchValue`:</span></span>  
  
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
  
 <span data-ttu-id="cbdfd-114">Для получения дополнительной информации об источниках следов можно найти раздел Trace Source в теме [«Настройка трассировки».](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-114">For more information about trace sources, see the Trace Source section in the [Configuring Tracing](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) topic.</span></span>  
  
## <a name="activity-tracing-and-propagation"></a><span data-ttu-id="cbdfd-115">Трассировка и распространение действий</span><span class="sxs-lookup"><span data-stu-id="cbdfd-115">Activity Tracing and Propagation</span></span>  
 <span data-ttu-id="cbdfd-116">Впустив `ActivityTracing` и `propagateActivity` установите `true` в `system.ServiceModel` источниках трассировки как для клиента, так и для службы, они обеспечивают корреляцию следов в рамках логических единиц обработки (деятельности), между действиями в конечных точках (через передачи активности) и между действиями, охватывающими несколько конечных точек (через распространение идентификатора активности).</span><span class="sxs-lookup"><span data-stu-id="cbdfd-116">Having `ActivityTracing` enabled and `propagateActivity` set to `true` in the `system.ServiceModel` trace sources for both the client and service provide correlation of traces within logical units of processing (activities), across activities within endpoints (through activity transfers), and across activities spanning multiple endpoints (through activity ID propagation).</span></span>  
  
 <span data-ttu-id="cbdfd-117">Эти три механизма (действия, перенаправление и распространение) могут помочь быстрее найти первопричину ошибки с использованием программы Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-117">These three mechanisms (activities, transfers, and propagation) can help you locate the root cause of an error more quickly using the Service Trace Viewer tool.</span></span> <span data-ttu-id="cbdfd-118">Для получения дополнительной информации [см.](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-118">For more information, see [Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).</span></span>  
  
 <span data-ttu-id="cbdfd-119">Возможно расширить трассировку, предоставляемую ServiceModel, создав пользовательские трассировки действий.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-119">It is possible to extend the tracing that is provided by the ServiceModel by creating user-defined activity traces.</span></span> <span data-ttu-id="cbdfd-120">Пользовательская трассировка действий позволяет пользователю создавать действия трассировки для следующих целей.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-120">User-defined activity tracing allows the user to create trace activities to:</span></span>  
  
- <span data-ttu-id="cbdfd-121">Группирование трассировок в логические блоки обработки.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-121">Group traces into logical units of work.</span></span>  
  
- <span data-ttu-id="cbdfd-122">Корреляция действий путем перенаправления и распространения.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-122">Correlate activities through transfers and propagation.</span></span>  
  
- <span data-ttu-id="cbdfd-123">Уменьшите стоимость производительность отслеживания WCF (например, стоимость дискового пространства файла журнала).</span><span class="sxs-lookup"><span data-stu-id="cbdfd-123">Lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
 <span data-ttu-id="cbdfd-124">Для получения дополнительной информации о отслеживании активности, определяемой пользователем, пожалуйста, ознакомьтесь с образцом [расширяющейся трассировки.](../../../../docs/framework/wcf/samples/extending-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-124">For more information about user-defined activity trace, please see the [Extending Tracing](../../../../docs/framework/wcf/samples/extending-tracing.md) sample.</span></span>  
  
## <a name="message-logging"></a><span data-ttu-id="cbdfd-125">Ведение журналов сообщений</span><span class="sxs-lookup"><span data-stu-id="cbdfd-125">Message Logging</span></span>  
 <span data-ttu-id="cbdfd-126">Регистрация сообщений может быть включена как на клиенте, так и на обслуживании любого приложения WCF.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-126">Message logging can be enabled both on the client and service of any WCF application.</span></span> <span data-ttu-id="cbdfd-127">Чтобы включить ведение журнала сообщений, необходимо добавить следующий код в клиент или службу.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-127">To enable message logging, you must add the following code to either the client or service:</span></span>  
  
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
  
 <span data-ttu-id="cbdfd-128">При записи сообщения тип трассировки зависит от того, трассируется оно на стороне клиента или сервера.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-128">When a message is recorded, the trace type depends on whether it is being traced at the client or the server.</span></span> <span data-ttu-id="cbdfd-129">Например, сообщение "Добавить", отправленное клиенту, трассируется в категории "TransportWrite" на стороне клиента, в то время как то же сообщение трассируется в категории "TransportRead" на стороне службы.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-129">For example, an "Add" message that is sent to a client is traced under the "TransportWrite" category at the client, whereas the same message is traced under the "TransportRead" category at the service.</span></span>  
  
 <span data-ttu-id="cbdfd-130">Настройте прослушиватель трассировки, добавив следующий код в раздел <xref:System.Diagnostics> файла App.config клиента или файла Web.config службы.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-130">Configure the trace listener by adding the following code to the <xref:System.Diagnostics> section of the client's App.config file or the service's Web.config file:</span></span>  
  
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
  
 <span data-ttu-id="cbdfd-131">Сообщения записываются в журнал в формате XML в целевом каталоге, указанном в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-131">Messages are logged in XML format in the target directory specified in the configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbdfd-132">Файлы трассировки невозможно создать, если не создан каталог журнала.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-132">Trace files are not created without initially creating the log directory.</span></span> <span data-ttu-id="cbdfd-133">Убедитесь, что каталог C:\logs\ существует или укажите альтернативный каталог ведения журнала в конфигурации прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-133">Make sure that the directory C:\logs\ exists, or specify an alternate logging directory in the listener configuration.</span></span> <span data-ttu-id="cbdfd-134">Дополнительные сведения см. в первоначальных инструкциях по настройке, приведенных в конце данного документа.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-134">See the initial setup instructions at the end of this document for more information.</span></span>  
  
 <span data-ttu-id="cbdfd-135">Для получения дополнительной информации о регистрации сообщений можно ознакомиться на теме [«Настройка регистрации сообщений».](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-135">For more information about message logging, see the [Configuring Message Logging](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) topic.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cbdfd-136">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cbdfd-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cbdfd-137">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cbdfd-138">Перед выполнением образца трассировки и ведения журнала сообщений создайте каталог C:\logs\, чтобы служба записывала данные в файлы с расширением SVCLOG.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-138">Before running the Tracing and Message Logging sample, create the directory C:\logs\ for the service to write the .svclog files to.</span></span> <span data-ttu-id="cbdfd-139">Имя этого каталога определяется в файле конфигурации как путь для трассировок и сообщений для записи в журнал, и его можно изменить.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-139">The name of this directory is defined in the configuration file as the path for the traces and messages to be logged and can be changed.</span></span> <span data-ttu-id="cbdfd-140">Предоставьте сетевой службе пользователя доступ к записи в каталог журналов.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-140">Give the user Network Service write access to the logs directory.</span></span>  
  
3. <span data-ttu-id="cbdfd-141">Чтобы создать выпуск решения для C,, C-, или Visual Basic .NET, следуйте инструкциям по [созданию образцов Фонда коммуникаций Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-141">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="cbdfd-142">Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbdfd-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cbdfd-143">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-143">The samples may already be installed on your computer.</span></span> <span data-ttu-id="cbdfd-144">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cbdfd-144">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="cbdfd-145">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbdfd-146">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cbdfd-146">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a><span data-ttu-id="cbdfd-147">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cbdfd-147">See also</span></span>

- [<span data-ttu-id="cbdfd-148">Трассировки</span><span class="sxs-lookup"><span data-stu-id="cbdfd-148">Tracing</span></span>](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- <span data-ttu-id="cbdfd-149">[Образцы наблюдения за AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="cbdfd-149">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
