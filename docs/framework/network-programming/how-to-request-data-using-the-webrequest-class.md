---
title: Практическое руководство. Запрос данных с помощью класса WebRequest
ms.date: 03/30/2017
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
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e02ad4772d3ba84a2735a2e146a9979862d75989
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397719"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a>Практическое руководство. Запрос данных с помощью класса WebRequest
Следующая процедура описывает шаги, используемые для запроса ресурсов с сервера, например веб-страницы или файла. Ресурс должен быть определен универсальным кодом ресурса (URI).  
  
### <a name="to-request-data-from-a-host-server"></a>Запрос данных с сервера узла  
  
1.  Создайте экземпляр <xref:System.Net.WebRequest> путем вызова <xref:System.Net.WebRequest.Create%2A> с URI ресурса.  
  
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
  
     В большинстве случаев класса **WebRequest** достаточно для получения данных. Однако если необходимо задать связанные с определенным протоколом свойства, следует привести **WebRequest** к типу, связанному с определенным протоколом. Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebRequest>, приведите **WebRequest** к ссылке **HttpWebRequest**. В следующем примере кода показано, как задать свойство <xref:System.Net.HttpWebRequest.UserAgent%2A>, связанное с протоколом HTTP.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Чтобы отправить запрос на сервер, вызовите <xref:System.Net.HttpWebRequest.GetResponse%2A>. Фактический тип возвращаемого объекта **WebResponse** определяется схемой запрошенного URI.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  После завершения работы с объектом <xref:System.Net.WebResponse> его необходимо закрыть путем вызова метода <xref:System.Net.WebResponse.Close%2A>. Кроме того, полученный поток ответа из объекта ответа можно закрыть путем вызова метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно может оказаться неспособным обрабатывать новые запросы.  
  
4.  Можно получить доступ к свойствам объекта **WebResponse** или привести объект **WebResponse** к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола. Например, чтобы получить доступ к свойствам, определенным для протокола HTTP, для <xref:System.Net.HttpWebResponse>, приведите **WebRequest** к ссылке **HttpWebRequest**. В следующем примере кода показано, как отобразить сведения о состоянии, отправленные в ответе.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Чтобы получить поток, содержащий данные ответа, отправленные сервером, используйте метод <xref:System.Net.HttpWebResponse.GetResponseStream%2A> объекта **WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  После считывания данных из ответа необходимо закрыть поток ответа с помощью метода **Stream.Close** или закрыть ответ с помощью метода **WebResponse.Close**. Вызывать метод **Close** как для потока ответа, так и для объекта **WebResponse** необязательно, но ничто не мешает это сделать. **WebResponse.Close** вызывает метод **Stream.Close** при закрытии ответа.  
  
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
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
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
  
## <a name="see-also"></a>См. также  
 [Создание интернет-запросов](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [Использование потоков в сети](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Доступ к Интернету через прокси-сервер](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Запрос данных](../../../docs/framework/network-programming/requesting-data.md)  
 [Практическое руководство. Отправка данных с помощью класса WebRequest](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
