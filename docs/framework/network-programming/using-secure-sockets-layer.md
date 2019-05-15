---
title: Использование протокола SSL
ms.date: 03/30/2017
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
ms.openlocfilehash: 9cfa8d6a71898a1d1ea91825ffc9a37f4654ebd5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64583520"
---
# <a name="using-secure-sockets-layer"></a><span data-ttu-id="2c525-102">Использование протокола SSL</span><span class="sxs-lookup"><span data-stu-id="2c525-102">Using Secure Sockets Layer</span></span>
<span data-ttu-id="2c525-103">Классы <xref:System.Net> используют протокол SSL для шифрования подключений по нескольким сетевым протоколам.</span><span class="sxs-lookup"><span data-stu-id="2c525-103">The <xref:System.Net> classes use the Secure Sockets Layer (SSL) to encrypt the connection for several network protocols.</span></span>  
  
 <span data-ttu-id="2c525-104">Для подключений по протоколу HTTP классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> используют протокол SSL для взаимодействия с веб-узлами, поддерживающими SSL.</span><span class="sxs-lookup"><span data-stu-id="2c525-104">For http connections, the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes use SSL to communicate with web hosts that support SSL.</span></span> <span data-ttu-id="2c525-105">Решение об использовании SSL принимается классом <xref:System.Net.WebRequest> в соответствии с предоставленным универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="2c525-105">The decision to use SSL is made by the <xref:System.Net.WebRequest> class, based on the URI it is given.</span></span> <span data-ttu-id="2c525-106">Если код URI начинается с префикса "https:", SSL используется. Если код URI начинается с "http:", подключение не шифруется.</span><span class="sxs-lookup"><span data-stu-id="2c525-106">If the URI begins with "https:", SSL is used; if the URI begins with "http:", an unencrypted connection is used.</span></span>  
  
 <span data-ttu-id="2c525-107">Чтобы использовать SSL с протоколом FTP, присвойте свойству <xref:System.Net.FtpWebRequest.EnableSsl> значение true перед вызовом <xref:System.Net.FtpWebRequest.GetResponse>.</span><span class="sxs-lookup"><span data-stu-id="2c525-107">To use SSL with File Transfer Protocol (FTP), set the <xref:System.Net.FtpWebRequest.EnableSsl> property to true prior to calling <xref:System.Net.FtpWebRequest.GetResponse>.</span></span> <span data-ttu-id="2c525-108">Аналогичным образом, чтобы использовать SSL с протоколом SMTP, присвойте свойству <xref:System.Net.Mail.SmtpClient.EnableSsl> значение true перед отправкой электронного сообщения.</span><span class="sxs-lookup"><span data-stu-id="2c525-108">Similarly, to use SSL with Simple Mail Transport Protocol (SMTP), set the <xref:System.Net.Mail.SmtpClient.EnableSsl> property to true prior to sending the email.</span></span>  
  
 <span data-ttu-id="2c525-109">Класс <xref:System.Net.Security.SslStream> обеспечивает абстрагирование протокола SSL на основе потоков и позволяет настраивать подтверждение SSL множеством способов.</span><span class="sxs-lookup"><span data-stu-id="2c525-109">The <xref:System.Net.Security.SslStream> class provides a stream-based abstraction for SSL, and offers many ways to configure the SSL handshake.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c525-110">Пример</span><span class="sxs-lookup"><span data-stu-id="2c525-110">Example</span></span>  
  
### <a name="code"></a><span data-ttu-id="2c525-111">Код</span><span class="sxs-lookup"><span data-stu-id="2c525-111">Code</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="2c525-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="2c525-112">Compiling the Code</span></span>  
 <span data-ttu-id="2c525-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="2c525-113">This example requires:</span></span>  
  
- <span data-ttu-id="2c525-114">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="2c525-114">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c525-115">См. также</span><span class="sxs-lookup"><span data-stu-id="2c525-115">See also</span></span>

- [<span data-ttu-id="2c525-116">Безопасность в сетевом программировании</span><span class="sxs-lookup"><span data-stu-id="2c525-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)
- [<span data-ttu-id="2c525-117">Сетевое программирование в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2c525-117">Network Programming in the .NET Framework</span></span>](../../../docs/framework/network-programming/index.md)
- [<span data-ttu-id="2c525-118">Выбор и проверка сертификата</span><span class="sxs-lookup"><span data-stu-id="2c525-118">Certificate Selection and Validation</span></span>](../../../docs/framework/network-programming/certificate-selection-and-validation.md)
