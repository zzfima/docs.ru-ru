---
title: '&lt;connectionPoolSettings&gt;'
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 87fcbf08d897cf8d9e1924a8a5ed2b5b20945638
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltconnectionpoolsettingsgt"></a>&lt;connectionPoolSettings&gt;
Задает дополнительные параметры пула подключений для привязки именованного канала.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<namePipeTransport >  
\<connectionPoolSettings >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<connectionPoolSettings  
        groupName="String"  
    idleTimeout"TimeSpan"  
    maxOutboundConnectionsPerEndpopint="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`groupName`|Строка, определяющая имя пула подключений, используемого для исходящих каналов. В потоковом режиме общий доступ к подключениям не предоставляется, то есть пул подключений отключен. Значение по умолчанию - строка «default». Это значение можно изменить, чтобы изолировать подключения для конкретного клиента в отдельные группы.|  
|`idleTimeout`|Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия для подключения перед его закрытием. Значение по умолчанию - 00:02:00.|  
|`maxOutboundConnectionsPerEndpoint`|Положительное целое число, указывающее максимальное число подключений к удаленной конечной точке, инициированных одной службой. Соединения сверх лимита помещаются в очередь до высвобождения ресурсов. Параметр `idleTimeout` ограничивает продолжительность времени, в течение которого подключения остаются в очереди до возникновения исключения. Значение по умолчанию — 10.<br /><br /> Этот атрибут ограничивает число одновременных активных подключений клиента к конкретной конечной точке службы. В случае превышения этого значения при наличии большего числа активных соединений клиентов служба может прекратить отвечать на запросы клиента. В таком случае это значение следует скорректировать, чтобы оно было больше предполагаемого максимума одновременных подключений клиента к конкретной конечной точке.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<namedPipeTransport >](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>  
 <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>  
 <xref:System.ServiceModel.Channels.TransportBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)  
 [Выбор транспорта](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
