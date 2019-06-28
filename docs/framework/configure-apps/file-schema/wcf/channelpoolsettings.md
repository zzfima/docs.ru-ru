---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 70f7452a22ae08d6eccd7d3644bdc8df45087ae0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423189"
---
# <a name="channelpoolsettings"></a>\<channelPoolSettings>
Задает параметры пула каналов для пользовательской привязки.  
  
 \<system.serviceModel>  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<oneWay >  
\<channelPoolSettings>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`idleTimeout`|Положительное значение <xref:System.TimeSpan>, указывающее максимальное время бездействия канала в пуле перед отключением. Значение по умолчанию - 00:02:00.|  
|`leaseTimeout`|Значение <xref:System.TimeSpan>, которое задает интервал времени, после которого канал закрывается при возвращении в пул. Значение по умолчанию - 00:10:00.|  
|`maxOutboundChannelsPerEndpoint`|Положительное целое число, задающее максимальное количество каналов, которое можно хранить в пуле для каждой удаленной конечной точки. Значение по умолчанию — 10.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<oneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)|Включает маршрутизацию пакетов для пользовательской привязки.|  
  
## <a name="remarks"></a>Примечания  
 Квоты используются как механизм политики, служащий для предотвращения чрезмерного потребления ресурсов. Они препятствуют злонамеренным или неумышленным атакам типа «отказ в обслуживании» (DoS). Этот элемент используется при установке квот на пользовательском канале.  
  
 `ChannelPoolSettings` задает три квоты.  
  
- Квота `idleTimeout` используется для ослабления эффекта атак типа «отказ в обслуживании» (DoS) на сервере, при котором ресурсы блокируются на продолжительный период времени. На клиенте установка правильного значения может повысить надежность соединения со службой. Значение по умолчанию основано на консервативно умеренном выделении ресурсов. Это подходит для среды разработки и небольших сценариев установок. Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.  
  
- Квота `leaseTimeout` используется для интеграции с механизмами балансировки нагрузки и для повышения надежности. Значение по умолчанию основано на консервативном выделении ресурсов. Это подходит для среды разработки и небольших сценариев установок. Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.  
  
- Квота `maxOutboundChannelsPerEndpoint` устанавливает предельные значения кэша на сервере и на клиенте и используется для повышения надежности. Значение по умолчанию основано на консервативно умеренном выделении ресурсов, которое подходит для среды разработки и небольших установок. Администраторы должны обновлять значение, если данной установке начинает не хватать ресурсов или если число подключений ограничено, несмотря на доступность дополнительных ресурсов.  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay >](../../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
