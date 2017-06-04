---
title: "Обычная и дайджест-аутентификация | Microsoft Docs"
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
  - "аутентификация [платформа .NET Framework], классы"
  - "Обычная аутентификация"
  - "аутентификация [платформа .NET Framework], обычная"
  - "аутентификация клиента, обычная"
  - "аутентификация пользователя, обычная"
  - "аутентификация [платформа .NET Framework], дайджест"
  - "получение данных, аутентификация"
  - "аутентификация клиента, дайджест"
  - "Интернет, аутентификация"
  - "дайджест-аутентификация"
  - "отправка данных, аутентификация"
  - "сетевые ресурсы, аутентификация"
  - "аутентификация пользователя, дайджест"
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# Обычная и дайджест-аутентификация
Реализация основных <xref:System.Net> проверки подлинности и дайджест\-проверки подлинности соответствует RFC2617 – проверкой подлинности HTTP: Основной и дайджест\-проверка подлинности \(доступен на веб\-сайте консорциума W3C по адресу www.w3.org.  
  
 Для использования проверки подлинности основных и дайджеста, приложение должно указать имя пользователя и пароль в свойстве <xref:System.Net.WebRequest.Credentials%2A> объекта <xref:System.Net.WebRequest>, который используется для запроса данных из Интернета, как показано в следующем примере.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  Данные, отправляемые с основным и дайджест\-проверкой подлинности не шифроватьы, поэтому данные могут быть видны злоумышленником.  Кроме того, учетные данные обычной проверки подлинности \(имя пользователя и пароль\) снимите отправлены откройте и могут быть перехватываются.  
  
## См. также  
 [проверка подлинности NTLM и Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Аутентификация в Интернете](../../../docs/framework/network-programming/internet-authentication.md)