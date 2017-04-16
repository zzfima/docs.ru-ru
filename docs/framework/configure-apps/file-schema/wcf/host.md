---
title: "&lt;хост&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: be566d55-9d50-4b2e-985d-52a5cc26cbbb
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# &lt;хост&gt;
Задает параметры узла службы.  
  
## Синтаксис  
  
```  
  
<host>  
      <baseAddresses>  
         <baseAddress baseAddress="string" />  
      </baseAddresses>  
      <timeOuts closeTimeout="TimeSpan"  
         openTimeout="TimeSpan" >  
</host>  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<baseAddresses\>](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Коллекция элементов`baseAddress`, которая задает базовые адреса, используемые узлом службы.|  
|[\<timeOuts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/timeouts.md)|Элемент конфигурации, задающий допустимый интервал времени для открытия или закрытия узла службы.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<service\>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|Задает параметры службы [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.HostElement>   
 <xref:System.ServiceModel.ServiceHost>   
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)