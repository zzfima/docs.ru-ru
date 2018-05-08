---
title: Использование класса сообщений
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d1d62bfb-2aa3-4170-b6f8-c93d3afdbbed
ms.openlocfilehash: 0ff65d9173838a8eb8850253e62d822f06942f26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="using-the-message-class"></a>Использование класса сообщений
<xref:System.ServiceModel.Channels.Message> Класс — это основа для Windows Communication Foundation (WCF). Все взаимодействие между клиентами и службами в конечном итоге приводит к отправке и получению экземпляров класса <xref:System.ServiceModel.Channels.Message>.  
  
 Как правило, с классом <xref:System.ServiceModel.Channels.Message> не приходится взаимодействовать напрямую. Вместо этого для описания входящих и исходящих сообщений используются конструкции модели службы WCF, такие как контракты данных, контракты сообщений и контракты операций. Однако в некоторых сложных сценариях можно создавать код непосредственно с использованием класса <xref:System.ServiceModel.Channels.Message>. Например, класс <xref:System.ServiceModel.Channels.Message> можно использовать в следующих случаях.  
  
-   Если необходим альтернативный способ создания содержимого исходящих сообщений (например, нужно создать сообщение непосредственно из файла на диске), отличный от сериализации объектов [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Если необходим альтернативный способ использования содержимого входящих сообщений (например, когда нужно применить преобразование XSLT к необработанному содержимому XML), отличный от десериализации в объекты [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
-   Если необходимо совершить общие операции с сообщениями независимо от их содержимого (например, маршрутизировать или переслать сообщения при создании маршрутизатора, подсистемы балансировки нагрузки или системы публикации-подписки).  
  
 Перед использованием <xref:System.ServiceModel.Channels.Message> класса, ознакомьтесь с архитектурой передачи данных WCF в [Обзор архитектуры передачи данных](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
 Класс <xref:System.ServiceModel.Channels.Message> представляет собой контейнер для данных общего назначения, структура которого во многом схожа со структурой сообщения в протоколе SOAP. Как и в протоколе SOAP, сообщение имеет тело и заголовки. Тело сообщения содержит фактическую полезную нагрузку данных, а заголовки - дополнительные именованные контейнеры с данными. Правила чтения и записи тела и заголовков сообщения различаются. Так, заголовки всегда буферизуются в памяти, доступ к ним можно получать в любой очередности неограниченное количество раз, в то время как тело можно прочитать только один раз, и тело может участвовать в потоковой передаче. Как правило, при использовании протокола SOAP тело сообщения сопоставляется телу сообщения SOAP, а его заголовки - заголовкам сообщения SOAP.  
  
## <a name="using-the-message-class-in-operations"></a>Использование класса сообщений в операциях  
 Класс <xref:System.ServiceModel.Channels.Message> можно использовать в качестве входного параметра или возвращаемого значения операции либо обоих. При использовании класса <xref:System.ServiceModel.Channels.Message> в любом месте операции действуют следующие ограничения.  
  
-   Операция не должна иметь параметров `out` или `ref`.  
  
-   Операция не должна иметь более одного параметра `input`. Если параметр присутствует, это должен быть параметр Message или тип контракта сообщений.  
  
-   Возвращаемый тип должен представлять собой `void`, `Message` или тип контракта сообщений.  
  
 В следующем примере кода показан действительный контракт операции.  
  
 [!code-csharp[C_UsingTheMessageClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#1)]
 [!code-vb[C_UsingTheMessageClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#1)]  
  
## <a name="creating-basic-messages"></a>Создание базовых сообщений  
 Класс <xref:System.ServiceModel.Channels.Message> предоставляет статические методы фабрики `CreateMessage`, которые можно использовать для создания базовых сообщений.  
  
 Все перегрузки `CreateMessage` могут принимать параметр версии типа <xref:System.ServiceModel.Channels.MessageVersion>, который указывает, какие версии протокола SOAP и WS-Addressing использовать для данного сообщения. При необходимости использовать те же версии протокола, что и входящее сообщение, можно использовать свойство <xref:System.ServiceModel.OperationContext.IncomingMessageVersion%2A> в экземпляре <xref:System.ServiceModel.OperationContext>, полученном из свойства <xref:System.ServiceModel.OperationContext.Current%2A>. Большинство перегрузок `CreateMessage` также имеют параметр строки, который указывает, какое действие SOAP следует использовать для сообщения. Чтобы отключить создание конверта SOAP, можно задать версии значение `None`, тогда сообщение будет состоять только из тела.  
  
## <a name="creating-messages-from-objects"></a>Создание сообщений из объектов  
 Самая обычная перегрузка метода `CreateMessage`, использующая только версию и действие, создает сообщение с пустым телом. Перегрузка, принимающая дополнительный параметр <xref:System.Object>, создает сообщение, тело которого представляет собой сериализуемое представление данного объекта. Для сериализации используйте сериализатор <xref:System.Runtime.Serialization.DataContractSerializer> с параметрами по умолчанию. При необходимости использовать другой сериализатор или сериализатор `DataContractSerializer` с другими настройками используйте перегрузку метода `CreateMessage`, которая также принимает параметр `XmlObjectSerializer`.  
  
 Например, чтобы вернуть объект в сообщение, следует воспользоваться следующим кодом.  
  
 [!code-csharp[C_UsingTheMessageClass#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#2)]
 [!code-vb[C_UsingTheMessageClass#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#2)]  
  
## <a name="creating-messages-from-xml-readers"></a>Создание сообщений из средств чтения XML  
 Существуют перегрузки метода `CreateMessage`, которые вместо объекта принимают средство чтения <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlDictionaryReader> для тела сообщения. В этом случае тело сообщения содержит XML-код, создаваемый в результате чтения из переданного средства чтения XML. Например, следующий код возвращает сообщение, содержимое тела которого прочитано из файла XML.  
  
 [!code-csharp[C_UsingTheMessageClass#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#3)]
 [!code-vb[C_UsingTheMessageClass#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#3)]  
  
 Кроме того, существуют перегрузки метода `CreateMessage`, которые принимают средство чтения <xref:System.Xml.XmlReader> или <xref:System.Xml.XmlDictionaryReader>, представляющее все сообщение, а не только его тело. Эти перегрузки также принимают целочисленный параметр `maxSizeOfHeaders`. Заголовки всегда буферизуются в память сразу после создания сообщения, а этот параметр ограничивает объем буферизации. Для снижения вероятности атаки типа "отказ в обслуживании" необходимо задать безопасное значение этому параметру, если XML-код поступает из ненадежного источника. Версии SOAP и WS-Addressing сообщения, представляемого средством чтения XML, должны соответствовать версиям, указанным с использованием параметра версии.  
  
## <a name="creating-messages-with-bodywriter"></a>Создание сообщений с помощью конструктора BodyWriter  
 Одна из перегрузок метода `CreateMessage` использует экземпляр `BodyWriter` для описания тела сообщения. `BodyWriter` - это абстрактный класс, который может наследоваться для настройки способа создания тел сообщений. Можно создать собственный производный класс `BodyWriter` для описания тел сообщений пользовательским способом. Необходимо переопределить метод `BodyWriter.OnWriteBodyContents`, принимающий <xref:System.Xml.XmlDictionaryWriter>; этот метод используется для записи тела сообщения.  
  
 Некоторые средства записи тела сообщения используют буферизацию, другие (потоковые) - нет. Средства записи тела с буферизацией могут записывать содержимое неограниченное число раз, а потоковые - только один раз. Свойство `IsBuffered` указывает, использует ли средство записи тела сообщения буферизацию или нет. Настроить это свойство для используемого средства записи тела сообщения можно вызовом защищенного конструктора `BodyWriter`, принимающего логический параметр `isBuffered`. Средства записи тела сообщения позволяют создавать средство записи тела сообщения с буферизацией из средства записи без буферизации. Для настройки этого процесса можно переопределить метод `OnCreateBufferedCopy`. По умолчанию используется буфер в памяти, который содержит XML-код, возвращаемый `OnWriteBodyContents`. `OnCreateBufferedCopy` принимает целочисленный параметр `maxBufferSize`; при переопределении этого метода не следует создавать буферы, размер которых превышает данное максимальное значение.  
  
 Класс `BodyWriter` предоставляет методы `WriteBodyContents` и `CreateBufferedCopy`, которые, по сути, являются тонкими программами-оболочками для методов `OnWriteBodyContents` и `OnCreateBufferedCopy` соответственно. Эти методы выполняют проверку состояния, чтобы убедиться, что доступ к средству записи тела сообщения без буферизации не осуществляется более одного раза. Эти методы вызываются непосредственно только при создании пользовательских производных классов `Message` на основе `BodyWriters`.  
  
## <a name="creating-fault-messages"></a>Создание сообщений об ошибках  
 Для создания сообщений об ошибке SOAP можно использовать определенные перегрузки `CreateMessage`. Основная из них принимает объект <xref:System.ServiceModel.Channels.MessageFault>, который описывает ошибку. Другие перегрузки предоставляются для удобства. Первая такая перегрузка принимает `FaultCode` и строку причины и создает `MessageFault` с помощью `MessageFault.CreateFault`, использующего эти сведения. Другая перегрузка этого метода принимает объект сведений и передает его `CreateFault` вместе с кодом ошибки и причиной. Например, следующая операция возвращает ошибку.  
  
 [!code-csharp[C_UsingTheMessageClass#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#4)]
 [!code-vb[C_UsingTheMessageClass#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#4)]  
  
## <a name="extracting-message-body-data"></a>Извлечение данных тела сообщения  
 Класс `Message` позволяет извлекать данные из его тела несколькими способами. Эти способы можно разделить на следующие категории.  
  
-   Возвращение целого тела сообщения, мгновенно записываемого в средство записи XML. Это называется *записи сообщения*.  
  
-   Размещение средства чтения XML над телом сообщения. Этот способ позволяет впоследствии при необходимости получать доступ к телу сообщения по частям. Это называется *прочтение сообщения*.  
  
-   Все сообщение, включая его тело, можно скопировать в буфер памяти типа <xref:System.ServiceModel.Channels.MessageBuffer>. Это называется *копирование сообщения*.  
  
 Доступ к телу `Message` можно получить только один раз независимо от того, каким способом осуществляется доступ. Объект сообщения имеет свойство `State`, которому изначально задано значение Created. Три способа доступа, описанные в вышеприведенном списке, устанавливают состояние Written, Read и Copied соответственно. Кроме того, метод `Close` может установить состояние Closed, если содержимое тела сообщения больше не требуется. Доступ к телу сообщения осуществляется только в состоянии Created, вернуться к состоянию Created после изменения состояния невозможно.  
  
## <a name="writing-messages"></a>Создание сообщений  
 Метод <xref:System.ServiceModel.Channels.Message.WriteBodyContents%28System.Xml.XmlDictionaryWriter%29> записывает содержимое тела заданного экземпляра `Message` в заданное средство записи XML. Метод <xref:System.ServiceModel.Channels.Message.WriteBody%2A> действует практически также, за исключением того, что он помещает содержимое тела в соответствующую программу-оболочку (например, <`soap:body`>). Наконец, метод <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> записывает все сообщение, включая конверт SOAP и заголовки, выполняющие функции оболочки. Если SOAP отключен (версия `MessageVersion.None`), все три метода действуют одинаково: они записывают содержимое тела сообщения.  
  
 Например, следующий код записывает тело входящего сообщения в файл.  
  
 [!code-csharp[C_UsingTheMessageClass#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#5)]
 [!code-vb[C_UsingTheMessageClass#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#5)]  
  
 Два дополнительных вспомогательных метода записывают определенные теги начального элемента SOAP. Эти методы не осуществляют доступ к телу сообщения, поэтому они не изменяют состояние сообщения. К ним относятся следующие методы.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartBody%2A> записывает начальный элемент тела, например `<soap:Body>`.  
  
-   <xref:System.ServiceModel.Channels.Message.WriteStartEnvelope%2A> записывает начальный элемент конверта, например `<soap:Envelope>`.  
  
 Для записи соответствующих тегов конечных элементов необходимо вызвать метод `WriteEndElement` в соответствующем средстве записи XML. Эти методы редко вызываются напрямую.  
  
## <a name="reading-messages"></a>Чтение сообщений  
 Основной способ прочитать тело сообщения - это вызвать метод <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>. В результате возвращается средство чтения <xref:System.Xml.XmlDictionaryReader>, которое можно использовать для чтения тела сообщения. Обратите внимания, что <xref:System.ServiceModel.Channels.Message> переходит в состояние Read сразу после вызова <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>, а не одновременно с использованием возвращенного средства чтения XML.  
  
 Метод <xref:System.ServiceModel.Channels.Message.GetBody%2A> также позволяет получать доступ к телу сообщения как типизированному объекту. Изнутри этот метод использует `GetReaderAtBodyContents`, поэтому он также изменяет состояние сообщения на <xref:System.ServiceModel.Channels.MessageState.Read> (см. свойство <xref:System.ServiceModel.Channels.Message.State%2A>).  
  
 Рекомендуется всегда проверять свойство <xref:System.ServiceModel.Channels.Message.IsEmpty%2A>; в этом случае тело сообщения пустое, а <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> создает исключение <xref:System.InvalidOperationException>. Кроме того, если речь идет о полученном сообщении (например, ответе), целесообразно проверить свойство <xref:System.ServiceModel.Channels.Message.IsFault%2A>, указывающее, содержит ли сообщение ошибку.  
  
 Основная перегрузка метода <xref:System.ServiceModel.Channels.Message.GetBody%2A> десериализует тело сообщения в экземпляр типа (определяемый универсальным параметром) с использованием сериализатора <xref:System.Runtime.Serialization.DataContractSerializer> с настроенными по умолчанию параметрами и отключенной квотой <xref:System.Runtime.Serialization.DataContractSerializer.MaxItemsInObjectGraph%2A>. При необходимости использовать другой модуль сериализации или изменить настройки `DataContractSerializer` по умолчанию используйте перегрузку метода <xref:System.ServiceModel.Channels.Message.GetBody%2A>, которая принимает параметр <xref:System.Runtime.Serialization.XmlObjectSerializer>.  
  
 Например, следующий код извлекает данные из тела сообщения, которое содержит сериализованный объект `Person` и выводит имя пользователя.  
  
 [!code-csharp[C_UsingTheMessageClass#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#6)]
 [!code-vb[C_UsingTheMessageClass#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#6)]  
  
## <a name="copying-a-message-into-a-buffer"></a>Копирование сообщения в буфер  
 Иногда необходимо получить доступ к телу сообщения более одного раза, например чтобы переслать одно и то же сообщение по нескольким назначениям в рамках системы "издатель-подписчик". В этом случае необходимо поместить в буфер памяти все сообщение (включая тело). Это выполняется вызовом метода <xref:System.ServiceModel.Channels.Message.CreateBufferedCopy%28System.Int32%29>. Этот метод принимает целочисленное значение, которое представляет максимальный размер буфера, и создает буфер, размеры которого не превышают это значение. Если сообщение поступает из ненадежного источника, важно задать этому параметру безопасное значение.  
  
 Буфер возвращается в виде экземпляра <xref:System.ServiceModel.Channels.MessageBuffer>. Доступ к данным в буфере осуществляется несколькими способами. Основной способ - это вызов метода <xref:System.ServiceModel.Channels.Message.CreateMessage%2A> для создания экземпляров `Message` из буфера.  
  
 Доступ к данным в буфере также можно получить реализацией интерфейса <xref:System.Xml.XPath.IXPathNavigable>, который класс <xref:System.ServiceModel.Channels.MessageBuffer> реализует для осуществления прямого доступа к лежащему в основе XML-коду. Некоторые перегрузки метода <xref:System.ServiceModel.Channels.MessageBuffer.CreateNavigator%2A> позволяют создавать навигаторы <xref:System.Xml.XPath>, защищенные квотой узла, которая ограничивает число узлов XML для посещения. Это позволяет предотвратить атаки типа "отказ в обслуживании", возникающие из-за длительного времени обработки. По умолчанию эта квота выключена. Некоторые перегрузки метода `CreateNavigator` позволяют задавать, как следует обрабатывать пробелы в XML с использованием перечисления <xref:System.Xml.XmlSpace>, по умолчанию установлено значение `XmlSpace.None`.  
  
 Наконец, доступ к содержимому буфера сообщений можно получить записью его содержимого в поток с использованием метода <xref:System.ServiceModel.Channels.Message.WriteMessage%2A>.  
  
 В следующем примере продемонстрирована работа с буфером сообщений `MessageBuffer`: входящее сообщение пересылается нескольким получателям, а затем записывается в файл. Это было бы невозможно без использования буфера, потому что в этом случае доступ к телу сообщения можно было бы получить только один раз.  
  
 [!code-csharp[C_UsingTheMessageClass#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#7)]
 [!code-vb[C_UsingTheMessageClass#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#7)]  
  
 Имеет смысл упомянуть и о других членах класса `MessageBuffer`. Метод <xref:System.ServiceModel.Channels.MessageBuffer.Close%2A> можно вызвать для освобождения ресурсов, когда содержимое буфера больше не требуется. Свойство <xref:System.ServiceModel.Channels.MessageBuffer.BufferSize%2A> возвращает размер выделенного буфера. Свойство <xref:System.ServiceModel.Channels.MessageBuffer.MessageContentType%2A> возвращает тип содержимого сообщения MIME.  
  
## <a name="accessing-the-message-body-for-debugging"></a>Доступ к телу сообщения для отладки  
 При отладке можно вызвать метод <xref:System.ServiceModel.Channels.Message.ToString%2A>, чтобы представить сообщение в качестве строки. Это представление, как правило, соответствует виду кодированного с помощью текстового кодировщика сообщения с той разницей, что XML лучше отформатирован для восприятия человеком. Единственным исключением из вышесказанного является тело сообщения. Тело сообщения можно прочитать только один раз, и `ToString` не меняет состояние сообщения. Таким образом `ToString` метод может оказаться невозможным доступ к тексту и может потребоваться заменить заполнитель (например, «...» или многоточие) вместо тела сообщения. Следовательно, не рекомендуется использовать `ToString` для записи сообщений в журнал, если важно содержимое тел сообщений.  
  
## <a name="accessing-other-message-parts"></a>Осуществление доступа к другим частям сообщения  
 Для получения доступа к другой информации о сообщении (кроме содержимого его тела) предоставляются различные свойства. Однако эти свойства невозможно вызвать после того, как сообщение было закрыто.  
  
-   Свойство <xref:System.ServiceModel.Channels.Message.Headers%2A> представляет заголовки сообщения. См. подраздел «Работа с заголовками» далее в этом разделе.  
  
-   Свойство <xref:System.ServiceModel.Channels.Message.Properties%2A> представляет свойства сообщения, которые являются элементами именованных данных, прикрепленных к сообщению; как правило, они не выдаются при отправке сообщения. См. подраздел "Работа со свойствами" далее в этом разделе.  
  
-   Свойство <xref:System.ServiceModel.Channels.Message.Version%2A> указывает на версию SOAP и WS-Addressing, связанную с сообщением, или имеет значение `None`, если SOAP отключен.  
  
-   Свойство <xref:System.ServiceModel.Channels.Message.IsFault%2A> возвращает значение `true`, если сообщение является сообщением об ошибке SOAP.  
  
-   Свойство <xref:System.ServiceModel.Channels.Message.IsEmpty%2A> возвращает значение `true`, если сообщение пустое.  
  
 Для доступа к определенному атрибуту в программе-оболочке тела (например, <xref:System.ServiceModel.Channels.Message.GetBodyAttribute%28System.String%2CSystem.String%29>), обозначаемому определенным именем и пространством имен, можно использовать метод `<soap:Body>`. Если такой атрибут не найден, возвращается значение `null`. Этот метод можно вызвать, только если сообщение `Message` находится в состоянии Created (если доступ к телу сообщения еще не осуществлялся).  
  
## <a name="working-with-headers"></a>Работа с заголовками  
 Объект `Message` может содержать любое число именованных фрагментов XML, которые называются *заголовки*. Как правило, каждый фрагмент сопоставляется заголовку SOAP. Доступ к заголовкам осуществляется через свойство `Headers` типа <xref:System.ServiceModel.Channels.MessageHeaders>. <xref:System.ServiceModel.Channels.MessageHeaders> - это коллекция объектов <xref:System.ServiceModel.Channels.MessageHeaderInfo>. Доступ к отдельным заголовкам осуществляется через его интерфейс <xref:System.Collections.IEnumerable> или индексатор. Например, в следующем коде перечислены имена всех заголовков в сообщении `Message`.  
  
 [!code-csharp[C_UsingTheMessageClass#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#8)]
 [!code-vb[C_UsingTheMessageClass#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#8)]  
  
#### <a name="adding-removing-finding-headers"></a>Добавление, удаление, нахождение заголовков  
 С помощью метода <xref:System.ServiceModel.Channels.MessageHeaders.Add%2A> можно добавлять новый заголовок в конце всех существующих заголовков. Для вставки заголовка в заданном индексе можно использовать метод <xref:System.ServiceModel.Channels.MessageHeaders.Insert%2A>. Существующие заголовки сдвигаются на вставленный элемент. Заголовки упорядочиваются по индексу, первым доступным индексом является 0. Можно использовать различные методы перегрузки <xref:System.ServiceModel.Channels.MessageHeaders.CopyHeadersFrom%2A> для добавления заголовков из другого экземпляра `Message` или `MessageHeaders`. Некоторые перегрузки копируют только один заголовок, другие копируют все заголовки. Метод <xref:System.ServiceModel.Channels.MessageHeaders.Clear%2A> удаляет все заголовки. Метод <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAt%2A> удаляет заголовок в определенном индексе (сдвигая все заголовки после него). Метод <xref:System.ServiceModel.Channels.MessageHeaders.RemoveAll%2A> удаляет все заголовки с определенным именем и пространством имен.  
  
 Метод <xref:System.ServiceModel.Channels.MessageHeaders.FindHeader%2A> позволяет извлечь определенный заголовок. Этот метод использует для нахождения заголовка его имя и пространство имен и возвращает его индекс. Если заголовок встречается более одного раза, создается исключение. Если заголовок не найден, возвращается -1.  
  
 В модели заголовков SOAP заголовки могут иметь значение `Actor`, которое задает законного получателя заголовка. Основная перегрузка метода `FindHeader` осуществляет только поиск заголовков, предназначенных для конечного получателя сообщения. Другая перегрузка метода позволяет указать, какие значения `Actor` необходимо включить в поиск. Дополнительные сведения см. в спецификации SOAP.  
  
 Метод <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> предоставляется для копирования заголовков из коллекции <xref:System.ServiceModel.Channels.MessageHeaders> в массив объектов <xref:System.ServiceModel.Channels.MessageHeaderInfo>.  
  
 Чтобы получить доступ к XML-данным в заголовке, можно вызвать метод <xref:System.ServiceModel.Channels.MessageHeaders.GetReaderAtHeader%2A> и вернуть средство чтения XML для конкретного индекса заголовка. При необходимости десериализовать содержимое заголовка в объект, следует использовать <xref:System.ServiceModel.Channels.MessageHeaders.GetHeader%60%601%28System.Int32%29> или любую другую перегрузку. Основные перегрузки десериализуют заголовки с помощью сериализатора <xref:System.Runtime.Serialization.DataContractSerializer>, настроенного по умолчанию. При необходимости использовать другой сериализатор или сериализатор `DataContractSerializer` с другими настройками используйте одну из перегрузок, принимающих `XmlObjectSerializer`. Существуют перегрузки, принимающие вместо индекса имя заголовка, пространство имен и дополнительно список значений `Actor`; в этом случае получается сочетание `FindHeader` и `GetHeader`.  
  
## <a name="working-with-properties"></a>Работа со свойствами  
 Экземпляр `Message` может содержать произвольное число именованных объектов произвольных типов. Доступ к этой коллекции осуществляется через свойство `Properties` типа `MessageProperties`. Коллекция реализует интерфейс <xref:System.Collections.Generic.IDictionary%602> и действует как сопоставление между <xref:System.String> и <xref:System.Object>. Как правило, значения свойств не сопоставляются непосредственно любую часть сообщения в сети, а также предоставляют различные сообщения подсказки об различным каналам в стеке каналов WCF или к обработке <xref:System.ServiceModel.Channels.MessageHeaders.CopyTo%28System.ServiceModel.Channels.MessageHeaderInfo%5B%5D%2CSystem.Int32%29> инфраструктура службы. Пример см. в разделе [Общие сведения об архитектуре передачи данных](../../../../docs/framework/wcf/feature-details/data-transfer-architectural-overview.md).  
  
## <a name="inheriting-from-the-message-class"></a>Наследование от класса сообщений  
 Если встроенные типы сообщений, созданные с использованием `CreateMessage`, не соответствуют предъявляемым требованиям, можно создать класс, который наследуется от класса `Message`.  
  
### <a name="defining-the-message-body-contents"></a>Определение содержимого тела сообщения  
 Для осуществления доступа к данным в теле сообщения существует три основных методики: запись, чтение и копирование в буфер. Эти операции, по сути, сводятся к вызову для производного класса <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> методов <xref:System.ServiceModel.Channels.Message.OnGetReaderAtBodyContents%2A>, <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A> и `Message` соответственно. Базовый класс `Message` гарантирует, что для каждого экземпляра `Message` вызывается только один из этих методов и вызывается однократно. Базовый класс также гарантирует, что эти методы не вызываются для закрытого сообщения. Нет необходимости отслеживать состояние сообщения в реализации.  
  
 Метод <xref:System.ServiceModel.Channels.Message.OnWriteBodyContents%2A> является абстрактным и должен быть реализован. Основным способом определения содержимого тела сообщения является его запись с помощью этого метода. Например, в следующем сообщении содержится 100 000 случайных чисел от 1 до 20.  
  
 [!code-csharp[C_UsingTheMessageClass#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#9)]
 [!code-vb[C_UsingTheMessageClass#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#9)]  
  
 Методы `OnGetReaderAtBodyContents` и `OnCreateBufferedCopy` имеют реализации по умолчанию, которые срабатывают в большинстве случаев. Реализации по умолчанию вызывают метод `OnWriteBodyContents`, буферизуют результаты и работают с получившимся буфером. Однако в некоторых случаях этого недостаточно. В предыдущем примере чтение сообщения приводит к буферизации 100 000 элементов XML, что может оказаться нежелательным. Возможно, для возвращения пользовательского производного класса `OnGetReaderAtBodyContents`, обслуживающего случайные числа, целесообразно переопределить метод `XmlDictionaryReader`. Затем можно переопределить метод `OnWriteBodyContents` для использования средства чтения, возвращаемого свойством `OnGetReaderAtBodyContents`, как показано в следующем примере.  
  
 [!code-csharp[C_UsingTheMessageClass#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_usingthemessageclass/cs/source.cs#10)]
 [!code-vb[C_UsingTheMessageClass#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_usingthemessageclass/vb/source.vb#10)]  
  
 Аналогично, для возвращения собственного производного класса `OnCreateBufferedCopy` имеет смысл переопределить метод `MessageBuffer`.  
  
 Производный класс сообщения должен не только предоставлять содержимое тела сообщения, но и переопределять свойства `Version`, `Headers` и `Properties`.  
  
 Обратите внимание, что если создать копию сообщения, в ней будут использоваться заголовки из оригинального сообщения.  
  
### <a name="other-members-that-can-be-overridden"></a>Другие переопределяемые члены  
 Чтобы задать способ записи конверта SOAP, заголовков SOAP и открывающих тегов элементов тела сообщения SOAP, можно переопределить методы <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A> и <xref:System.ServiceModel.Channels.Message.OnWriteStartBody%2A>. Как правило, эти методы соответствуют `<soap:Envelope>`, `<soap:Header>` и `<soap:Body>`. Если свойство `Version` возвращает значение `MessageVersion.None`, как правило, эти методы ничего не записывают.  
  
> [!NOTE]
>  До вызова метода `OnGetReaderAtBodyContents` и буферизации результатов используемая по умолчанию реализация `OnWriteStartEnvelope` вызывает методы `OnWriteStartBody` и `OnWriteBodyContents`. Заголовки не записываются.  
  
 Чтобы изменить способ создания целого сообщения из различных элементов, необходимо переопределить метод <xref:System.ServiceModel.Channels.Message.OnWriteMessage%2A>. Метод `OnWriteMessage` вызывается из <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> и реализации по умолчанию <xref:System.ServiceModel.Channels.Message.OnCreateBufferedCopy%2A>. Обратите внимание, что переопределять <xref:System.ServiceModel.Channels.Message.WriteMessage%2A> не рекомендуется. Вместо этого целесообразнее переопределить соответствующие методы `On` (например, <xref:System.ServiceModel.Channels.Message.OnWriteStartEnvelope%2A>, <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A> и <xref:System.ServiceModel.Channels.BodyWriter.OnWriteBodyContents%2A>).  
  
 Чтобы переопределить способ представления тела сообщения в ходе отладки необходимо переопределить метод <xref:System.ServiceModel.Channels.Message.OnBodyToString%2A>. По умолчанию для этого необходимо представить его в виде многоточия ("..."). Обратите внимание, что этот метод можно вызывать несколько раз при любом состоянии сообщения, кроме Closed. Реализация этого метода никогда не должна вызывать действие, которое должно выполняться однократно (например, чтение из потока только в прямом направлении).  
  
 Чтобы разрешить доступ к атрибутам в элементе тела сообщения SOAP, нужно переопределить метод <xref:System.ServiceModel.Channels.Message.OnGetBodyAttribute%2A>. Этот метод можно вызывать неограниченное количество раз, но базовый тип сообщения `Message` гарантирует, что этот метод вызывается, только если сообщение находится в состоянии Created. В реализации не требуется проверять состояние сообщения. Реализация по умолчанию всегда возвращает значение `null`, что указывает на отсутствие атрибутов в элементе тела сообщения.  
  
 Если объект `Message` должен выполнить какие-либо специальные операции очистки, когда тело сообщения больше не требуется, можно переопределить метод <xref:System.ServiceModel.Channels.Message.OnClose%2A>. Реализация по умолчанию не выполняет никаких действий.  
  
 Свойства `IsEmpty` и `IsFault` могут переопределяться. По умолчанию оба свойства возвращают `false`.
