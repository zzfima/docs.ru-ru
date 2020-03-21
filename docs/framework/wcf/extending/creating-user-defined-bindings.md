---
title: Создание пользовательских привязок
ms.date: 03/30/2017
helpviewer_keywords:
- user-defined bindings [WCF]
ms.assetid: c4960675-d701-4bc9-b400-36a752fdd08b
ms.openlocfilehash: 34100569dc5cd5a340abca66fedca40ba21c1e0b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185634"
---
# <a name="creating-user-defined-bindings"></a>Создание пользовательских привязок
Существует несколько способов создания привязок, не предоставленных системой.  
  
- Создать пользовательскую привязку на основе класса <xref:System.ServiceModel.Channels.CustomBinding>, который служит контейнером, вмещающим элементы привязки. Впоследствии пользовательская привязка добавляется к конечной точке службы. Для создания пользовательской привязки можно использовать программные методы или файл конфигурации приложения. Для использования элемента привязки из файла конфигурации приложения элемент привязки должен быть производным от класса <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>. Для получения дополнительной информации о пользовательских <xref:System.ServiceModel.Channels.CustomBinding>привязок, см [пользовательских привязок](custom-bindings.md) и .  
  
- Создать класс, производный от стандартной привязки. Например, чтобы получить элементы привязки и вставить элемент пользовательской привязки или установить определенное значение для обеспечения безопасности, можно создать класс, производный от <xref:System.ServiceModel.WSHttpBinding>, и переопределить метод <xref:System.ServiceModel.Channels.CustomBinding.CreateBindingElements%2A>.  
  
- Создать новый тип <xref:System.ServiceModel.Channels.Binding> для того, чтобы полностью контролировать реализацию всей привязки.  
  
## <a name="the-order-of-binding-elements"></a>Порядок элементов привязки  
 Каждый элемент привязки представляет собой этап обработки при отправке или получении сообщений. Во время работы элементы привязки создают каналы и прослушиватели, необходимые для построения стеков исходящих и входящих каналов.  
  
 Существует три основных типа элементов привязки: элементы привязки протокола, элементы привязки кодирования и элементы привязки транспорта.  
  
 Элементы привязки протокола - эти элементы представляют собой высокоуровневые этапы обработки сообщений. Каналы и прослушиватели, созданные этими элементами привязки, могут добавлять, удалять или изменять содержание сообщения. Данная привязка может иметь произвольное число элементов привязки протокола, каждый из которых наследуется от <xref:System.ServiceModel.Channels.BindingElement>. Windows Communication Foundation (WCF) включает в <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> себя <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>несколько элементов связывания протоколов, включая и .  
  
 Элемент привязки кодирования - эти элементы представляют собой преобразования сообщений в кодировку для передачи по сети. Типичные привязки WCF включают в себя ровно один элемент связывания кодирования. Примерами элементов привязки кодирования служат <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>, <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement> и <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>. Если для привязки не задан элемент привязки кодирования, используется кодирование по умолчанию. Для передачи по протоколу HTTP по умолчанию используется текстовое кодирование, в остальных случаях - двоичное.  
  
 Элементы привязки транспорта - эти элементы представляют собой передачу закодированного сообщения по транспортному протоколу. Типичные привязки WCF включают ровно один <xref:System.ServiceModel.Channels.TransportBindingElement>транспортный связывающий элемент, который наследует от . Примерами элементов привязки транспорта служат <xref:System.ServiceModel.Channels.TcpTransportBindingElement>, <xref:System.ServiceModel.Channels.HttpTransportBindingElement> и <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>.  
  
 При создании новых привязок важно соблюдать порядок вновь добавляемых элементов привязки. При добавлении элементов привязки необходимо соблюдать следующий порядок.  
  
|Уровень|Параметры|Обязательно|  
|-----------|-------------|--------------|  
|Поток транзакций|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement?displayProperty=nameWithType>|нет|  
|Надежность|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement?displayProperty=nameWithType>|нет|  
|Безопасность|<xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>|нет|  
|Составной дуплексный|<xref:System.ServiceModel.Channels.CompositeDuplexBindingElement?displayProperty=nameWithType>|нет|  
|Кодирование|Текстовая, двоичная, MTOM, пользовательская|Да\*|  
|Транспортировка|TCP, именованные каналы, HTTP, HTTPS, MSMQ, определенный пользователем|Да|  
  
\*Поскольку кодирование требуется для каждой привязки, если кодирование не указано, WCF добавляет кодирование по умолчанию для вас. Для передачи по протоколам HTTP и HTTPS по умолчанию используется текстовое/XML-кодирование, в остальных случаях - двоичное.  
  
## <a name="creating-a-new-binding-element"></a>Создание нового элемента привязки  
 В дополнение к типам, полученным из <xref:System.ServiceModel.Channels.BindingElement> которые предоставляются WCF, вы можете создать свои собственные элементы связывания. Это позволяет настроить способ создания стека привязок, а также добавления к нему компонентов путем создания собственного класса <xref:System.ServiceModel.Channels.BindingElement>, который может формироваться из других типов элементов стека, предоставляемых системой.  
  
 Например, при реализации `LoggingBindingElement`, позволяющего заносить сообщение в базу данных, его необходимо размещать в стеке каналов над транспортным каналом. В этом случае приложение создает пользовательскую привязку, состоящую из `LoggingBindingElement` с `TcpTransportBindingElement`, как показано в примере.  
  
