---
title: Рекомендуемые параметры для трассировки и ведения журналов сообщений
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 604aae2c0a0c5390428e7f1a2c99e17e90ee76a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185735"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a>Рекомендуемые параметры для трассировки и ведения журналов сообщений
Этот раздел содержит описание рекомендуемых параметров трассировки и регистрации сообщений для различных операционных сред.  
  
## <a name="recommended-settings-for-a-production-environment"></a>Параметры, рекомендуемые для рабочей среды  
 В рабочей среде, если используются источники трассировки WCF, рекомендуется в `switchValue` задать значение Warning. При использовании источника трассировки WCF `System.ServiceModel` рекомендуется задать в атрибуте `switchValue` значение `Warning`, а в атрибуте `propagateActivity` - значение `true`. При использовании источника трассировки, определенного пользователем, рекомендуется присвоить атрибуту `switchValue` значение `Warning, ActivityTracing`. Это можно сделать вручную с помощью [инструмента редактора конфигурации (SvcConfigEditor.exe).](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md) Если в работе не ожидается резкого подъема производительности, во всех перечисленных выше случаях атрибуту `switchValue` можно присвоить значение `Information`, при котором генерируется достаточно большое количество данных трассировки. Следующий пример иллюстрирует задание описанных рекомендуемых параметров.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a>Параметры, рекомендуемые для развертывания или отладки  
 При работе в среде развертывания или отладки рекомендуется выбирать значения `Information` или `Verbose` наряду с `ActivityTracing` как для определенных пользователем, так и для заданных `System.ServiceModel` источников трассировки. Чтобы улучшить процесс отладки, к конфигурации необходимо добавить дополнительный источник трассировки (`System.ServiceModel.MessageLogging`) для активации функции регистрации сообщений. Обратите внимание, что атрибут `switchValue` не влияет на этот источник трассировки.  
  
 Следующий пример иллюстрирует задание рекомендуемых параметров с помощью общего прослушивателя, использующего `XmlWriterTraceListener`.  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a>Изменение параметров с помощью инструментария WMI  
 Для изменения параметров конфигурации во время работы можно использовать инструментарий WMI (выполняется путем включения атрибута `wmiProviderEnabled` в конфигурации, как показано в предыдущем примере конфигурации). Например, для изменения во время работы уровней источника трассировки с Warning на Information можно использовать инструментарий WMI в CIM Studio. Следует помнить о том, что такой способ отладки может значительно снизить производительность. Для получения дополнительной информации об использовании WMI можно ознакомиться на тему [«Использование инструментов управления Windows для диагностики».](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a>Использование корреляции событий в трассировке ASP.NET  
 События ASP.NET не получают корреляционный идентификатор (ActivityID), если не включена функция трассировки событий ASP.NET. Чтобы правильно увидеть коррелированные события, необходимо включить ASP.NET отслеживания событий, используя следующую команду в командной консоли, на которую можно ссылаться, перейдя в **Start,** **Run** и type **cmd,**  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 Для отключения трассировки событий ASP.NET используйте следующую команду.  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a>См. также раздел

- [Использование инструментов управления Windows для диагностики](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)
