---
title: "&lt;фильтр&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3266700b-904b-44e4-93a7-e06a1a445100
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;фильтр&gt;
Задает фильтр маршрутизации, который определяет тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при оценке входящих сообщений, а также все требуемые фильтру сопутствующие данные или параметры.  
  
## Синтаксис  
  
```vb  
  
<routing>  
      <filters>  
        <filter customType=”String”  
                filterData=”String”  
                filterType="Action/Address/AddressPrefix/And/Custom/Endpoint/MatchAll/XPath"   
                name="String" />  
      </filters>  
</routing>  
  
```  
  
```csharp  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|customType|Строка, содержащая полное имя пользовательского типа, используемого в качестве фильтра. Если `filterType` присвоено значение `custom`, то этот атрибут будет содержать полное имя типа создаваемого класса.  `filterData` также может содержать значения, используемые при оценке фильтра с пользовательским типом.|  
|filterData|Строка, содержащая данные фильтра.  Дополнительные сведения об указании этого атрибута см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|filterType|Строка, содержащая тип фильтра.  Этот атрибут имеет тип <xref:System.ServiceModel.Routing.Configuration.FilterType>.  Дополнительные сведения о том, как это работает с атрибутом `filterData`, см. в разделе <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>.|  
|имя|Строка, содержащая уникальное имя этого элемента фильтра.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<маршрутизация\>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Раздел конфигурации, в котором определяется набор фильтров маршрутизации, которые определяют тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] <xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при вычислении входящих сообщений.|  
  
## См. также  
 [System.ServiceModel.Routing.Configuration.FilterElement](assetId:///System.ServiceModel.Routing.Configuration.FilterElement?qualifyHint=False&amp;autoUpgrade=True)   
 <xref:System.ServiceModel.Routing.Configuration.FilterElement.FilterData%2A>   
 <xref:System.ServiceModel.Routing.Configuration.FilterType>