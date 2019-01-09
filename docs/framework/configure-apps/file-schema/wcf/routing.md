---
title: '&lt;Маршрутизация&gt;'
ms.date: 03/30/2017
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
ms.openlocfilehash: 220c18ab8ea6222fcf7d9fb8a93950281c9de796
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145150"
---
# <a name="ltroutinggt"></a>&lt;Маршрутизация&gt;

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF) <xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения.

[**\<system.serviceModel >**](system-servicemodel.md)   
&nbsp;&nbsp;**\<Маршрутизация >**
  
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
    <routingTables>
      <table name="String">
        <entries>
          <add endpoint="String"
               filterName="String"
               priority="Integer" />
        </entries>
      </table>
    </routingTables>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

Нет

### <a name="child-elements"></a>Дочерние элементы

|     | Описание: |
| --- | ----------- |
| [**\<Фильтры >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Содержит набор фильтров маршрутизации, которые определяют, что тип MessageFilter Windows Communication Foundation (WCF), который будет использоваться при вычислении входящих сообщений. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание: |
| --- | ----------- |
| **\<система. ServiceModel >** | Корневой элемент всех элементов конфигурации WCF. |

## <a name="see-also"></a>См. также

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
