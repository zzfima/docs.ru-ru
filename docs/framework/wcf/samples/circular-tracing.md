---
title: Циклическая трассировка
ms.date: 03/30/2017
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
ms.openlocfilehash: 0b1d62177828b52b21a3e43cc083f79c27878804
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741976"
---
# <a name="circular-tracing"></a><span data-ttu-id="61989-102">Циклическая трассировка</span><span class="sxs-lookup"><span data-stu-id="61989-102">Circular Tracing</span></span>

<span data-ttu-id="61989-103">Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера.</span><span class="sxs-lookup"><span data-stu-id="61989-103">This sample demonstrates the implementation of a circular buffer trace listener.</span></span> <span data-ttu-id="61989-104">Обычным сценарием для производственных служб является длительная доступность этих служб и включенное ведение журнала трассировки на низком уровне.</span><span class="sxs-lookup"><span data-stu-id="61989-104">A common scenario for production services is to have services that are available for long periods of time and to have trace logging enabled at a low level.</span></span> <span data-ttu-id="61989-105">Этим службам требуется много пространства на диске.</span><span class="sxs-lookup"><span data-stu-id="61989-105">These services consume a lot of disk space.</span></span> <span data-ttu-id="61989-106">При устранении неполадок службы к устранению проблемы имеют отношение последние записанные данные из журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="61989-106">When troubleshooting a service, the most recent data in the trace log is relevant to solving a problem.</span></span> <span data-ttu-id="61989-107">Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера, в котором на диске хранятся только самые последние трассировки с объемом данных, не превышающим заданного в настройках.</span><span class="sxs-lookup"><span data-stu-id="61989-107">This sample demonstrates an implementation of a circular buffer trace listener in which only the most recent traces are kept on disk up to a configurable amount of data.</span></span> <span data-ttu-id="61989-108">Этот образец основан на [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает пользовательский прослушиватель трассировки.</span><span class="sxs-lookup"><span data-stu-id="61989-108">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and includes a custom tracing listener.</span></span>

> [!NOTE]
> <span data-ttu-id="61989-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="61989-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="61989-110">В этом примере предполагается, что вы знакомы с примером [трассировки и ведения журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) и прочитали документацию, предоставленную для примера [трассировки и регистрации сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) .</span><span class="sxs-lookup"><span data-stu-id="61989-110">This sample assumes that you are familiar with the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample and have read the documentation provided for the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) sample.</span></span>

## <a name="circular-buffer-trace-listener"></a><span data-ttu-id="61989-111">Прослушиватель трассировки циклического буфера</span><span class="sxs-lookup"><span data-stu-id="61989-111">Circular Buffer Trace Listener</span></span>

<span data-ttu-id="61989-112">Реализация прослушивателя трассировки циклического буфера основана на двух файлах, каждый из которых может содержать до половины общего требуемого объема данных журнала трассировки.</span><span class="sxs-lookup"><span data-stu-id="61989-112">The concept behind the implementation of the Circular Buffer Trace Listener is to have two files that can each store up to half of the total desired trace log data.</span></span> <span data-ttu-id="61989-113">Прослушиватель создает один файл и производит запись в этот файл до тех пор, пока не будет достигнут предел, равный половине объема данных, после чего переключается на второй файл.</span><span class="sxs-lookup"><span data-stu-id="61989-113">The listener creates one file and writes to that file until it reaches the limit of half of the data size, at which point it switches to a second file.</span></span> <span data-ttu-id="61989-114">После того как прослушивать достигает предела для второго файла, он перезаписывает первый файл, заполняя его новыми трассировками.</span><span class="sxs-lookup"><span data-stu-id="61989-114">When the listener reaches the limit for the second file - it overwrites the first file with new traces.</span></span>

<span data-ttu-id="61989-115">Этот прослушиватель является производным от `XmlWriteTraceListener` и позволяет просматривать журналы с помощью [средства Service Trace Viewer (SvcTraceViewer. exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="61989-115">This listener derives from the `XmlWriteTraceListener` and allows the logs to be viewed with the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="61989-116">При просмотре журналов можно легко объединить два файла журнала, одновременно открыв их в средстве Service Trace Viewer.</span><span class="sxs-lookup"><span data-stu-id="61989-116">When attempting to view the logs, the two log files can be easily recombined by opening both of the log files at the same time in the Service Trace Viewer tool.</span></span> <span data-ttu-id="61989-117">Средство Service Trace Viewer автоматически сортирует трассировки, чтобы они отображались в правильном порядке.</span><span class="sxs-lookup"><span data-stu-id="61989-117">The Service Trace Viewer tool automatically takes care of sorting the traces so that they appear in the correct order.</span></span>

## <a name="configuration"></a><span data-ttu-id="61989-118">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="61989-118">Configuration</span></span>

<span data-ttu-id="61989-119">Службу можно настроить для использования прослушивателя трассировки циклического буфера, добавив приведенный ниже код в элементы прослушивателя и источника.</span><span class="sxs-lookup"><span data-stu-id="61989-119">A service can be configured to use the Circular Buffer Trace Listener by adding the following code for a listener and source elements.</span></span> <span data-ttu-id="61989-120">Максимальный размер файла задается с помощью атрибута `maxFileSizeKB` в конфигурации прослушивателя трассировки циклического буфера.</span><span class="sxs-lookup"><span data-stu-id="61989-120">The max file size is specified by setting the `maxFileSizeKB` attribute in the circular trace listener's configuration.</span></span> <span data-ttu-id="61989-121">Это показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="61989-121">This is demonstrated in the following code.</span></span>

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

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="61989-122">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="61989-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="61989-123">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="61989-123">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="61989-124">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="61989-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="61989-125">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="61989-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="61989-126">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="61989-126">The samples may already be installed on your computer.</span></span> <span data-ttu-id="61989-127">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="61989-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="61989-128">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="61989-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="61989-129">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="61989-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`

## <a name="see-also"></a><span data-ttu-id="61989-130">См. также:</span><span class="sxs-lookup"><span data-stu-id="61989-130">See also</span></span>

- <span data-ttu-id="61989-131">[Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="61989-131">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
