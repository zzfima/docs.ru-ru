---
title: "&lt;callbackDebug&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;callbackDebug&gt;
Задает отладку службы для объекта обратного вызова [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Синтаксис  
  
```  
  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`includeExceptionDetailInFaults`|Значение, которое указывает, возвращают ли объекты обратного вызова клиента сведения об управляемом исключении в ошибках SOAP назад в службу.<br /><br /> Если программным способом задать этому атрибуту значение `true`, в объекте обратного вызова клиента можно включить поток сведений об управляемом исключении назад в службу для отладки. **Caution:**  Возвращение клиентам сведений об управляемых исключениях может представлять риск с точки зрения безопасности.  Это связано с тем, что подробные данные об исключении содержат сведения о внутренней реализации службы, которые могут использоваться неавторизованными клиентами.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>   
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>