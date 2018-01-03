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
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 7ca66a65c05da3d515358c0fdb26682fa4ec1438
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="basic-and-digest-authentication"></a><span data-ttu-id="486a4-102">Обычная и дайджест-аутентификация</span><span class="sxs-lookup"><span data-stu-id="486a4-102">Basic and Digest Authentication</span></span>
<span data-ttu-id="486a4-103">Реализация основной и дайджест-проверки подлинности в <xref:System.Net> соответствует требованиям RFC2617 "Проверка подлинности HTTP. Основная и дайджест-проверка подлинности" (размещен на веб-сайте консорциума World Wide Web по адресу www.w3.org).</span><span class="sxs-lookup"><span data-stu-id="486a4-103">The <xref:System.Net> implementation of basic and digest authentication complies with RFC2617 – HTTP Authentication: Basic and Digest Authentication (available on the World Wide Web Consortium's Web site at www.w3.org).</span></span>  
  
 <span data-ttu-id="486a4-104">Чтобы использовать обычную и дайджест-проверку подлинности, приложение должно предоставлять имя пользователя и пароль в свойстве <xref:System.Net.WebRequest.Credentials%2A> объекта <xref:System.Net.WebRequest>, которое используется для запроса данных из Интернета, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="486a4-104">To use basic and digest authentication, an application must provide a user name and password in the <xref:System.Net.WebRequest.Credentials%2A> property of the <xref:System.Net.WebRequest> object that it uses to request data from the Internet, as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="486a4-105">Данные, отправляемые с помощью базовой и дайджест-аутентификации, не шифруются, поэтому злоумышленник может их видеть.</span><span class="sxs-lookup"><span data-stu-id="486a4-105">Data sent with Basic and Digest Authentication is not encrypted, so the data can be seen by an adversary.</span></span> <span data-ttu-id="486a4-106">Кроме того, базовые учетные данные аутентификации (имя пользователя и пароль) передаются в открытом виде и могут быть перехвачены.</span><span class="sxs-lookup"><span data-stu-id="486a4-106">Additionally, Basic Authentication credentials (user name and password) are sent in the clear and can be intercepted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="486a4-107">См. также</span><span class="sxs-lookup"><span data-stu-id="486a4-107">See Also</span></span>  
 [<span data-ttu-id="486a4-108">Проверка подлинности NTLM и Kerberos</span><span class="sxs-lookup"><span data-stu-id="486a4-108">NTLM and Kerberos Authentication</span></span>](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)  
 [<span data-ttu-id="486a4-109">Проверка подлинности в Интернете</span><span class="sxs-lookup"><span data-stu-id="486a4-109">Internet Authentication</span></span>](../../../docs/framework/network-programming/internet-authentication.md)
