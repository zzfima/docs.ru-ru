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
ms.openlocfilehash: 255a4ab3d6d6e3fc133e809ce360b25d6f82c8d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940070"
---
# <a name="handling-errors"></a><span data-ttu-id="aa137-102">Обработка ошибок</span><span class="sxs-lookup"><span data-stu-id="aa137-102">Handling Errors</span></span>
<span data-ttu-id="aa137-103">Классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> вызывают одновременно системные исключения (например, <xref:System.ArgumentException>) и веб-исключения (исключения <xref:System.Net.WebException>, вызываемые методом <xref:System.Net.WebRequest.GetResponse%2A>).</span><span class="sxs-lookup"><span data-stu-id="aa137-103">The <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes throw both system exceptions (such as <xref:System.ArgumentException>) and Web-specific exceptions (which are <xref:System.Net.WebException> thrown by the <xref:System.Net.WebRequest.GetResponse%2A> method).</span></span>  
  
 <span data-ttu-id="aa137-104">Каждый класс **WebException** включает свойство <xref:System.Net.WebException.Status%2A>, которое содержит значение перечисления <xref:System.Net.WebExceptionStatus>.</span><span class="sxs-lookup"><span data-stu-id="aa137-104">Each **WebException** includes a <xref:System.Net.WebException.Status%2A> property that contains a value from the <xref:System.Net.WebExceptionStatus> enumeration.</span></span> <span data-ttu-id="aa137-105">Значение свойства **Status** позволяет определить произошедшую ошибку и действия, которые следует предпринять для ее устранения.</span><span class="sxs-lookup"><span data-stu-id="aa137-105">You can examine the **Status** property to determine the error that occurred and take the proper steps to resolve the error.</span></span>  
  
 <span data-ttu-id="aa137-106">В следующей таблице описаны возможные значения свойства **Status**.</span><span class="sxs-lookup"><span data-stu-id="aa137-106">The following table describes the possible values for the **Status** property.</span></span>  
  
