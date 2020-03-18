---
title: Использование потоков в сети
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, streams
- Networking
- response to Internet request, streams
- network resources, stream capabilities
- receiving data, stream capabilities
- Network Resources
- sending data, stream capabilities
- downloading Internet resources, streams
- streams, capabilities
- Internet, streams
- streams
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
ms.openlocfilehash: 7d5a2e3eec9b49731a09f6eb41a8d8500a59b45c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180623"
---
# <a name="using-streams-on-the-network"></a><span data-ttu-id="e95cd-102">Использование потоков в сети</span><span class="sxs-lookup"><span data-stu-id="e95cd-102">Using Streams on the Network</span></span>
<span data-ttu-id="e95cd-103">Сетевые ресурсы представлены в .NET Framework как потоки.</span><span class="sxs-lookup"><span data-stu-id="e95cd-103">Network resources are represented in the .NET Framework as streams.</span></span> <span data-ttu-id="e95cd-104">Если рассматривать потоки в целом, платформа .NET Framework предоставляет указанные ниже возможности.</span><span class="sxs-lookup"><span data-stu-id="e95cd-104">By treating streams generically, the .NET Framework offers the following capabilities:</span></span>  
  
- <span data-ttu-id="e95cd-105">Единый способ отправки и получения данных через Интернет.</span><span class="sxs-lookup"><span data-stu-id="e95cd-105">A common way to send and receive Web data.</span></span> <span data-ttu-id="e95cd-106">Каким бы ни было содержимое файла — HTML, XML или что-то иное — приложение будет использовать для отправки и получения данных методы <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> и <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-106">Whatever the actual contents of the file — HTML, XML, or anything else — your application will use <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> and <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType> to send and receive data.</span></span>  
  
- <span data-ttu-id="e95cd-107">Совместимость с другими потоками в платформе .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e95cd-107">Compatibility with streams across the .NET Framework.</span></span> <span data-ttu-id="e95cd-108">Потоки используются в .NET Framework в самых разных целях, и для их обработки имеется развитая инфраструктура.</span><span class="sxs-lookup"><span data-stu-id="e95cd-108">Streams are used throughout the .NET Framework, which has a rich infrastructure for handling them.</span></span> <span data-ttu-id="e95cd-109">Например, вы можете изменить приложение, считывающее данные XML из потока <xref:System.IO.FileStream>, так, чтобы оно считывало данные из <xref:System.Net.Sockets.NetworkStream>, изменив всего лишь несколько строк кода, которые инициализируют поток.</span><span class="sxs-lookup"><span data-stu-id="e95cd-109">For example, you can modify an application that reads XML data from a <xref:System.IO.FileStream> to read data from a <xref:System.Net.Sockets.NetworkStream> instead by changing only the few lines of code that initialize the stream.</span></span> <span data-ttu-id="e95cd-110">Основные отличия класса **NetworkStream** от других потоков заключаются в том, что **NetworkStream** не поддерживает поиск, свойство <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> всегда возвращает значение **false**, а методы <xref:System.Net.Sockets.NetworkStream.Seek%2A> и <xref:System.Net.Sockets.NetworkStream.Position%2A> создают исключение <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-110">The major differences between the **NetworkStream** class and other streams are that **NetworkStream** is not seekable, the <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> property always returns **false**, and the <xref:System.Net.Sockets.NetworkStream.Seek%2A> and <xref:System.Net.Sockets.NetworkStream.Position%2A> methods throw a <xref:System.NotSupportedException>.</span></span>  
  
