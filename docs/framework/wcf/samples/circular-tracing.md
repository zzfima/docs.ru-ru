---
title: "Циклическая трассировка"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 21a455c0fcb7a6b4164da6f7fdc7efaa007273ae
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="circular-tracing"></a>Циклическая трассировка
Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера. Обычным сценарием для производственных служб является длительная доступность этих служб и включенное ведение журнала трассировки на низком уровне. Этим службам требуется много пространства на диске. При устранении неполадок службы к устранению проблемы имеют отношение последние записанные данные из журнала трассировки. Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера, в котором на диске хранятся только самые последние трассировки с объемом данных, не превышающим заданного в настройках. Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает прослушиватель пользовательские трассировку.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом примере предполагается, что вы знакомы с [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) образца и прочитаны в документации, предоставленной для [трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) образца.  
  
## <a name="circular-buffer-trace-listener"></a>Прослушиватель трассировки циклического буфера  
 Реализация прослушивателя трассировки циклического буфера основана на двух файлах, каждый из которых может содержать до половины общего требуемого объема данных журнала трассировки. Прослушиватель создает один файл и производит запись в этот файл до тех пор, пока не будет достигнут предел, равный половине объема данных, после чего переключается на второй файл. После того как прослушивать достигает предела для второго файла, он перезаписывает первый файл, заполняя его новыми трассировками.  
  
 Этот прослушиватель является производным от `XmlWriteTraceListener` и позволяет просматривать журналы [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). При просмотре журналов можно легко объединить два файла журнала, одновременно открыв их в средстве Service Trace Viewer. Средство Service Trace Viewer автоматически сортирует трассировки, чтобы они отображались в правильном порядке.  
  
## <a name="configuration"></a>Конфигурация  
 Службу можно настроить для использования прослушивателя трассировки циклического буфера, добавив приведенный ниже код в элементы прослушивателя и источника. Максимальный размер файла задается с помощью атрибута `maxFileSizeKB` в конфигурации прослушивателя трассировки циклического буфера. Это показано в следующем коде.  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a>См. также  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
