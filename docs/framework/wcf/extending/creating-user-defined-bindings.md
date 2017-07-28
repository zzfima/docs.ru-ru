---
title: "Создание пользовательских привязок | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "пользовательские привязки [WCF]"
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
caps.latest.revision: 19
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 19
---
# Создание пользовательских привязок
Существует несколько способов создания привязок, не предоставленных системой.  
  
-   Создать пользовательскую привязку на основе класса <xref:System.ServiceModel.Channels.CustomBinding>, который служит контейнером, вмещающим элементы привязки.  Впоследствии пользовательская привязка добавляется к конечной точке службы.  Для создания пользовательской привязки можно использовать программные методы или файл конфигурации приложения.  Для использования элемента привязки из файла конфигурации приложения элемент привязки должен быть производным от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] пользовательских привязках см. в разделах [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md) и <xref:System.ServiceModel.Channels.CustomBinding>.  
  
-   Создать класс, производный от стандартной привязки.  Например, чтобы получить элементы привязки и вставить элемент пользовательской привязки или установить определенное значение для обеспечения безопасности, можно создать класс, производный от <xref:System.ServiceModel.WSHttpBinding>, и переопределить метод <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A>.  
  
-   Создать новый тип <xref:System.ServiceModel.Channels.Binding> для того, чтобы полностью контролировать реализацию всей привязки.  
  
## Порядок элементов привязки  
 Каждый элемент привязки представляет собой этап обработки при отправке или получении сообщений.  Во время работы элементы привязки создают каналы и прослушиватели, необходимые для построения стеков исходящих и входящих каналов.  
  
 Существует три основных типа элементов привязки: элементы привязки протокола, элементы привязки кодирования и элементы привязки транспорта.  
  
 Элементы привязки протокола \- эти элементы представляют собой высокоуровневые этапы обработки сообщений.  Каналы и прослушиватели, созданные этими элементами привязки, могут добавлять, удалять или изменять содержание сообщения.  Данная привязка может иметь произвольное число элементов привязки протокола, каждый из которых наследуется от <xref:System.ServiceModel.Channels.BindingElement>.  [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] включает несколько элементов привязки протокола, в том числе <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> и <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
 Элемент привязки кодирования \- эти элементы представляют собой преобразования сообщений в кодировку для передачи по сети.  Типичные привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержат ровно один элемент привязки кодирования.  Примерами элементов привязки кодирования служат <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>.  Если для привязки не задан элемент привязки кодирования, используется кодирование по умолчанию.  Для передачи по протоколу HTTP по умолчанию используется текстовое кодирование, в остальных случаях \- двоичное.  
  
 Элементы привязки транспорта \- эти элементы представляют собой передачу закодированного сообщения по транспортному протоколу.  Типичные привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] содержат ровно один элемент привязки транспорта, который наследуется от <xref:System.ServiceModel.Channels.TransportBindingElement>.  Примерами элементов привязки транспорта служат <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> и <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>.  
  
 При создании новых привязок важно соблюдать порядок вновь добавляемых элементов привязки.  При добавлении элементов привязки необходимо соблюдать следующий порядок.  
  
|Уровень|Параметры|Обязательно|  
|-------------|---------------|-----------------|  
|Поток транзакций|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=fullName>|Нет|  
|Надежность|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=fullName>|Нет|  
|Безопасность|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=fullName>|Нет|  
|Составной дуплексный|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=fullName>|Нет|  
|кодировка|Текстовая, двоичная, MTOM, пользовательская|Да\*|  
|Transport|TCP, именованные каналы, HTTP, HTTPS, MSMQ, определенный пользователем|Да|  
  
 \*Поскольку кодирование обязательно для каждой привязки, если элемент кодирования не задан, то [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] добавляет параметр для кодирования по умолчанию.  Для передачи по протоколам HTTP и HTTPS по умолчанию используется текстовое\/XML\-кодирование, в остальных случаях \- двоичное.  
  
