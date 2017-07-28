---
title: "Практическое руководство. Запрос данных с помощью класса WebRequest | Microsoft Docs"
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
  - "загрузка интернет-ресурсов, действия"
  - "запрос данных из Интернета, действия"
  - "Класс WebRequest, получение данных"
  - "получение данных, использование класса WebRequest"
  - "Интернет, запрос данных"
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Практическое руководство. Запрос данных с помощью класса WebRequest
Следующая процедура описывает шаги, используемые для запроса ресурс из сервера, например страницы или файла.  Ресурс должен быть задан универсальный код ресурса \(uri\).  
  
### Запросить данные из хоста\-сервера  
  
1.  Создайте экземпляр <xref:System.Net.WebRequest> путем вызова <xref:System.Net.WebRequest.Create%2A> с uri ресурса.  
  
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
  
     В большинстве случаев класс **WebRequest** достаточен для получения данных.  Однако при необходимости настроить свойства для конкретного протокол\-, необходимо привести к типу протокол\- **WebRequest** XML\-структуру.  Например, чтобы получить доступ к свойствам определенного Http\- <xref:System.Net.HttpWebRequest> приведение **WebRequest** к ссылке **HttpWebRequest**.  В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A> Http\- в XML\-структуру.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
  
    ```  
  
3.  Отправить запрос на сервер, вызов <xref:System.Net.HttpWebRequest.GetResponse%2A>.  Фактический тип возвращаемого объекта **WebResponse** определяется схемой универсального кода ресурса \(uri\) типа.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  После завершения работы с объектом <xref:System.Net.WebResponse>, необходимо закрыть его путем вызова метода <xref:System.Net.WebResponse.Close%2A>.  Кроме того, если поток ответа, полученные из объекта ответа, можно закрыть поток путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=fullName>.  Если не закрыть или ответ или поток, то приложение может производить из подключений к серверу и оказаться неспособным обработки дополнительных запросов.  
  
4.  Можно получить доступ к свойствам **WebResponse** или привести **WebResponse** к экземпляру протокол\- определенной для считывания свойства протокол\- в XML\-структуру.  Например, чтобы получить доступ к свойствам определенного Http\- <xref:System.Net.HttpWebResponse> приведение **WebResponse** к ссылке **HttpWebResponse**.  В следующем примере кода показано, как отобразить информацию о состоянии, отправленные с ответом.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Получить поток, содержащий данные ответа для отправки сервером, используется метод <xref:System.Net.HttpWebResponse.GetResponseStream%2A>**WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream ();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
  
    ```  
  
6.  После считывания данных из ответа, необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**.  Не нужно вызывать метод **Закрыть** на обоих поток ответа, и **WebResponse**, но это не вредн.  Вызовы **Stream.Close** **WebResponse.Close** закрыть ответ.  
  
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
  
## См. также  
 [Создание интернет\-запросов](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Доступ к Интернету через прокси\-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)   
 [Практическое руководство. Отправка данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)