---
title: Запрос данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sending data
- WebRequest class, sending and receiving data
- requesting data from Internet, about requesting data
- WebClient class, sending and receiving data
- network, requesting data
- receiving data
- sending data, about sending data
- response to Internet request, about responding to Internet requests
- data requests
- receiving data, about receiving data
- Internet, requesting data
ms.assetid: df6f1e1d-6f2a-45dd-8141-4a85c3dafe1d
ms.openlocfilehash: 1f367caf7656a83597b6262a5746686df15d33b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047318"
---
# <a name="requesting-data"></a>Запрос данных
Для разработки современных интернет-приложений, выполняющихся в распределенной операционной среде, требуется простой и эффективный способ извлечения данных из ресурсов любого типа. Благодаря подключаемым протоколам можно разрабатывать приложения, использующие единый интерфейс для извлечения данных из нескольких интернет-протоколов.  
  
## <a name="uploading-and-downloading-data-from-an-internet-server"></a>Загрузка и скачивание данных с интернет-сервера  
 Для реализации простых операций запроса и ответа класс <xref:System.Net.WebClient> предоставляет простейший способ загрузки данных на интернет-сервер или скачивания с него. В классе **WebClient** представлены методы для скачивания и загрузки файлов, отправки и получения потоков, а также отправки буфера данных на сервер и получения ответа от него. Класс **WebClient** использует классы <xref:System.Net.WebRequest> и <xref:System.Net.WebResponse> для установления фактических подключений к интернет-ресурсу, что позволяет использовать любой зарегистрированный подключаемый протокол.  
  
 Клиентские приложения, которые выполняют более сложные транзакции, используют для запроса данных с серверов класс **WebRequest** и его потомки. Класс **WebRequest** инкапсулирует сведения о подключении к серверу, отправке запроса и получении ответа. **WebRequest** — это абстрактный класс, в котором определяется набор свойств и методов, доступных всем приложениям, использующим подключаемые протоколы. Потомки класса **WebRequest**, такие как <xref:System.Net.HttpWebRequest>, реализуют свойства и методы, определенные в **WebRequest**, в соответствии с особенностями базового протокола.  
  
 Класс **WebRequest** создает экземпляры потомков **WebRequest** для определенных протоколов, используя значение URI, которое передано в его метод <xref:System.Net.WebRequest.Create%2A> и определяет конкретный создаваемый экземпляр производного класса. Приложения указывают, какой потомок класса **WebRequest** необходимо использовать для обработки запроса, регистрируя конструктор такого потомка с помощью метода <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>.  
  
 Запрос к интернет-ресурсу выполняется посредством вызова метода <xref:System.Net.WebRequest.GetResponse%2A> для **WebRequest**. Метод **GetResponse** создает запрос для определенного протокола на основании свойств **WebRequest**, устанавливает подключение TCP или UDP к сокету сервера и отправляет запрос. Для запросов, которые отправляют данные на сервер, таких как HTTP-запрос **Post** или FTP-запрос **Put**, метод <xref:System.Net.WebRequest.GetRequestStream%2A?displayProperty=nameWithType> предоставляет сетевой поток для отправки данных.  
  
 Метод **GetResponse** возвращает **WebResponse** для определенного протокола, соответствующий **WebRequest.**  
  
 **WebResponse** — это также абстрактный класс, в котором определяются свойства и методы, доступные всем приложениям, использующим подключаемые протоколы. Потомки класса **WebResponse** реализуют эти свойства и методы для соответствующих базовых протоколов. Например, класс <xref:System.Net.HttpWebResponse> реализует класс **WebResponse** для протокола HTTP.  
  
 Возвращаемые сервером данные предоставляются приложению в потоке, который возвращается методом <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>. Этот поток используется так же, как и любые другие, что показано в следующем примере.  
  
```csharp  
StreamReader sr =  
   new StreamReader(resp.GetResponseStream(), Encoding.ASCII);  
```  
  
```vb  
Dim sr As StreamReader  
sr = New StreamReader(resp.GetResponseStream(), Encoding.ASCII)  
```  
  
## <a name="see-also"></a>См. также раздел

- [Сетевое программирование в .NET Framework](index.md)
- [Практическое руководство. Запрос веб-страницы и получение результатов в виде потока](how-to-request-a-web-page-and-retrieve-the-results-as-a-stream.md)
- [Практическое руководство. Получение объекта WebResponse, соответствующего объекту WebRequest, для определенного протокола](how-to-retrieve-a-protocol-specific-webresponse-that-matches-a-webrequest.md)
