---
title: "Трассировка и ведение журнала сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "трассировка и ведение журнала"
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: 53
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 53
---
# Трассировка и ведение журнала сообщений
В этом образце показано, как включить трассировку и ведение журнала сообщений.Получаемые трассировки и журналы сообщений можно просмотреть с помощью программы [Программа Service Trace Viewer \(SvcTraceViewer.exe\)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).Этот образец основан на примере [Начало работы](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для этого образца приведены в конце этого раздела.  
  
## Трассировка  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует механизм трассировки, определенный в пространстве имен <xref:System.Diagnostics>.В этой модели трассировки данные трассировки создаются источниками трассировки, реализуемыми приложениями.Каждый источник определяется именем.Потребители трассировки создают прослушиватели трассировки для источников трассировки, для которых необходимо извлечь информацию.Чтобы получить данные трассировки, необходимо создать прослушиватель для источника трассировки.В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] это можно сделать путем добавления следующего кода в файл конфигурации службы или клиента, задав значение `switchValue` для источника трассировки модели службы.  
  
```  
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
  
 Дополнительные сведения об источниках трассировки см. в подразделе "Источник трассировки" раздела [Настройка трассировки](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md).  
  
## Трассировка и распространение действий  
 Включив `ActivityTracing` и присвоив параметру `propagateActivity` значение `true` в источниках трассировки `system.ServiceModel` для клиента и службы, можно обеспечить корреляцию трассировок в логических единицах обработки \(действиях\), между действиями в конечных точках \(путем перенаправления действий\) и между действиями с охватом нескольких конечных точек \(путем распространения идентификатора действия\).  
  
 Эти три механизма \(действия, перенаправление и распространение\) могут помочь быстрее найти первопричину ошибки с использованием программы Service Trace Viewer.Дополнительные сведения см. в разделе [Использование программы Service Trace Viewer для просмотра скоррелированных трассировок и устранения неполадок](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md).  
  
 Возможно расширить трассировку, предоставляемую ServiceModel, создав пользовательские трассировки действий.Пользовательская трассировка действий позволяет пользователю создавать действия трассировки для следующих целей.  
  
-   Группирование трассировок в логические блоки обработки.  
  
-   Корреляция действий путем перенаправления и распространения.  
  
-   Снижение расходов производительности, связанных с трассировкой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] \(например, расходы на дисковое пространство, занимаемое файлом журнала\).  
  
 Дополнительные сведения о пользовательской трассировке действий см. в образце [Расширение трассировки](../../../../docs/framework/wcf/samples/extending-tracing.md).  
  
## Ведение журнала сообщений  
 Ведение журнала сообщений можно включить как на стороне клиента, так и на стороне службы любого приложения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Чтобы включить ведение журнала сообщений, необходимо добавить следующий код в клиент или службу.  
  
```  
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
  
 При записи сообщения тип трассировки зависит от того, трассируется оно на стороне клиента или сервера.Например, сообщение "Добавить", отправленное клиенту, трассируется в категории "TransportWrite" на стороне клиента, в то время как то же сообщение трассируется в категории "TransportRead" на стороне службы.  
  
 Настройте прослушиватель трассировки, добавив следующий код в раздел <xref:System.Diagnostics> файла App.config клиента или файла Web.config службы.  
  
```  
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
>  Файлы трассировки невозможно создать, если не создан каталог журнала.Убедитесь, что каталог C:\\logs\\ существует или укажите альтернативный каталог ведения журнала в конфигурации прослушивателя.Дополнительные сведения см. в первоначальных инструкциях по настройке, приведенных в конце данного документа.  
  
 Дополнительные сведения о ведении журнала сообщений см. в разделе [Настройка ведения журнала сообщений](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md).  
  
#### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнены процедуры, описанные в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Перед выполнением образца трассировки и ведения журнала сообщений создайте каталог C:\\logs\\, чтобы служба записывала данные в файлы с расширением SVCLOG.Имя этого каталога определяется в файле конфигурации как путь для трассировок и сообщений для записи в журнал, и его можно изменить.Предоставьте сетевой службе пользователя доступ к записи в каталог журналов.  
  
3.  Чтобы выполнить построение выпуска решения для языка C\#, C\+\+ или Visual Basic .NET, следуйте инструкциям раздела [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## См. также  
 [Трассировка](../../../../docs/framework/wcf/diagnostics/tracing/index.md)   
 [Образцы наблюдения за AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)