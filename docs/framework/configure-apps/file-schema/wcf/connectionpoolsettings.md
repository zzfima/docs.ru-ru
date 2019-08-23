---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 3c8d905a04f8f6d7ecff9b0ef9e7d3c8afa727e3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925971"
---
# <a name="connectionpoolsettings"></a>\<Коннектионпулсеттингс >
Задает дополнительные параметры пула подключений для привязки именованного канала.  
  
 \<> System. serviceModel  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Намепипетранспорт >  
\<Коннектионпулсеттингс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
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
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Намедпипетранспорт >](namedpipetransport.md)|Определяет транспорт, вызывающий передачу сообщений с использованием именованных каналов.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Транспорты](../../../wcf/feature-details/transports.md)
- [Выбор транспорта](../../../wcf/feature-details/choosing-a-transport.md)
- [Привязки](../../../wcf/bindings.md)
- [Расширение привязок](../../../wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../wcf/extending/custom-bindings.md)
- [\<customBinding >](custombinding.md)
