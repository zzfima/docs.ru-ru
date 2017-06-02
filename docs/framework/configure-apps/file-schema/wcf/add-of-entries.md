---
title: "&lt;add&gt; для &lt;entries&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3af4805b-dc72-4f68-b168-da4fba8c6170
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;add&gt; для &lt;entries&gt;
Представляет запись маршрутизации, которая сопоставляет фильтр с ранее определенной конечной точкой клиента.  Сообщения, соответствующие этому фильтру, будут отправлены по данному назначению.  
  
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
  
|Атрибут|Описание|  
|-------------|--------------|  
|backupList|Строка, указывающая ссылку на резервный список конечных точек.|  
|конечная точка|Строка, в которой указана ссылка на конечную точку клиента, получающую сообщения, которые соответствуют критериям фильтра, указанного в атрибуте `filterName`.|  
|filterName|Строка, в которой указана ссылка на элемент фильтра.|  
|priority|Целое число, задающее приоритет этой записи.<br /><br /> Записи в таблице маршрутизации обрабатываются исходя из приоритета, причем 0 является самым низким приоритетом.  Все записи определенного приоритета обрабатываются одновременно, и, если для текущего приоритета не находится совпадающая запись, вычисляется следующий уровень приоритета.<br /><br /> Это значение является необязательным.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, в котором содержатся записи сопоставления маршрутизации.|  
  
## См. также  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Routing.Configuration.FilterTableEntryElement](assetId:///System.ServiceModel.Routing.Configuration.FilterTableEntryElement?qualifyHint=False&amp;autoUpgrade=True)