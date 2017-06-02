---
title: "AspNetCompatibilityRequirementsAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# AspNetCompatibilityRequirementsAttribute
AspNetCompatibilityRequirementsAttribute  
  
## Синтаксис  
  
```  
class AspNetCompatibilityRequirementsAttribute : Behavior  
{  
  string RequirementsMode;  
};  
```  
  
## Методы  
 Класс AspNetCompatibilityRequirementsAttribute не определяет никаких методов.  
  
## Свойства  
 Класс AspNetCompatibilityRequirementsAttribute имеет следующее свойство.  
  
### RequirementsMode  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Указывает, активен ли режим совместимости Asp.Net.  
  
## Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------------|  
|Пространство имен|Определено в root\\ServiceModel.|  
  
## См. также  
 <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>