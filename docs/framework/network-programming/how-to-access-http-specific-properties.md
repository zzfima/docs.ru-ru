---
title: "Практическое руководство. Доступ к свойствам, относящимся с HTTP | Microsoft Docs"
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
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Практическое руководство. Доступ к свойствам, относящимся с HTTP
В этом образце показано, как отключить расширения функциональности **Keep\-alive** HTTP и получить номер версии протокола с веб\-сервера.  
  
## Пример  
  
```vb  
Dim HttpWReq As HttpWebRequest= _  
    CType(WebRequest.Create("http://www.contoso.com"), HttpWebRequest)  
' Turn off connection keep-alives.  
HttpWReq.KeepAlive = False  
  
Dim HttpWResp As HttpWebResponse = _  
    CType(HttpWReq.GetResponse(), HttpWebResponse)  
  
' Get the HTTP protocol version number returned by the server.  
Dim ver As String = HttpWResp.ProtocolVersion.ToString()  
HttpWResp.Close()  
```  
  
```csharp  
HttpWebRequest HttpWReq =   
    (HttpWebRequest)WebRequest.Create("http://www.contoso.com");  
// Turn off connection keep-alives.  
HttpWReq.KeepAlive = false;  
  
HttpWebResponse HttpWResp = (HttpWebResponse)HttpWReq.GetResponse();  
  
// Get the HTTP protocol version number returned by the server.  
String ver = HttpWResp.ProtocolVersion.ToString();  
HttpWResp.Close();  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространство имен **System.Net**.  
  
## См. также  
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Использование протоколов приложений](../../../docs/framework/network-programming/using-application-protocols.md)   
 [HTTP](../../../docs/framework/network-programming/http.md)