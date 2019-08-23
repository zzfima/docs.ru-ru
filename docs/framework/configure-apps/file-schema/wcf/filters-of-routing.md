---
title: <filters> из <routing>
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: ba60958ad33b46b40285f3f70001273bb3af3a63
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925617"
---
# <a name="filters-of-routing"></a>\<фильтрует > \<> маршрутизации

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений.

[ **\<> System. serviceModel**](system-servicemodel.md)   
&nbsp;&nbsp;[ **\<> маршрутизации**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp; **\<Фильтры >**
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <routing>
    <filters>
      <filter customType="String"
              filterData="String"
              filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"
              name="String" />
    </filters>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Отсутствуют

### <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [ **\<> фильтра**](filter.md) | Содержит фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [ **\<> маршрутизации**](routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений, а также таблицы маршрутизации, определяющие целевые конечные точки. Отправка сообщений в при совпадении фильтра. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
