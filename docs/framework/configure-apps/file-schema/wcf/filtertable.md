---
title: '&lt;filterTable&gt;'
ms.date: 03/30/2017
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
ms.openlocfilehash: 7bdc76ba7a8e2927b93fa0207f48cc569279482f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltfiltertablegt"></a>&lt;filterTable&gt;
Представляет таблицу маршрутизации, содержащую список фильтров для оценки сообщения, а конечная точка клиента для перенаправления сообщений, если фильтр имеет значение true.  
  
 \<system.serviceModel >  
\<Маршрутизация >  
\<routingTables >  
\<Таблица >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
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
|[\<Фильтры >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Сопоставление между фильтрами маршрутизации и целевыми конечными точками (которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров).|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, содержащий таблицы маршрутизации.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>    
