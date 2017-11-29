---
title: "&lt;Диагностика&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: df86d364d75f62cbe8be5f72e0b3b120784c35a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltdiagnosticsgt"></a>&lt;Диагностика&gt;
Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.  
  
 \<система. ServiceModel >  
\<Диагностика >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>  
   <diagnostics etwProviderId="String"       performanceCounters="Off/ServiceOnly/All/Default"              wmiProviderEnabled="Boolean" >       <endToEndTracing activityTracing="Boolean"  
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
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|etwProviderId|Строка, которая задает идентификатор для поставщика отслеживания событий, который записывает события в сеансы ETW.|  
|performanceCounters|Указывает, включены ли счетчики производительности для сборки. Допустимы следующие значения:<br /><br /> -Off: Счетчики производительности отключены.<br />-ServiceOnly: Включены только те счетчики производительности, относящиеся к данной службе.<br />— Все: Производительности счетчики можно просматривать во время выполнения.<br />-По умолчанию: Один производительности счетчика экземпляра _wcf_admin. Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой. Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми. Если для WCF не задана конфигурация, это значение используется по умолчанию.|  
|wmiProviderEnabled|Логическое значение, определяющее, включен ли поставщик WMI для сборки. Данный поставщик WMI требуется пользователю, чтобы на время выполнения получить доступ к функциональным возможностям проверки и контроля Windows Communication Foundation (WCF). Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<endToEndTracing >](../../../../../docs/framework/configure-apps/file-schema/wcf/endtoendtracing.md)|Элемент конфигурации, который позволяет включать и отключать различные аспекты сквозной отслеживания во время выполнения приложения службы.|  
|[\<messageLogging >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagelogging.md)|Описывает параметры ведения журнала сообщений WCF.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|serviceModel|Корневой элемент всех элементов конфигурации WCF.|  
  
## <a name="remarks"></a>Примечания  
 В разделе `diagnostics` определяются параметры диагностики для всех служб, содержащихся в сборке. Отдельные параметры диагностики можно определить на уровне службы, только если сборка содержит одну службу. Атрибуты заданы в соответствии с требованиями раздела.  
  
## <a name="example"></a>Пример  
  
```xml  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>
