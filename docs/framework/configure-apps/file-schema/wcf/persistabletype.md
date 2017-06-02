---
title: "&lt;persistableType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;persistableType&gt;
Задает все восстанавливаемые типы.  
  
## Синтаксис  
  
```  
  
<comContracts>  
  <comContract>  
      <persistableTypes>  
         <persistableType id="string"  
            name="string">  
         </persistableType>  
      </persistableTypes>  
  </comContract>  
</comContracts>  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|id|Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.|  
|имя|Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<persistableTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|Коллекция элементов `persistableType`.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>   
 <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>   
 [\<comContracts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)   
 [Интеграция с приложениями COM\+](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)   
 [Практическое руководство. Настройка параметров службы COM\+](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)