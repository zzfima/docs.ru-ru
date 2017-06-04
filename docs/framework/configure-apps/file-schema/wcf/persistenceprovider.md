---
title: "&lt;persistenceProvider&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;persistenceProvider&gt;
Задает тип используемой реализации поставщика сохраняемости, а также время ожидания операций сохраняемости.  
  
## Синтаксис  
  
```  
  
<persistenceProvider persistenceOperationTimeout="TimeSpan"  
   type="String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|persistenceOperationTimeout|Значение <xref:System.TimeSpan>, которое задает время ожидания, используемое для операций сохраняемости.  Значение по умолчанию \- 00:00:30.|  
|тип|Строка, указывающая тип используемой фабрики поставщика сохраняемости.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## Заметки  
 Этот элемент задает поставщика сохраняемости, используемого для сериализации состояния службы WCF.  Он должен использоваться вместе с атрибутом `wsHttpContextBinding`, который передает сведения о состоянии в HTTP\-заголовки.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PersistenceProviderElement>   
 <xref:System.ServiceModel.Persistence.PersistenceProvider>