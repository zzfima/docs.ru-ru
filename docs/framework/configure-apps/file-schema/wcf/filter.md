---
title: "&lt;Фильтр&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: af2095289d5f711733c71238b855c685114d1997
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltfiltergt"></a>&lt;Фильтр&gt;

Задает фильтр маршрутизации, который определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при оценке входящих сообщений, а также все требуемые фильтру сопутствующие данные или параметры.

\<system.serviceModel > \<маршрутизации > \<фильтры > \<фильтра >

## <a name="syntax"></a>Синтаксис

```xml
<routing>
  <filters>
    <filter customType="String" 
            filterData="String" 
            filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath" 
            name="String" />
  </filters>
</routing>
```

## <a name="attributes-and-elements"></a>Элементы и атрибуты

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

| Атрибут  | Описание |
| ---------- | ----------- |
| customType | Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра. Если `filterType` равно `custom`, этот атрибут содержит имя класса, чтобы создать полное имя типа.  `filterData`также может содержать значения для использования во время вычисления фильтра пользовательского типа. |
| filterData | Строка, содержащая данные фильтра. Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Строка, содержащая тип фильтра. Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| имя       | Строка, содержащая уникальное имя этого элемента фильтра. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Раздел конфигурации, в котором определяется набор фильтров маршрутизации, которые определяют тип [!INCLUDE[ indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при вычислении входящих сообщений. |

## <a name="see-also"></a>См. также

<xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>    
<xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>   
<xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>   
