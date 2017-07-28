---
title: "&lt;поведения&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0e5da4e6-1aa5-466c-924e-f10efee57f0b
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;поведения&gt;
Данный элемент определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно.  Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel\>  
  
## Синтаксис  
  
```  
  
<behaviors>  
   <serviceBehaviors>  
   </serviceBehaviors>  
   <endpointBehaviors>  
   </endpointBehaviors>  
</behaviors>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Данный раздел конфигурации представляет все типы поведения, определенные для конкретной конечной точки.|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|В данном разделе конфигурации представлены все поведения, определенные для конкретной службы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation \(WCF\).|  
  
## Заметки  
 Элемент `<remove>` можно использовать для удаления определенного поведения из коллекции.  Для этого нужно просто указать имя удаляемого поведения в атрибуте `name` элемента `<remove>`.  Также можно использовать элемент `<clear>`, очищающий все содержимое коллекции, чтобы обеспечить запуск пустой коллекции.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.BehaviorsSection>   
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.EndpointBehaviorElement>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElementCollection>   
 <xref:System.ServiceModel.Configuration.ServiceBehaviorElement>   
 [Настройка и расширение среды выполнения с помощью поведений](../../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)   
 [Настройка поведений клиентов](../../../../../docs/framework/wcf/configuring-client-behaviors.md)   
 [Задание поведения клиента во время выполнения](../../../../../docs/framework/wcf/specifying-client-run-time-behavior.md)   
 [Указание поведения службы во время выполнения](../../../../../docs/framework/wcf/specifying-service-run-time-behavior.md)   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)