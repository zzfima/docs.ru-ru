---
title: <diagnostics>
ms.date: 03/30/2017
ms.assetid: 0c2f95c4-cc12-4fb5-a70c-7fc6fa95db58
ms.openlocfilehash: 3fc7828d399555f7c459f6dd067ce9a24b8998b6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704067"
---
# <a name="diagnostics"></a>\<Диагностика >
Элемент `diagnostics` определяет параметры, которые могут быть использованы администратором для проверки и контроля времени выполнения.  
  
 \<system.ServiceModel>  
\<Диагностика >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <diagnostics etwProviderId="String"
               performanceCounters="Off/ServiceOnly/All/Default"
               wmiProviderEnabled="Boolean">
    <endToEndTracing activityTracing="Boolean"
                     messageFlowTracing="Boolean"
                     propagateActivity="Boolean" />
    <messageLogging logEntireMessage="Boolean"
                    logMalformedMessages="Boolean"
                    logMessagesAtServiceLevel="Boolean"
                    logMessagesAtTransportLevel="Boolean"
                    maxMessagesToLog="Integer"
                    maxSizeOfMessageToLog="Integer">
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
|performanceCounters|Указывает, включены ли счетчики производительности для сборки. Допустимы следующие значения:<br /><br /> -Off: Счетчики производительности отключены.<br />-ServiceOnly Включены только счетчики производительности, относящиеся к данной службе.<br />— Все: Счетчики производительности можно просматривать во время выполнения.<br />-Значение по умолчанию: Создается единичный экземпляр счетчика производительности _WCF_Admin. Данный экземпляр используется, чтобы включить коллекцию данных SQM для использования инфраструктурой. Значения счетчика для данного экземпляра не обновляются и, соответственно, остаются нулевыми. Если для WCF не задана конфигурация, это значение используется по умолчанию.|  
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

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
