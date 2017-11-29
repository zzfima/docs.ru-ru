---
title: "&lt;filters&gt; для &lt;routing&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7993cf90-9afd-4c3c-9608-184d5da1105c
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9dddd9f9ba5f4c2cea7e92c666e8d224ccf21cee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="ltfiltersgt-of-ltroutinggt"></a>&lt;filters&gt; для &lt;routing&gt;

Представляет раздел конфигурации, где задается набор фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при вычислении входящих сообщений.

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
| [**\<Фильтр >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Содержит фильтр маршрутизации, определяющий тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, который будет использован при оценке входящих сообщений. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<Маршрутизация >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра. |

## <a name="see-also"></a>См. также

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
