---
title: '&lt;заголовки&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 7683b07093719cda6b210a4174d47e5785d4644d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltheadersgt"></a>&lt;заголовки&gt;
Помимо базового универсального кода ресурса (URI) к конечной точке можно обратиться по одному или нескольким заголовкам SOAP. К сценариям, в которых это бывает удобно, относятся сценарии с посредниками протокола SOAP, в которых конечная точка требует, чтобы клиенты включали заголовки SOAP, нацеленные на посредники. Данный элемент конфигурации можно использовать для определения подобных пользовательских заголовков адресов. Записи в коллекции заголовков конечной точки являются пользовательскими элементами XML. Каждый элемент должен представлять собой XML-код правильного формата.  
  
 \<система. ServiceModel >  
\<Клиент >  
\<Конечная точка >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|Region||  
|Член||  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Конечная точка >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Настраивает разные типы конечных точек.|  
  
## <a name="remarks"></a>Примечания  
 Необязательные заголовки содержат более подробную информацию для идентификации конечной точки и взаимодействия с ней. Например, в заголовках может содержаться информация о том, как следует обрабатывать входящее сообщение, куда конечная точка должна отправить ответное сообщение или какой экземпляр службы необходимо использовать для обработки входящего сообщения от конкретного пользователя, если доступно несколько экземпляров.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [Конечные точки: адреса, привязки и контракты](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
