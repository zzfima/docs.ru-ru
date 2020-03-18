---
title: Практическое руководство. Запрос данных с помощью класса WebRequest
ms.date: 03/21/2019
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
ms.openlocfilehash: e670a2a503ce704eff847e9e0b3ee340ab52fe62
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048165"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="ea871-102">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="ea871-102">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="ea871-103">Следующая процедура описывает шаги для запроса ресурсов, например веб-страницы или файла, с сервера.</span><span class="sxs-lookup"><span data-stu-id="ea871-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="ea871-104">Ресурс должен быть определен универсальным кодом ресурса (URI).</span><span class="sxs-lookup"><span data-stu-id="ea871-104">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="ea871-105">Запрос данных с сервера узла</span><span class="sxs-lookup"><span data-stu-id="ea871-105">To request data from a host server</span></span>

1. <span data-ttu-id="ea871-106">Создайте экземпляр <xref:System.Net.WebRequest> путем вызова <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> с URI ресурса.</span><span class="sxs-lookup"><span data-stu-id="ea871-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="ea871-107">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea871-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="ea871-108">Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, для URI, которые начинаются с *http:* , *https:* , *ftp:* и *file:* .</span><span class="sxs-lookup"><span data-stu-id="ea871-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="ea871-109">Если нужно задать или считать связанные с определенным протоколом свойства, следует привести объект <xref:System.Net.WebRequest> или <xref:System.Net.WebResponse> к типу объекта, связанному с определенным протоколом.</span><span class="sxs-lookup"><span data-stu-id="ea871-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="ea871-110">Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="ea871-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="ea871-111">Укажите все необходимые значения свойств в объекте `WebRequest`.</span><span class="sxs-lookup"><span data-stu-id="ea871-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="ea871-112">Например, чтобы включить проверку подлинности, установите для свойства <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> значение экземпляра класса <xref:System.Net.NetworkCredential>:</span><span class="sxs-lookup"><span data-stu-id="ea871-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="ea871-113">Отправьте запрос на сервер, вызвав метод <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea871-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ea871-114">Этот метод возвращает объект, содержащий ответ сервера.</span><span class="sxs-lookup"><span data-stu-id="ea871-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="ea871-115">Тип возвращенного объекта <xref:System.Net.WebResponse> определяется с помощью схемы URI запроса.</span><span class="sxs-lookup"><span data-stu-id="ea871-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="ea871-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea871-116">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="ea871-117">Вы можете получить доступ к свойствам объекта `WebResponse` или привести этот объект к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола.</span><span class="sxs-lookup"><span data-stu-id="ea871-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="ea871-118">Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebResponse>, приведите объект `WebResponse` к ссылке `HttpWebResponse`.</span><span class="sxs-lookup"><span data-stu-id="ea871-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="ea871-119">В следующем примере кода показано, как отобразить свойство <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, связанное с протоколом HTTP, которое было отправлено в ответе:</span><span class="sxs-lookup"><span data-stu-id="ea871-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="ea871-120">Чтобы получить поток, содержащий данные ответа, отправленные сервером, вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea871-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ea871-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea871-121">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="ea871-122">После считывания данных из объекта ответа закройте его с помощью метода <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> или закройте поток ответа с помощью метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ea871-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ea871-123">Если не закрыть объект ответа или поток, у приложения могут закончиться подключения к серверу и оно может оказаться неспособным обрабатывать новые запросы.</span><span class="sxs-lookup"><span data-stu-id="ea871-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="ea871-124">Так как при закрытии ответа метод `WebResponse.Close` вызывает `Stream.Close`, вызывать `Close` для объектов как потока, так и ответа не требуется (при этом выполнение такой операции не приведет к негативным последствиям).</span><span class="sxs-lookup"><span data-stu-id="ea871-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="ea871-125">Пример:</span><span class="sxs-lookup"><span data-stu-id="ea871-125">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="ea871-126">Пример</span><span class="sxs-lookup"><span data-stu-id="ea871-126">Example</span></span>

<span data-ttu-id="ea871-127">В следующем примере кода показано создание запроса к веб-серверу и считывание данных в ответе:</span><span class="sxs-lookup"><span data-stu-id="ea871-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="ea871-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ea871-128">See also</span></span>

- [<span data-ttu-id="ea871-129">Создание интернет-запросов</span><span class="sxs-lookup"><span data-stu-id="ea871-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="ea871-130">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="ea871-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="ea871-131">Доступ к Интернету через прокси-сервер</span><span class="sxs-lookup"><span data-stu-id="ea871-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="ea871-132">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="ea871-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="ea871-133">Практическое руководство. Отправка данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="ea871-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
