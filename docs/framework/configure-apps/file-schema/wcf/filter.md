---
title: <filter>
ms.date: 03/30/2017
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
ms.openlocfilehash: 68de255b9f11dc4377159d1cc3efa575633db316
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918894"
---
# <a name="filter"></a>\<> фильтра

Определяет фильтр маршрутизации, определяющий тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , который будет использоваться при оценке входящих сообщений, а также любые вспомогательные данные или параметры, необходимые для фильтра.

\<\<> \< фильтровмаршрутизации>System.\<ServiceModel > фильтров >
  
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
| customType | Строка, содержащая полное имя для пользовательского типа, используемого в качестве фильтра. Если `filterType` параметр имеет `custom`значение, этот атрибут содержит полное имя типа создаваемого класса.  `filterData`может также содержать значения, используемые при вычислении настраиваемого фильтра типов. |
| filterData | Строка, содержащая данные фильтра. Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| filterType | Строка, содержащая тип фильтра. Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>. |
| имя       | Строка, содержащая уникальное имя этого элемента фильтра. |

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

| Элемент | Описание |
| ------- | ----------- |
| [\<> маршрутизации](routing.md) | Раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> , используемый при оценке входящих сообщений. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.FilterElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.Routing.Configuration.FilterType?displayProperty=nameWithType>
