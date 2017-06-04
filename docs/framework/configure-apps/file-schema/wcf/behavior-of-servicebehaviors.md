---
title: "&lt;behavior&gt; для &lt;serviceBehaviors&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 78fc0a08-55de-416a-ac12-a5e6ffc9a987
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;behavior&gt; для &lt;serviceBehaviors&gt;
Элемент `behavior` содержит коллекцию параметров для поведения службы.  Каждое поведение индексируется по атрибуту `name`.  Службы могут связаться с каждым поведением посредством этого имени, используя атрибут `behaviorConfiguration` элемента [\<конечная точка\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md).  Это позволяет конечным точкам иметь общие конфигурации поведений без переопределения параметров.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
> [!NOTE]
>  Элементы поведения, специфичные для действий рабочих процессов Windows, такие как [\<sendMessageChannelCache\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/sendmessagechannelcache.md), задокументированы на странице [\<behavior\> для \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md).  
  
## Синтаксис  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <serviceBehaviors>  
       <behavior name="String" />  
    </serviceBehaviors>  
  </behaviors>  
</system.ServiceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Уникальная строка, содержащая имя конфигурации поведения.  Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<persistenceProvider\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistenceprovider.md)|Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md)|Обеспечивает доступ к службе маршрутизации во время выполнения, чтобы вносить динамические изменения в конфигурацию маршрутизации.|  
|[\<serviceAuthenticationManager\>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthenticationmanager.md)|Обеспечивает элемент конфигурации рабочего процесса, который устанавливает на уровне службы действительность передачи, сообщения или инициатора.|  
|[\<serviceAuthorization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)|Задает параметры авторизации доступа к операциям службы.|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
|[\<serviceDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicedebug.md)|Задает функции по отладке и функции справки для службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
|[\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)|Указывает возможность обнаружения конечных точек службы.|  
|[\<serviceMetadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicemetadata.md)|Задает публикацию метаданных службы и связанных сведений.|  
|[\<serviceSecurityAudit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicesecurityaudit.md)|Задает параметры, позволяющие проводить аудит событий безопасности во время обслуживания.|  
|[\<serviceThrottling\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md)|Определяет механизм регулирования для службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
|[\<serviceTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicetimeouts.md)|Задает время ожидания для службы.|  
|[\<workflowRuntime\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Задает параметры для экземпляра WorkflowRuntime, связанные с размещением служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], основанных на рабочих процессах.|  
|[\<useRequestHeadersForMetadataAddress\>](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Включает получение сведений об адресе метаданных из заголовков сообщений запросов.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)|Коллекция элементов поведений службы.|