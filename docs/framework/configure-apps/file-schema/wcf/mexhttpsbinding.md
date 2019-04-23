---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 4e96c28ac9b372092d06538d24d165dde6c5fe48
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203136"
---
# <a name="mexhttpsbinding"></a>\<mexHttpsBinding>
Задает параметры для привязки, используемой для обмена сообщениями WS-MetadataExchange (WS-MEX) посредством HTTPS.  
  
 \<system.ServiceModel>  
\<привязки >  
\<mexHttpsBinding>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
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
  
## <a name="remarks"></a>Примечания  
 Эта привязка по существу является привязкой `WSHttpBinding`, которая поддерживает безопасность уровня транспорта с помощью сертификатов. Дополнительные сведения о настройке и использовании такой конечной точки метаданных см. в разделе [как: Настройка пользовательских WS-Metadata Exchange привязки](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [как: Получение метаданных через - MEX привязку, не](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), образец [конечной точки метаданных Secure Custom](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [Практическое руководство. Публикация метаданных для службы с помощью файла конфигурации](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Публикация и получение метаданных через пользовательскую привязку](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [Практическое руководство. Настройка пользовательских WS-Metadata Exchange привязки](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Практическое руководство. Получение метаданных через - MEX привязку, не](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [Пользовательская конечная точка защищенных метаданных](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)
- [Метаданные](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../../../docs/framework/misc/binding.md)
