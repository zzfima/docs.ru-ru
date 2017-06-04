---
title: "Использование потоков в сети | Microsoft Docs"
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
  - "запрос данных из Интернета, потоки"
  - "Сеть"
  - "ответ на интернет-запрос, потоки"
  - "сетевые ресурсы, возможности потоков"
  - "получение данных, возможности потоков"
  - "Сетевые ресурсы"
  - "отправка данных, возможности потоков"
  - "скачивание интернет-ресурсов, потоки"
  - "потоки, возможности"
  - "Интернет, потоки"
  - "потоки"
ms.assetid: 02b05fba-7235-45ce-94e5-060436ee0875
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# Использование потоков в сети
Сетевые ресурсы представлены в платформе .NET Framework, как потоки.  Путем обработки потоков родово платформа .NET Framework предлагает следующие возможности:  
  
-   Распространенным способом отправлять и получать данные в интернете.  Все действия фактическое содержимое файла — HTML, XML или что\-нибудь еще — приложение будет использовать <xref:System.IO.Stream.Write%2A?displayProperty=fullName> и <xref:System.IO.Stream.Read%2A?displayProperty=fullName> отправлять и получать данные.  
  
-   Совместимость с потоками с помощью платформы .NET Framework.  Потоки используются во всем платформы .NET Framework, которая имеет богатую инфраструктуру для обработки их.  Например, можно изменить приложение, которое считывает XML\-данные из <xref:System.IO.FileStream> для чтения данных из <xref:System.Net.Sockets.NetworkStream> а не изменять только несколько строк кода, которые инициализируют поток.  Основные различия между классом **NetworkStream** и другими потоками, что **NetworkStream** не seekable, свойство <xref:System.Net.Sockets.NetworkStream.CanSeek%2A> всегда возвращают **false** и методы <xref:System.Net.Sockets.NetworkStream.Seek%2A> и <xref:System.Net.Sockets.NetworkStream.Position%2A> вызывают <xref:System.NotSupportedException>.  
  
-   Обработка данных при поступлении.  Потоки обеспечивает доступ к данным по мере того, как они поступают от сети, а не применение приложение ожидает полный набор данных, который требуется загрузить.  
  
 Пространство имен <xref:System.Net.Sockets> содержит класс **NetworkStream**, реализующий класс <xref:System.IO.Stream> специально для использования с сетевыми ресурсами.  Классы в пространстве имен <xref:System.Net.Sockets> используют класс **NetworkStream** для представления потоки.  
  
 Отправлять данные в поток, возвращенный сети с помощью вызова <xref:System.Net.WebRequest.GetRequestStream%2A> на локальном <xref:System.Net.WebRequest>.  **WebRequest** отправляет заголовки запроса к серверу; затем можно отправлять данные к сетевому ресурсу, вызвав <xref:System.IO.Stream.BeginWrite%2A>, <xref:System.IO.Stream.EndWrite%2A> или метод <xref:System.IO.Stream.Write%2A> в возвращаемом потоке.  Для некоторых протоколов, таких как HTTP, могут потребовать устанавливающих свойства протокол\- определенной, прежде чем отправлять данные.  В следующем примере кода показано, как задать свойства Http\- определенной для отправки данных.  Он предполагает, что переменная `sendData` содержащий данные отправлять и что переменная `sendLength` число байтов данных, чтобы отправить.  
  
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
  
 Получить данные из сети, то вызов <xref:System.Net.WebResponse.GetResponseStream%2A> на локальном <xref:System.Net.WebResponse>.  После этого можно прочитать данные из сетевого ресурса путем вызова <xref:System.IO.Stream.BeginRead%2A>, <xref:System.IO.Stream.EndRead%2A> или метод <xref:System.IO.Stream.Read%2A> в возвращаемом потоке.  
  
 При использовании потоков из сетевых ресурсов, имейте в виду следующее:  
  
-   Свойство **CanSeek** всегда возвращает **false** поскольку класс не может **NetworkStream** смена позицию в потоке.  Методы **Искать** и **Положение** вызывают **NotSupportedException**.  
  
-   При использовании **WebRequest** и **WebResponse**, экземпляры потока, созданные путем вызова **GetResponseStream** только для чтения и экземпляры потока, созданные путем вызова **GetRequestStream** доступный только на запись.  
  
-   Используйте класс <xref:System.IO.StreamReader> для кодирования.  В следующем примере кода используется **StreamReader** для чтения ASCII\- закодированный поток из **WebResponse** \(пример не отображает создать запрос\).  
  
-   Вызов **GetResponse** может отключить, если сетевые ресурсы недоступны.  Следует рассмотреть использование асинхронного запроса с методами <xref:System.Net.WebRequest.BeginGetResponse%2A> и <xref:System.Net.WebRequest.EndGetResponse%2A>.  
  
-   Вызов **GetRequestStream** может блокировать при создано подключение к серверу.  Следует рассмотреть использование асинхронного запроса для потока с методами <xref:System.Net.WebRequest.BeginGetRequestStream%2A> и <xref:System.Net.WebRequest.EndGetRequestStream%2A>.  
  
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
  
## См. также  
 [Практическое руководство. Запрос данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)   
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)