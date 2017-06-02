---
title: "Практическое руководство. Отправка данных с помощью класса WebRequest | Microsoft Docs"
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
  - "класс WebRequest, отправка данных в узел"
  - "Отправка данных в узел с помощью класса WebRequest"
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Практическое руководство. Отправка данных с помощью класса WebRequest
Следующая процедура описывает шаги, используемые для отправки данных на сервер.  Эта процедура обычно используется для отправки данных на страницу.  
  
### Отправлять данные в хосту\-серверу  
  
1.  Создайте экземпляр <xref:System.Net.WebRequest> путем вызова <xref:System.Net.WebRequest.Create%2A> с uri ресурса, который принимает данные, например, скрипт или страницы ASP.NET.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
  
    ```  
  
    > [!NOTE]
    >  Платформа .NET Framework предоставляет классы, производные от протокол\- определенной **WebRequest** и **WebResponse** для универсальных кодов ресурса \(uri\), начинающиеся с "http: ", "HTTPs:'' ". " и "файл: ".  Для доступа к ресурсам с использованием других протоколов, необходимо реализовать определенный протокол\- классы, производные от **WebRequest** и **WebResponse**.  Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Установите все значения свойств, которые необходимы в **WebRequest**.  Например, чтобы включить проверку подлинности, установите свойство **Учетные данные** к экземпляру класса <xref:System.Net.NetworkCredential>.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
  
    ```  
  
     В большинстве случаев достаточно сам экземпляр **WebRequest** отправлять данные.  Однако при необходимости настроить свойства для конкретного протокол\-, необходимо привести к типу протокол\- **WebRequest** XML\-структуру.  Например, чтобы получить доступ к свойствам определенного Http\- <xref:System.Net.HttpWebRequest> приведение **WebRequest** к ссылке **HttpWebRequest** .  В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A> Http\- в XML\-структуру.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Определите метод протокола, который разрешает данных, отправляемых с запросом, например метод **ОТПРАВИТЬ** HTTP.  
  
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
  
5.  Установите свойство **ContentType** соответствующее значение.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Получает поток, содержащий данные запроса путем вызова метода <xref:System.Net.WebRequest.GetRequestStream%2A>.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Запишите данные в объект <xref:System.IO.Stream>, возвращенным данным методом.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Закройте поток запроса путем вызова метода **Stream.Close**.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Отправьте запрос с сервером путем вызова <xref:System.Net.WebRequest.GetResponse%2A>.  Этот метод возвращает объект, содержащий ответ сервера.  Тип возвращаемого объекта <xref:System.Net.WebResponse> определяется схемой универсального кода ресурса \(uri\) запроса.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  После завершения работы с объектом <xref:System.Net.WebResponse>, необходимо закрыть его путем вызова метода <xref:System.Net.WebResponse.Close%2A>.  Кроме того, если поток ответа, полученные из объекта ответа, можно закрыть поток путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=fullName>.  Если не закрыть ответ или поток, то приложение может производить из подключений к серверу и оказаться неспособным обработки дополнительных запросов.  
  
10. Можно получить доступ к свойствам **WebResponse** или привести **WebResponse** к экземпляру протокол\- определенной для считывания свойства протокол\- в XML\-структуру.  Например, чтобы получить доступ к свойствам определенного Http\- <xref:System.Net.HttpWebResponse> приведение **WebResponse** к ссылке **HttpWebResponse**.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Получить поток, содержащий данные ответа для отправки сервером, вызывает метод <xref:System.Net.WebResponse.GetResponseStream%2A>**WebResponse**.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. После считывания данных из ответа, необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**.  Не нужно вызывать метод **Закрыть** на обоих поток ответа, и **WebResponse**, но это не вредн.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
  
    ```  
  
## Пример  
  
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
  
## См. также  
 [Создание интернет\-запросов](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)   
 [Практическое руководство. Запрос данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)