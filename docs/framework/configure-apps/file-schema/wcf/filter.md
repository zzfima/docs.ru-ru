---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: bff19f106d86c73dea80b8b57bb73442eaa2cf9f
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278789"
---
# <a name="filter"></a>\<Фильтр >

Определяет фильтр маршрутизации, который определяет тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений также все вспомогательные данные и параметры, необходимые для фильтра.

\<system.serviceModel> \<routing> \<filters> \<filter>
  
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
| customType | Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра. Если `filterType` присваивается `custom`, этот атрибут содержит имя полное имя типа создаваемого класса.  `filterData` также может содержать значения, используемые при оценке фильтра с пользовательским типом. |
| filterData | Строка, содержащая данные фильтра. Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Строка, содержащая тип фильтра. Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| имя       | Строка, содержащая уникальное имя этого элемента фильтра. |

### <a name="child-elements"></a>Дочерние элементы

Отсутствует.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
