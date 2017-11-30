---
title: "Практическое руководство. Запрос данных с помощью класса WebRequest"
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
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
caps.latest.revision: "8"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e831f3c305716afe11df6c0b1e21db1ed5a4f01e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="cf528-102">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="cf528-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="cf528-103">Следующая процедура описывает шаги, используемые для запроса ресурсов с сервера, например веб-страницы или файла.</span><span class="sxs-lookup"><span data-stu-id="cf528-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="cf528-104">Ресурс должен быть определен универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="cf528-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="cf528-105">Запрос данных с сервера узла</span><span class="sxs-lookup"><span data-stu-id="cf528-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="cf528-106">Создайте экземпляр <xref:System.Net.WebRequest> путем вызова <xref:System.Net.WebRequest.Create%2A> с URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="cf528-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf528-107">Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**, для URI, которые начинаются с "http:", "https:'', "ftp:" и "file:".</span><span class="sxs-lookup"><span data-stu-id="cf528-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="cf528-108">Чтобы получить доступ к ресурсам с использованием других протоколов, необходимо реализовать связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cf528-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="cf528-109">Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="cf528-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="cf528-110">Укажите все необходимые значения свойств в объекте **WebRequest**.</span><span class="sxs-lookup"><span data-stu-id="cf528-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="cf528-111">Например, чтобы включить проверку подлинности, установите для свойства **Credentials** значение экземпляра класса <xref:System.Net.NetworkCredential>.</span><span class="sxs-lookup"><span data-stu-id="cf528-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="cf528-112">В большинстве случаев класса **WebRequest** достаточно для получения данных.</span><span class="sxs-lookup"><span data-stu-id="cf528-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="cf528-113">Однако если необходимо задать связанные с определенным протоколом свойства, следует привести **WebRequest** к типу, связанному с определенным протоколом.</span><span class="sxs-lookup"><span data-stu-id="cf528-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="cf528-114">Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebRequest>, приведите **WebRequest** к ссылке **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="cf528-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="cf528-115">В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A>, связанное с протоколом HTTP.</span><span class="sxs-lookup"><span data-stu-id="cf528-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="cf528-116">Чтобы отправить запрос на сервер, вызовите <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf528-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="cf528-117">Фактический тип возвращаемого объекта **WebResponse** определяется схемой запрошенного URI.</span><span class="sxs-lookup"><span data-stu-id="cf528-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="cf528-118">После завершения работы с объектом <xref:System.Net.WebResponse> его необходимо закрыть путем вызова метода <xref:System.Net.WebResponse.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="cf528-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="cf528-119">Кроме того, полученный поток ответа из объекта ответа можно закрыть путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cf528-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="cf528-120">Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно может оказаться неспособным обрабатывать новые запросы.</span><span class="sxs-lookup"><span data-stu-id="cf528-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="cf528-121">Можно получить доступ к свойствам объекта **WebResponse** или привести объект **WebResponse** к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="cf528-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="cf528-122">Например, чтобы получить доступ к свойствам, определенным для протокола HTTP, для <xref:System.Net.HttpWebResponse>, приведите **WebRequest** к ссылке **HttpWebRequest**.</span><span class="sxs-lookup"><span data-stu-id="cf528-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="cf528-123">В следующем примере кода показано, как отобразить сведения о состоянии, отправленные в ответе.</span><span class="sxs-lookup"><span data-stu-id="cf528-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="cf528-124">Чтобы получить поток, содержащий данные ответа, отправленные сервером, используйте метод <xref:System.Net.HttpWebResponse.GetResponseStream%2A> объекта **WebResponse**.</span><span class="sxs-lookup"><span data-stu-id="cf528-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream ();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="cf528-125">После считывания данных из ответа необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**.</span><span class="sxs-lookup"><span data-stu-id="cf528-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="cf528-126">Вызывать метод **Close** как для потока ответа, так и для объекта **WebResponse** необязательно, но ничто не мешает это сделать.</span><span class="sxs-lookup"><span data-stu-id="cf528-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="cf528-127">**WebResponse.Close** вызывает метод **Stream.Close** при закрытии ответа.</span><span class="sxs-lookup"><span data-stu-id="cf528-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="cf528-128">Пример</span><span class="sxs-lookup"><span data-stu-id="cf528-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main ()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create (  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close ();  
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
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="cf528-129">См. также</span><span class="sxs-lookup"><span data-stu-id="cf528-129">See Also</span></span>  
 [<span data-ttu-id="cf528-130">Создание Интернет-запросов</span><span class="sxs-lookup"><span data-stu-id="cf528-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [<span data-ttu-id="cf528-131">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="cf528-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [<span data-ttu-id="cf528-132">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="cf528-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [<span data-ttu-id="cf528-133">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="cf528-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)  
 [<span data-ttu-id="cf528-134">Практическое руководство. Отправка данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="cf528-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
