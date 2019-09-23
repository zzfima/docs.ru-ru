---
title: Практическое руководство. Доступ к свойствам, относящимся с HTTP
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8848c7e-f5c5-4d42-b86d-9951ff8f4146
ms.openlocfilehash: f902fb3ee97e94c85192836be047dfe632249735
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048492"
---
# <a name="how-to-access-http-specific-properties"></a>Практическое руководство. Доступ к свойствам, относящимся с HTTP
В этом примере показано, как отключить функции HTTP **Keep-alive** и получить номер версии протокола с веб-сервера.  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Для этого примера требуются:  
  
- Ссылки на пространство имен **System.Net**.  
  
## <a name="see-also"></a>См. также

- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
- [Использование протоколов приложений](using-application-protocols.md)
- [HTTP](http.md)
