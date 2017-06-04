---
title: "Использование протокола SSL | Microsoft Docs"
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
helpviewer_keywords: 
  - "Сетевое взаимодействие"
  - "SSL"
  - "протокол SSL"
  - "запрос данных из Интернета, протокол SSL"
  - "отправка данных, протокол SSL"
  - "Сетевые ресурсы"
  - "запросы данных, протокол SSL"
  - "получение данных, протокол SSL"
  - "Интернет, протокол SSL"
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 14
---
# Использование протокола SSL
Классы <xref:System.Net> используют протокол SSL для шифрования соединения для нескольких сетевых протоколов.  
  
 Для HTTP\-соединений, классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> используют протокол SSL для обмена данными с узлами в интернете, которые поддерживают протокол SSL.  Решение использовать протокол SSL является классом <xref:System.Net.WebRequest>, на основе uri оно задано.  Если универсальный код ресурса \(uri\) начинается с "HTTPs: " SSL используется; если универсальный код ресурса \(uri\) начинается с "http: незашифрованный", используется соединение.  
  
 Для использования SSL с использованием протокола FTP, задайте свойство <xref:System.Net.FtpWebRequest.EnableSsl> true перед вызовом <xref:System.Net.FtpWebRequest.GetResponse>.  Аналогично, значение SSL использования с простым транспортным протоколом Почты \(SMTP\), установите свойство <xref:System.Net.Mail.SmtpClient.EnableSsl> true до отправки электронной почты.  
  
 Класс <xref:System.Net.Security.SslStream> предоставляет поток\- based абстракцию для SSL и предлагает множество способов настройки подтверждения SSL.  
  
## Пример  
  
### Код  
  
```vb  
Dim MyURI As String = "https://www.contoso.com/"  
Dim Wreq As WebRequest = WebRequest.Create(MyURI)  
  
Dim serverUri As String = "ftp://ftp.contoso.com/file.txt"  
Dim request As FtpWebRequest = CType(WebRequest.Create(serverUri), FtpWebRequest)  
request.Method = WebRequestMethods.Ftp.DeleteFile  
request.EnableSsl = True  
Dim response As FtpWebResponse = CType(request.GetResponse(), FtpWebResponse)  
```  
  
```csharp  
String MyURI = "https://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
  
String serverUri = "ftp://ftp.contoso.com/file.txt"  
FtpWebRequest request = (FtpWebRequest)WebRequest.Create(serverUri);  
request.EnableSsl = true;  
request.Method = WebRequestMethods.Ftp.DeleteFile;  
FtpWebResponse response = (FtpWebResponse)request.GetResponse();  
```  
  
## Компиляция кода  
 Для этого примера необходимо следующее.  
  
-   Ссылки на пространство имен **System.Net**.  
  
## См. также  
 [Безопасность в сетевом программировании](../../../docs/framework/network-programming/security-in-network-programming.md)   
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)   
 [Выбор и проверка сертификата](../../../docs/framework/network-programming/certificate-selection-and-validation.md)