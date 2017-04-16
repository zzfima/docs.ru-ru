---
title: "&lt;behavior&gt; для &lt;endpointBehaviors&gt; | Microsoft Docs"
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
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# &lt;behavior&gt; для &lt;endpointBehaviors&gt;
Элемент `behavior` содержит коллекцию параметров поведения конечной точки.  Каждое поведение индексируется по атрибуту `name`.  Конечные точки могут ссылаться на каждое поведение по этому имени.  Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена.  Дополнительные сведения о конфигурации по умолчанию и о безымянных привязках и поведениях см. в разделах [Упрощенная конфигурация](../../../../../docs/framework/wcf/simplified-configuration.md) и [Упрощенная конфигурация служб WCF](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
## Синтаксис  
  
```  
  
<system.ServiceModel>  
  <behaviors>  
    <endpointBehaviors>  
       <behavior name="String" />  
    </endpointBehaviors>  
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
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
|[\<callbackDebug\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|Задает отладку службы для объекта обратного вызова [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
|[\<callbackTimeouts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|Задает время ожидания для обратного вызова клиента.|  
|[\<clientVia\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|Задает маршрут, по которому должно быть передано сообщение.|  
|[\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<dispatcherSynchronization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.|  
|[\<enableWebScript\>](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|Включает поведение конечной точки, позволяющее использовать службу с веб\-страниц ASP.NET с поддержкой технологии AJAX.  Поведение должно использоваться только в сочетании со стандартной привязкой \<webHttpBinding\>, либо с элементом привязки \<webMessageEncoding\>.|  
|[\<endpointDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.|  
|[\<soapProcessing\>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|Определяет поведение конечной точки клиента, используемое для упаковки сообщений между различными типами привязок и версиями сообщения.|  
|[\<synchronousReceive\>](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|Задает поведение времени выполнения для получения сообщений в службе или клиентском приложении.  Он не имеет атрибутов или дочерних элементов.|  
|[\<transactedBatching\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|Указывает, поддерживается ли объединение транзакций для операций получения.|  
|[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|Задает WebHttpBehavior в конечной точке посредством настройки конфигурации.  Данное поведение, при совместной работе со стандартной привязкой \<webHttpBinding\>, позволяет использовать модель веб\-программирования для службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<endpointBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Коллекция элементов поведения конечной точки.|