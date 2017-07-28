---
title: "Рекомендуемые параметры для трассировки и ведения журналов сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Рекомендуемые параметры для трассировки и ведения журналов сообщений
Этот раздел содержит описание рекомендуемых параметров трассировки и регистрации сообщений для различных операционных сред.  
  
## Параметры, рекомендуемые для рабочей среды  
 В рабочей среде, если используются источники трассировки WCF, рекомендуется в `switchValue` задать значение Warning.  При использовании источника трассировки WCF `System.ServiceModel` рекомендуется задать в атрибуте `switchValue` значение `Warning`, а в атрибуте `propagateActivity` \- значение `true`.  При использовании источника трассировки, определенного пользователем, рекомендуется присвоить атрибуту `switchValue` значение `Warning, ActivityTracing`.  Это можно сделать вручную с помощью объекта [Средство редактирования конфигурации \(SvcConfigEditor.exe\)](../../../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  Если в работе не ожидается резкого подъема производительности, во всех перечисленных выше случаях атрибуту `switchValue` можно присвоить значение `Information`, при котором генерируется достаточно большое количество данных трассировки.  Следующий пример иллюстрирует задание описанных рекомендуемых параметров.  
  
```  
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
  
## Параметры, рекомендуемые для развертывания или отладки  
 При работе в среде развертывания или отладки рекомендуется выбирать значения `Information` или `Verbose` наряду с `ActivityTracing` как для определенных пользователем, так и для заданных `System.ServiceModel` источников трассировки.  Чтобы улучшить процесс отладки, к конфигурации необходимо добавить дополнительный источник трассировки \(`System.ServiceModel.MessageLogging`\) для активации функции регистрации сообщений.  Обратите внимание, что атрибут `switchValue` не влияет на этот источник трассировки.  
  
 Следующий пример иллюстрирует задание рекомендуемых параметров с помощью общего прослушивателя, использующего `XmlWriterTraceListener`.  
  
```  
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
  
## Изменение параметров с помощью инструментария WMI  
 Для изменения параметров конфигурации во время работы можно использовать инструментарий WMI \(выполняется путем включения атрибута `wmiProviderEnabled` в конфигурации, как показано в предыдущем примере конфигурации\).  Например, для изменения во время работы уровней источника трассировки с Warning на Information можно использовать инструментарий WMI в CIM Studio.  Следует помнить о том, что такой способ отладки может значительно снизить производительность.  Дополнительные сведения об использовании инструментария WMI см. в разделе [Использование Windows Management Instrumentation для диагностики](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).  
  
## Использование корреляции событий в трассировке ASP.NET  
 События ASP.NET не получают корреляционный идентификатор \(ActivityID\), если не включена функция трассировки событий ASP.NET.  Чтобы просматривать корреляционные события, необходимо активировать трассировку событий ASP.NET с помощью следующей команды в командной консоли, которая вызывается путем нажатия **Пуск**, **Выполнить** и ввода **cmd**.  
  
```  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 Для отключения трассировки событий ASP.NET используйте следующую команду.  
  
```  
logman stop mytrace -ets  
```  
  
## См. также  
 [Использование Windows Management Instrumentation для диагностики](../../../../../docs/framework/wcf/diagnostics/wmi/index.md)