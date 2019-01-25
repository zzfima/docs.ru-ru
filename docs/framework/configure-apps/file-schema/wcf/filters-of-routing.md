---
title: '&lt;filters&gt; для &lt;routing&gt;'
ms.date: 03/30/2017
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
ms.openlocfilehash: 468c10bc06b60f80ce93cf413c02582fe3861f70
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704437"
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;filters&gt; для &lt;routing&gt;

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений.

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

|     | Описание: |
| --- | ----------- |
| [**\<Маршрутизация >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