|<span data-ttu-id="aa137-107">Status</span><span class="sxs-lookup"><span data-stu-id="aa137-107">Status</span></span>|<span data-ttu-id="aa137-108">ОПИСАНИЕ</span><span class="sxs-lookup"><span data-stu-id="aa137-108">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="aa137-109">ConnectFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-109">ConnectFailure</span></span>|<span data-ttu-id="aa137-110">Не удалось связаться с удаленной службой на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="aa137-110">The remote service could not be contacted at the transport level.</span></span>|  
|<span data-ttu-id="aa137-111">ConnectionClosed</span><span class="sxs-lookup"><span data-stu-id="aa137-111">ConnectionClosed</span></span>|<span data-ttu-id="aa137-112">Соединение было преждевременно закрыто.</span><span class="sxs-lookup"><span data-stu-id="aa137-112">The connection was closed prematurely.</span></span>|  
|<span data-ttu-id="aa137-113">KeepAliveFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-113">KeepAliveFailure</span></span>|<span data-ttu-id="aa137-114">Сервер закрыл подключение, установленное с заданным заголовком проверки активности.</span><span class="sxs-lookup"><span data-stu-id="aa137-114">The server closed a connection made with the Keep-alive header set.</span></span>|  
|<span data-ttu-id="aa137-115">NameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-115">NameResolutionFailure</span></span>|<span data-ttu-id="aa137-116">Службе имен не удалось разрешить имя узла.</span><span class="sxs-lookup"><span data-stu-id="aa137-116">The name service could not resolve the host name.</span></span>|  
|<span data-ttu-id="aa137-117">ProtocolError</span><span class="sxs-lookup"><span data-stu-id="aa137-117">ProtocolError</span></span>|<span data-ttu-id="aa137-118">От сервера получен полный ответ, указывающий на ошибку на уровне протокола.</span><span class="sxs-lookup"><span data-stu-id="aa137-118">The response received from the server was complete but indicated an error at the protocol level.</span></span>|  
|<span data-ttu-id="aa137-119">ReceiveFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-119">ReceiveFailure</span></span>|<span data-ttu-id="aa137-120">От удаленного сервера не получен полный ответ.</span><span class="sxs-lookup"><span data-stu-id="aa137-120">A complete response was not received from the remote server.</span></span>|  
|<span data-ttu-id="aa137-121">RequestCanceled</span><span class="sxs-lookup"><span data-stu-id="aa137-121">RequestCanceled</span></span>|<span data-ttu-id="aa137-122">Запрос отменен.</span><span class="sxs-lookup"><span data-stu-id="aa137-122">The request was canceled.</span></span>|  
|<span data-ttu-id="aa137-123">SecureChannelFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-123">SecureChannelFailure</span></span>|<span data-ttu-id="aa137-124">Произошла ошибка в защищенном канале связи.</span><span class="sxs-lookup"><span data-stu-id="aa137-124">An error occurred in a secure channel link.</span></span>|  
|<span data-ttu-id="aa137-125">SendFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-125">SendFailure</span></span>|<span data-ttu-id="aa137-126">Не удалось отправить полный запрос на удаленный сервер.</span><span class="sxs-lookup"><span data-stu-id="aa137-126">A complete request could not be sent to the remote server.</span></span>|  
|<span data-ttu-id="aa137-127">ServerProtocolViolation</span><span class="sxs-lookup"><span data-stu-id="aa137-127">ServerProtocolViolation</span></span>|<span data-ttu-id="aa137-128">Ответ от сервера не является допустимым ответом HTTP.</span><span class="sxs-lookup"><span data-stu-id="aa137-128">The server response was not a valid HTTP response.</span></span>|  
|<span data-ttu-id="aa137-129">Success</span><span class="sxs-lookup"><span data-stu-id="aa137-129">Success</span></span>|<span data-ttu-id="aa137-130">Ошибки не обнаружены.</span><span class="sxs-lookup"><span data-stu-id="aa137-130">No error was encountered.</span></span>|  
|<span data-ttu-id="aa137-131">Время ожидания</span><span class="sxs-lookup"><span data-stu-id="aa137-131">Timeout</span></span>|<span data-ttu-id="aa137-132">В течение заданного для запроса времени ожидания не был получен ответ.</span><span class="sxs-lookup"><span data-stu-id="aa137-132">No response was received within the time-out set for the request.</span></span>|  
|<span data-ttu-id="aa137-133">TrustFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-133">TrustFailure</span></span>|<span data-ttu-id="aa137-134">Не удалось проверить сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="aa137-134">A server certificate could not be validated.</span></span>|  
|<span data-ttu-id="aa137-135">MessageLengthLimitExceeded</span><span class="sxs-lookup"><span data-stu-id="aa137-135">MessageLengthLimitExceeded</span></span>|<span data-ttu-id="aa137-136">Получено сообщение, которое превышает ограничение, заданное при отправке запроса или получении ответа от сервера.</span><span class="sxs-lookup"><span data-stu-id="aa137-136">A message was received that exceeded the specified limit when sending a request or receiving a response from the server.</span></span>|  
|<span data-ttu-id="aa137-137">Не завершен</span><span class="sxs-lookup"><span data-stu-id="aa137-137">Pending</span></span>|<span data-ttu-id="aa137-138">Ожидается выполнение внутреннего асинхронного запроса.</span><span class="sxs-lookup"><span data-stu-id="aa137-138">An internal asynchronous request is pending.</span></span>|  
|<span data-ttu-id="aa137-139">PipelineFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-139">PipelineFailure</span></span>|<span data-ttu-id="aa137-140">Это значение поддерживает платформу .NET Framework и не должно использоваться непосредственно из вашего кода.</span><span class="sxs-lookup"><span data-stu-id="aa137-140">This value supports the .NET Framework infrastructure and is not intended to be used directly in your code.</span></span>|  
|<span data-ttu-id="aa137-141">ProxyNameResolutionFailure</span><span class="sxs-lookup"><span data-stu-id="aa137-141">ProxyNameResolutionFailure</span></span>|<span data-ttu-id="aa137-142">Службе разрешения имен не удалось разрешить имя узла прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="aa137-142">The name resolver service could not resolve the proxy host name.</span></span>|  
|<span data-ttu-id="aa137-143">UnknownError</span><span class="sxs-lookup"><span data-stu-id="aa137-143">UnknownError</span></span>|<span data-ttu-id="aa137-144">Возникло исключение неизвестного типа.</span><span class="sxs-lookup"><span data-stu-id="aa137-144">An exception of unknown type has occurred.</span></span>|  
  
 <span data-ttu-id="aa137-145">Если свойство **Status** имеет значение **WebExceptionStatus.ProtocolError**, доступен **WebResponse**, содержащий ответ сервера.</span><span class="sxs-lookup"><span data-stu-id="aa137-145">When the **Status** property is **WebExceptionStatus.ProtocolError**, a **WebResponse** that contains the response from the server is available.</span></span> <span data-ttu-id="aa137-146">Содержимое этого ответа позволяет определить фактический источник ошибки протокола.</span><span class="sxs-lookup"><span data-stu-id="aa137-146">You can examine this response to determine the actual source of the protocol error.</span></span>  
  
 <span data-ttu-id="aa137-147">В следующем примере демонстрируется перехват исключения **WebException**.</span><span class="sxs-lookup"><span data-stu-id="aa137-147">The following example shows how to catch a **WebException**.</span></span>  
  
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
  
 <span data-ttu-id="aa137-148">Приложения, использующие класс <xref:System.Net.Sockets.Socket>, вызывают исключение <xref:System.Net.Sockets.SocketException> при возникновении ошибки в сокете Windows.</span><span class="sxs-lookup"><span data-stu-id="aa137-148">Applications that use the <xref:System.Net.Sockets.Socket> class throw <xref:System.Net.Sockets.SocketException> when errors occur on the Windows socket.</span></span> <span data-ttu-id="aa137-149">Классы <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener> и <xref:System.Net.Sockets.UdpClient> построены на основе класса **Socket** и также вызывают исключения **SocketException**.</span><span class="sxs-lookup"><span data-stu-id="aa137-149">The <xref:System.Net.Sockets.TcpClient>, <xref:System.Net.Sockets.TcpListener>, and <xref:System.Net.Sockets.UdpClient> classes are built on top of the **Socket** class and throw **SocketExceptions** as well.</span></span>  
  
 <span data-ttu-id="aa137-150">Если возникает исключение **SocketException**, класс **SocketException** присваивает свойству <xref:System.Net.Sockets.SocketException.ErrorCode%2A> значение, отражающее последнюю ошибку сокета операционной системы.</span><span class="sxs-lookup"><span data-stu-id="aa137-150">When a **SocketException** is thrown, the **SocketException** class sets the <xref:System.Net.Sockets.SocketException.ErrorCode%2A> property to the last operating system socket error that occurred.</span></span> <span data-ttu-id="aa137-151">Дополнительные сведения о кодах ошибок сокета см. в документации по кодам ошибок API Winsock 2.0 на веб-сайте MSDN.</span><span class="sxs-lookup"><span data-stu-id="aa137-151">For more information about socket error codes, see the Winsock 2.0 API error code documentation in MSDN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa137-152">См. также</span><span class="sxs-lookup"><span data-stu-id="aa137-152">See also</span></span>

- [<span data-ttu-id="aa137-153">Основы обработки исключений</span><span class="sxs-lookup"><span data-stu-id="aa137-153">Exception Handling Fundamentals</span></span>](../../standard/exceptions/exception-handling-fundamentals.md)
- [<span data-ttu-id="aa137-154">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="aa137-154">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
