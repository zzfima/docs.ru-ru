---
title: "Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest | Microsoft Docs"
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
ms.assetid: 98ddbdb9-66b1-4080-92ad-51f5c447fcf8
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Практическое руководство. Регистрация пользовательского протокола с помощью WebRequest
В этом примере показано, как зарегистрировать протокол определенное classthat  указано в другом месте.  В этом примере `CustomWebRequestCreator` пользователь\-, реализованный объектом, средства **Создать** метод, который возвращает объект `CustomWebRequest`.  В примере кода предполагается, что написан код `CustomWebRequest`, реализующего пользовательский протокол.  
  
## Пример  
  
```csharp  
WebRequest.RegisterPrefix("custom", new CustomWebRequestCreator());  
WebRequest req = WebRequest.Create("custom://customHost.contoso.com/");  
```  
  
```vb  
WebRequest.RegisterPrefix("custom", New CustomWebRequestCreator())  
Dim req As WebRequest = WebRequest.Create("custom://customHost.contoso.com/")  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
 Ссылки на пространство имен <xref:System.Net>.  
  
## См. также  
 [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md)