- <span data-ttu-id="e95cd-111">Обработка данных по мере поступления.</span><span class="sxs-lookup"><span data-stu-id="e95cd-111">Processing of data as it arrives.</span></span> <span data-ttu-id="e95cd-112">Потоки обеспечивают доступ к данным в процессе их поступления из сети, так что приложению не нужно ждать, когда скачается весь набор данных.</span><span class="sxs-lookup"><span data-stu-id="e95cd-112">Streams provide access to data as it arrives from the network, rather than forcing your application to wait for an entire data set to be downloaded.</span></span>  
  
 <span data-ttu-id="e95cd-113">Пространство имен <xref:System.Net.Sockets> содержит класс **NetworkStream**, который реализует класс <xref:System.IO.Stream> специально для использования с сетевыми ресурсами.</span><span class="sxs-lookup"><span data-stu-id="e95cd-113">The <xref:System.Net.Sockets> namespace contains a **NetworkStream** class that implements the <xref:System.IO.Stream> class specifically for use with network resources.</span></span> <span data-ttu-id="e95cd-114">Классы из пространства имен <xref:System.Net.Sockets> используют класс **NetworkStream** для представления потоков.</span><span class="sxs-lookup"><span data-stu-id="e95cd-114">Classes in the <xref:System.Net.Sockets> namespace use the **NetworkStream** class to represent streams.</span></span>  
  
 <span data-ttu-id="e95cd-115">Для отправки данных в сеть с помощью полученного потока вызовите метод <xref:System.Net.WebRequest.GetRequestStream%2A> класса <xref:System.Net.WebRequest>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-115">To send data to the network using the returned stream, call <xref:System.Net.WebRequest.GetRequestStream%2A> on your <xref:System.Net.WebRequest>.</span></span> <span data-ttu-id="e95cd-116">**WebRequest** отправит заголовки запроса на сервер, после чего можно отправлять данные в сетевой ресурс, вызывая метод <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> или <xref:System.IO.Stream.Write%2A> возвращенного потока.</span><span class="sxs-lookup"><span data-stu-id="e95cd-116">The **WebRequest** will send request headers to the server; then you can send data to the network resource by calling the <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A>, or <xref:System.IO.Stream.Write%2A> method on the returned stream.</span></span> <span data-ttu-id="e95cd-117">Некоторые протоколы, такие как HTTP, могут требовать задания определенных свойств протокола перед отправкой данных.</span><span class="sxs-lookup"><span data-stu-id="e95cd-117">Some protocols, such as HTTP, may require you to set protocol-specific properties before sending data.</span></span> <span data-ttu-id="e95cd-118">В приведенном ниже примере кода показано, как задать свойства протокола HTTP для отправки данных.</span><span class="sxs-lookup"><span data-stu-id="e95cd-118">The following code example shows how to set HTTP-specific properties for sending data.</span></span> <span data-ttu-id="e95cd-119">Предполагается, что переменная `sendData` содержит отправляемые данные, а в переменной `sendLength` указывается число передаваемых байтов.</span><span class="sxs-lookup"><span data-stu-id="e95cd-119">It assumes that the variable `sendData` contains the data to send and that the variable `sendLength` is the number of bytes of data to send.</span></span>  
  
```csharp  
HttpWebRequest request =
   (HttpWebRequest) WebRequest.Create("http://www.contoso.com/");  
request.Method = "POST";  
request.ContentLength = sendLength;  
try  
{  
   Stream sendStream = request.GetRequestStream();  
   sendStream.Write(sendData,0,sendLength);  
   sendStream.Close();  
}  
catch  
{  
   // Handle errors . . .  
}  
```  
  
```vb  
Dim request As HttpWebRequest = _  
   CType(WebRequest.Create("http://www.contoso.com/"), HttpWebRequest)  
request.Method = "POST"  
request.ContentLength = sendLength  
Try  
   Dim sendStream As Stream = request.GetRequestStream()  
   sendStream.Write(sendData, 0, sendLength)  
   sendStream.Close()  
Catch  
   ' Handle errors . . .  
End Try  
```  
  
 <span data-ttu-id="e95cd-120">Для получения данных из сети вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A> класса <xref:System.Net.WebResponse>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-120">To receive data from the network, call <xref:System.Net.WebResponse.GetResponseStream%2A> on your <xref:System.Net.WebResponse>.</span></span> <span data-ttu-id="e95cd-121">После этого можно считывать данные из сетевого ресурса, вызывая метод <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> или <xref:System.IO.Stream.Read%2A> возвращенного потока.</span><span class="sxs-lookup"><span data-stu-id="e95cd-121">You can then read data from the network resource by calling the <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A>, or <xref:System.IO.Stream.Read%2A> method on the returned stream.</span></span>  
  
 <span data-ttu-id="e95cd-122">При использовании потоков из сетевых ресурсов следует учитывать указанные ниже моменты.</span><span class="sxs-lookup"><span data-stu-id="e95cd-122">When using streams from network resources, keep in mind the following points:</span></span>  
  
