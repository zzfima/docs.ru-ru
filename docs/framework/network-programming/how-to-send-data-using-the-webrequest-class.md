---
title: Практическое руководство. Отправка данных с помощью класса WebRequest
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 2467b289df7a0361b51ad91d4458d32742c42275
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "70040833"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a><span data-ttu-id="40467-102">Практическое руководство. Отправка данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="40467-102">How to: Send data by using the WebRequest class</span></span>

<span data-ttu-id="40467-103">В следующей процедуре описаны действия для отправки данных на сервер.</span><span class="sxs-lookup"><span data-stu-id="40467-103">The following procedure describes the steps to send data to a server.</span></span> <span data-ttu-id="40467-104">Эта процедура обычно используется для отправки данных на веб-страницу.</span><span class="sxs-lookup"><span data-stu-id="40467-104">This procedure is commonly used to post data to a Web page.</span></span>

## <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="40467-105">Отправка данных на сервер узла</span><span class="sxs-lookup"><span data-stu-id="40467-105">To send data to a host server</span></span>

1. <span data-ttu-id="40467-106">Создайте экземпляр <xref:System.Net.WebRequest>, вызвав метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> с URI ресурса, например сценария или страницы ASP.NET, который принимает данные.</span><span class="sxs-lookup"><span data-stu-id="40467-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource, such as a script or ASP.NET page, that accepts data.</span></span> <span data-ttu-id="40467-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > <span data-ttu-id="40467-108">Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, для URI, которые начинаются с *http:* , *https:* , *ftp:* и *file:* .</span><span class="sxs-lookup"><span data-stu-id="40467-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="40467-109">Если нужно задать или считать связанные с определенным протоколом свойства, следует привести объект <xref:System.Net.WebRequest> или <xref:System.Net.WebResponse> к типу объекта, связанному с определенным протоколом.</span><span class="sxs-lookup"><span data-stu-id="40467-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="40467-110">Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="40467-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="40467-111">Укажите все необходимые значения свойств в объекте `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="40467-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="40467-112">Например, чтобы включить проверку подлинности, установите для свойства <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> значение экземпляра класса <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="40467-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="40467-113">Укажите метод протокола, который разрешает отправлять данные с запросом, например метод `POST` HTTP:</span><span class="sxs-lookup"><span data-stu-id="40467-113">Specify a protocol method that permits data to be sent with a request, such as the HTTP `POST` method:</span></span>

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. <span data-ttu-id="40467-114">Задайте для свойства <xref:System.Web.HttpRequest.ContentLength> число байт, включаемых в запрос.</span><span class="sxs-lookup"><span data-stu-id="40467-114">Set the <xref:System.Web.HttpRequest.ContentLength> property to the number of bytes you're including with your request.</span></span> <span data-ttu-id="40467-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-115">For example:</span></span>

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. <span data-ttu-id="40467-116">Присвойте свойству <xref:System.Web.HttpRequest.ContentType> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="40467-116">Set the <xref:System.Web.HttpRequest.ContentType> property to an appropriate value.</span></span> <span data-ttu-id="40467-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-117">For example:</span></span>

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. <span data-ttu-id="40467-118">Получите поток, который содержит данные запроса, вызвав метод <xref:System.Net.WebRequest.GetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="40467-118">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span> <span data-ttu-id="40467-119">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-119">For example:</span></span>

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. <span data-ttu-id="40467-120">Запишите данные в объект <xref:System.IO.Stream>, возвращенный методом `GetRequestStream`.</span><span class="sxs-lookup"><span data-stu-id="40467-120">Write the data to the <xref:System.IO.Stream> object returned by the `GetRequestStream` method.</span></span> <span data-ttu-id="40467-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-121">For example:</span></span>

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. <span data-ttu-id="40467-122">Закройте поток запроса, вызвав метод <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40467-122">Close the request stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="40467-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-123">For example:</span></span>

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. <span data-ttu-id="40467-124">Отправьте запрос на сервер, вызвав метод <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40467-124">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="40467-125">Этот метод возвращает объект, содержащий ответ сервера.</span><span class="sxs-lookup"><span data-stu-id="40467-125">This method returns an object containing the server's response.</span></span> <span data-ttu-id="40467-126">Тип возвращенного объекта `WebResponse` определяется с помощью схемы URI запроса.</span><span class="sxs-lookup"><span data-stu-id="40467-126">The returned `WebResponse` object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="40467-127">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-127">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. <span data-ttu-id="40467-128">Вы можете получить доступ к свойствам объекта `WebResponse` или привести этот объект к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="40467-128">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="40467-129">Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebResponse>, приведите объект `WebResponse` к ссылке <xref:System.Net.HttpWebResponse>.</span><span class="sxs-lookup"><span data-stu-id="40467-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an <xref:System.Net.HttpWebResponse> reference.</span></span> <span data-ttu-id="40467-130">В следующем примере кода показано, как отобразить свойство <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, связанное с протоколом HTTP, которое было отправлено в ответе:</span><span class="sxs-lookup"><span data-stu-id="40467-130">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. <span data-ttu-id="40467-131">Чтобы получить поток, содержащий данные ответа, отправленные сервером, вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> объекта `WebResponse`.</span><span class="sxs-lookup"><span data-stu-id="40467-131">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method of your `WebResponse` object.</span></span> <span data-ttu-id="40467-132">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-132">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. <span data-ttu-id="40467-133">После считывания данных из объекта ответа закройте его с помощью метода <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> или закройте поток ответа с помощью метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="40467-133">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="40467-134">Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно может оказаться неспособным обрабатывать новые запросы.</span><span class="sxs-lookup"><span data-stu-id="40467-134">If you don't close either the response or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="40467-135">Так как при закрытии ответа метод `WebResponse.Close` вызывает `Stream.Close`, вызывать `Close` для объектов как потока, так и ответа не требуется (при этом выполнение такой операции не приведет к негативным последствиям).</span><span class="sxs-lookup"><span data-stu-id="40467-135">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="40467-136">Пример:</span><span class="sxs-lookup"><span data-stu-id="40467-136">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="40467-137">Пример</span><span class="sxs-lookup"><span data-stu-id="40467-137">Example</span></span>

<span data-ttu-id="40467-138">В следующем примере показана отправка данных на веб-сервер и считывание данных в ответе:</span><span class="sxs-lookup"><span data-stu-id="40467-138">The following example shows how to send data to a web server and read the data in its response:</span></span>

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a><span data-ttu-id="40467-139">См. также</span><span class="sxs-lookup"><span data-stu-id="40467-139">See also</span></span>

- [<span data-ttu-id="40467-140">Создание интернет-запросов</span><span class="sxs-lookup"><span data-stu-id="40467-140">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="40467-141">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="40467-141">Using streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="40467-142">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="40467-142">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="40467-143">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="40467-143">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="40467-144">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="40467-144">How to: Request data by using the WebRequest class</span></span>](how-to-request-data-using-the-webrequest-class.md)
