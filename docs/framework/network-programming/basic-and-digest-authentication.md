---
title: "Обычная и дайджест-аутентификация"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
caps.latest.revision: 11
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 369a473b2e9172abe10d263bb066b253500f9502
ms.contentlocale: ru-ru
ms.lasthandoff: 08/21/2017

---
# <a name="basic-and-digest-authentication"></a>Обычная и дайджест-аутентификация
Реализация основной и дайджест-проверки подлинности в <xref:System.Net> соответствует требованиям RFC2617 "Проверка подлинности HTTP. Основная и дайджест-проверка подлинности" (размещен на веб-сайте консорциума World Wide Web по адресу www.w3.org).  
  
 Чтобы использовать обычную и дайджест-проверку подлинности, приложение должно предоставлять имя пользователя и пароль в свойстве <xref:System.Net.WebRequest.Credentials%2A> объекта <xref:System.Net.WebRequest>, которое используется для запроса данных из Интернета, как показано в следующем примере.  
  
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
>  Данные, отправляемые с помощью базовой и дайджест-аутентификации, не шифруются, поэтому злоумышленник может их видеть. Кроме того, базовые учетные данные аутентификации (имя пользователя и пароль) передаются в открытом виде и могут быть перехвачены.  
  
## <a name="see-also"></a>См. также  
 [Проверка подлинности NTLM и Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)   
 [Проверка подлинности в Интернете](../../../docs/framework/network-programming/internet-authentication.md)

