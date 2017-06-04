---
title: "Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом | Microsoft Docs"
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
ms.assetid: d9a8eae2-7454-46f9-b43b-c98477c5bcde
caps.latest.revision: 6
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 6
---
# Практическое руководство. Приведение типа объекта WebRequest для доступа к свойствам, связанным с определенным протоколом
В этом примере показано, как получить подходящую роль WebRequest, чтобы можно было свойства протокола доступа конкретных.  
  
## Пример  
  
```csharp  
HttpWebRequest httpreq =   
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
```  
  
```vb  
Dim httpreq As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
```  
  
## См. также  
 [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)