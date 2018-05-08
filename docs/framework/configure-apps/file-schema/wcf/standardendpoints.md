---
title: '&lt;standardEndpoints&gt;'
ms.date: 03/30/2017
ms.assetid: d62153d7-a6e6-462a-a784-cca61e9c2ba1
ms.openlocfilehash: 689ed041304d5ae84218dde2575d7bbd0440490d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltstandardendpointsgt"></a>&lt;standardEndpoints&gt;
Этот раздел конфигурации позволяет задать коллекцию стандартных конечных точек (многократно используемых, заранее настроенных конечных точек). Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным. Например, в конечной точке обнаружения фиксированным является контракт. По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.  
  
 \<система. ServiceModel >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>  
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<announcementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/announcementendpoint.md)|Определяет стандартную конечную точку с фиксированным контрактом объявления. Служба может также объявлять свою доступность путем отправки сообщения в режимах «в сети» и «не в сети» соответственно при открытии и закрытии службы. Службы Windows Communication Foundation (WCF) задает конечные точки объявлений в [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) элемент и использует AnnouncementClient для выполнения объявления. Клиент, вызывающий должен прослушивать заявление от другой службы фактически работает как служба WCF; Таким образом, вы должны настроить конечные точки объявлений для этого клиента в [ \<services >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md) раздела.|  
|[\<конечной точки discoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryendpoint.md)|Определяет стандартную конечную точку с фиксированным контрактом обнаружения. При добавлении в конфигурацию службы указывает, где необходимо следить за появлением сообщений обнаружения. При добавлении в клиентскую конфигурацию указывает, куда необходимо отправлять запросы обнаружения.|  
|[\<dynamicEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/dynamicendpoint.md)|Этот элемент конфигурации определяет стандартную конечную точку, содержащую сведения, позволяющие приложению работать в качестве клиентской программы, которая может найти адрес конечной точки динамически во время выполнения.|  
|[\<mexEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/mexendpoint.md)|Определяет стандартную конечную точку с фиксированным контрактом IMetadataExchange. Поскольку все конечные точки обмена метаданными указывают IMetadataExchange в качестве своего контракта, можно использовать эту стандартную точку вместо определения собственной точки.|  
|[\<udpAnnoucementEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpannoucementendpoint.md)|Определяет стандартную конечную точку, используемую службами для отправки сообщений с объявлениями по привязке UDP. Имеет фиксированный контракт и поддерживает две версии обнаружения. Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1). Можно задать многопоточный адрес, который будет использовать для отправки и получения сообщений объявлений.|  
|[\<точка udpDiscoveryEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/udpdiscoveryendpoint.md)|Определяет стандартную конечную точку, заранее настроенную для операций обнаружения по привязке многоадресной рассылки UDP. Эта конечная точка имеет фиксированный контракт и поддерживает две версии протокола WS-Discovery. Кроме того, она имеет фиксированную привязку UDP и значение адреса по умолчанию, как определено в спецификациях WS-Discovery (WS-Discovery от апреля 2005 или WS-Discovery версии 1.1).|  
|[\<webHttpEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpendpoint.md)|Определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязки, которая автоматически добавляет [ \<webHttp >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md) поведение. Используйте эту конечную точку при написании службы REST.|  
|[\<webScriptEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/webscriptendpoint.md)|Определяет стандартную конечную точку с фиксированным [ \<webHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md) привязки, которая автоматически добавляет [ \<enableWebScript >](../../../../../docs/framework/configure-apps/file-schema/wcf/enablewebscript.md) поведение. Используйте эту конечную точку при написании службы, вызываемой из приложения ASP.NET AJAX.|  
|[\<workflowControlEndpoint >](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowcontrolendpoint.md)|Определяет стандартную конечную точку для управления выполнением экземпляров рабочего процесса (создание, выполнение, приостановка, завершение и т. д.).|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|\<система. ServiceModel >|Корневой элемент всех элементов конфигурации WCF.|  
  
## <a name="see-also"></a>См. также  
 [Стандартные конечные точки](../../../../../docs/framework/wcf/feature-details/standard-endpoints.md)
