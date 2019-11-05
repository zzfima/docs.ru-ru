---
title: Обработка ошибок
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, WebRequest and WebResponse classes exceptions
- Status property
- WebExceptions class, about WebExceptions class
- Timeout enumeration member
- ConnectFailure enumeration member
- TrustFailure enumeration member
- WebRequest class, exceptions
- requesting data from Internet, error handling
- Success enumeration member
- receiving data, errors
- ProtocolError enumeration member
- downloading Internet resources, error handling
- WebResponse class, exceptions
- SendFailure enumeration member
- errors [.NET Framework], WebRequest and WebResponse classes exceptions
- sending data, errors
- response to Internet request, error handling
- NameResolutionFailure enumeration member
- KeepAliveFailure enumeration member
- network resources, WebRequest and WebResponse classes exceptions
- RequestCanceled enumeration member
- ReceiveFailure enumeration member
- ServerProtocolViolation enumeration member
- ConnectionClosed enumeration member
- SecureChannelFailure enumeration member
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
ms.openlocfilehash: 7084c4579dd5fca0075c7516754195f7cea9e27c
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458037"
---
# <a name="handling-errors"></a>Обработка ошибок

Классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вызывают одновременно системные исключения (например, <xref:System.ArgumentException>) и веб-исключения (исключения <xref:System.Net.WebException>, вызываемые методом <xref:System.Net.WebRequest.GetResponse%2A>).  
  
Каждый класс **WebException** включает свойство <xref:System.Net.WebException.Status%2A>, которое содержит значение перечисления <xref:System.Net.WebExceptionStatus>. Значение свойства **Status** позволяет определить произошедшую ошибку и действия, которые следует предпринять для ее устранения.  
  
В следующей таблице описаны возможные значения свойства **Status**.  
  
|Status|ОПИСАНИЕ|  
|------------|-----------------|  
|ConnectFailure|Не удалось связаться с удаленной службой на транспортном уровне.|  
|ConnectionClosed|Соединение было преждевременно закрыто.|  
|KeepAliveFailure|Сервер закрыл подключение, установленное с заданным заголовком проверки активности.|  
|NameResolutionFailure|Службе имен не удалось разрешить имя узла.|  
|ProtocolError|От сервера получен полный ответ, указывающий на ошибку на уровне протокола.|  
|ReceiveFailure|От удаленного сервера не получен полный ответ.|  
|RequestCanceled|Запрос отменен.|  
|SecureChannelFailure|Произошла ошибка в защищенном канале связи.|  
|SendFailure|Не удалось отправить полный запрос на удаленный сервер.|  
|ServerProtocolViolation|Ответ от сервера не является допустимым ответом HTTP.|  
|Success|Ошибки не обнаружены.|  
|Время ожидания|В течение заданного для запроса времени ожидания не был получен ответ.|  
|TrustFailure|Не удалось проверить сертификат сервера.|  
|MessageLengthLimitExceeded|Получено сообщение, которое превышает ограничение, заданное при отправке запроса или получении ответа от сервера.|  
|Не завершен|Ожидается выполнение внутреннего асинхронного запроса.|  
|PipelineFailure|Это значение поддерживает платформу .NET Framework и не должно использоваться непосредственно из вашего кода.|  
|ProxyNameResolutionFailure|Службе разрешения имен не удалось разрешить имя узла прокси-сервера.|  
|UnknownError|Возникло исключение неизвестного типа.|  
  
Если свойство **Status** имеет значение **WebExceptionStatus.ProtocolError**, доступен **WebResponse**, содержащий ответ сервера. Содержимое этого ответа позволяет определить фактический источник ошибки протокола.  
  
В следующем примере демонстрируется перехват исключения **WebException**.  
  
