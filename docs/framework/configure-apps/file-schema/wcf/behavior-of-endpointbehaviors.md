---
title: <behavior> из <endpointBehaviors>
ms.date: 03/30/2017
ms.assetid: b90ca3bc-3c22-4174-b903-e3a39898bd27
ms.openlocfilehash: 81c9ec7bd82fa0b947e438632b293ab9110067f5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398242"
---
# <a name="behavior-of-endpointbehaviors"></a>\<> поведения > \<EndpointBehaviors
Элемент `behavior` содержит коллекцию параметров поведения конечной точки. Каждое поведение индексируется по атрибуту `name`. Конечные точки могут ссылаться на каждое поведение по этому имени. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<endpointBehaviors >** ](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> поведения**  
  
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
|имя|Уникальная строка, содержащая имя конфигурации поведения. Это значение является заданной пользователем строкой, которая должна быть уникальной, поскольку она действует как строка идентификации для элемента. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и привязках и поведении, которые не имеют имен, см. в разделе [упрощенная конфигурация](../../../wcf/simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> clientCredentials](clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
|[\<Каллбаккдебуг >](callbackdebug.md)|Указывает отладку службы для объекта обратного вызова Windows Communication Foundation (WCF).|  
|[\<Каллбакктимеаутс >](callbacktimeouts.md)|Задает время ожидания для обратного вызова клиента.|  
|[\<Клиентвиа >](clientvia.md)|Задает маршрут, по которому должно быть передано сообщение.|  
|[\<dataContractSerializer >](datacontractserializer.md)|Содержит данные конфигурации для DataContractSerializer.|  
|[\<Диспатчерсинчронизатион >](dispatchersynchronization.md)|Указывает поведение конечной точки, которое позволяет службе отправлять ответы в асинхронном режиме.|  
|[\<Енаблевебскрипт >](enablewebscript.md)|Включает поведение конечной точки, позволяющее использовать службу с веб-страниц ASP.NET с поддержкой технологии AJAX. Поведение следует использовать только в сочетании с \<привязкой WebHttpBinding > Standard или с \<элементом привязки вебмессажеенкодинг >.|  
|[\<Ендпоинтдисковери >](endpointdiscovery.md)|Указывает различные параметры обнаружения для конечной точки, такие как возможность обнаружения, области и любые пользовательские модули для ее метаданных.|  
|[\<Соаппроцессинг >](soapprocessing.md)|Определяет поведение конечной точки клиента, используемое для маршалинга сообщений между различными типами привязок и версиями сообщения.|  
|[\<Синчронаусрецеиве >](synchronousreceive-element.md)|Задает поведение времени выполнения для получения сообщений в службе или клиентском приложении. Он не имеет атрибутов или дочерних элементов.|  
|[\<Трансактедбатчинг >](transactedbatching.md)|Указывает, поддерживается ли объединение транзакций для операций получения.|  
|[\<> http](webhttp.md)|Задает WebHttpBehavior в конечной точке посредством настройки конфигурации. Это поведение при использовании в сочетании с \<привязкой WebHttpBinding > Standard включает модель веб-программирования для службы WCF.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<endpointBehaviors >](endpointbehaviors.md)|Коллекция элементов поведения конечной точки.|
