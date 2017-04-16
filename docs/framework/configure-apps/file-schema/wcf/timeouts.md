---
title: "&lt;timeOuts&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;timeOuts&gt;
Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.  
  
## Синтаксис  
  
```  
  
<timeOuts closeTimeout="TimeSpan"  
   openTimeout="TimeSpan" >  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<хост\>](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Элемент конфигурации, который задает параметры узла службы.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 <xref:System.ServiceModel.ServiceHost.CloseTimeout%2A>   
 <xref:System.ServiceModel.ServiceHost.OpenTimeout%2A>   
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)