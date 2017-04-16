---
title: "Обработка ошибок | Microsoft Docs"
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
  - "Интернет, классы исключений WebRequest и WebResponse"
  - "Свойство Status"
  - "класс WebExceptions, о классе WebExceptions"
  - "элемент перечисления Timeout"
  - "элемент перечисления ConnectFailure"
  - "элемент перечисления TrustFailure"
  - "класс WebRequest, исключения"
  - "запрос данных из Интернета, обработка ошибок"
  - "элемент перечисления Success"
  - "получение данных, ошибки"
  - "элемент перечисления ProtocolError"
  - "загрузка интернет-ресурсов, обработка ошибок"
  - "класс WebResponse, исключения"
  - "элемент перечисления SendFailure"
  - "ошибки [платформа .NET Framework], классы исключений WebRequest и WebResponse"
  - "отправка данных, ошибки"
  - "ответ на интернет-запрос, обработка ошибок"
  - "элемент перечисления NameResolutionFailure"
  - "элемент перечисления KeepAliveFailure"
  - "сетевые ресурсы, классы исключений WebRequest и WebResponse"
  - "элемент перечисления RequestCanceled"
  - "элемент перечисления ReceiveFailure"
  - "элемент перечисления ServerProtocolViolation"
  - "элемент перечисления ConnectionClosed"
  - "элемент перечисления SecureChannelFailure"
ms.assetid: 657141cd-5cf5-4fdb-a4b2-4c040eba84b5
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Обработка ошибок
Классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> создают и исключения системы \(например, <xref:System.ArgumentException>\) и исключения Интернет\- \( [WebExceptions](frlrfsystemnetwebexceptionclasstopic), вызванное методом, <xref:System.Net.WebRequest.GetResponse%2A> \).  
  
 Каждое **WebException** включает свойство <xref:System.Net.WebException.Status%2A>, содержащее значение из перечисления <xref:System.Net.WebExceptionStatus>.  Можно изучить свойство **Состояние**, чтобы определить, произошедшую ошибку и предпринять необходимые для разрешения ошибки.  
  
 В следующей таблице описаны возможные значения для свойства **Состояние**.  
  
|Состояние|Описание|  
|---------------|--------------|  
|ConnectFailure|Удаленная служба не может быть связана на уровне транспорта.|  
|ConnectionClosed|Соединение было закрыто преждевременно.|  
|KeepAliveFailure|Сервер закрыл установлено соединение с Держать\- значением заголовка в активном состоянии.|  
|NameResolutionFailure|Служба имен не может разрешить данное имя узла.|  
|ProtocolError|Ответ, полученный от сервера был завершен, но показывал ошибку на уровне протокола.|  
|ReceiveFailure|От удаленного сервера не был получен полный ответ.|  
|RequestCanceled|Запрос был отменить.|  
|SecureChannelFailure|Произошла ошибка в связи безопасного канала.|  
|SendFailure|Полный запрос не был передан на удаленный сервер.|  
|ServerProtocolViolation|Ответ сервера не являлся допустимым ответом HTTP.|  
|Успешное выполнение|Ошибок не было.|  
|Время ожидания|Ответ не был получен в наборе времени ожидания для запроса.|  
|TrustFailure|Сертификат сервера не может быть проверен.|  
|MessageLengthLimitExceeded|Принято сообщение о превышении заданного ограничения при передаче запроса или приеме ответа сервера.|  
|Отложенный|Внутренний асинхронный запрос находится в очереди.|  
|PipelineFailure|Это значение поддерживает инфраструктуру платформы .NET Framework и не предназначено для использования непосредственно в коде.|  
|ProxyNameResolutionFailure|Служба разрешения имен не может распознать имя узла прокси\-сервера.|  
|UnknownError|Возникло исключение неизвестного типа.|  
  
 Если свойство **Состояние** **WebExceptionStatus.ProtocolError**, **WebResponse**, содержащий ответ от сервера доступно.  Можно изучить этот ответ, чтобы определить фактический источник ошибки протокола.  
  
 В следующем примере показано, как перехватывать **WebException**.  
  
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
  
 Приложения, использующие throw [SocketExceptions](frlrfsystemnetsocketssocketexceptionclasstopic) класса <xref:System.Net.Sockets.Socket> при возникновении ошибки на сокете Windows.  Классы [TCPClient](frlrfsystemnetsocketstcpclientclasstopic), [TCPListener](frlrfsystemnetsocketstcplistenerclasstopic) и [UDPClient](frlrfsystemnetsocketsudpclientclasstopic) строятся поверх класса **Сокет** и вызывают **SocketExceptions**.  
  
 При **SocketException** создается класс **SocketException** задает свойство <xref:System.Net.Sockets.SocketException.ErrorCode%2A> к последней ошибки сокета операционной системы, которая возникла.  Дополнительные сведения о кодах ошибок сокета см. в документации по API код ошибки Winsock 2.0 в MSDN.  
  
## См. также  
 [Основы обработки исключений](../../../docs/standard/exceptions/exception-handling-fundamentals.md)   
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)