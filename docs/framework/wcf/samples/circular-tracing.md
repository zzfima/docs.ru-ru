---
title: Циклическая трассировка
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 1f6c5287e6a53ed26ee5c9ed477e08dafc512e3f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43739985"
---
# <a name="circular-tracing"></a><span data-ttu-id="e92c2-102">Циклическая трассировка</span><span class="sxs-lookup"><span data-stu-id="e92c2-102">Circular Tracing</span></span>
<span data-ttu-id="e92c2-103">Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера.</span><span class="sxs-lookup"><span data-stu-id="e92c2-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="e92c2-104">Обычным сценарием для производственных служб является длительная доступность этих служб и включенное ведение журнала трассировки на низком уровне.</span><span class="sxs-lookup"><span data-stu-id="e92c2-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="e92c2-105">Этим службам требуется много пространства на диске.</span><span class="sxs-lookup"><span data-stu-id="e92c2-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="e92c2-106">При устранении неполадок службы к устранению проблемы имеют отношение последние записанные данные из журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="e92c2-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="e92c2-107">Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера, в котором на диске хранятся только самые последние трассировки с объемом данных, не превышающим заданного в настройках.</span><span class="sxs-lookup"><span data-stu-id="e92c2-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="e92c2-108">Этот образец основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает в себя пользовательский прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="e92c2-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes a custom tracing listener.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e92c2-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="e92c2-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="e92c2-110">В этом примере предполагается, что вы знакомы с [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) образца и прочитаны в документации, предоставленной для [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) образца.</span><span class="sxs-lookup"><span data-stu-id="e92c2-110">This sample assumes that you are familiar with the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>  
  
## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="e92c2-111">Прослушиватель трассировки циклического буфера</span><span class="sxs-lookup"><span data-stu-id="e92c2-111">Circular Buffer Trace Listener</span></span>  
 <span data-ttu-id="e92c2-112">Реализация прослушивателя трассировки циклического буфера основана на двух файлах, каждый из которых может содержать до половины общего требуемого объема данных журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="e92c2-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="e92c2-113">Прослушиватель создает один файл и производит запись в этот файл до тех пор, пока не будет достигнут предел, равный половине объема данных, после чего переключается на второй файл.</span><span class="sxs-lookup"><span data-stu-id="e92c2-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="e92c2-114">После того как прослушивать достигает предела для второго файла, он перезаписывает первый файл, заполняя его новыми трассировками.</span><span class="sxs-lookup"><span data-stu-id="e92c2-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>  
  
 <span data-ttu-id="e92c2-115">Этот прослушиватель наследует от класса `XmlWriteTraceListener` и позволяет журналы, чтобы просмотреть с помощью [программа Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="e92c2-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="e92c2-116">При просмотре журналов можно легко объединить два файла журнала, одновременно открыв их в средстве Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="e92c2-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="e92c2-117">Средство Service Trace Viewer автоматически сортирует трассировки, чтобы они отображались в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="e92c2-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="e92c2-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="e92c2-118">Configuration</span></span>  
 <span data-ttu-id="e92c2-119">Службу можно настроить для использования прослушивателя трассировки циклического буфера, добавив приведенный ниже код в элементы прослушивателя и источника.</span><span class="sxs-lookup"><span data-stu-id="e92c2-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="e92c2-120">Максимальный размер файла задается с помощью атрибута `maxFileSizeKB` в конфигурации прослушивателя трассировки циклического буфера.</span><span class="sxs-lookup"><span data-stu-id="e92c2-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="e92c2-121">Это показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e92c2-121">This is demonstrated in the following code.</span></span>  
  
```xml  
<system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">  
      <listeners>  
        <add name="CircularTraceListener" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"   
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e92c2-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e92c2-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="e92c2-123">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e92c2-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="e92c2-124">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e92c2-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="e92c2-125">Чтобы запустить образец в конфигурации с одной или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e92c2-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e92c2-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e92c2-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="e92c2-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e92c2-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e92c2-128">Если этот каталог не существует, перейдите к [Windows Communication Foundation (WCF) и образцы Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) для загрузки всех Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры.</span><span class="sxs-lookup"><span data-stu-id="e92c2-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e92c2-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e92c2-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a><span data-ttu-id="e92c2-130">См. также</span><span class="sxs-lookup"><span data-stu-id="e92c2-130">See Also</span></span>  
 [<span data-ttu-id="e92c2-131">Образцы наблюдения за AppFabric</span><span class="sxs-lookup"><span data-stu-id="e92c2-131">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
