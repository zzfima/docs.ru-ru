---
title: "Циклическая трассировка | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
caps.latest.revision: 21
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 21
---
# Циклическая трассировка
Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера.Обычным сценарием для производственных служб является длительная доступность этих служб и включенное ведение журнала трассировки на низком уровне.Этим службам требуется много пространства на диске.При устранении неполадок службы к устранению проблемы имеют отношение последние записанные данные из журнала трассировки.Этот образец демонстрирует реализацию прослушивателя трассировки циклического буфера, в котором на диске хранятся только самые последние трассировки с объемом данных, не превышающим заданного в настройках.Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md) и включает в себя пользовательский прослушиватель трассировки.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В образце предполагается, что читатель знаком с образцом [Трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) и ознакомился с документацией, предоставляемой для образца [Трассировка и ведение журнала сообщений](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).  
  
## Прослушиватель трассировки циклического буфера  
 Реализация прослушивателя трассировки циклического буфера основана на двух файлах, каждый из которых может содержать до половины общего требуемого объема данных журнала трассировки.Прослушиватель создает один файл и производит запись в этот файл до тех пор, пока не будет достигнут предел, равный половине объема данных, после чего переключается на второй файл.После того как прослушивать достигает предела для второго файла, он перезаписывает первый файл, заполняя его новыми трассировками.  
  
 Этот прослушиватель наследует от класса `XmlWriteTraceListener` и обеспечивает просмотр журналов с помощью средства [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).При просмотре журналов можно легко объединить два файла журнала, одновременно открыв их в средстве Service Trace Viewer.Средство Service Trace Viewer автоматически сортирует трассировки, чтобы они отображались в правильном порядке.  
  
## Конфигурация  
 Службу можно настроить для использования прослушивателя трассировки циклического буфера, добавив приведенный ниже код в элементы прослушивателя и источника.Максимальный размер файла задается с помощью атрибута `maxFileSizeKB` в конфигурации прослушивателя трассировки циклического буфера.Это показано в следующем коде.  
  
```  
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
  
#### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## См. также  
 [Образцы наблюдения за AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)