---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269579"
---
# <a name="namespacetable"></a>\<namespaceTable>

Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.

**\<system.serviceModel >**   
&nbsp;&nbsp;**\<Маршрутизация >**   
&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable >**
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
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
| [**\<Фильтр >**](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | Определяет сопоставление префикса пространства имен, используемого в выражениях XPath. |

### <a name="parent-elements"></a>Родительские элементы

|     | Описание |
| --- | ----------- |
| [**\<Маршрутизация >**](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> для использования при вычислении входящих сообщений, а также маршрутизации, определяющих целевые конечные точки для таблиц Если фильтр соответствует отправите сообщения. |

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
