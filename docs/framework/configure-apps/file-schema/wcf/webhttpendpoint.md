---
title: "&lt;webHttpEndpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecaaeb6f-ebd0-411d-8b53-92477cd45347
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;webHttpEndpoint&gt;
Этот элемент конфигурации определяет стандартную конечную точку с фиксированной привязкой [\<webHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)[\<webHttp\>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttp.md).  Используйте эту конечную точку при написании службы REST.  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <webHttpEndpoint>   
          <standardEndpoint  
             automaticFormatSelectionEnabled="String"   
             defaultOutgoingResponseFormat=”Xml/Json”  
             helpEnabled=”Boolean”  
             webEndpointType=”String”/>        
       </webHttpEndpoint>   
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|automaticFormatSelectionEnabled|Логическое значение, указывающее, включен ли автоматический выбор формата.<br /><br /> Если автоматический выбор формата включен, инфраструктура выполняет синтаксический анализ заголовка `Accept` сообщения запроса и определяет наиболее подходящий формат ответа.  Если в заголовке `Accept` не указан подходящий формат ответа, инфраструктура использует тип `Content-Type` сообщения запроса или формат ответа, заданный для этой операции по умолчанию.|  
|defaultOutgoingResponseFormat|Атрибут, определяющий формат исходящего ответа по умолчанию.  Это атрибут типа <xref:System.Servicemodel.Web.Webmessageformat>.|  
|helpEnabled|Логическое значение, указывающее, включена ли страница справки HTTP для конечной точки.|  
|webEndpointType|Строка, указывающая тип конечной точки.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Коллекция стандартных конечных точек, одно или несколько свойств которых \(адрес, привязка, контракт\) являются фиксированными.|  
  
## См. также  
 <xref:System.ServiceModel.Description.WebHttpEndpoint>   
 <xref:System.ServiceModel.Configuration.WebHttpEndpointElement>