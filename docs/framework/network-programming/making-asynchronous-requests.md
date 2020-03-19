---
title: Выполнение асинхронных запросов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, asynchronous access
- Networking
- asynchronous requests, Internet resources
- Network Resources
- WebRequest class, asynchronous access
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
ms.openlocfilehash: a49233596bafebd4f07372e59f29ea77afb21458
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180724"
---
# <a name="making-asynchronous-requests"></a>Выполнение асинхронных запросов
В классах <xref:System.Net> используется стандартная асинхронная модель программирования .NET Framework для асинхронного доступа к ресурсам в Интернете. Методы <xref:System.Net.WebRequest.BeginGetResponse%2A> и <xref:System.Net.WebRequest.EndGetResponse%2A> класса <xref:System.Net.WebRequest> запускают и завершают асинхронные запросы к интернет-ресурсу.  
  
> [!NOTE]
> Использование синхронных вызовов в асинхронных методах обратного вызова может привести к существенному снижению производительности. В запросах к интернет-ресурсам, которые выполняются с помощью класса **WebRequest** и его потомков, необходимо использовать <xref:System.IO.Stream.BeginRead%2A?displayProperty=nameWithType> для считывания потока, возвращенного методом <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>.  
  
 В следующем примере кода показано использование асинхронных вызовов с классом **WebRequest**. В примере показана консольная программа, которая принимает URI из командной строки, запрашивает ресурс по указанному URI и выводит полученные из Интернета данные в консоль.  
  
 В программе определены два собственных класса. Класс **RequestState** передает данные между асинхронными вызовами, класс **ClientGetAsync** реализует асинхронный запрос к интернет-ресурсу.  
  
 Класс **RequestState** сохраняет состояние запроса между вызовами асинхронных методов, которые обслуживают запрос. Этот класс включает экземпляры классов **WebRequest** и <xref:System.IO.Stream>, содержащие текущий запрос к ресурсу и поток, полученный в ответе, буфер с данными от интернет-ресурса и объект <xref:System.Text.StringBuilder>, содержащий полный ответ. Объект **RequestState** передается в качестве параметра *state* при регистрации метода <xref:System.AsyncCallback> с помощью вызова **WebRequest.BeginGetResponse**.  
  
 Класс **ClientGetAsync** реализует асинхронный запрос к интернет-ресурсу и записывает полученный ответ в консоль. Он содержит методы и свойства, указанные в следующем списке.  
  
- Свойство `allDone` содержит экземпляр класса <xref:System.Threading.ManualResetEvent>, который уведомляет о завершении запроса.  
  
- Метод `Main()` считывает командную строку и отправляет запрос для указанного интернет-ресурса. Он создает **WebRequest** `wreq` и **RequestState** `rs`, вызывает метод **BeginGetResponse**, который начинает обрабатывать запрос, а затем вызывает метод `allDone.WaitOne()`, чтобы приложение не завершало работу до тех пор, пока обратный вызов не будет завершен. После получения ответа от интернет-ресурса `Main()` записывает его в консоль, и работа приложения завершается.  
  
- Метод `showusage()` выводит пример команды в консоль. Он вызывается методом `Main()`, если в командной строке не был указан URI.  
  
- Метод `RespCallBack()` реализует асинхронный метод обратного вызова для запроса к интернет-ресурсу. Он создает экземпляр класса **WebResponse**, содержащий ответ от интернет-ресурса, получает поток ответа, а затем начинает асинхронное считывание данных из потока.  
  
- Метод `ReadCallBack()` реализует асинхронный метод обратного вызова для чтения потока ответа. Этот метод передает данные, полученные от интернет-ресурса, в свойство **ResponseData** экземпляра класса **RequestState**, а затем запускает другую операцию асинхронного считывания потока ответа, и так до тех пор, пока все данные не будут прочитаны. После считывания всех данных метод `ReadCallBack()` закрывает поток ответа и вызывает метод `allDone.Set()`, чтобы определить, что в объекте **ResponseData** представлен весь ответ.  
  
    > [!NOTE]
    > Очень важно закрывать все сетевые потоки. Если не закрывать запросы и потоки ответов, у приложения могут закончиться подключения к серверу и оно не сможет обрабатывать новые запросы.  
  