## Создание нового элемента привязки  
 Помимо типов, производных от класса <xref:System.ServiceModel.Channels.BindingElement>, предоставляемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], можно создать собственные элементы привязки.  Это позволяет настроить способ создания стека привязок, а также добавления к нему компонентов путем создания собственного класса <xref:System.ServiceModel.Channels.BindingElement>, который может формироваться из других типов элементов стека, предоставляемых системой.  
  
 Например, при реализации `LoggingBindingElement`, позволяющего заносить сообщение в базу данных, его необходимо размещать в стеке каналов над транспортным каналом.  В этом случае приложение создает пользовательскую привязку, состоящую из `LoggingBindingElement` с `TcpTransportBindingElement`, как показано в примере.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),   
  new TcpTransportBindingElement()  
);  
```  
  
 Способ записи нового элемента привязки зависит от его непосредственной функциональности.  В одном из образцов [Транспорт: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) предоставлено подробное описание способа реализации одного вида элементов привязки.  
  
## Создание новой привязки  
 Созданный пользователем элемент привязки можно использовать двумя способами.  В предыдущем разделе описан первый способ: посредством пользовательской привязки.  Пользовательская привязка позволяет пользователю создать собственную привязку на основе произвольного набора элементов привязки, включающего помимо прочих элементы, созданные пользователем.  
  
 При необходимости использования привязки в нескольких приложениях нужно создать собственную привязку и расширить <xref:System.ServiceModel.Channels.Binding>.  Это избавит от необходимости создания пользовательской привязки вручную каждый раз, когда она нужна.  Определенные пользователем привязки позволяют определить поведение привязки и включить элементы привязки, определенные пользователем.  Кроме того, привязка *упакована заранее*: нет необходимости перестраивать ее каждый раз при использовании.  
  
 Определенная пользователем привязка должна, как минимум, реализовать метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> и свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
 Метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> возвращает новую коллекцию <xref:System.ServiceModel.Channels.BindingElementCollection>, содержащую элементы для привязки.  Коллекция упорядочена и должна содержать элементы привязки протокола, следующий за ними элемент привязки кодирования и, идущий последним, элемент привязки транспорта.  При использовании элементов привязки, предоставленных системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо соблюдать строгий порядок следования элементов привязки, описанный в [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md).  Эта коллекция не должна ссылаться на объекты, на которые имеются ссылки в пределах класса привязки, определенной пользователем; а, следовательно, авторы привязок должны возвращать `Clone()` коллекции <xref:System.ServiceModel.Channels.BindingElementCollection> при каждом вызове <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>.  
  
 Свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A> представляет схему универсального кода ресурса \(URI\) для транспортного протокола, используемого в привязке.  Например, *WSHttpBinding* и *NetTcpBinding* возвращают “http” и “net.tcp” из соответствующих им свойств <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
 Полный список необязательных методов и свойств для определяемых пользователем привязок см. в разделе <xref:System.ServiceModel.Channels.Binding>.  
  
### Пример  
 В этом примере реализуется профиль привязки в `SampleProfileUdpBinding`, производном от <xref:System.ServiceModel.Channels.Binding>.  Класс `SampleProfileUdpBinding` содержит до четырех элементов привязки: один, созданный пользователем `UdpTransportBindingElement`, и три, предоставленных системой: `TextMessageEncodingBindingElement`, `CompositeDuplexBindingElement` и `ReliableSessionBindingElement`.  
  
```  
public override BindingElementCollection CreateBindingElements()  
{     
    BindingElementCollection bindingElements = new BindingElementCollection();  
    if (ReliableSessionEnabled)  
    {  
        bindingElements.Add(session);  
        bindingElements.Add(compositeDuplex);  
    }  
    bindingElements.Add(encoding);  
    bindingElements.Add(transport);  
    return bindingElements.Clone();  
}  
```  
  
## Ограничения безопасности с дуплексными контрактами  
 Не все элементы привязки совместимы друг с другом.  В частности, существует несколько ограничений, налагаемых на элементы привязки безопасности, при их использовании с дуплексными контрактами.  
  
### Одноступенчатый способ обеспечения безопасности  
 Можно реализовать "одноступенчатый" способ обеспечения безопасности, при котором все необходимые учетные данные безопасности запрашиваются в одном сообщении, присвоив атрибуту `negotiateServiceCredential` конфигурационного элемента \<message\> значение `false`.  
  
 Одноступенчатая проверка подлинности не работает с дуплексными контрактами.  
  
 При контрактах типа запрос\-ответ одноступенчатая проверка подлинности работает только в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 При односторонних контрактах одноступенчатая проверка подлинности работает в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, <xref:System.ServiceModel.Channels.IOutputChannel> или <xref:System.ServiceModel.Channels.IOutputSessionChannel>.  
  
### Маркеры контекста безопасности режима "cookie"  
 Маркеры контекста безопасности режима "cookie" нельзя использовать с дуплексными контрактами.  
  
 При контрактах типа запрос\-ответ маркеры контекста безопасности режима "cookie" работают только при условии, что стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 При односторонних контрактах маркеры контекста безопасности режима "cookie" работают в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
### Маркеры контекста безопасности режима сеанса  
 Маркеры контекста безопасности режима сеанса работают для дуплексных контрактов тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel> или <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 Маркеры контекста безопасности режима сеанса работают для контрактов типа запрос\-ответ тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 Маркеры контекста безопасности режима сеанса работают для односторонних контрактов тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
## Класс, производный от стандартной привязки  
 Вместо создания абсолютно нового класса привязки можно расширить одну из существующих привязок, предоставленных системой.  Здесь так же, как в предыдущем случае, необходимо переопределить метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> и свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
## См. также  
 <xref:System.ServiceModel.Channels.Binding>   
 [Пользовательские привязки](../../../../docs/framework/wcf/extending/custom-bindings.md)