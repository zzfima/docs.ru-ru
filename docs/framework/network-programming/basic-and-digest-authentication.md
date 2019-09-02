---
title: Обычная и дайджест-аутентификация
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
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
ms.openlocfilehash: 029243f9f8b02275c0f0a6ec1a74a9a2ca198d9c
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70044111"
---
# <a name="basic-and-digest-authentication"></a>Обычная и дайджест-аутентификация
Реализация базовой аутентификации и аутентификации с использованием дайджеста в <xref:System.Net> соответствует требованиям документа RFC2617 – HTTP Authentication: Basic and Digest Authentication (RFC2617 — аутентификация HTTP: базовая аутентификация и аутентификация с использованием дайджеста), который доступен на веб-сайте [консорциума World Wide Web](https://www.w3.org).  
  
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
> Данные, отправляемые с помощью базовой и дайджест-проверки подлинности, не шифруются, поэтому злоумышленник может их видеть. Кроме того, базовые учетные данные аутентификации (имя пользователя и пароль) передаются в открытом виде и могут быть перехвачены.  
  
## <a name="see-also"></a>См. также

- [Проверка подлинности NTLM и Kerberos](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)
- [Проверка подлинности в Интернете](../../../docs/framework/network-programming/internet-authentication.md)
