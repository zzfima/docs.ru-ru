---
title: Наследование от WebResponse
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, pluggable protocols
- protocol-specific request handler
- sending data, pluggable protocols
- pluggable protocols, class criteria
- Internet, pluggable protocols
- receiving data, pluggable protocols
- protocols, pluggable
ms.assetid: 9810c177-973e-43d7-823c-14960bd625ea
ms.openlocfilehash: 6bee864f8d24076d16f226c29d61801e856739d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "71048602"
---
# <a name="deriving-from-webrequest"></a>Наследование от WebResponse
<xref:System.Net.WebRequest> — это абстрактный базовый класс, который предоставляет базовые методы и свойства для создания обработчика запросов определенного протокола в соответствии с требованиями модели подключаемых протоколов .NET Framework. Приложения, использующие класс **WebRequest**, могут запрашивать данные с использованием любого поддерживаемого протокола, не указывая конкретный протокол.  
  
 Чтобы использовать класс определенного протокола в качестве подключаемого протокола, должны соблюдаться два условия: класс должен реализовывать интерфейс <xref:System.Net.IWebRequestCreate> и выполнять регистрацию с использованием метода <xref:System.Net.WebRequest.RegisterPrefix%2A?displayProperty=nameWithType>. Для предоставления подключаемого интерфейса класс должен переопределять все абстрактные методы и свойства класса **WebRequest**.  
  
 Экземпляры **WebRequest** предназначены для однократного использования. Чтобы выполнить другой запрос, необходимо создать новый экземпляр **WebRequest**. Класс **WebRequest** поддерживает интерфейс <xref:System.Runtime.Serialization.ISerializable>, с помощью которого разработчик может выполнить сериализацию шаблона **WebRequest**, а затем воссоздать шаблон для дополнительных запросов.  
  
## <a name="iwebrequest-create-method"></a>Метод IWebRequest Create  
 Метод <xref:System.Net.IWebRequestCreate.Create%2A> используется для инициализации нового экземпляра класса определенного протокола. При создании нового экземпляра **WebRequest** метод <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> сопоставляет запрашиваемый URI с префиксами URI, зарегистрированными с помощью метода **RegisterPrefix**. Метод **Create** соответствующего потомка класса определенного протокола должен возвращать инициализированный экземпляр потомка, который может выполнить стандартную операцию запроса-ответа для протокола, не изменяя при этом соответствующие протоколу поля.  
  
## <a name="connectiongroupname-property"></a>Свойство ConnectionGroupName  
 Свойство <xref:System.Net.WebRequest.ConnectionGroupName%2A> используется для присваивания имени группе подключений к ресурсу, чтобы выполнять несколько запросов с применением одного подключения. Чтобы реализовать совместное использование подключения, необходимо применить метод определенного протокола для опроса и присваивания подключений. Например, предоставленный класс <xref:System.Net.ServicePointManager> реализует совместное использование подключения для класса <xref:System.Net.HttpWebRequest>. Класс **ServicePointManager** создает <xref:System.Net.ServicePoint>, который предоставляет подключение к конкретному серверу для каждой группы подключений.  
  
## <a name="contentlength-property"></a>Свойство ContentLength  
 Свойство <xref:System.Net.WebRequest.ContentLength%2A> задает число байтов, которое будет передаваться на сервер при загрузке данных.  
  
 Как правило, свойство <xref:System.Net.WebRequest.Method%2A> передается, указывая на идущий процесс загрузки, а свойству **ContentLength** присваивается значение больше нуля.  
  
## <a name="contenttype-property"></a>Свойство ContentType  
 Свойство <xref:System.Net.WebRequest.ContentType%2A> предоставляет особые сведения, которые необходимы протоколу для отправки на сервер, чтобы идентифицировать тип отправляемого содержимого. Обычно это тип MIME загружаемых данных.  
  