- <span data-ttu-id="e95cd-123">Свойство **CanSeek** всегда возвращает значение **false**, так как класс **NetworkStream** не может изменять позицию в потоке.</span><span class="sxs-lookup"><span data-stu-id="e95cd-123">The **CanSeek** property always returns **false** since the **NetworkStream** class cannot change position in the stream.</span></span> <span data-ttu-id="e95cd-124">Методы **Seek** и **Position** создают исключение **NotSupportedException**.</span><span class="sxs-lookup"><span data-stu-id="e95cd-124">The **Seek** and **Position** methods throw a **NotSupportedException**.</span></span>  
  
- <span data-ttu-id="e95cd-125">При использовании классов **WebRequest** и **WebResponse** экземпляры потока, создаваемые путем вызова метода **GetResponseStream**, доступны только для чтения, а экземпляры, создаваемые путем вызова метода **GetRequestStream**, доступны только для записи.</span><span class="sxs-lookup"><span data-stu-id="e95cd-125">When you use **WebRequest** and **WebResponse**, stream instances created by calling **GetResponseStream** are read-only and stream instances created by calling **GetRequestStream** are write-only.</span></span>  
  
- <span data-ttu-id="e95cd-126">Чтобы упростить кодирование, используйте класс <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-126">Use the <xref:System.IO.StreamReader> class to make encoding easier.</span></span> <span data-ttu-id="e95cd-127">В приведенном ниже примере кода **StreamReader** используется для чтения потока в кодировке ASCII из объекта **WebResponse** (создание запроса в примере не показано).</span><span class="sxs-lookup"><span data-stu-id="e95cd-127">The following code example uses a **StreamReader** to read an ASCII-encoded stream from a **WebResponse** (the example does not show creating the request).</span></span>  
  
- <span data-ttu-id="e95cd-128">Вызов метода **GetResponse** может быть блокирован, если сетевые ресурсы недоступны.</span><span class="sxs-lookup"><span data-stu-id="e95cd-128">The call to **GetResponse** can block if network resources are not available.</span></span> <span data-ttu-id="e95cd-129">Вместо этого можно использовать асинхронный запрос с помощью методов <xref:System.Net.WebRequest.BeginGetResponse%2A> и <xref:System.Net.WebRequest.EndGetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-129">You should consider using an asynchronous request with the <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods.</span></span>  
  
- <span data-ttu-id="e95cd-130">Вызов метода **GetRequestStream** может быть заблокирован во время установления соединения с сервером.</span><span class="sxs-lookup"><span data-stu-id="e95cd-130">The call to **GetRequestStream** can block while the connection to the server is created.</span></span> <span data-ttu-id="e95cd-131">Вместо этого можно использовать асинхронный запрос потока с помощью методов <xref:System.Net.WebRequest.BeginGetRequestStream%2A> и <xref:System.Net.WebRequest.EndGetRequestStream%2A>.</span><span class="sxs-lookup"><span data-stu-id="e95cd-131">You should consider using an asynchronous request for the stream with the <xref:System.Net.WebRequest.BeginGetRequestStream%2A> and <xref:System.Net.WebRequest.EndGetRequestStream%2A> methods.</span></span>  
  
```csharp  
// Create a response object.  
WebResponse response = request.GetResponse();  
// Get a readable stream from the server.  
StreamReader sr =
   new StreamReader(response.GetResponseStream(), Encoding.ASCII);  
// Use the stream. Remember when you are through with the stream to close it.  
sr.Close();  
```  
  
```vb  
' Create a response object.  
Dim response As WebResponse = request.GetResponse()  
' Get a readable stream from the server.  
Dim sr As _
   New StreamReader(response.GetResponseStream(), Encoding.ASCII)  
' Use the stream. Remember when you are through with the stream to close it.  
sr.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="e95cd-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e95cd-132">See also</span></span>

- [<span data-ttu-id="e95cd-133">Практическое руководство. Запрос данных с помощью класса WebRequest</span><span class="sxs-lookup"><span data-stu-id="e95cd-133">How to: Request Data Using the WebRequest Class</span></span>](how-to-request-data-using-the-webrequest-class.md)
- [<span data-ttu-id="e95cd-134">Запрос данных</span><span class="sxs-lookup"><span data-stu-id="e95cd-134">Requesting Data</span></span>](requesting-data.md)
