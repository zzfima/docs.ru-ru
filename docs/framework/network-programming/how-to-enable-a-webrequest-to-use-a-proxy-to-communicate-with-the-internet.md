---
title: "Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом | Microsoft Docs"
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
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Практическое руководство. Включение в WebRequest использования прокси-сервера для связи с Интернетом
Этот пример создает глобальный экземпляр прокси, который разрешает любое <xref:System.Net.WebRequest> для использования прокси\-сервера взаимодействия с Интернетом.  Пример предполагает, что прокси\-сервер называется `webproxy` и что он взаимодействует через порт 80 \- стандартный порт HTTP.  
  
## Пример  
  
```csharp  
WebProxy proxyObject = new WebProxy("http://webproxy:80/");  
GlobalProxySelection.Select = proxyObject;  
```  
  
```vb  
Dim proxyObject As WebProxy = New WebProxy("http://webproxy:80/")  
GlobalProxySelection.Select = proxyObject  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространство имен **System.Net**.  
  
## См. также  
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)   
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)