## <a name="credentials-property"></a>Свойство Credentials  
 Свойство <xref:System.Net.WebRequest.Credentials%2A> содержит информацию, необходимую для проверки подлинности запроса к серверу. Необходимо указать сведения о процессе проверки подлинности для протокола. Класс <xref:System.Net.AuthenticationManager> обеспечивает проверку подлинности запросов и предоставляет маркер проверки подлинности. Класс, который предоставляет учетные данные, используемые протоколом, должен реализовывать интерфейс <xref:System.Net.ICredentials>.  
  
## <a name="headers-property"></a>Свойство Headers  
 Свойство <xref:System.Net.WebRequest.Headers%2A> содержит произвольную коллекцию пар "имя-значение" для метаданных, связанных с запросом. В свойство **Headers** можно включать любые метаданные для протокола, которые могут быть выражены в виде пар "имя-значение". Как правило, эти сведения необходимо передавать до вызова методов <xref:System.Net.WebRequest.GetRequestStream%2A> или <xref:System.Net.WebRequest.GetResponse%2A>. После выполнения запроса метаданные будут доступны только для чтения.  
  
 Чтобы использовать метаданные заголовка, применять свойство **Headers** необязательно. Относящиеся к протоколу метаданные могут предоставляться в виде свойств. Например, свойство <xref:System.Net.HttpWebRequest.UserAgent%2A?displayProperty=nameWithType> предоставляет заголовок HTTP **User-Agent**. Если метаданные заголовка предоставляются в виде свойства, необходимо запретить установку этого свойства с использованием свойства **Headers**.  
  
## <a name="method-property"></a>Свойство Method  
 Свойство <xref:System.Net.WebRequest.Method%2A> содержит команду или операцию, которую должен выполнить сервер при получении запроса. Значение свойства **Method** по умолчанию должно обеспечивать выполнение стандартной операции запроса-ответа без установки относящихся к протоколу свойств. Например, в качестве метода <xref:System.Net.HttpWebResponse.Method%2A> по умолчанию устанавливается GET, который запрашивает ресурс с веб-сервера и возвращает ответ.  
  
 Как правило, свойству **ContentLength** присваивается положительное значение, а свойство **Method** содержит команду или операцию, указывая на идущий процесс загрузки.  
  
## <a name="preauthenticate-property"></a>Свойство PreAuthenticate  
 Свойство <xref:System.Net.WebRequest.PreAuthenticate%2A> задается приложениями, указывая на то, что данные для проверки подлинности должны отправляться с первоначальным запросом, не дожидаясь встречного запроса проверки подлинности. Свойство **PreAuthenticate** учитывается только в том случае, если протокол поддерживает передачу учетных данных проверки подлинности вместе с первоначальным запросом.  
  
## <a name="proxy-property"></a>Свойство Proxy  
 Свойство <xref:System.Net.WebRequest.Proxy%2A> содержит интерфейс <xref:System.Net.IWebProxy>, который используется для доступа к запрашиваемому ресурсу. Свойство **Proxy** учитывается только в том случае, если протокол поддерживает запросы через прокси. Если этого требует протокол, необходимо задать прокси-сервер по умолчанию.  
  
 В некоторых средах, например, защищенных корпоративным брандмауэром, использование прокси-сервера протоколом может быть обязательным. В этом случае необходимо реализовать интерфейс **IWebProxy**, чтобы создать прокси-класс для работы с протоколом.  
  
## <a name="requesturi-property"></a>Свойство RequestUri  
 Свойство <xref:System.Net.WebRequest.RequestUri%2A> содержит URI, который был передан в метод **WebRequest.Create**. После создания экземпляра **WebRequest** это свойство будет доступно только для чтения и не может быть изменено. Если протокол поддерживает перенаправление, ответ может поступать от ресурса с другим URI. Если требуется предоставить доступ к URI, от которого поступил ответ, необходимо предоставить дополнительное свойство, содержащее этот URI.  
  
## <a name="timeout-property"></a>Свойство времени ожидания  
 Свойство <xref:System.Net.WebRequest.Timeout%2A> содержит продолжительность периода ожидания запроса в миллисекундах, по истечении которого возникает исключение. Свойство **Timeout** применяется только к синхронным запросам, выполняемым с помощью метода <xref:System.Net.WebRequest.GetResponse%2A>. Чтобы отменить ожидающий асинхронный запрос, следует использовать метод <xref:System.Net.WebRequest.Abort%2A>.  
  
 Свойство **Timeout** учитывается только в том случае, если в классе определенного протокола реализуется процесс управления временем ожидания.  
  