```csharp  
using System;  
using System.Net;  
using System.Threading;  
using System.Text;  
using System.IO;  
  
// The RequestState class passes data across async calls.  
public class RequestState  
{  
   const int BufferSize = 1024;  
   public StringBuilder RequestData;  
   public byte[] BufferRead;  
   public WebRequest Request;  
   public Stream ResponseStream;  
   // Create Decoder for appropriate enconding type.  
   public Decoder StreamDecode = Encoding.UTF8.GetDecoder();  
  
   public RequestState()  
   {  
      BufferRead = new byte[BufferSize];  
      RequestData = new StringBuilder(String.Empty);  
      Request = null;  
      ResponseStream = null;  
   }
}  
  
// ClientGetAsync issues the async request.  
class ClientGetAsync
{  
   public static ManualResetEvent allDone = new ManualResetEvent(false);  
   const int BUFFER_SIZE = 1024;  
  
   public static void Main(string[] args)
   {  
      if (args.Length < 1)
      {  
         showusage();  
         return;  
      }  
  
      // Get the URI from the command line.  
      Uri httpSite = new Uri(args[0]);  
  
      // Create the request object.  
      WebRequest wreq = WebRequest.Create(httpSite);  
  
      // Create the state object.  
      RequestState rs = new RequestState();  
  
      // Put the request into the state object so it can be passed around.  
      rs.Request = wreq;  
  
      // Issue the async request.  
      IAsyncResult r = (IAsyncResult) wreq.BeginGetResponse(  
         new AsyncCallback(RespCallback), rs);  
  
      // Wait until the ManualResetEvent is set so that the application
      // does not exit until after the callback is called.  
      allDone.WaitOne();  
  
      Console.WriteLine(rs.RequestData.ToString());  
   }  
  
   public static void showusage() {  
      Console.WriteLine("Attempts to GET a URL");  
      Console.WriteLine("\r\nUsage:");  
      Console.WriteLine("   ClientGetAsync URL");  
      Console.WriteLine("   Example:");  
      Console.WriteLine("      ClientGetAsync http://www.contoso.com/");  
   }  
  
   private static void RespCallback(IAsyncResult ar)  
   {  
      // Get the RequestState object from the async result.  
      RequestState rs = (RequestState) ar.AsyncState;  
  
      // Get the WebRequest from RequestState.  
      WebRequest req = rs.Request;  
  
      // Call EndGetResponse, which produces the WebResponse object  
      //  that came from the request issued above.  
      WebResponse resp = req.EndGetResponse(ar);
  
      //  Start reading data from the response stream.  
      Stream ResponseStream = resp.GetResponseStream();  
  
      // Store the response stream in RequestState to read
      // the stream asynchronously.  
      rs.ResponseStream = ResponseStream;  
  
      //  Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead  
      IAsyncResult iarRead = ResponseStream.BeginRead(rs.BufferRead, 0,
         BUFFER_SIZE, new AsyncCallback(ReadCallBack), rs);
   }  
  
   private static void ReadCallBack(IAsyncResult asyncResult)  
   {  
      // Get the RequestState object from AsyncResult.  
      RequestState rs = (RequestState)asyncResult.AsyncState;  
  
      // Retrieve the ResponseStream that was set in RespCallback.
      Stream responseStream = rs.ResponseStream;  
  
      // Read rs.BufferRead to verify that it contains data.
      int read = responseStream.EndRead( asyncResult );  
      if (read > 0)  
      {  
         // Prepare a Char array buffer for converting to Unicode.  
         Char[] charBuffer = new Char[BUFFER_SIZE];  
  
         // Convert byte stream to Char array and then to String.  
         // len contains the number of characters converted to Unicode.  
      int len =
         rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0);  
  
         String str = new String(charBuffer, 0, len);  
  
         // Append the recently read data to the RequestData stringbuilder  
         // object contained in RequestState.  
         rs.RequestData.Append(  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read));
  
         // Continue reading data until
         // responseStream.EndRead returns –1.  
         IAsyncResult ar = responseStream.BeginRead(
            rs.BufferRead, 0, BUFFER_SIZE,
            new AsyncCallback(ReadCallBack), rs);  
      }  
      else  
      {  
         if(rs.RequestData.Length>0)  
         {  
            //  Display data to the console.  
            string strContent;
            strContent = rs.RequestData.ToString();  
         }  
         // Close down the response stream.  
         responseStream.Close();
         // Set the ManualResetEvent so the main thread can exit.  
         allDone.Set();
      }  
      return;  
   }
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Threading  
Imports System.Text  
Imports System.IO  
  
' The RequestState class passes data across async calls.  
Public Class RequestState  
  
      Public RequestData As New StringBuilder("")  
      Public BufferRead(1024) As Byte  
      Public Request As HttpWebRequest  
      Public ResponseStream As Stream  
      ' Create Decoder for appropriate encoding type.  
      Public StreamDecode As Decoder = Encoding.UTF8.GetDecoder()  
  
      Public Sub New  
         Request = Nothing  
         ResponseStream = Nothing  
      End Sub  
End Class  
  
' ClientGetAsync issues the async request.  
Class ClientGetAsync  
   Shared allDone As New ManualResetEvent(False)  
      Const BUFFER_SIZE As Integer = 1024  
  
    Shared Sub Main()  
        Dim Args As String() = Environment.GetCommandLineArgs()  
  
        If Args.Length < 2 Then  
            ShowUsage()  
            Return  
        End If  
  
      ' Get the URI from the command line.  
        Dim HttpSite As Uri = New Uri(Args(1))  
  
      ' Create the request object.  
        Dim wreq As HttpWebRequest = _  
           CType(WebRequest.Create(HttpSite), HttpWebRequest)  
  
      ' Create the state object.  
      Dim rs As RequestState = New RequestState()  
  
      ' Put the request into the state so it can be passed around.  
      rs.Request = wreq  
  
      ' Issue the async request.  
        Dim r As IAsyncResult = _  
           CType(wreq.BeginGetResponse( _  
           New AsyncCallback(AddressOf RespCallback), rs), IAsyncResult)  
  
      ' Wait until the ManualResetEvent is set so that the application  
      ' does not exit until after the callback is called.  
        allDone.WaitOne()  
    End Sub  
  
    Shared Sub ShowUsage()  
        Console.WriteLine("Attempts to GET a URI")  
        Console.WriteLine()  
        Console.WriteLine("Usage:")  
        Console.WriteLine("ClientGetAsync URI")  
        Console.WriteLine("Examples:")  
        Console.WriteLine("ClientGetAsync http://www.contoso.com/")  
    End Sub  
  
    Shared Sub RespCallback(ar As IAsyncResult)  
       ' Get the RequestState object from the async result.  
       Dim rs As RequestState = CType(ar.AsyncState, RequestState)  
  
       ' Get the HttpWebRequest from RequestState.  
       Dim req As HttpWebRequest= rs.Request  
  
       ' Call EndGetResponse, which returns the HttpWebResponse object  
       ' that came from the request issued above.  
       Dim resp As HttpWebResponse = _  
           CType(req.EndGetResponse(ar), HttpWebResponse)  
  
       ' Start reading data from the response stream.  
       Dim ResponseStream As Stream = resp.GetResponseStream()  
  
       ' Store the reponse stream in RequestState to read  
       ' the stream asynchronously.  
       rs.ResponseStream = ResponseStream  
  
       ' Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead.  
       Dim iarRead As IAsyncResult = _  
          ResponseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
          New AsyncCallback(AddressOf ReadCallBack), rs)  
    End Sub  
  
   Shared Sub ReadCallBack(asyncResult As IAsyncResult)  
      ' Get the RequestState object from the AsyncResult.  
      Dim rs As RequestState = CType(asyncResult.AsyncState, RequestState)  
  
      ' Retrieve the ResponseStream that was set in RespCallback.  
      Dim responseStream As Stream = rs.ResponseStream  
  
      ' Read rs.BufferRead to verify that it contains data.  
      Dim read As Integer = responseStream.EndRead( asyncResult )  
      If read > 0 Then  
         ' Prepare a Char array buffer for converting to Unicode.  
         Dim charBuffer(1024) As Char  
  
         ' Convert byte stream to Char array and then String.  
         ' len contains the number of characters converted to Unicode.  
         Dim len As Integer = _  
           rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0)  
         Dim str As String = new String(charBuffer, 0, len)
  
         ' Append the recently read data to the RequestData stringbuilder
         ' object contained in RequestState.  
         rs.RequestData.Append( _  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read))  
  
         ' Continue reading data until responseStream.EndRead  
         ' returns –1.  
         Dim ar As IAsyncResult = _  
            responseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
            New AsyncCallback(AddressOf ReadCallBack), rs)  
      Else  
          If rs.RequestData.Length > 1 Then  
            ' Display data to the console.  
            Dim strContent As String  
            strContent = rs.RequestData.ToString()  
            Console.WriteLine(strContent)  
         End If  
  
         ' Close down the response stream.  
         responseStream.Close()  
  
         ' Set the ManualResetEvent so the main thread can exit.  
         allDone.Set()  
      End If  
  
      Return  
   End Sub  
End Class  
```  
  
## <a name="see-also"></a>См. также

- [Запрос данных](requesting-data.md)
