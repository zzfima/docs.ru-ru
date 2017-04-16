---
title: "Практическое руководство. Переопределение глобальных прокси-серверов | Microsoft Docs"
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
ms.assetid: 0da481a9-b414-4230-beb0-e3ceba882fe5
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Практическое руководство. Переопределение глобальных прокси-серверов
Этот пример отправляет **WebRequest** www.contoso.com, который переопределяет глобальный выделение прокси с `alternateproxy` с именем учетной записи\-посредника на порту 80.  
  
## Пример  
  
```csharp  
WebRequest req = WebRequest.Create("http://www.contoso.com/");  
req.Proxy = new WebProxy("http://alternateproxy:80/");  
```  
  
```vb  
Dim req As WebRequest = WebRequest.Create("http://www.contoso.com/")  
req.Proxy = New WebProxy("http://alternateproxy:80/")  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространство имен **System.Net**.  
  
## См. также  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)