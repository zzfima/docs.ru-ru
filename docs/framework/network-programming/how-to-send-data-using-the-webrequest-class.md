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
# <a name="how-to-send-data-by-using-the-webrequest-class"></a>Практическое руководство. Отправка данных с помощью класса WebRequest

В следующей процедуре описаны действия для отправки данных на сервер. Эта процедура обычно используется для отправки данных на веб-страницу.

## <a name="to-send-data-to-a-host-server"></a>Отправка данных на сервер узла

1. Создайте экземпляр <xref:System.Net.WebRequest>, вызвав метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> с URI ресурса, например сценария или страницы ASP.NET, который принимает данные. Пример:

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > Платформа .NET Framework предоставляет связанные с определенным протоколом классы, производные от классов <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse>, для URI, которые начинаются с *http:* , *https:* , *ftp:* и *file:* .

    Если нужно задать или считать связанные с определенным протоколом свойства, следует привести объект <xref:System.Net.WebRequest> или <xref:System.Net.WebResponse> к типу объекта, связанному с определенным протоколом. Дополнительные сведения см. в разделе [Программирование подключаемых протоколов](programming-pluggable-protocols.md).

2. Укажите все необходимые значения свойств в объекте `WebRequest`. Например, чтобы включить проверку подлинности, установите для свойства <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> значение экземпляра класса <xref:System.Net.NetworkCredential>:

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. Укажите метод протокола, который разрешает отправлять данные с запросом, например метод `POST` HTTP:

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. Задайте для свойства <xref:System.Web.HttpRequest.ContentLength> число байт, включаемых в запрос. Пример:

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. Присвойте свойству <xref:System.Web.HttpRequest.ContentType> соответствующее значение. Пример:

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. Получите поток, который содержит данные запроса, вызвав метод <xref:System.Net.WebRequest.GetRequestStream%2A>. Пример:

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. Запишите данные в объект <xref:System.IO.Stream>, возвращенный методом `GetRequestStream`. Пример:

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. Закройте поток запроса, вызвав метод <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Пример:

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. Отправьте запрос на сервер, вызвав метод <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>. Этот метод возвращает объект, содержащий ответ сервера. Тип возвращенного объекта `WebResponse` определяется с помощью схемы URI запроса. Пример:

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. Вы можете получить доступ к свойствам объекта `WebResponse` или привести этот объект к связанному с определенным протоколом экземпляру для считывания свойств для определенного протокола.

    Например, чтобы получить доступ к свойствам, связанным с протоколом HTTP, для <xref:System.Net.HttpWebResponse>, приведите объект `WebResponse` к ссылке <xref:System.Net.HttpWebResponse>. В следующем примере кода показано, как отобразить свойство <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, связанное с протоколом HTTP, которое было отправлено в ответе:

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. Чтобы получить поток, содержащий данные ответа, отправленные сервером, вызовите метод <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> объекта `WebResponse`. Пример:

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. После считывания данных из объекта ответа закройте его с помощью метода <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> или закройте поток ответа с помощью метода <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>. Если не закрыть ответ или поток, у приложения могут закончиться подключения к серверу и оно может оказаться неспособным обрабатывать новые запросы. Так как при закрытии ответа метод `WebResponse.Close` вызывает `Stream.Close`, вызывать `Close` для объектов как потока, так и ответа не требуется (при этом выполнение такой операции не приведет к негативным последствиям). Пример:

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a>Пример

В следующем примере показана отправка данных на веб-сервер и считывание данных в ответе:

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a>См. также

- [Создание интернет-запросов](creating-internet-requests.md)
- [Использование потоков в сети](using-streams-on-the-network.md)
- [Доступ к Интернету через прокси-сервер](accessing-the-internet-through-a-proxy.md)
- [Запрос данных](requesting-data.md)
- [Практическое руководство. Запрос данных с помощью класса WebRequest](how-to-request-data-using-the-webrequest-class.md)
