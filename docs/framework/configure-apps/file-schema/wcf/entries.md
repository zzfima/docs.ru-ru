---
title: "&lt;entries&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 202e430c-c1b9-4343-abe2-ac78c181a3b7
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;entries&gt;
Запись маршрутизации, содержащая сопоставление между фильтрами маршрутизации и целевыми конечными точками \(которые будут использованы при отправке сообщений при условии совпадения с критериями фильтров\).  
  
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
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<фильтры\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Сопоставляет фильтр с ранее определенной конечной точкой клиента.  Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, содержащий таблицу маршрутизации.|  
  
## См. также  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Routing.Configuration.FilterTableEntryElement](assetId:///System.ServiceModel.Routing.Configuration.FilterTableEntryElement?qualifyHint=False&amp;autoUpgrade=True)