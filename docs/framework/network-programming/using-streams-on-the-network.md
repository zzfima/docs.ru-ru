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
# <a name="using-streams-on-the-network"></a>Использование потоков в сети
Сетевые ресурсы представлены в .NET Framework как потоки. Если рассматривать потоки в целом, платформа .NET Framework предоставляет указанные ниже возможности.  
  
- Единый способ отправки и получения данных через Интернет. Каким бы ни было содержимое файла — HTML, XML или что-то иное — приложение будет использовать для отправки и получения данных методы <xref:System.IO.Stream.Write%2A?displayProperty=nameWithType> и <xref:System.IO.Stream.Read%2A?displayProperty=nameWithType>.  
  
- Совместимость с другими потоками в платформе .NET Framework. Потоки используются в .NET Framework в самых разных целях, и для их обработки имеется развитая инфраструктура. Например, вы можете изменить приложение, считывающее данные XML из потока <xref:System.IO.FileStream>, так, чтобы оно считывало данные из <xref:System.Net.Sockets.NetworkStream>, изменив всего лишь несколько строк кода, которые инициализируют поток. Основные отличия класса **NetworkStream** от других потоков заключаются в том, что **NetworkStream** не поддерживает поиск, свойство <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> всегда возвращает значение **false**, а методы <xref:System.Net.Sockets.NetworkStream.Seek%2A> и <xref:System.Net.Sockets.NetworkStream.Position%2A> создают исключение <xref:System.NotSupportedException>.  
  
- Обработка данных по мере поступления. Потоки обеспечивают доступ к данным в процессе их поступления из сети, так что приложению не нужно ждать, когда скачается весь набор данных.  
  
 Пространство имен <xref:System.Net.Sockets> содержит класс **NetworkStream**, который реализует класс <xref:System.IO.Stream> специально для использования с сетевыми ресурсами. Классы из пространства имен <xref:System.Net.Sockets> используют класс **NetworkStream** для представления потоков.  
  
 Для отправки данных в сеть с помощью полученного потока вызовите метод <xref:System.Net.WebRequest.GetRequestStream%2A> класса <xref:System.Net.WebRequest>. **WebRequest** отправит заголовки запроса на сервер, после чего можно отправлять данные в сетевой ресурс, вызывая метод <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> или <xref:System.IO.Stream.Write%2A> возвращенного потока. Некоторые протоколы, такие как HTTP, могут требовать задания определенных свойств протокола перед отправкой данных. В приведенном ниже примере кода показано, как задать свойства протокола HTTP для отправки данных. Предполагается, что переменная `sendData` содержит отправляемые данные, а в переменной `sendLength` указывается число передаваемых байтов.  
  
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
  
 Для получения данных из сети вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A> класса <xref:System.Net.WebResponse>. После этого можно считывать данные из сетевого ресурса, вызывая метод <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> или <xref:System.IO.Stream.Read%2A> возвращенного потока.  
  
 При использовании потоков из сетевых ресурсов следует учитывать указанные ниже моменты.  
  
- Свойство **CanSeek** всегда возвращает значение **false**, так как класс **NetworkStream** не может изменять позицию в потоке. Методы **Seek** и **Position** создают исключение **NotSupportedException**.  
  
- При использовании классов **WebRequest** и **WebResponse** экземпляры потока, создаваемые путем вызова метода **GetResponseStream**, доступны только для чтения, а экземпляры, создаваемые путем вызова метода **GetRequestStream**, доступны только для записи.  
  
- Чтобы упростить кодирование, используйте класс <xref:System.IO.StreamReader>. В приведенном ниже примере кода **StreamReader** используется для чтения потока в кодировке ASCII из объекта **WebResponse** (создание запроса в примере не показано).  
  
- Вызов метода **GetResponse** может быть блокирован, если сетевые ресурсы недоступны. Вместо этого можно использовать асинхронный запрос с помощью методов <xref:System.Net.WebRequest.BeginGetResponse%2A> и <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
- Вызов метода **GetRequestStream** может быть заблокирован во время установления соединения с сервером. Вместо этого можно использовать асинхронный запрос потока с помощью методов <xref:System.Net.WebRequest.BeginGetRequestStream%2A> и <xref:System.Net.WebRequest.EndGetRequestStream%2A>.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Практическое руководство. Запрос данных с помощью класса WebRequest](how-to-request-data-using-the-webrequest-class.md)
- [Запрос данных](requesting-data.md)