## <a name="abort-method"></a>Метод Abort  
 Метод <xref:System.Net.WebRequest.Abort%2A> отменяет ожидающий асинхронный запрос к серверу. Если после отмены запроса вызвать метод **GetResponse**, **BeginGetResponse**, **EndGetResponse**, **GetRequestStream**, **BeginGetRequestStream** или **EndGetRequestStream**, возникнет исключение <xref:System.Net.WebException>, а свойству <xref:System.Net.WebException.Status%2A> будет присвоено значение <xref:System.Net.WebExceptionStatus>.  
  
## <a name="begingetrequeststream-and-endgetrequeststream-methods"></a>Методы BeginGetRequestStream и EndGetRequestStream  
 Метод <xref:System.Net.WebRequest.BeginGetRequestStream%2A> начинает выполнение асинхронного запроса для потока, который используется для загрузки данных на сервер. Метод <xref:System.Net.WebRequest.EndGetRequestStream%2A> завершает асинхронный запрос и возвращает запрошенный поток. Эти методы реализуют метод **GetRequestStream** с использованием стандартной асинхронной модели .NET Framework.  
  
## <a name="begingetresponse-and-endgetresponse-methods"></a>Методы BeginGetResponse и EndGetResponse  
 Метод <xref:System.Net.WebRequest.BeginGetResponse%2A> начинает выполнение асинхронного запроса к серверу. Метод <xref:System.Net.WebRequest.EndGetResponse%2A> завершает выполнение асинхронного запроса и возвращает запрошенный ответ. Эти методы реализуют метод **GetResponse** с использованием стандартной асинхронной модели .NET Framework.  
  
## <a name="getrequeststream-method"></a>Метод GetRequestStream  
 Метод <xref:System.Net.WebRequest.GetRequestStream%2A> возвращает поток, который используется для записи данных на запрашиваемый сервер. Возвращаемый поток должен быть доступен только для записи и не должен осуществлять поиск. Это однонаправленный поток данных, предназначенный для записи на сервер. Этот поток возвращает значение false для свойств <xref:System.IO.Stream.CanRead%2A> или <xref:System.IO.Stream.CanSeek%2A> и значение true для свойства <xref:System.IO.Stream.CanWrite%2A>.  
  
 Метод **GetRequestStream** обычно открывает подключение к серверу и, прежде чем вернуть поток, отправляет данные заголовка, указывающие на то, что на сервер передаются данные. Поскольку метод **GetRequestStream** начинает выполнение запроса, свойства **Header** или **ContentLength**, как правило, нельзя устанавливать после вызова метода **GetRequestStream**.  
  
## <a name="getresponse-method"></a>Метод GetResponse  
 Метод <xref:System.Net.WebRequest.GetResponse%2A> возвращает потомок класса определенного протокола <xref:System.Net.WebResponse>, который представляет ответ сервера. Если запрос не был ранее инициирован методом **GetRequestStream**, метод **GetResponse** создает подключение к ресурсу, на который указывает **RequestUri**, отправляет данные заголовка с типом выполняемого запроса, после чего принимает ответ ресурса.  
  
 После вызова метода **GetResponse** все свойства обрабатываются как доступные только для чтения. Экземпляры **WebRequest** предназначены для однократного использования. Чтобы выполнить другой запрос, необходимо создать новый экземпляр **WebRequest**.  
  
 Метод **GetResponse** используется для создания соответствующего потомка класса **WebResponse**, который содержит полученный ответ.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebRequest>
- <xref:System.Net.HttpWebRequest>
- <xref:System.Net.FileWebRequest>
- [Программирование подключаемых протоколов](programming-pluggable-protocols.md)
- [Наследование от класса WebResponse](deriving-from-webresponse.md)
