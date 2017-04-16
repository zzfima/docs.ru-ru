---
title: "Использование класса сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Использование класса сообщений
<xref:System.ServiceModel.Channels.Message> класс является основой [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Весь обмен данными между клиентами и службами в конечном итоге приводит к <xref:System.ServiceModel.Channels.Message> отправленных и полученных экземпляров.  
  
 Не приходится взаимодействовать обычно с <xref:System.ServiceModel.Channels.Message> напрямую. Вместо этого для описания входящих и исходящих сообщений используются конструкции модели служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], такие как контракты данных, контракты сообщений и контракты операций. Однако в некоторых сложных сценариях можно программировать с помощью <xref:System.ServiceModel.Channels.Message> напрямую. Например, может потребоваться использовать <xref:System.ServiceModel.Channels.Message> класса:  
  
-   Если необходим альтернативный способ создания содержимого исходящих сообщений (например, нужно создать сообщение непосредственно из файла на диске), отличный от сериализации объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Если необходим альтернативный способ использования содержимого входящих сообщений (например, когда нужно применить преобразование XSLT к необработанному содержимому XML), отличный от десериализации в объекты [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Если необходимо совершить общие операции с сообщениями независимо от их содержимого (например, маршрутизировать или переслать сообщения при создании маршрутизатора, подсистемы балансировки нагрузки или системы публикации-подписки).  
  
 Перед использованием <xref:System.ServiceModel.Channels.Message> класса, ознакомиться с [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] передачи данных архитектуры в [Обзор архитектуры передачи данных](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
 Объект <xref:System.ServiceModel.Channels.Message> является универсальным контейнером для данных, но его структура многом схожа со структурой сообщения в протоколе SOAP. Как и в протоколе SOAP, сообщение имеет тело и заголовки. Тело сообщения содержит фактическую полезную нагрузку данных, а заголовки - дополнительные именованные контейнеры с данными. Правила чтения и записи тела и заголовков сообщения различаются. Так, заголовки всегда буферизуются в памяти, доступ к ним можно получать в любой очередности неограниченное количество раз, в то время как тело можно прочитать только один раз, и тело может участвовать в потоковой передаче. Как правило, при использовании протокола SOAP тело сообщения сопоставляется телу сообщения SOAP, а его заголовки - заголовкам сообщения SOAP.  
  
## <a name="using-the-message-class-in-operations"></a>Использование класса сообщений в операциях  
 Можно использовать <xref:System.ServiceModel.Channels.Message> операции, возвращаемое значение операции или оба класса как входной параметр. Если <xref:System.ServiceModel.Channels.Message> используется в любом месте операции действуют следующие ограничения:  
  
-   Операция не должна иметь параметров `out` или `ref`.  
  
-   Операция не должна иметь более одного параметра `input`. Если параметр присутствует, это должен быть параметр Message или тип контракта сообщений.  
  
-   Возвращаемый тип должен представлять собой `void`, `Message` или тип контракта сообщений.  
  
 В следующем примере кода показан действительный контракт операции.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Создание базовых сообщений  
 <xref:System.ServiceModel.Channels.Message> класс предоставляет статические `CreateMessage` фабричные методы, которые можно использовать для создания базовых сообщений.  
  
 Все `CreateMessage` перегруженные методы принимают параметр версии типа <xref:System.ServiceModel.Channels.MessageVersion> указывает версии SOAP и WS-Addressing для сообщения. Если вы хотите использовать те же версии протокола в качестве входящего сообщения, можно использовать <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> свойство <xref:System.ServiceModel.OperationContext> получен экземпляр из <xref:System.ServiceModel.OperationContext.Current%2A> свойство. Большинство перегрузок `CreateMessage` также имеют параметр строки, который указывает, какое действие SOAP следует использовать для сообщения. Чтобы отключить создание конверта SOAP, можно задать версии значение `None`, тогда сообщение будет состоять только из тела.  
  
## <a name="creating-messages-from-objects"></a>Создание сообщений из объектов  
 Самая обычная перегрузка метода `CreateMessage`, использующая только версию и действие, создает сообщение с пустым телом. Другая перегрузка, принимающая дополнительный <xref:System.Object> параметр; создает сообщение, тело которого представляет собой сериализуемое представление данного объекта. Используйте <xref:System.Runtime.Serialization.DataContractSerializer> с параметрами по умолчанию для сериализации. При необходимости использовать другой сериализатор или сериализатор `DataContractSerializer` с другими настройками используйте перегрузку метода `CreateMessage`, которая также принимает параметр `XmlObjectSerializer`.  
  
 Например, чтобы вернуть объект в сообщение, следует воспользоваться следующим кодом.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Создание сообщений из средств чтения XML  
 Существуют `CreateMessage` перегрузок, принимающих <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlDictionaryReader> текста вместо объекта. В этом случае тело сообщения содержит XML-код, создаваемый в результате чтения из переданного средства чтения XML. Например, следующий код возвращает сообщение, содержимое тела которого прочитано из файла XML.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Кроме того, существуют `CreateMessage` перегрузок, принимающих <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlDictionaryReader> , представляющий все сообщение, а не текста. Эти перегрузки также принимают целочисленный параметр `maxSizeOfHeaders`. Заголовки всегда буферизуются в память сразу после создания сообщения, а этот параметр ограничивает объем буферизации. Для снижения вероятности атаки типа "отказ в обслуживании" необходимо задать безопасное значение этому параметру, если XML-код поступает из ненадежного источника. Версии SOAP и WS-Addressing сообщения, представляемого средством чтения XML, должны соответствовать версиям, указанным с использованием параметра версии.  
  
## <a name="creating-messages-with-bodywriter"></a>Создание сообщений с помощью конструктора BodyWriter  
 Одна из перегрузок метода `CreateMessage` использует экземпляр `BodyWriter` для описания тела сообщения. `BodyWriter` - это абстрактный класс, который может наследоваться для настройки способа создания тел сообщений. Можно создать собственный производный класс `BodyWriter` для описания тел сообщений пользовательским способом. Необходимо переопределить `BodyWriter.OnWriteBodyContents` метода, принимающего <xref:System.Xml.XmlDictionaryWriter>; этот метод используется для записи тела сообщения.  
  
 Некоторые средства записи тела сообщения используют буферизацию, другие (потоковые) - нет. Средства записи тела с буферизацией могут записывать содержимое неограниченное число раз, а потоковые - только один раз. Свойство `IsBuffered` указывает, использует ли средство записи тела сообщения буферизацию или нет. Настроить это свойство для используемого средства записи тела сообщения можно вызовом защищенного конструктора `BodyWriter`, принимающего логический параметр `isBuffered`. Средства записи тела сообщения позволяют создавать средство записи тела сообщения с буферизацией из средства записи без буферизации. Для настройки этого процесса можно переопределить метод `OnCreateBufferedCopy`. По умолчанию используется буфер в памяти, который содержит XML-код, возвращаемый `OnWriteBodyContents`. `OnCreateBufferedCopy` принимает целочисленный параметр `maxBufferSize`; при переопределении этого метода не следует создавать буферы, размер которых превышает данное максимальное значение.  
  
 Класс `BodyWriter` предоставляет методы `WriteBodyContents` и `CreateBufferedCopy`, которые, по сути, являются тонкими программами-оболочками для методов `OnWriteBodyContents` и `OnCreateBufferedCopy` соответственно. Эти методы выполняют проверку состояния, чтобы убедиться, что доступ к средству записи тела сообщения без буферизации не осуществляется более одного раза. Эти методы вызываются непосредственно только при создании пользовательских производных классов `Message` на основе `BodyWriters`.  
  
## <a name="creating-fault-messages"></a>Создание сообщений об ошибках  
 Для создания сообщений об ошибке SOAP можно использовать определенные перегрузки `CreateMessage`. Самый простой из них принимает <xref:System.ServiceModel.Channels.MessageFault> объект, описывающий ошибку. Другие перегрузки предоставляются для удобства. Первая такая перегрузка принимает `FaultCode` и строку причины и создает `MessageFault` с помощью `MessageFault.CreateFault`, использующего эти сведения. Другая перегрузка этого метода принимает объект сведений и передает его `CreateFault` вместе с кодом ошибки и причиной. Например, следующая операция возвращает ошибку.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Извлечение данных тела сообщения  
 Класс `Message` позволяет извлекать данные из его тела несколькими способами. Эти способы можно разделить на следующие категории.  
  
-   Возвращение целого тела сообщения, мгновенно записываемого в средство записи XML. Это называется *записи сообщения*.  
  
-   Размещение средства чтения XML над телом сообщения. Этот способ позволяет впоследствии при необходимости получать доступ к телу сообщения по частям. Это называется *чтение сообщения*.  
  
-   Все сообщения, включая его тело, можно скопировать в буфер в памяти типа <xref:System.ServiceModel.Channels.MessageBuffer> типа. Это называется *копирование сообщения*.  
  
 Доступ к телу `Message` можно получить только один раз независимо от того, каким способом осуществляется доступ. Объект сообщения имеет свойство `State`, которому изначально задано значение Created. Три способа доступа, описанные в вышеприведенном списке, устанавливают состояние Written, Read и Copied соответственно. Кроме того, метод `Close` может установить состояние Closed, если содержимое тела сообщения больше не требуется. Доступ к телу сообщения осуществляется только в состоянии Created, вернуться к состоянию Created после изменения состояния невозможно.  
  
## <a name="writing-messages"></a>Создание сообщений  
 <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> метод записывает содержимое тела заданного `Message` экземпляра в заданное средство записи XML. <xref:System.ServiceModel.Channels.Message.WriteBody%2A> метод делает то же самое, за исключением того, что он помещает содержимое тела в соответствующую оболочку (например, `soap:body`настроек). Наконец <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> записывает сообщение целиком, включая упаковки конверт SOAP и заголовки. Если SOAP отключен (версия `MessageVersion.None`), все три метода действуют одинаково: они записывают содержимое тела сообщения.  
  
 Например, следующий код записывает тело входящего сообщения в файл.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Два дополнительных вспомогательных метода записывают определенные теги начального элемента SOAP. Эти методы не осуществляют доступ к телу сообщения, поэтому они не изменяют состояние сообщения. Сюда входит следующее.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> записывает начальный элемент тела, например `<soap:Body>`.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> записывает начальный элемент конверта, например `<soap:Envelope>`.  
  
 Для записи соответствующих тегов конечных элементов необходимо вызвать метод `WriteEndElement` в соответствующем средстве записи XML. Эти методы редко вызываются напрямую.  
  
## <a name="reading-messages"></a>Чтение сообщений  
 Основной способ прочитать тело сообщения является вызов <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. Вы получаете <xref:System.Xml.XmlDictionaryReader> , можно использовать для чтения тела сообщения. Обратите внимание, что <xref:System.ServiceModel.Channels.Message> переходит в состояние Read сразу <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> вызывается, а не с использованием возвращенного средства чтения XML.  
  
 <xref:System.ServiceModel.Channels.Message.GetBody%2A> метод также позволяет получить доступ к телу сообщения как типизированному объекту. На внутреннем уровне этот метод использует `GetReaderAtBodyContents`, поэтому он также изменяет состояние сообщения <xref:System.ServiceModel.Channels.MessageState> состояние (см. <xref:System.ServiceModel.Channels.Message.State%2A> свойство).  
  
 Рекомендуется проверить <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> свойство, в этом случае текст сообщения будет пустым и <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> вызывает <xref:System.InvalidOperationException>. Кроме того, если полученное сообщение (например, ответе), также можно проверить <xref:System.ServiceModel.Channels.Message.IsFault%2A>, указывающее, содержит ли сообщение ошибку.  
  
 Основная перегрузка метода <xref:System.ServiceModel.Channels.Message.GetBody%2A> десериализует текст сообщения в экземпляр типа (определяемый универсальным параметром) с помощью <xref:System.Runtime.Serialization.DataContractSerializer> настроены параметры по умолчанию и <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A> отключенной квотой. Если вы хотите использовать другой механизм сериализации, или настроить `DataContractSerializer` образом не по умолчанию использовать <xref:System.ServiceModel.Channels.Message.GetBody%2A> перегрузку, принимающую <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Например, следующий код извлекает данные из тела сообщения, которое содержит сериализованный объект `Person` и выводит имя пользователя.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Копирование сообщения в буфер  
 Иногда необходимо получить доступ к телу сообщения более одного раза, например чтобы переслать одно и то же сообщение по нескольким назначениям в рамках системы "издатель-подписчик". В этом случае необходимо поместить в буфер памяти все сообщение (включая тело). Это можно сделать, вызвав <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Этот метод принимает целочисленное значение, которое представляет максимальный размер буфера, и создает буфер, размеры которого не превышают это значение. Если сообщение поступает из ненадежного источника, важно задать этому параметру безопасное значение.  
  
 Буфер возвращается в виде <xref:System.ServiceModel.Channels.MessageBuffer> экземпляра. Доступ к данным в буфере осуществляется несколькими способами. Основным способом является вызов <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> для создания `Message` экземпляров из буфера.  
  
 Другой способ доступа к данным в буфере является реализация <xref:System.Xml.XPath.IXPathNavigable> интерфейс, который <xref:System.ServiceModel.Channels.MessageBuffer> реализует прямого доступа к базового документа XML. Некоторые <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> перегрузки позволяют создавать <xref:System.Xml.XPath> навигаторов, защищенные квотой узла, ограничивая количество узлов XML для посещения. Это позволяет предотвратить атаки типа "отказ в обслуживании", возникающие из-за длительного времени обработки. По умолчанию эта квота выключена. Некоторые `CreateNavigator` перегрузки позволяют указать, как следует обрабатывать пробелы в XML с помощью <xref:System.Xml.XmlSpace> перечисления по умолчанию используется значение `XmlSpace.None`.  
  
 Последний способ доступа к содержимому буфера сообщений — записью его содержимого в поток с помощью <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 В следующем примере продемонстрирована работа с буфером сообщений `MessageBuffer`: входящее сообщение пересылается нескольким получателям, а затем записывается в файл. Это было бы невозможно без использования буфера, потому что в этом случае доступ к телу сообщения можно было бы получить только один раз.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 Имеет смысл упомянуть и о других членах класса `MessageBuffer`. <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> метод можно вызывать для освобождения ресурсов, если содержимое буфера больше не требуются. <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> свойство возвращает размер выделенного буфера. <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> свойство возвращает тип содержимого MIME сообщения.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Доступ к телу сообщения для отладки  
 В целях отладки можно вызвать <xref:System.ServiceModel.Channels.Message.ToString%2A> метод, чтобы получить представление сообщения в виде строки. Это представление, как правило, соответствует виду кодированного с помощью текстового кодировщика сообщения с той разницей, что XML лучше отформатирован для восприятия человеком. Единственным исключением из вышесказанного является тело сообщения. Тело сообщения можно прочитать только один раз, и `ToString` не меняет состояние сообщения. Таким образом `ToString` метод может оказаться невозможным доступ к тексту и может потребоваться заменить заполнитель (например, «...» или многоточие). Следовательно, не рекомендуется использовать `ToString` для записи сообщений в журнал, если важно содержимое тел сообщений.  
  
## <a name="accessing-other-message-parts"></a>Осуществление доступа к другим частям сообщения  
 Для получения доступа к другой информации о сообщении (кроме содержимого его тела) предоставляются различные свойства. Однако эти свойства невозможно вызвать после того, как сообщение было закрыто.  
  
-   <xref:System.ServiceModel.Channels.Message.Headers%2A> свойство представляет заголовки сообщения. См. подраздел "Работа с заголовками" далее в этом разделе.  
  
-   <xref:System.ServiceModel.Channels.Message.Properties%2A> свойство представляет свойства сообщения, которые являются элементами именованных данных, прикрепленных к сообщению, не обычно выдаются при отправке сообщения. См. подраздел "Работа со свойствами" далее в этом разделе.  
  
-   <xref:System.ServiceModel.Channels.Message.Version%2A> свойство указывает версию SOAP и WS-Addressing, связанные с данным сообщением или `None` Если SOAP отключен.  
  
-   <xref:System.ServiceModel.Channels.Message.IsFault%2A> возвращает `true` Если сообщение является сообщением об ошибке SOAP.  
  
-   <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> возвращает `true` Если сообщение является пустым.  
  
 Можно использовать <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29> метод для доступа к определенному атрибуту в программе-оболочке тела (например, `<soap:Body>`) обозначаемому определенным именем и пространством имен. Если такой атрибут не найден, возвращается значение `null`. Этот метод можно вызвать, только если сообщение `Message` находится в состоянии Created (если доступ к телу сообщения еще не осуществлялся).  
  
## <a name="working-with-headers"></a>Работа с заголовками  
 Объект `Message` может содержать любое число именованных фрагментов XML, называются *заголовки*. Как правило, каждый фрагмент сопоставляется заголовку SOAP. Заголовкам осуществляется через `Headers` свойство типа <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> — это коллекция <xref:System.ServiceModel.Channels.MessageHeaderInfo> объектов и отдельным заголовкам осуществляется через его <xref:System.Collections.IEnumerable> интерфейс или индексатор. Например, в следующем коде перечислены имена всех заголовков в сообщении `Message`.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Добавление, удаление, нахождение заголовков  
 Можно добавить новый заголовок в конце всех существующих заголовков с помощью <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A> метод. Можно использовать <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A> метод для вставки заголовка с заданным индексом. Существующие заголовки сдвигаются на вставленный элемент. Заголовки упорядочиваются по индексу, первым доступным индексом является 0. Можно использовать различные <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> перегрузок метода для добавления заголовков из другого `Message` или `MessageHeaders` экземпляра. Некоторые перегрузки копируют только один заголовок, другие копируют все заголовки. <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> метод удаляет все заголовки. <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> метод удаляет заголовок в определенном индексе (сдвигая все заголовки после него). <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> метод удаляет все заголовки с определенным именем и пространством имен.  
  
 Получить определенный заголовок <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A> метод. Этот метод использует для нахождения заголовка его имя и пространство имен и возвращает его индекс. Если заголовок встречается более одного раза, создается исключение. Если заголовок не найден, возвращается -1.  
  
 В модели заголовков SOAP заголовки могут иметь значение `Actor`, которое задает законного получателя заголовка. Основная перегрузка метода `FindHeader` осуществляет только поиск заголовков, предназначенных для конечного получателя сообщения. Другая перегрузка метода позволяет указать, какие значения `Actor` необходимо включить в поиск. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] в спецификации языка SOAP.  
  
 Объект [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> метод предоставляется для копирования заголовков из <xref:System.ServiceModel.Channels.MessageHeaders> коллекции в массив <xref:System.ServiceModel.Channels.MessageHeaderInfo> объектов.  
  
 Чтобы получить доступ к данным XML в заголовке, можно вызвать <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> и вернуть средство чтения XML для конкретного индекса заголовка. Если требуется десериализовать содержимое заголовка в объект, используйте <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> или одной из других перегрузок. Основные перегрузки десериализуют заголовки с помощью <xref:System.Runtime.Serialization.DataContractSerializer> настроенного по умолчанию способом. При необходимости использовать другой сериализатор или сериализатор `DataContractSerializer` с другими настройками используйте одну из перегрузок, принимающих `XmlObjectSerializer`. Существуют перегрузки, принимающие вместо индекса имя заголовка, пространство имен и дополнительно список значений `Actor`; в этом случае получается сочетание `FindHeader` и `GetHeader`.  
  
## <a name="working-with-properties"></a>Работа со свойствами  
 Экземпляр `Message` может содержать произвольное число именованных объектов произвольных типов. Доступ к этой коллекции осуществляется через свойство `Properties` типа `MessageProperties`. Коллекция реализует <xref:System.Collections.Generic.IDictionary%602> интерфейс и действует как сопоставление между <xref:System.String> для <xref:System.Object>.\</TKey, TValue> Как правило, значения свойств не сопоставляются непосредственно к любой части сообщения в сети, но предоставляют различные подсказки об различным каналам в обработке сообщения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] стека каналов или [CopyTo (MessageHeaderInfo\<xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> инфраструктура службы. Например, в разделе [Обзор архитектуры передачи данных](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Наследование от класса сообщений  
 Если встроенные типы сообщений, созданные с использованием `CreateMessage`, не соответствуют предъявляемым требованиям, можно создать класс, который наследуется от класса `Message`.  
  
### <a name="defining-the-message-body-contents"></a>Определение содержимого тела сообщения  
 Для осуществления доступа к данным в теле сообщения существует три основных методики: запись, чтение и копирование в буфер. Эти операции сводятся к <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A>, и <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> методов вызывается, соответственно, в производный класс `Message`. Базовый класс `Message` гарантирует, что для каждого экземпляра `Message` вызывается только один из этих методов и вызывается однократно. Базовый класс также гарантирует, что эти методы не вызываются для закрытого сообщения. Нет необходимости отслеживать состояние сообщения в реализации.  
  
 <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> метод абстрактным и должен быть реализован. Основным способом определения содержимого тела сообщения является его запись с помощью этого метода. Например, в следующем сообщении содержится 100 000 случайных чисел от 1 до 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 Методы `OnGetReaderAtBodyContents` и `OnCreateBufferedCopy` имеют реализации по умолчанию, которые срабатывают в большинстве случаев. Реализации по умолчанию вызывают метод `OnWriteBodyContents`, буферизуют результаты и работают с получившимся буфером. Однако в некоторых случаях этого недостаточно. В предыдущем примере чтение сообщения приводит к буферизации 100 000 элементов XML, что может оказаться нежелательным. Возможно, для возвращения пользовательского производного класса `OnGetReaderAtBodyContents`, обслуживающего случайные числа, целесообразно переопределить метод `XmlDictionaryReader`. Затем можно переопределить метод `OnWriteBodyContents` для использования средства чтения, возвращаемого свойством `OnGetReaderAtBodyContents`, как показано в следующем примере.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 Аналогично, для возвращения собственного производного класса `OnCreateBufferedCopy` имеет смысл переопределить метод `MessageBuffer`.  
  
 Производный класс сообщения должен не только предоставлять содержимое тела сообщения, но и переопределять свойства `Version`, `Headers` и `Properties`.  
  
 Обратите внимание, что если создать копию сообщения, в ней будут использоваться заголовки из оригинального сообщения.  
  
### <a name="other-members-that-can-be-overridden"></a>Другие переопределяемые члены  
 Можно переопределить <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, и <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A> записываются методы, чтобы задать способ конверта SOAP, заголовков SOAP и элемента body SOAP тегов. Как правило, эти методы соответствуют `<soap:Envelope>`, `<soap:Header>` и `<soap:Body>`. Если свойство `Version` возвращает значение `MessageVersion.None`, как правило, эти методы ничего не записывают.  
  
> [!NOTE]
>  До вызова метода `OnGetReaderAtBodyContents` и буферизации результатов используемая по умолчанию реализация `OnWriteStartEnvelope` вызывает методы `OnWriteStartBody` и `OnWriteBodyContents`. Заголовки не записываются.  
  
 Переопределение <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A> метод, чтобы изменить способ целого сообщения из различных элементов. `OnWriteMessage` Метод вызывается из <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> и значение по умолчанию <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> реализации. Обратите внимание, что переопределять <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> не рекомендуется. Рекомендуется заменить соответствующие `On` методов (например, <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A>, и <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>.  
  
 Переопределение <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A> переопределить способ представления тела сообщения в ходе отладки. По умолчанию для этого необходимо представить его в виде многоточия ("..."). Обратите внимание, что этот метод можно вызывать несколько раз при любом состоянии сообщения, кроме Closed. Реализация этого метода никогда не должна вызывать действие, которое должно выполняться однократно (например, чтение из потока только в прямом направлении).  
  
 Переопределение <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A> метод, чтобы разрешить доступ к атрибутам в элементе тела сообщения SOAP. Этот метод можно вызывать неограниченное количество раз, но базовый тип сообщения `Message` гарантирует, что этот метод вызывается, только если сообщение находится в состоянии Created. В реализации не требуется проверять состояние сообщения. Реализация по умолчанию всегда возвращает значение `null`, что указывает на отсутствие атрибутов в элементе тела сообщения.  
  
 Если ваш `Message` объект должен выполнить какие-либо специальные очистки, когда тело сообщения больше не требуется, можно переопределить <xref:System.ServiceModel.Channels.Message.OnClose%2A>. Реализация по умолчанию не выполняет никаких действий.  
  
 Свойства `IsEmpty` и `IsFault` могут переопределяться. По умолчанию оба свойства возвращают `false`.