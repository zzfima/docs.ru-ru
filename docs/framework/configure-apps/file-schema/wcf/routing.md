---
title: "&lt;маршрутизация&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a210c209-3940-4288-9a8e-39b1e62606bc
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;маршрутизация&gt;
Представляет раздел конфигурации для определения набора фильтров маршрутизации, которые определяют тип фильтра [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемого при вычислении входящих сообщений, а также в качестве таблиц маршрутизации, определяющих целевые конечные точки для отправки сообщений при соответствии критериям фильтра.  
  
## Синтаксис  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
                filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"   
                name="String" />  
      </filters>  
      <routingTables>  
        <table name="String">  
          <entries>  
            <add endpoint="String"   
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
|[\<фильтры\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Содержит набор фильтров маршрутизации, которые определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] MessageFilter, который будет использован при вычислении входящих сообщений.|  
|[\<filterTables\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filtertables.md)|Содержит сопоставление между фильтрами маршрутизации и целевыми конечными точками для определения того, какие конечные точки будут использоваться при совпадении с критериями фильтра.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|system.ServiceModel|Корневой элемент всех элементов конфигурации WCF.|  
  
## См. также  
 [System.ServiceModel.Routing.Configuration.RoutingSection](assetId:///System.ServiceModel.Routing.Configuration.RoutingSection?qualifyHint=False&amp;autoUpgrade=True)