```csharp  
Binding customBinding = new CustomBinding(  
  new LoggingBindingElement(),
  new TcpTransportBindingElement()  
);  
```  
  
 Способ записи нового элемента привязки зависит от его непосредственной функциональности. Один из образцов, [Transport: UDP](../samples/transport-udp.md), содержит подробное описание того, как реализовать один вид связывающего элемента.  
  
## <a name="creating-a-new-binding"></a>Создание новой привязки  
 Созданный пользователем элемент привязки можно использовать двумя способами. В предыдущем разделе описан первый способ: посредством пользовательской привязки. Пользовательская привязка позволяет пользователю создать собственную привязку на основе произвольного набора элементов привязки, включающего помимо прочих элементы, созданные пользователем.  
  
 При необходимости использования привязки в нескольких приложениях нужно создать собственную привязку и расширить <xref:System.ServiceModel.Channels.Binding>. Это избавит от необходимости создания пользовательской привязки вручную каждый раз, когда она нужна. Определенные пользователем привязки позволяют определить поведение привязки и включить элементы привязки, определенные пользователем. И это *предварительно упакованы*: вам не придется перестраивать связывания каждый раз, когда вы используете его.  
  
 Определенная пользователем привязка должна, как минимум, реализовать метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> и свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
 Метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> возвращает новую коллекцию <xref:System.ServiceModel.Channels.BindingElementCollection>, содержащую элементы для привязки. Коллекция упорядочена и должна содержать элементы привязки протокола, следующий за ними элемент привязки кодирования и, идущий последним, элемент привязки транспорта. При использовании обязательных элементов системы WCF необходимо следовать правилам обязательного элемента, указанным в [пользовательских привязки.](custom-bindings.md) Эта коллекция не должна ссылаться на объекты, на которые имеются ссылки в пределах класса привязки, определенной пользователем; а, следовательно, авторы привязок должны возвращать `Clone()` коллекции <xref:System.ServiceModel.Channels.BindingElementCollection> при каждом вызове <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A>.  
  
 Свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A> представляет схему универсального кода ресурса (URI) для транспортного протокола, используемого в привязке. Например, *WSHttpBinding* и *NetTcpBinding* возвращают "http" и "net.tcp" из своих соответствующих <xref:System.ServiceModel.Channels.Binding.Scheme%2A> свойств.  
  
 Полный список необязательных методов и свойств для определяемых пользователем привязок см. в разделе <xref:System.ServiceModel.Channels.Binding>.  
  
### <a name="example"></a>Пример  
 В этом примере реализуется профиль привязки в `SampleProfileUdpBinding`, производном от <xref:System.ServiceModel.Channels.Binding>. В `SampleProfileUdpBinding` нем содержится до четырех связывающих `UdpTransportBindingElement`элементов: один созданный пользователем; и три системы, предоставляемые: `TextMessageEncodingBindingElement`, `CompositeDuplexBindingElement`и `ReliableSessionBindingElement`.  
  
```csharp
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
  
## <a name="security-restrictions-with-duplex-contracts"></a>Ограничения безопасности с дуплексными контрактами  
 Не все элементы привязки совместимы друг с другом. В частности, существует несколько ограничений, налагаемых на элементы привязки безопасности, при их использовании с дуплексными контрактами.  
  
### <a name="one-shot-security"></a>Одноступенчатый способ обеспечения безопасности  
 Можно реализовать безопасность "одного выстрела", где все необходимые учетные данные `negotiateServiceCredential` безопасности \<отправляются в `false`одном сообщении, установив атрибут сообщения> элемент конфигурации.  
  
 Одноступенчатая проверка подлинности не работает с дуплексными контрактами.  
  
 При контрактах типа запрос-ответ одноступенчатая проверка подлинности работает только в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 При односторонних контрактах одноступенчатая проверка подлинности работает в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel>, <xref:System.ServiceModel.Channels.IRequestSessionChannel>, <xref:System.ServiceModel.Channels.IOutputChannel> или <xref:System.ServiceModel.Channels.IOutputSessionChannel>.  
  
### <a name="cookie-mode-security-context-tokens"></a>Маркеры контекста безопасности режима "cookie"  
 Маркеры контекста безопасности режима "cookie" нельзя использовать с дуплексными контрактами.  
  
 При контрактах типа запрос-ответ маркеры контекста безопасности режима "cookie" работают только при условии, что стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 При односторонних контрактах маркеры контекста безопасности режима "cookie" работают в том случае, если стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
### <a name="session-mode-security-context-tokens"></a>Маркеры контекста безопасности режима сеанса  
 Маркеры контекста безопасности режима сеанса работают для дуплексных контрактов тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel> или <xref:System.ServiceModel.Channels.IDuplexSessionChannel>.  
  
 Маркеры контекста безопасности режима сеанса работают для контрактов типа запрос-ответ тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
 Маркеры контекста безопасности режима сеанса работают для односторонних контрактов тогда, когда стек привязки, находящийся после элемента безопасности привязки, поддерживает возможность создания экземпляров <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IDuplexSessionChannel>, <xref:System.ServiceModel.Channels.IRequestChannel> или <xref:System.ServiceModel.Channels.IRequestSessionChannel>.  
  
## <a name="deriving-from-a-standard-binding"></a>Класс, производный от стандартной привязки  
 Вместо создания абсолютно нового класса привязки можно расширить одну из существующих привязок, предоставленных системой. Здесь так же, как в предыдущем случае, необходимо переопределить метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> и свойство <xref:System.ServiceModel.Channels.Binding.Scheme%2A>.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Channels.Binding>
- [Пользовательские привязки](custom-bindings.md)
