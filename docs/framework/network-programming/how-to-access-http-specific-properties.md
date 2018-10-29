---
title: Практическое руководство. Доступ к свойствам, относящимся с HTTP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: c883321d74bb4309f483604d51057390d00189e6
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50043020"
---
# <a name="how-to-access-http-specific-properties"></a><span data-ttu-id="b10eb-102">Практическое руководство. Доступ к свойствам, относящимся с HTTP</span><span class="sxs-lookup"><span data-stu-id="b10eb-102">How to: Access HTTP-Specific Properties</span></span>
<span data-ttu-id="b10eb-103">В этом примере показано, как отключить функции HTTP **Keep-alive** и получить номер версии протокола с веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="b10eb-103">This sample shows how to turn off the HTTP **Keep-alive** behavior and get the protocol version number from the Web server.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b10eb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="b10eb-104">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="b10eb-105">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b10eb-105">Compiling the Code</span></span>  
 <span data-ttu-id="b10eb-106">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b10eb-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b10eb-107">Ссылки на пространство имен **System.Net**.</span><span class="sxs-lookup"><span data-stu-id="b10eb-107">References to the **System.Net** namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b10eb-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b10eb-108">See Also</span></span>  
 [<span data-ttu-id="b10eb-109">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="b10eb-109">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="b10eb-110">Использование протоколов приложений</span><span class="sxs-lookup"><span data-stu-id="b10eb-110">Using Application Protocols</span></span>](../../../docs/framework/network-programming/using-application-protocols.md)  
 [<span data-ttu-id="b10eb-111">HTTP</span><span class="sxs-lookup"><span data-stu-id="b10eb-111">HTTP</span></span>](../../../docs/framework/network-programming/http.md)
