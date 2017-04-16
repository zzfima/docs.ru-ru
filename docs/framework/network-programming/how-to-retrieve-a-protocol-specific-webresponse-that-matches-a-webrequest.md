---
title: "Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d8c90785-f16b-42a5-8439-ed2f731b2ba8
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола
В этом примере показано, как получить протокол\- специфичные WebResponse, соответствующий WebRequest.  
  
## Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
WebResponse resp = req.GetResponse();  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com")  
Dim resp As WebResponse = req.GetResponse()  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространство имен **System.Net**.  
  
## См. также  
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)