---
title: '&lt;mexTcpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 01baba8d-d784-4255-9ea2-7afff1482bf0
ms.openlocfilehash: a69f0af60d3f6723285ceb239a86775c9a1b510f
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147178"
---
# <a name="ltmextcpbindinggt"></a>&lt;mexTcpBinding&gt;
Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) по TCP.  
  
 \<система. ServiceModel >  
\<привязки >  
\<mexTcpBinding >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<mexTcpBinding>
  <binding closeTimeout="TimeSpan"
           name="string"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan">
  </binding>
</mexTcpBinding>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции закрытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`name`|Строка, содержащая имя конфигурации привязки. Это значение должно быть уникальным, поскольку оно используется в качестве идентификатора привязки. Каждая привязка имеет атрибуты `name` и `namespace`, которые совместно однозначно идентифицируют привязку в метаданных службы. Кроме того, это имя является уникальным среди привязок одного типа. Начиная с версии [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] для привязок и поведений необязательно задавать имена. Дополнительные сведения о конфигурации по умолчанию и безымянных привязках и поведениях см. в разделе [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) и [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции открытия. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
|`receiveTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции получения. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:10:00.|  
|`sendTimeout`|Значение <xref:System.TimeSpan>, которое задает длительность времени ожидания для завершения операции отправки. Это значение должно быть больше или равно <xref:System.TimeSpan.Zero>. Значение по умолчанию - 00:01:00.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<привязки >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|Этот элемент содержит коллекцию стандартных и пользовательских привязок.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.MexTcpBindingElement>  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexTcpBinding%2A>  
 [Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Публикация и получение метаданных через пользовательскую привязку](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)  
 [Метаданные](../../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
