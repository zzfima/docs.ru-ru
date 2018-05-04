---
title: '&lt;filters&gt; для &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 9f0fa9bf51d264346738172f57a8efca7950fdb7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;filters&gt; для &lt;routing&gt;

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при вычислении входящих сообщений.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;[**\<Маршрутизация >**](routing.md)   
&nbsp;&nbsp;&nbsp;&nbsp;**\<Фильтры >**

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

Нет

### <a name="child-elements"></a>Дочерние элементы

|     | Описание |
| --- | ----------- |
| [**\<Фильтр >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Содержит фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> будет использоваться при вычислении входящих сообщений. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<Маршрутизация >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизацию таблиц, определяющих целевые конечные точки для Отправка сообщений при соответствии критериям фильтра. |

## <a name="see-also"></a>См. также

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
