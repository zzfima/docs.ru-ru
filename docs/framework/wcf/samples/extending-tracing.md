---
title: Расширение трассировки
ms.date: 03/30/2017
ms.assetid: 2b971a99-16ec-4949-ad2e-b0c8731a873f
ms.openlocfilehash: 829ebd2f935135b8765ccd48532d357bf95f805a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208245"
---
# <a name="extending-tracing"></a><span data-ttu-id="79f04-102">Расширение трассировки</span><span class="sxs-lookup"><span data-stu-id="79f04-102">Extending Tracing</span></span>
<span data-ttu-id="79f04-103">В этом примере показано, как расширить возможности трассировки Windows Communication Foundation (WCF), добавив трассировки пользовательских действий в коде клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="79f04-103">This sample demonstrates how to extend the Windows Communication Foundation (WCF) tracing feature by writing user-defined activity traces in client and service code.</span></span> <span data-ttu-id="79f04-104">Это позволяет пользователю создавать действия трассировки и группировать трассировки в логические пакеты работ.</span><span class="sxs-lookup"><span data-stu-id="79f04-104">This allows the user to create trace activities and group traces into logical units of work.</span></span> <span data-ttu-id="79f04-105">Кроме того, возможно согласование действий с помощью передач (в рамках одной конечной точки) и распространения (между конечными точками).</span><span class="sxs-lookup"><span data-stu-id="79f04-105">It is also possible to correlate activities through transfers (within the same endpoint) and propagation (across endpoints).</span></span> <span data-ttu-id="79f04-106">В этом образце трассировка включается как для клиента, так и для службы.</span><span class="sxs-lookup"><span data-stu-id="79f04-106">In this sample, tracing is enabled for both the client and the service.</span></span> <span data-ttu-id="79f04-107">Дополнительные сведения о том, как включить трассировку в файлах конфигурации клиента и службы, см. в разделе [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-107">For more information about how to enable tracing in client and service configuration files, see [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span>  
  
 <span data-ttu-id="79f04-108">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79f04-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="79f04-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79f04-110">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="79f04-110">The samples may already be installed on your computer.</span></span> <span data-ttu-id="79f04-111">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="79f04-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="79f04-112">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="79f04-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="79f04-113">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="79f04-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ExtendingTracing`  
  
## <a name="tracing-and-activity-propagation"></a><span data-ttu-id="79f04-114">Трассировка и распространение действий</span><span class="sxs-lookup"><span data-stu-id="79f04-114">Tracing and Activity Propagation</span></span>  
 <span data-ttu-id="79f04-115">Отслеживание пользовательских операций позволяет пользователю создавать собственные действия трассировки для объединения трассировок в логические пакеты работ, корреляция действий путем перенаправления и распространения и снижение расходов производительности, трассировки WCF (например, стоимость дискового пространства файлом журнала).</span><span class="sxs-lookup"><span data-stu-id="79f04-115">User-defined activity tracing allows the user to create their own trace activities to group traces into logical units of work, correlate activities through transfers and propagation, and lessen the performance cost of WCF tracing (for example, the disk space cost of a log file).</span></span>  
  
### <a name="adding-custom-sources"></a><span data-ttu-id="79f04-116">Добавление пользовательских источников</span><span class="sxs-lookup"><span data-stu-id="79f04-116">Adding Custom Sources</span></span>  
 <span data-ttu-id="79f04-117">Пользовательские трассировки можно добавлять как в код клиента, так и в код службы.</span><span class="sxs-lookup"><span data-stu-id="79f04-117">User-defined traces can be added to both client and service code.</span></span> <span data-ttu-id="79f04-118">Добавление источников трассировки в файлах конфигурации клиента или службы позволяют эти пользовательские трассировки позволяет записывать и отображать в [программа Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-118">Adding trace sources to the client or service configuration files allow for these custom traces to be recorded and displayed in the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="79f04-119">В следующем примере кода показано, как добавить в файл конфигурации пользовательский источник трассировки с именем `ServerCalculatorTraceSource`.</span><span class="sxs-lookup"><span data-stu-id="79f04-119">The following code shows how to add a user-defined trace source named `ServerCalculatorTraceSource` to the configuration file.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
        <source name="ServerCalculatorTraceSource" switchValue="Information,ActivityTracing">  
            <listeners>  
                <add type="System.Diagnostics.DefaultTraceListener" name="Default">  
                    <filter type="" />  
                </add>  
                <add name="xml">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
       <add initializeData="C:\logs\ServerTraces.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" traceOutputOptions="Callstack">  
            <filter type="" />  
        </add>  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>....  
....  
```  
  
### <a name="correlating-activities"></a><span data-ttu-id="79f04-120">Согласование действий</span><span class="sxs-lookup"><span data-stu-id="79f04-120">Correlating Activities</span></span>  
 <span data-ttu-id="79f04-121">Для непосредственного согласования действий между конечными точками в источнике трассировки `propagateActivity` атрибут `true` должен иметь значение `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="79f04-121">To correlate activities directly across endpoints, the `propagateActivity` attribute must be set to `true` in the `System.ServiceModel` trace source.</span></span> <span data-ttu-id="79f04-122">Кроме того для распространения трассировки, не обращаясь к действиям WCF, трассировка действий ServiceModel должен быть отключен.</span><span class="sxs-lookup"><span data-stu-id="79f04-122">Also, to propagate traces without going through WCF activities, ServiceModel Activity Tracing must be turned off.</span></span> <span data-ttu-id="79f04-123">Это показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="79f04-123">This can be seen in the following code example.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79f04-124">Отключение трассировки действия ServiceModel не эквивалентно указанию значения off для уровня трассировки, обозначаемого свойством `switchValue`.</span><span class="sxs-lookup"><span data-stu-id="79f04-124">Turning off ServiceModel Activity Tracing is not the same as having the trace level, denoted by the `switchValue` property, set to off.</span></span>  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Warning" propagateActivity="true">  
  
    ...  
  
       </source>  
    </sources>  
</system.diagnostics>  
```  
  
### <a name="lessening-performance-cost"></a><span data-ttu-id="79f04-125">Снижение нагрузки на производительность</span><span class="sxs-lookup"><span data-stu-id="79f04-125">Lessening Performance Cost</span></span>  
 <span data-ttu-id="79f04-126">Установка для свойства `ActivityTracing` значения off в трассировке `System.ServiceModel` создает файл трассировки, который содержит только пользовательские трассировки действий без включения каких-либо трассировок действий ServiceModel.</span><span class="sxs-lookup"><span data-stu-id="79f04-126">Setting `ActivityTracing` to off in the `System.ServiceModel` trace source generates a trace file that contains only user-defined activity traces, without any of the ServiceModel activity traces included.</span></span> <span data-ttu-id="79f04-127">В результате уменьшится размер файла журнала.</span><span class="sxs-lookup"><span data-stu-id="79f04-127">This results in a log file of much smaller size.</span></span> <span data-ttu-id="79f04-128">Тем не менее теряется возможность согласования трассировок обработки WCF.</span><span class="sxs-lookup"><span data-stu-id="79f04-128">However, the opportunity to correlate WCF processing traces is lost.</span></span>  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="79f04-129">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="79f04-129">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="79f04-130">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-130">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="79f04-131">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-131">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="79f04-132">Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="79f04-132">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79f04-133">См. также</span><span class="sxs-lookup"><span data-stu-id="79f04-133">See also</span></span>

- [<span data-ttu-id="79f04-134">Образцы наблюдения за AppFabric</span><span class="sxs-lookup"><span data-stu-id="79f04-134">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
