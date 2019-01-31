---
title: Как выполнить Отправка данных с помощью класса WebRequest
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: dac372ce4f9da99b91b6f8d140d69ce9f1238f30
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562908"
---
# <a name="how-to-send-data-using-the-webrequest-class"></a>Как выполнить Отправка данных с помощью класса WebRequest
В следующей процедуре описаны действия, используемые для отправки данных на сервер. Эта процедура обычно используется для отправки данных на веб-страницу.  
  
### <a name="to-send-data-to-a-host-server"></a>Отправка данных на сервер узла  
  
1.  Создайте экземпляр <xref:System.Net.WebRequest>, вызвав метод <xref:System.Net.WebRequest.Create%2A> с URI ресурса, который принимает данные, например сценария или страницы ASP.NET.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**, для URI, которые начинаются с "http:", "https:'', "ftp:" и "file:". Чтобы получить доступ к ресурсам с использованием других протоколов, необходимо реализовать связанные с определенным протоколом классы, производные от **WebRequest** и **WebResponse**. Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Укажите все необходимые значения свойств в объекте **WebRequest**. Например, чтобы включить проверку подлинности, установите для свойства **Credentials** значение экземпляра класса <xref:System.Net.NetworkCredential>.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     В большинстве случаев для отправки данных достаточно самого экземпляра класса **WebRequest**. Однако если необходимо задать связанные с определенным протоколом свойства, следует привести **WebRequest** к типу, связанному с определенным протоколом. Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebRequest>, приведите **WebRequest** к ссылке **HttpWebRequest**. В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A>, связанное с протоколом HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Укажите метод протокола, который разрешает отправлять данные с запросом, например метод **POST** HTTP.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Установите свойство **ContentLength**.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Укажите необходимое значение для свойства **ContentType**.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Получите поток, который содержит данные запроса, вызвав метод <xref:System.Net.WebRequest.GetRequestStream%2A>.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Запишите данные в объект <xref:System.IO.Stream>, возвращенный этим методом.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Закройте поток запроса, вызвав метод **Stream.Close**.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Отправьте запрос на сервер, вызвав метод <xref:System.Net.WebRequest.GetResponse%2A>. Этот метод возвращает объект, содержащий ответ сервера. Тип возвращенного объекта <xref:System.Net.WebResponse> определяется с помощью схемы URI запроса.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  После завершения работы с объектом <xref:System.Net.WebResponse> его необходимо закрыть путем вызова метода <xref:System.Net.WebResponse.Close%2A>. Кроме того, полученный поток ответа из объекта ответа можно закрыть путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно не сможет обрабатывать новые запросы.  
  
10. Можно получить доступ к свойствам объекта **WebResponse** или привести объект **WebResponse** к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола. Например, чтобы получить доступ к свойствам, определенным для протокола HTTP, для <xref:System.Net.HttpWebResponse>, приведите **WebRequest** к ссылке **HttpWebRequest**.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Чтобы получить поток, содержащий данные ответа, отправленные сервером, вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A> объекта **WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. После считывания данных из ответа необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**. Вызывать метод **Close** как для потока ответа, так и для объекта **WebResponse** необязательно, но ничто не мешает это сделать.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также
- [Создание интернет-запросов](../../../docs/framework/network-programming/creating-internet-requests.md)
- [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)
- [Практическое руководство. Запрос данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
