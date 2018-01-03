---
title: "Практическое руководство. Отправка данных с помощью класса WebRequest"
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
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: b4cc524b3b3c1dbe42f3fe3926ed44c1e917e871
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-send-data-using-the-webrequest-class"></a><span data-ttu-id="fa317-102">Практическое руководство. Отправка данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="fa317-102">How to: Send Data Using the WebRequest Class</span></span>
<span data-ttu-id="fa317-103">В следующей процедуре описаны действия, используемые для отправки данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="fa317-103">The following procedure describes the steps used to send data to a server.</span></span> <span data-ttu-id="fa317-104">Эта процедура обычно используется для отправки данных на веб-страницу.</span><span class="sxs-lookup"><span data-stu-id="fa317-104">This procedure is commonly used to post data to a Web page.</span></span>  
  
### <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="fa317-105">Отправка данных на сервер узла</span><span class="sxs-lookup"><span data-stu-id="fa317-105">To send data to a host server</span></span>  
  
1.  <span data-ttu-id="fa317-106">Создайте экземпляр <xref:System.Net.WebRequest>, вызвав метод <xref:System.Net.WebRequest.Create%2A> с URI ресурса, который принимает данные, например сценария или страницы ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="fa317-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource that accepts data, for example, a script or ASP.NET page.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa317-107">Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**, для URI, которые начинаются с "http:", "https:'', "ftp:" и "file:".</span><span class="sxs-lookup"><span data-stu-id="fa317-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="fa317-108">Чтобы получить доступ к ресурсам с использованием других протоколов, необходимо реализовать связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="fa317-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="fa317-109">Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="fa317-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="fa317-110">Укажите все необходимые значения свойств в объекте **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="fa317-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="fa317-111">Например, чтобы включить проверку подлинности, установите для свойства **Credentials** значение экземпляра класса <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="fa317-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="fa317-112">В большинстве случаев для отправки данных достаточно самого экземпляра класса **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="fa317-112">In most cases, the **WebRequest** instance itself is sufficient to send data.</span></span> <span data-ttu-id="fa317-113">Однако если необходимо задать связанные с определенным протоколом свойства, следует привести **WebRequest** к типу, связанному с определенным протоколом.</span><span class="sxs-lookup"><span data-stu-id="fa317-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="fa317-114">Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebRequest>, приведите **WebRequest** к ссылке **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="fa317-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="fa317-115">В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A>, связанное с протоколом HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa317-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="fa317-116">Укажите метод протокола, который разрешает отправлять данные с запросом, например метод **POST** HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa317-116">Specify a protocol method that permits data to be sent with a request, such as the HTTP **POST** method.</span></span>  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  <span data-ttu-id="fa317-117">Установите свойство **ContentLength**.</span><span class="sxs-lookup"><span data-stu-id="fa317-117">Set the **ContentLength** property.</span></span>  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  <span data-ttu-id="fa317-118">Укажите необходимое значение для свойства **ContentType**.</span><span class="sxs-lookup"><span data-stu-id="fa317-118">Set the **ContentType** property to an appropriate value.</span></span>  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  <span data-ttu-id="fa317-119">Получите поток, который содержит данные запроса, вызвав метод <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa317-119">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span>  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  <span data-ttu-id="fa317-120">Запишите данные в объект <xref:System.IO.Stream>, возвращенный этим методом.</span><span class="sxs-lookup"><span data-stu-id="fa317-120">Write the data to the <xref:System.IO.Stream> object returned by this method.</span></span>  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  <span data-ttu-id="fa317-121">Закройте поток запроса, вызвав метод **Stream.Close**.</span><span class="sxs-lookup"><span data-stu-id="fa317-121">Close the request stream by calling the **Stream.Close** method.</span></span>  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. <span data-ttu-id="fa317-122">Отправьте запрос на сервер, вызвав метод <xref:System.Net.WebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa317-122">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="fa317-123">Этот метод возвращает объект, содержащий ответ сервера.</span><span class="sxs-lookup"><span data-stu-id="fa317-123">This method returns an object containing the server's response.</span></span> <span data-ttu-id="fa317-124">Тип возвращенного объекта <xref:System.Net.WebResponse> определяется с помощью схемы URI запроса.</span><span class="sxs-lookup"><span data-stu-id="fa317-124">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="fa317-125">После завершения работы с объектом <xref:System.Net.WebResponse> его необходимо закрыть путем вызова метода <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa317-125">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="fa317-126">Кроме того, полученный поток ответа из объекта ответа можно закрыть путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa317-126">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="fa317-127">Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно не сможет обрабатывать новые запросы.</span><span class="sxs-lookup"><span data-stu-id="fa317-127">If you do not close the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
10. <span data-ttu-id="fa317-128">Можно получить доступ к свойствам объекта **WebResponse** или привести объект **WebResponse** к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="fa317-128">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="fa317-129">Например, чтобы получить доступ к свойствам, определенным для протокола HTTP, для <xref:System.Net.HttpWebResponse>, приведите **WebRequest** к ссылке **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="fa317-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to an **HttpWebResponse** reference.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. <span data-ttu-id="fa317-130">Чтобы получить поток, содержащий данные ответа, отправленные сервером, вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A> объекта **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="fa317-130">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. <span data-ttu-id="fa317-131">После считывания данных из ответа необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="fa317-131">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="fa317-132">Вызывать метод **Close** как для потока ответа, так и для объекта **WebResponse** необязательно, но ничто не мешает это сделать.</span><span class="sxs-lookup"><span data-stu-id="fa317-132">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="fa317-133">Пример</span><span class="sxs-lookup"><span data-stu-id="fa317-133">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa317-134">См. также</span><span class="sxs-lookup"><span data-stu-id="fa317-134">See Also</span></span>  
 [<span data-ttu-id="fa317-135">Создание интернет-запросов</span><span class="sxs-lookup"><span data-stu-id="fa317-135">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="fa317-136">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="fa317-136">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="fa317-137">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="fa317-137">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="fa317-138">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="fa317-138">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="fa317-139">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="fa317-139">How to: Request Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
