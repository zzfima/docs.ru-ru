---
title: <behavior> из <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 34306f99f2343c987700e964aaa9800aa3f488fa
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55283950"
---
# <a name="behavior-of-endpointbehaviors"></a>\<поведение > из \<endpointBehaviors >
Элемент `behavior` содержит коллекцию параметров поведения конечной точки. Каждое поведение индексируется по атрибуту `name`. Конечные точки могут ссылаться на каждое поведение по этому имени. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<endpointBehaviors>  
\<поведение >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.ServiceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="String" />
    </endpointBehaviors>
  </behaviors>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Уникальная строка, содержащая имя конфигурации поведения. Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
|[\<callbackDebug >](../../../../../docs/framework/configure-apps/file-schema/wcf/callbackdebug.md)|Задает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).|  
|[\<callbackTimeouts >](../../../../../docs/framework/configure-apps/file-schema/wcf/callbacktimeouts.md)|Задает время ожидания для обратного вызова клиента.|  
|[\<clientVia >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientvia.md)|Задает маршрут, по которому должно быть передано сообщение.|  
|[\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<dispatcherSynchronization >](../../../../../docs/framework/configure-apps/file-schema/wcf/dispatchersynchronization.md)|Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.|  
|[\<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md)|Включает поведение конечной точки, позволяющее использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX. Поведение следует использовать только в сочетании со \<webHttpBinding > стандартной привязки или \<webMessageEncoding > элемента привязки.|  
|[\<endpointDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointdiscovery.md)|Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.|  
|[\<soapProcessing >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md)|Определяет поведение конечной точки клиента, используемое для маршалинга сообщений между различными типами привязок и версиями сообщения.|  
|[\<synchronousReceive >](../../../../../docs/framework/configure-apps/file-schema/wcf/synchronousreceive-element.md)|Задает поведение времени выполнения для получения сообщений в службе или клиентском приложении. Он не имеет атрибутов или дочерних элементов.|  
|[\<transactedBatching >](../../../../../docs/framework/configure-apps/file-schema/wcf/transactedbatching.md)|Указывает, поддерживается ли объединение транзакций для операций получения.|  
|[\<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md)|Задает WebHttpBehavior в конечной точке посредством настройки конфигурации. Это поведение, при использовании в сочетании с \<webHttpBinding > Стандартная привязка включает модель веб-программирования для службы WCF.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<endpointBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpointbehaviors.md)|Коллекция элементов поведения конечной точки.|
