---
title: "Трассировка и ведение журнала сообщений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: "53"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a73c6e544b7aae003a525c29743d68db18a54515
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="tracing-and-message-logging"></a>Трассировка и ведение журнала сообщений
В этом образце показано, как включить трассировку и ведение журнала сообщений. Полученный трассировки и журналы сообщений просматриваются с помощью [программы Service Trace Viewer (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md). Этот пример построен на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="tracing"></a>Трассировка  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует механизм трассировки, определенный в пространстве имен <xref:System.Diagnostics>. В этой модели трассировки данные трассировки создаются источниками трассировки, реализуемыми приложениями. Каждый источник определяется именем. Потребители трассировки создают прослушиватели трассировки для источников трассировки, для которых необходимо извлечь информацию. Чтобы получить данные трассировки, необходимо создать прослушиватель для источника трассировки. В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] это можно сделать путем добавления следующего кода в файл конфигурации службы или клиента, задав значение `switchValue` для источника трассировки модели службы.  
  
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
  
 Дополнительные сведения об источниках трассировки см. в разделе источника трассировки в [Настройка трассировки](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) раздела.  
  
## <a name="activity-tracing-and-propagation"></a>Трассировка и распространение действий  
 Наличие `ActivityTracing` включен и `propagateActivity` значение `true` в `system.ServiceModel` источники трассировки клиента и службы обеспечить корреляцию трассировок в логических единицах обработки (действиях), между действиями в конечных точек () путем перенаправления действий) и между действиями с охватом нескольких конечных точек (путем распространения идентификатора действия).  
  
 Эти три механизма (действия, перенаправление и распространение) могут помочь быстрее найти первопричину ошибки с использованием программы Service Trace Viewer. Дополнительные сведения см. в разделе [с помощью программы Service Trace Viewer для просмотра корреляцию трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Возможно расширить трассировку, предоставляемую ServiceModel, создав пользовательские трассировки действий. Пользовательская трассировка действий позволяет пользователю создавать действия трассировки для следующих целей.  
  
-   Группирование трассировок в логические блоки обработки.  
  
-   Корреляция действий путем перенаправления и распространения.  
  
-   Снижение расходов производительности, связанных с трассировкой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] (например, расходы на дисковое пространство, занимаемое файлом журнала).  
  
 Дополнительные сведения о трассировке пользовательского действия, см. в разделе [расширение трассировки](../../../../docs/framework/wcf/samples/extending-tracing.md) образца.  
  
## <a name="message-logging"></a>Ведение журналов сообщений  
 Ведение журнала сообщений можно включить как на стороне клиента, так и на стороне службы любого приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Чтобы включить ведение журнала сообщений, необходимо добавить следующий код в клиент или службу.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels >  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 При записи сообщения тип трассировки зависит от того, трассируется оно на стороне клиента или сервера. Например, сообщение "Добавить", отправленное клиенту, трассируется в категории "TransportWrite" на стороне клиента, в то время как то же сообщение трассируется в категории "TransportRead" на стороне службы.  
  
 Настройте прослушиватель трассировки, добавив следующий код в раздел <xref:System.Diagnostics> файла App.config клиента или файла Web.config службы.  
  
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
  
 Сообщения записываются в журнал в формате XML в целевом каталоге, указанном в файле конфигурации.  
  
> [!NOTE]
>  Файлы трассировки невозможно создать, если не создан каталог журнала. Убедитесь, что каталог C:\logs\ существует или укажите альтернативный каталог ведения журнала в конфигурации прослушивателя. Дополнительные сведения см. в первоначальных инструкциях по настройке, приведенных в конце данного документа.  
  
 Дополнительные сведения о ведении журнала сообщений см. в разделе [Настройка ведения журнала сообщений](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) раздела.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Перед выполнением образца трассировки и ведения журнала сообщений создайте каталог C:\logs\, чтобы служба записывала данные в файлы с расширением SVCLOG. Имя этого каталога определяется в файле конфигурации как путь для трассировок и сообщений для записи в журнал, и его можно изменить. Предоставьте сетевой службе пользователя доступ к записи в каталог журналов.  
  
3.  Чтобы создать выпуск решения C#, C++ или Visual Basic .NET, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Для запуска образца в конфигурации с одним или несколькими компьютерами следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Этот образец расположен в следующем каталоге.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>См. также  
 [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [Примеры мониторинга AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
