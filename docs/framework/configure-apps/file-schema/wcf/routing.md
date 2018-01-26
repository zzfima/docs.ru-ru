---
title: "&lt;Маршрутизация&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6ef71753a4b0ff20a966842119adb6e637ded1f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltroutinggt"></a>&lt;Маршрутизация&gt;

Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра.

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
| [**\<Фильтры >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md) | Содержит набор фильтров маршрутизации, которые определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter, который будет использован при вычислении входящих сообщений. |
| [**\<filterTables >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md) | Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание: |
| --- | ----------- |
| **\<система. ServiceModel >** | Корневой элемент всех элементов конфигурации WCF. |

## <a name="see-also"></a>См. также

<xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
