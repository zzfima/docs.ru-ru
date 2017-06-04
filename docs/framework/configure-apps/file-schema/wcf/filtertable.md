---
title: "&lt;filterTable&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e9f05441-3ad1-49b9-a267-71724aa094b4
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;filterTable&gt;
Представляет таблицу маршрутизации, которая содержит список фильтров, с помощью которых вычисляются сообщения, а также клиентскую конечную точку, которой будут направляться сообщения, если фильтр возвратит значение true.  
  
## Синтаксис  
  
```vb  
  
<routing>  
      <filterTables>  
        <filterTable name="String">  
          <entries>  
            <add backupList=”String”  
                 endpointName="String"   
                 filterName="String"   
                 priority="Integer" />  
          </entries>  
        </table>  
      </routingTables>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Элемент|Описание|  
|-------------|--------------|  
|имя|Строка, содержащая уникальное имя этого элемента конфигурации.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<фильтры\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Сопоставление между фильтрами маршрутизации и целевыми конечными точками \(которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров\).|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, содержащий таблицы маршрутизации.|  
  
## См. также  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)