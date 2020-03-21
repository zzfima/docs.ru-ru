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
# <a name="tracing-and-message-logging"></a>Трассировка и ведение журнала сообщений
В этом образце показано, как включить трассировку и ведение журнала сообщений. Полученные следы и журналы сообщений просматриваются с помощью [инструмента просмотра служебного следа (SvcTraceViewer.exe).](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) Этот пример основан на [получении начала](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## <a name="tracing"></a>Трассировка  
 Фонд связи Windows (WCF) использует механизм <xref:System.Diagnostics> отслеживания, определяемый в пространстве имен. В этой модели трассировки данные трассировки создаются источниками трассировки, реализуемыми приложениями. Каждый источник определяется именем. Потребители трассировки создают прослушиватели трассировки для источников трассировки, для которых необходимо извлечь информацию. Чтобы получить данные трассировки, необходимо создать прослушиватель для источника трассировки. В WCF это можно сделать, добавив следующий код в файл конфигурации службы или `switchValue`клиента, установив источник трассировки модели обслуживания:  
  
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
  
 Для получения дополнительной информации об источниках следов можно найти раздел Trace Source в теме [«Настройка трассировки».](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
## <a name="activity-tracing-and-propagation"></a>Трассировка и распространение действий  
 Впустив `ActivityTracing` и `propagateActivity` установите `true` в `system.ServiceModel` источниках трассировки как для клиента, так и для службы, они обеспечивают корреляцию следов в рамках логических единиц обработки (деятельности), между действиями в конечных точках (через передачи активности) и между действиями, охватывающими несколько конечных точек (через распространение идентификатора активности).  
  
 Эти три механизма (действия, перенаправление и распространение) могут помочь быстрее найти первопричину ошибки с использованием программы Service Trace Viewer. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
  
 Возможно расширить трассировку, предоставляемую ServiceModel, создав пользовательские трассировки действий. Пользовательская трассировка действий позволяет пользователю создавать действия трассировки для следующих целей.  
  
- Группирование трассировок в логические блоки обработки.  
  
- Корреляция действий путем перенаправления и распространения.  
  
- Уменьшите стоимость производительность отслеживания WCF (например, стоимость дискового пространства файла журнала).  
  
 Для получения дополнительной информации о отслеживании активности, определяемой пользователем, пожалуйста, ознакомьтесь с образцом [расширяющейся трассировки.](../../../../docs/framework/wcf/samples/extending-tracing.md)  
  
## <a name="message-logging"></a>Ведение журналов сообщений  
 Регистрация сообщений может быть включена как на клиенте, так и на обслуживании любого приложения WCF. Чтобы включить ведение журнала сообщений, необходимо добавить следующий код в клиент или службу.  
  
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
> Файлы трассировки невозможно создать, если не создан каталог журнала. Убедитесь, что каталог C:\logs\ существует или укажите альтернативный каталог ведения журнала в конфигурации прослушивателя. Дополнительные сведения см. в первоначальных инструкциях по настройке, приведенных в конце данного документа.  
  
 Для получения дополнительной информации о регистрации сообщений можно ознакомиться на теме [«Настройка регистрации сообщений».](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)  
  
2. Перед выполнением образца трассировки и ведения журнала сообщений создайте каталог C:\logs\, чтобы служба записывала данные в файлы с расширением SVCLOG. Имя этого каталога определяется в файле конфигурации как путь для трассировок и сообщений для записи в журнал, и его можно изменить. Предоставьте сетевой службе пользователя доступ к записи в каталог журналов.  
  
3. Чтобы создать выпуск решения для C,, C-, или Visual Basic .NET, следуйте инструкциям по [созданию образцов Фонда коммуникаций Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)  
  
4. Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>См. также раздел

- [Трассировки](../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Образцы наблюдения за AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))
