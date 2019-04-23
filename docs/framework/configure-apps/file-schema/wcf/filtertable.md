---
title: <filterTable>
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 4e5c7d56e35afe3001f4c70064adbfef7702c720
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59229281"
---
# <a name="filtertable"></a>\<filterTable >
Представляет таблицу маршрутизации, которая содержит список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр возвращает значение true.  
  
 \<system.serviceModel>  
\<Маршрутизация >  
\<routingTables>  
\<Таблица >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<routing>
  <filterTables>
    <filterTable name="String">
      <entries>
        <add backupList="String"
             endpointName="String"
             filterName="String"
             priority="Integer" />
      </entries>
    </filterTable>
  </filterTables>
</routing>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|имя|Строка, содержащая уникальное имя этого элемента конфигурации.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Фильтры>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, содержащий таблицы маршрутизации.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>