```csharp  
try   
{  
    // Create a request instance.  
    WebRequest myRequest =   
    WebRequest.Create("http://www.contoso.com");  
    // Get the response.  
    WebResponse myResponse = myRequest.GetResponse();  
    //Get a readable stream from the server.   
    Stream sr = myResponse.GetResponseStream();  
  
    //Read from the stream and write any data to the console.  
    bytesread = sr.Read( myBuffer, 0, length);  
    while( bytesread > 0 )   
    {  
        for (int i=0; i<bytesread; i++) {  
            Console.Write( "{0}", myBuffer[i]);  
        }  
        Console.WriteLine();  
        bytesread = sr.Read( myBuffer, 0, length);  
    }  
    sr.Close();  
    myResponse.Close();  
}  
catch (WebException webExcp)   
{  
    // If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.");  
    // Write out the WebException message.  
    Console.WriteLine(webExcp.ToString());  
    // Get the WebException status code.  
    WebExceptionStatus status =  webExcp.Status;  
    // If status is WebExceptionStatus.ProtocolError,   
    //   there has been a protocol error and a WebResponse   
    //   should exist. Display the protocol error.  
    if (status == WebExceptionStatus.ProtocolError) {  
        Console.Write("The server returned protocol error ");  
        // Get HttpWebResponse so that you can check the HTTP status code.  
        HttpWebResponse httpResponse = (HttpWebResponse)webExcp.Response;  
        Console.WriteLine((int)httpResponse.StatusCode + " - "  
           + httpResponse.StatusCode);  
    }  
}  
catch (Exception e)   
{  
    // Code to catch other exceptions goes here.  
}  
```  
  
```vb  
Try  
    ' Create a request instance.  
    Dim myRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ' Get the response.  
    Dim myResponse As WebResponse = myRequest.GetResponse()  
    'Get a readable stream from the server.   
    Dim sr As Stream = myResponse.GetResponseStream()  
  
    Dim i As Integer      
    'Read from the stream and write any data to the console.  
    bytesread = sr.Read(myBuffer, 0, length)  
    While bytesread > 0  
        For i = 0 To bytesread - 1  
            Console.Write("{0}", myBuffer(i))  
        Next i  
        Console.WriteLine()  
        bytesread = sr.Read(myBuffer, 0, length)  
    End While  
    sr.Close()  
    myResponse.Close()  
Catch webExcp As WebException  
    ' If you reach this point, an exception has been caught.  
    Console.WriteLine("A WebException has been caught.")  
    ' Write out the WebException message.  
    Console.WriteLine(webExcp.ToString())  
    ' Get the WebException status code.  
    Dim status As WebExceptionStatus = webExcp.Status  
    ' If status is WebExceptionStatus.ProtocolError,   
    '   there has been a protocol error and a WebResponse   
    '   should exist. Display the protocol error.  
    If status = WebExceptionStatus.ProtocolError Then  
        Console.Write("The server returned protocol error ")  
        ' Get HttpWebResponse so that you can check the HTTP status code.  
        Dim httpResponse As HttpWebResponse = _  
           CType(webExcp.Response, HttpWebResponse)  
        Console.WriteLine(CInt(httpResponse.StatusCode).ToString() & _  
           " - " & httpResponse.StatusCode.ToString())  
    End If  
Catch e As Exception  
    ' Code to catch other exceptions goes here.  
End Try  
```  
  
Приложения, использующие класс <xref:System.Net.Sockets.Socket>, вызывают исключение <xref:System.Net.Sockets.SocketException> при возникновении ошибки в сокете Windows. Классы <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и <xref:System.Net.Sockets.UdpClient> построены на основе класса **Socket** и также вызывают исключения **SocketException**.  
  
Если возникает исключение **SocketException**, класс **SocketException** присваивает свойству <xref:System.Net.Sockets.SocketException.ErrorCode%2A> значение, отражающее последнюю ошибку сокета операционной системы. Дополнительные сведения о кодах ошибок сокета см. в документации по кодам ошибок API Winsock 2.0 на веб-сайте MSDN.  
  
## <a name="see-also"></a>См. также

- [Обработка и создание исключений в .NET](../../standard/exceptions/index.md)
- [Запрос данных](requesting-data.md)
