---
title: "проверка подлинности NTLM и Kerberos | Microsoft Docs"
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
  - "проверка подлинности [платформа .NET Framework], NTLM"
  - "проверка подлинности [платформа .NET Framework], Kerberos"
  - "проверка подлинности пользователя, Kerberos"
  - "проверка подлинности пользователя, NTLM"
  - "проверка подлинности Kerberos"
  - "получение данных, проверка подлинности"
  - "проверка подлинности NTLM"
  - "Интернет, проверка подлинности"
  - "проверка подлинности клиента, Kerberos"
  - "отправка данных, проверка подлинности"
  - "сетевые ресурсы, проверка подлинности"
  - "классы [платформа .NET Framework], проверка подлинности"
  - "проверка подлинности клиента, NTLM"
ms.assetid: 9ef65560-f596-4469-bcce-f4d5407b55cd
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# проверка подлинности NTLM и Kerberos
По умолчанию проверка подлинности NTLM и проверка подлинности Kerberos использует учетные данные пользователя Microsoft Windows NT, связанные с вызывающим приложением выполнить проверку подлинности на сервере.  При использовании проверки подлинности NTLM не значения по умолчанию, приложение задает тип проверки подлинности NTLM и использует объект <xref:System.Net.NetworkCredential>, чтобы передать имя пользователя, пароль и домен к узлу, как показано в следующем примере.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = _  
    New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials =   
    new NetworkCredential(UserName, SecurelyStoredPassword, Domain);  
```  
  
 Приложения, которым требуется подключение к службам интернета, используя учетные данные пользователя приложения могут сделать с учетными данными пользователя по умолчанию, как показано в следующем примере.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = CredentialCache.DefaultCredentials  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create (MyURI);  
WReq.Credentials = CredentialCache.DefaultCredentials;  
```  
  
 Модуль проверки подлинности negotiate указывает, использует ли удаленный сервер проверку подлинности NTLM или Kerberos и отправляет соответствующий ответ.  
  
> [!NOTE]
>  Проверка подлинности NTLM не работает через прокси\-сервер.  
  
## См. также  
 [Обычная и дайджест\-аутентификация](../../../docs/framework/network-programming/basic-and-digest-authentication.md)   
 [Аутентификация в Интернете](../../../docs/framework/network-programming/internet-authentication.md)