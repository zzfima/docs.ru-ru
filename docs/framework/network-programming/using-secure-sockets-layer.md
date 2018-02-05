---
title: "Использование протокола SSL"
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
- Networking
- SSL
- Secure Sockets Layer
- requesting data from Internet, Secure Sockets Layer
- sending data, Secure Sockets Layer
- Network Resources
- data requests, Secure Sockets Layer
- receiving data, Secure Sockets Layer
- Internet, Secure Sockets Layer
ms.assetid: 6e4289e6-d1b7-4e82-ab0d-e83e3b6063ed
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 31c8a3d22e6a7fa074eae18de8f9b2a9903457c1
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2018
---
# <a name="using-secure-sockets-layer"></a>Использование протокола SSL
Классы <xref:System.Net> используют протокол SSL для шифрования подключений по нескольким сетевым протоколам.  
  
 Для подключений по протоколу HTTP классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> используют протокол SSL для взаимодействия с веб-узлами, поддерживающими SSL. Решение об использовании SSL принимается классом <xref:System.Net.WebRequest> в соответствии с предоставленным универсальным кодом ресурса (URI). Если код URI начинается с префикса "https:", SSL используется. Если код URI начинается с "http:", подключение не шифруется.  
  
 Чтобы использовать SSL с протоколом FTP, присвойте свойству <xref:System.Net.FtpWebRequest.EnableSsl> значение true перед вызовом <xref:System.Net.FtpWebRequest.GetResponse>. Аналогичным образом, чтобы использовать SSL с помощью транспортного протокола SMTP (Simple Mail), задайте <xref:System.Net.Mail.SmtpClient.EnableSsl> равным true перед отправкой сообщения электронной почты.  
  
 Класс <xref:System.Net.Security.SslStream> обеспечивает абстрагирование протокола SSL на основе потоков и позволяет настраивать подтверждение SSL множеством способов.  
  
## <a name="example"></a>Пример  
  
### <a name="code"></a>Код  
  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
-   Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также  
 [Безопасность в сетевом программировании](../../../docs/framework/network-programming/security-in-network-programming.md)  
 [Сетевое программирование в .NET Framework](../../../docs/framework/network-programming/index.md)  
 [Выбор и проверка сертификата](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
