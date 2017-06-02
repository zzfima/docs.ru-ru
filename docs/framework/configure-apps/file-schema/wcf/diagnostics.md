---
title: "&lt;диагностика&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# &lt;диагностика&gt;
Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
   <diagnostics etwProviderId=”String”  
       performanceCounters="Off/ServiceOnly/All/Default"         
       wmiProviderEnabled="Boolean" >  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
       <messageLogging logEntireMessage="Boolean"  
          logMalformedMessages="Boolean"  
          logMessagesAtServiceLevel="Boolean"  
          logMessagesAtTransportLevel="Boolean"  
          maxMessagesToLog="Integer"  
          maxSizeOfMessageToLog="Integer" >  
          <filters>  
             <clear />  
          </filters>  
       </messageLogging>  
   </diagnostics>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|etwProviderId|Строка, которая задает идентификатор для поставщика отслеживания событий, который записывает события в сеансы ETW.|  
|performanceCounters|Указывает, включены ли счетчики производительности для сборки.  Допустимы следующие значения:<br /><br /> -   Off \- счетчики производительности отключены;<br />-   ServiceOnly \- включены только счетчики производительности, относящиеся к данной службе;<br />-   All \- счетчики производительности можно просматривать во время выполнения;<br />-   Default \- создается единичный экземпляр счетчика производительности \_WCF\_Admin.  Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой.  Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми.  Если для WCF не задана конфигурация, это значение используется по умолчанию.|  
|wmiProviderEnabled|Логическое значение, определяющее, включен ли поставщик WMI для сборки.  Данный поставщик WMI требуется пользователю, чтобы на время выполнения получить доступ к функциональным возможностям проверки и контроля Windows Communication Foundation \(WCF\).  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<endToEndTracing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.|  
|[\<messageLogging\>](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Описывает параметры ведения журнала сообщений WCF.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|serviceModel|Корневой элемент всех элементов конфигурации WCF.|  
  
## Заметки  
 В разделе `diagnostics` определяются параметры диагностики для всех служб, содержащихся в сборке.  Отдельные параметры диагностики можно определить на уровне службы, только если сборка содержит одну службу.  Атрибуты заданы в соответствии с требованиями раздела.  
  
## Пример  
  
```  
<diagnostics wmiProviderEnabled="false"  
       performanceCounters="all">  
       <messageLogging logEntireMessage="true"  
          logMalformedMessages="true"  
          logMessagesAtServiceLevel="true"  
          logMessagesAtTransportLevel="true"  
          maxMessagesToLog="42"  
          maxSizeOfMessageToLog="42">  
         <filters>  
         <clear />  
    </filters>  
       </messageLogging>  
</diagnostics>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>