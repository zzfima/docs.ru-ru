---
title: Обработка исключений и сбоев
ms.date: 03/30/2017
ms.assetid: a64d01c6-f221-4f58-93e5-da4e87a5682e
ms.openlocfilehash: 7fa045dc6fd6e31eccf29e22ae2e212f59dfaec0
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80111872"
---
# <a name="handling-exceptions-and-faults"></a>Обработка исключений и сбоев
Исключения используются, чтобы передать сведения об ошибках локально в службе или реализации клиента. С другой стороны, сбои используются, чтобы передать ошибки за пределы службы, например, от сервера клиенту или наоборот. Помимо сбоев каналы транспорта часто используют механизмы, связанные с транспортом, чтобы сообщить об ошибках на транспортном уровне. Например, транспорт HTTP использует коды состояния, такие как «404», чтобы сообщить о несуществующем конечном URL-адресе (отсутствует конечная точка, чтобы вернуть ошибку). Этот документ состоит из трех разделов, в которых содержится руководство для разработчиков пользовательских каналов. В первом разделе содержится руководство о том, когда и как определять и выдавать исключения. Во втором разделе содержится руководство по созданию и использованию ошибок. В третьем разделе разъясняется, как предоставить данные трассировки, которые помогут пользователю созданного канала устранить неполадки в выполняемых приложениях.  
  
## <a name="exceptions"></a>Исключения  
 Важно учитывать два момента при создании исключения: во-первых, его тип должен позволять пользователям написать правильный программный код, который будет соответствующим образом реагировать на исключение. Во-вторых, исключение должно содержать достаточно сведений для пользователя, чтобы понять, какой произошел сбой, его последствия и возможные способы устранения. В следующих разделах содержатся рекомендации по типам исключений и сообщениям для каналов Windows Communication Foundation (WCF). Общие инструкции об исключениях в .NET можно также найти в документе «Правила разработки исключений».  
  
### <a name="exception-types"></a>Типы исключения  
 Все исключения, создаваемые каналами, должны быть типа <xref:System.TimeoutException?displayProperty=nameWithType>, <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> или типа, унаследованного от <xref:System.ServiceModel.CommunicationException>. (Могут также создаваться такие исключения, как <xref:System.ObjectDisposedException>, но только для того, чтобы указать на неправильное использование канала вызывающим кодом. Если канал используется правильно, он должен только бросить данные исключения.) WCF предоставляет семь типов <xref:System.ServiceModel.CommunicationException> исключений, которые вытекают из каналов и предназначены для использования. Существуют другие исключения, унаследованные от <xref:System.ServiceModel.CommunicationException>, которые созданы для использования с другими частями системы. Эти типы исключений приведены в следующей таблице.  
  
|Тип исключения|Значение|Внутреннее содержимое исключения|Стратегия восстановления|  
|--------------------|-------------|-----------------------------|-----------------------|  
|<xref:System.ServiceModel.AddressAlreadyInUseException>|Адрес конечной точки, указанный для прослушивания, уже используется.|Если имеется, предоставляет дополнительные сведения об ошибке транспорта, вызвавшей это исключение. Например, если выбран диапазон 10.0.0.0/20 для виртуальной сети, для пространства клиентских адресов можно выбрать 10.1.0.0/24. <xref:System.IO.PipeException>, <xref:System.Net.HttpListenerException> или <xref:System.Net.Sockets.SocketException>.|Повторите попытку с другим адресом.|  
|<xref:System.ServiceModel.AddressAccessDeniedException>|Доступ к адресу конечной точки, указанному для прослушивания, не разрешен процессом.|Если имеется, предоставляет дополнительные сведения об ошибке транспорта, вызвавшей это исключение. Например, <xref:System.IO.PipeException> или <xref:System.Net.HttpListenerException>.|Повторите попытку с другими учетными данными.|  
|<xref:System.ServiceModel.CommunicationObjectFaultedException>|Используется <xref:System.ServiceModel.ICommunicationObject> в неисправном состоянии (для получения дополнительной информации [см. Понимание изменений состояния).](understanding-state-changes.md) Обратите внимание, когда объект с несколькими ожидающими вызовами переходит в состояние сбоя, только один вызов создает исключение, относящееся к сбою, а остальные вызовы создают исключение <xref:System.ServiceModel.CommunicationObjectFaultedException>. Это исключение обычно создается потому, что приложение пропускает какое-либо исключение и пытается использовать объект с уже имеющимся сбоем, возможно находящимся не в том потоке, который перехватил исходное исключение.|Если имеется, предоставляет сведения о внутреннем исключении.|Создать новый объект. Обратите внимание, что в зависимости от причины сбоя <xref:System.ServiceModel.ICommunicationObject>, могут потребоваться другие действия для восстановления.|  
|<xref:System.ServiceModel.CommunicationObjectAbortedException>|Используемый <xref:System.ServiceModel.ICommunicationObject> был прерван (для получения дополнительной информации [см. Понимание изменений состояния](understanding-state-changes.md)). Подобно <xref:System.ServiceModel.CommunicationObjectFaultedException>тому, это исключение указывает <xref:System.ServiceModel.ICommunicationObject.Abort%2A> на то, что приложение вызвало объект, возможно, из другого потока, и объект больше не может быть пригоден по этой причине.|Если имеется, предоставляет сведения о внутреннем исключении.|Создать новый объект. Обратите внимание, что в зависимости от причины прерывания <xref:System.ServiceModel.ICommunicationObject>, могут потребоваться другие действия для восстановления.|  
|<xref:System.ServiceModel.EndpointNotFoundException>|Удаленная целевая конечная точка не выполняет прослушивание. Это может быть вызвано тем, что адреса конечной точки неверен или неразрешим, либо конечная точка недоступна. Примерами являются ошибка DNS, недоступность диспетчера очередей и незапущенная служба.|Внутреннее исключение предоставляет сведения, как правило, из используемого транспорта.|Повторите попытку с другим адресом. Пользователь также может повторить попытку после небольшой паузы, если служба была недоступна.|  
|<xref:System.ServiceModel.ProtocolException>|Протоколы связи, как описано в политике конечных точек, несовместимы между конечными точками. Например, не совпадают типы содержимого кадрирования или превышен максимальный размер сообщения.|Если имеется, предоставляет дополнительную информацию о конкретной ошибке протокола. Например, <xref:System.ServiceModel.QuotaExceededException> - внутреннее исключение, создаваемое когда причина ошибки превышает MaxReceivedMessageSize.|Восстановление: убедитесь в соответствии параметров протоколов отправителя и получателя. Одним из способов сделать это является повторное импорт метаданных (политики) конечных точек службы и использование генерируемой связки для воссоздания канала.|  
|<xref:System.ServiceModel.ServerTooBusyException>|Удаленная конечная точка выполняет прослушивание, но не готова к обработке сообщений.|Если имеется, внутренне исключение предоставляет ошибку протокола SOAP или сведения об ошибке на транспортном уровне.|Восстановление: повторите операцию после небольшой паузы.|  
|<xref:System.TimeoutException>|Не удалось завершить операцию в течение времени ожидания.|Может содержать сведение о времени ожидания.|Повторите операцию после небольшой паузы.|  
  
 Определите новый тип исключения только в том случае, если данный тип соответствует конкретной стратегии восстановления, отличной от всех существующих типов исключений. В случае определения нового типа исключения, он должен быть унаследован от <xref:System.ServiceModel.CommunicationException> или одного из его производных классов.  
  
### <a name="exception-messages"></a>Сообщения об исключении  
 Сообщения об исключениях предназначены для пользователя, а не для программы, поэтому в них должно содержаться достаточно сведений, чтобы помочь пользователю понять и решить проблему. Ниже приведены три неотъемлемые части хорошего сообщения об исключении.  
  
 Что произошло. Предоставьте четкое описание проблемы, используя термины, относящиеся к опыту пользователя. Например, "Недопустимый раздел конфигурации" является примером неправильного сообщения об исключении. В этом случае у пользователя нет сведений о том, какой раздел и почему является неправильным. Улучшенное сообщение будет "Недействительный раздел \<конфигурации customBinding>". Примером еще более точного сообщения может быть "Не удается добавить транспорт с именем myTransport в привязку myBinding, так как в привязке уже есть транспорт с именем myTransport". Это очень конкретное сообщение с использованием терминов и имен, которые пользователь может легко определить в файле конфигурации приложения. Однако в сообщении по-прежнему не хватает нескольких ключевых компонентов.  
  
 Значимость ошибки. Если в сообщении четко не указано значение ошибки, у пользователя может возникнуть вопрос, является ли ошибка неустранимой, либо ее можно игнорировать. Как правило, в сообщениях должно выводиться значение и значимость ошибки. Предыдущий пример может быть улучшен следующим образом: «Не удалось открыть ServiceHost из-за ошибки конфигурации. Не удается добавить транспорт с имением myTransport в привязку myBinding, так как в привязке уже есть транспорт с именем myTransport».  
  
 Способы устранения проблемы пользователем. Самая важная часть сообщения - помочь пользователю устранить проблему. В сообщении должны содержаться некоторые рекомендации или указания о том, что необходимо проверить или исправить, чтобы устранить проблему. Например, «Не удалось открыть ServiceHost из-за ошибки конфигурации. Не удается добавить транспорт с имением myTransport в привязку myBinding, так как в привязке уже есть транспорт с именем myTransport. Убедитесь в том, что в привязке есть только один транспорт».  
  
## <a name="communicating-faults"></a>Информирование об ошибках  
 Протоколы SOAP 1.1 и SOAP 1.2 определяют конкретную структуру для ошибок. Между двумя спецификациями существуют определенные отличия, но для создания и использования ошибок обычно применяются типы Message и MessageFault.  
  
 ![Обработка исключений и неисправностей](./media/wcfc-soap1-1andsoap1-2faultcomparisonc.gif "wcfc_SOAP1-1AndSOAP1-2FaultComparisonc")  
Ошибка SOAP 1.2 (слева) и ошибка SOAP 1.1 (справа). Обратите внимание, что только в SOAP 1.1 элемент с ошибкой перечислен в пространстве имен.  
  
 Протокол SOAP определяет сообщение об ошибке, как сообщение, содержащее элемент с ошибкой (элемент с именем `<env:Fault>`), в качестве дочернего элемента `<env:Body>`. Содержимое элемента с ошибкой немного отличается в протоколах SOAP 1.1 и SOAP 1.2, как показано на рисунке 1. Однако класс <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType> нормализует эти различия в одной модели объекта:  
  
```csharp
public abstract class MessageFault  
{  
    protected MessageFault();  
  
    public virtual string Actor { get; }  
    public virtual string Node { get; }  
    public static string DefaultAction { get; }  
    public abstract FaultCode Code { get; }  
    public abstract bool HasDetail { get; }  
    public abstract FaultReason Reason { get; }  
  
    public T GetDetail<T>();  
    public T GetDetail<T>( XmlObjectSerializer serializer);  
    public System.Xml.XmlDictionaryReader GetReaderAtDetailContents();  
  
    // other methods omitted  
}  
```  
  
 Свойство `Code` соответствует свойству `env:Code` (или `faultCode` в SOAP 1.1) и определяет тип ошибки. Протокол SOAP 1.2 определяет пять допустимых значений для `faultCode` (например, отправитель и получатель), а также определяет элемент `Subcode`, который может содержать значение дополнительного кода. (См. [спецификацию SOAP 1.2](https://www.w3.org/TR/soap12-part1/#tabsoapfaultcodes) для списка допустимых кодов неисправностей и их значения.) SOAP 1.1 имеет несколько иной `faultCode` механизм: он определяет четыре значения (например, Клиент и Сервер), которые могут быть расширены `faultCodes`либо путем определения совершенно новых, либо с помощью обозначения точек для создания более конкретных, например, Client.Authentication.  
  
 При использовании типа MessageFault для программирования ошибок, значение FaultCode.Name и FaultCode.Namespace сопоставляется с именем и пространством имен `env:Code` в SOAP 1.2 или `faultCode` в SOAP 1.1. Значение FaultCode.SubCode сопоставляется со значением `env:Subcode` для протокола SOAP 1.2, а для SOAP 1.1 оно равно NULL.  
  
 Если требуется различать ошибку программными средствами, необходимо создать новые дополнительные коды ошибок (или новые коды ошибок при использовании протокола SOAP 1.1). Это аналогично созданию нового типа исключения. Не следует использовать запись через точку с кодами ошибок SOAP 1.1. [(Базовый профиль WS-I](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html#SOAP_Custom_Fault_Codes) также препятствует использованию обозначения точки кода неисправности.)  
  
```csharp
public class FaultCode  
{  
    public FaultCode(string name);  
    public FaultCode(string name, FaultCode subCode);  
    public FaultCode(string name, string ns);  
    public FaultCode(string name, string ns, FaultCode subCode);  
  
    public bool IsPredefinedFault { get; }  
    public bool IsReceiverFault { get; }  
    public bool IsSenderFault { get; }  
    public string Name { get; }  
    public string Namespace { get; }  
    public FaultCode SubCode { get; }  
  
//  methods omitted  
  
}  
```  
  
 Свойство `Reason` соответствует `env:Reason` (или `faultString` в SOAP 1.1) читаемым человеком описанию состояния ошибки, аналогичному сообщению исключения. Класс `FaultReason` (и `env:Reason/faultString`в протоколе SOAP) имеет встроенную поддержку нескольких переводов для обеспечения глобализации.  
  
```csharp
public class FaultReason  
{  
    public FaultReason(FaultReasonText translation);  
    public FaultReason(IEnumerable<FaultReasonText> translations);  
    public FaultReason(string text);  
  
    public SynchronizedReadOnlyCollection<FaultReasonText> Translations
    {
       get;
    }  
  
 }  
```  
  
 Содержимое детали неисправности разоблачается на `GetDetail` \<MessageFault `GetReaderAtDetailContents`с использованием различных методов, включая T> и (). Сведения об ошибке — это непрозрачный элемент для передачи дополнительных данных об ошибке. Это полезно, если существуют произвольные структурированные сведения, которые необходимо передать с ошибкой.  
  
### <a name="generating-faults"></a>Создание ошибок  
 В данном разделе объясняется процесс создания ошибки в ответ на условие ошибки, обнаруженное в канале или свойстве сообщения, созданном каналом. Типичным примером является отправка обратно ошибки в ответ на сообщение запроса, содержащее недопустимые данные.  
  
 При создании ошибки пользовательский канал должен не отправлять ее напрямую, а вызвать исключение и позволить вышестоящему уровню решить, необходимо ли преобразовывать это исключение в ошибку и как ее отправлять. Для облегчения данного преобразования канал должен предоставить реализацию `FaultConverter`, которая может преобразовать исключение, вызываемое пользовательским каналом, в соответствующую ошибку. `FaultConverter` определяется следующим образом.  
  
```csharp
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                   MessageVersion version);  
    protected abstract bool OnTryCreateFaultMessage(  
                                   Exception exception,
                                   out Message message);  
    public bool TryCreateFaultMessage(  
                                   Exception exception,
                                   out Message message);  
}  
```  
  
 Каждый канал, создающий пользовательские ошибки, должен реализовать преобразователь `FaultConverter` и вернуть его из вызова в `GetProperty<FaultConverter>`. Пользовательская `OnTryCreateFaultMessage` реализация должна либо преобразовать исключение в сбой, либо делегировать внутренний `FaultConverter`канал. Если канал является транспортом, он должен либо преобразовать исключение, либо делегировать в кодере, `FaultConverter` либо по умолчанию, `FaultConverter` предусмотренному в WCF. Преобразователь по умолчанию `FaultConverter` преобразует ошибки, соответствующие сообщениям об ошибках, которые указаны в WS-Addressing и SOAP. Ниже приведен пример реализации `OnTryCreateFaultMessage`.  
  
```csharp
public override bool OnTryCreateFaultMessage(Exception exception,
                                             out Message message)  
{  
    if (exception is ...)  
    {  
        message = ...;  
        return true;  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =
                    this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&
        (encoderConverter.TryCreateFaultMessage(  
         exception, out message)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =
                   FaultConverter.GetDefaultFaultConverter(  
                   this.channel.messageVersion);  
    return defaultConverter.TryCreateFaultMessage(  
                   exception,
                   out message);  
#else  
    FaultConverter inner =
                   this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateFaultMessage(exception, out message);  
    }  
    else  
    {  
        message = null;  
        return false;  
    }  
#endif  
}  
```  
  
 В этом шаблоне показано, что исключения, вызываемые между уровнями для требующих ошибок условий, должны содержать достаточно сведений для соответствующего генератора ошибок, чтобы создать правильную ошибку. Разработчики пользовательских каналов могут определять типы исключений, соответствующие условиям ошибок, если такие исключения не существуют. Обратите внимание, что исключения, затрагивающий разные уровни канала, должны передавать условие ошибки, а не непрозрачные данные ошибки.  
  
### <a name="fault-categories"></a>Категории ошибок  
 Обычно существует три категории ошибок.  
  
1. Ошибки, распространяющиеся на весь стек. Эти ошибки встречаются на любом уровне в стеке каналов, например, InvalidCardinalityAddressingException.  
  
2. Ошибки, встречающиеся выше определенного уровня в стеке. Например, некоторые ошибки, относящиеся к поточной транзакции или ролям безопасности.  
  
3. Ошибки, направленные на один уровень в стеке, например, ошибки номера последовательности WS-RM.  
  
 Категория 1. Как правило, ошибки WS-Addressing и SOAP. Базовый `FaultConverter` класс, предоставляемый WCF, преобразует ошибки, соответствующие сообщениям о неисправностях, указанным WS-Addressing и SOAP, так что вам не придется обрабатывать преобразование этих исключений самостоятельно.  
  
 Категория 2. Ошибки происходят, когда уровень добавляет в сообщение свойство, которое не полностью использует сведения о сообщении, относящиеся к данному уровню. Ошибки могут быть обнаружены позже, когда расположенный выше уровень запрашивает свойство сообщения для дальнейшей обработки сведений о сообщении. Такие каналы должны реализовать свойство `GetProperty`, заданное ранее, чтобы разрешить расположенному выше уровню отправлять обратно правильную ошибку. Примером этого может служить свойство TransactionMessageProperty. Это свойство добавляется в сообщение без полной проверки всех данных в заголовке (для проверки может понадобиться обратиться к координатору распределенных транзакций (DTC).  
  
 Категория 3. Ошибки создаются и отправляются только одним уровнем в процессоре. Таким образом, все исключения содержатся на одном уровне. Чтобы улучшить согласованность между каналами и упростить обслуживание, в пользовательском канале следует использовать приведенный ранее шаблон для создания сообщений об ошибках даже для внутренних ошибок.  
  
### <a name="interpreting-received-faults"></a>Интерпретация полученных ошибок  
 В данном разделе содержится руководство по созданию соответствующего исключения при получении сообщения об ошибке. Ниже приведено дерево принятия решений для обработки сообщения на каждом из уровней стека.  
  
1. Если слой считает сообщение недействительным, слой должен выполнять свою обработку "недействительного сообщения". Данная обработка зависит от уровня, но она может включать удаление сообщения, трассировку или вызов исключения, преобразуемого в ошибку. Примерами являются случаи, когда безопасность получает сообщение с ненадлежащей защитой, или диспетчер ресурсов получает сообщение с неправильным порядковым номером.  
  
2. В противном случае, если сообщение является сообщением о неисправности, которое применяется конкретно к слою, и сообщение не имеет смысла вне взаимодействия слоя, слой должен обрабатывать условие ошибки. Примером этого является ошибка «отказ последовательности диспетчера ресурсов», являющаяся бессмысленной для уровней, расположенных выше канала диспетчера ресурсов. Это подразумевает сбой канала диспетчера ресурсов и вызов из незавершенных операций.  
  
3. В противном случае сообщение должно быть возвращено из запроса() или получения(). Сюда также входят случаи, когда уровень распознает ошибку, но ошибка указывает на сбой запроса и не подразумевает сбой канала и вызов из незавершенных операций. Чтобы упростить использование, уровень должен реализовать `GetProperty<FaultConverter>` и возвратить производный класс `FaultConverter`, который может преобразовать исключение, переопределив `OnTryCreateException`.  
  
 Приведенные ниже объектные модели поддерживают преобразование сообщений в исключения.  
  
```csharp
public class FaultConverter  
{  
    public static FaultConverter GetDefaultFaultConverter(  
                                  MessageVersion version);  
    protected abstract bool OnTryCreateException(  
                                 Message message,
                                 MessageFault fault,
                                 out Exception exception);  
    public bool TryCreateException(  
                                 Message message,
                                 MessageFault fault,
                                 out Exception exception);  
}  
```  
  
 Уровень канала может реализовать `GetProperty<FaultConverter>`, чтобы поддержать преобразование сообщений об ошибках в исключения. Для этого переопределите `OnTryCreateException` и проверьте сообщение об ошибке. При подтверждении выполните преобразование, в противном случае запросите преобразование у внутреннего канала. Каналы транспорта должны делегировать `FaultConverter.GetDefaultFaultConverter` получение FaultConverter для SOAP и WS-Addressing.  
  
 Типичная реализация выглядит следующим образом.  
  
```csharp
public override bool OnTryCreateException(  
                            Message message,
                            MessageFault fault,
                            out Exception exception)  
{  
    if (message.Action == "...")  
    {  
        exception = ...;  
        return true;  
    }  
    // OR  
    if ((fault.Code.Name == "...") && (fault.Code.Namespace == "..."))  
    {  
        exception = ...;  
        return true;  
    }  
  
    if (fault.IsMustUnderstand)  
    {  
        if (fault.WasHeaderNotUnderstood(  
                   message.Headers, "...", "..."))  
        {  
            exception = new ProtocolException(...);  
            return true;  
        }  
    }  
  
#if IMPLEMENTING_TRANSPORT_CHANNEL  
    FaultConverter encoderConverter =
              this.encoder.GetProperty<FaultConverter>();  
    if ((encoderConverter != null) &&
        (encoderConverter.TryCreateException(  
                              message, fault, out exception)))  
    {  
        return true;  
    }  
  
    FaultConverter defaultConverter =  
             FaultConverter.GetDefaultFaultConverter(  
                             this.channel.messageVersion);  
    return defaultConverter.TryCreateException(  
                             message, fault, out exception);  
#else  
    FaultConverter inner =
                    this.innerChannel.GetProperty<FaultConverter>();  
    if (inner != null)  
    {  
        return inner.TryCreateException(message, fault, out exception);  
    }  
    else  
    {  
        exception = null;  
        return false;  
    }  
#endif  
}  
```  
  
 Для конкретных условий ошибки, имеющих определенные сценарии восстановления, можно задать производный класс `ProtocolException`.  
  
### <a name="mustunderstand-processing"></a>Обработка MustUnderstand  
 Протокол SOAP определяет общую ошибку для оповещения о том, что необходимый заголовок не был понят получателем. Эта ошибка называется ошибкой `mustUnderstand`. В WCF пользовательские `mustUnderstand` каналы никогда не генерируют неисправности. Вместо этого диспетчер WCF, который находится в верхней части стека связи WCF, проверяет, что все заголовки, которые были помечены как MustUnderstand'true, были поняты базовым стеком. Если какой-то из заголовков не был понят, в этой точке создается ошибка `mustUnderstand`. (Пользователь может отключить обработку `mustUnderstand`, и приложение будет принимать все заголовки сообщений. В этом случае приложение отвечает `mustUnderstand` за выполнение обработки.) Сгенерированный сбой включает в себя заголовок NotUnderstood, который содержит имена всех заголовков с MustUnderstand'true, которые не были поняты.  
  
 Если канал протокола отправляет пользовательский заголовок со значением MustUnderstand=true и получает ошибку `mustUnderstand`, он должен определить, вызвана ли эта ошибка отправленным заголовком. Для этого можно использовать два члена в классе `MessageFault`:  
  
```csharp
public class MessageFault  
{  
    ...  
    public bool IsMustUnderstandFault { get; }  
    public static bool WasHeaderNotUnderstood(MessageHeaders headers,
        string name, string ns) { }  
    ...  
  
}  
```  
  
 `IsMustUnderstandFault` возвращает значение `true`, если это ошибка `mustUnderstand`. `WasHeaderNotUnderstood` возвращает значение `true`, если заголовок с указанным именем и пространством имен включен в ошибку в качестве заголовка NotUnderstood.  В противном случае возвращается значение `false`.  
  
 Если канал выдает заголовок со значением MustUnderstand = true, уровень также должен реализовать шаблон API для создания исключения и преобразовать ошибки `mustUnderstand`, вызванные этим заголовком, в более полезное исключение, описанное ранее.  
  
## <a name="tracing"></a>Трассировка  
 Платформа .NET Framework обеспечивает механизм для трассировки выполнения программы, который полезен для диагностики приложений в производственной среде или периодических проблем, когда нет возможности использовать отладчик для пошаговой проверки кода. Основные компоненты этого механизма расположены в пространстве имен <xref:System.Diagnostics?displayProperty=nameWithType> и состоят из следующих элементов.  
  
- <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType>, являющийся источником записываемых данных трассировки, <xref:System.Diagnostics.TraceListener?displayProperty=nameWithType>, являющийся абстрактным базовым классом для конкретных прослушивателей, которые получают подлежащие трассировке сведения из <xref:System.Diagnostics.TraceSource> и выводят их в назначение, зависящее от прослушивателя. Например, <xref:System.Diagnostics.XmlWriterTraceListener> выводит данные трассировки в XML-файл. Наконец, класс <xref:System.Diagnostics.TraceSwitch?displayProperty=nameWithType> позволяет пользователю управлять детализацией трассировке и обычно задается в конфигурации.  
  
- В дополнение к основным компонентам, вы можете использовать [инструмент просмотра службы (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) для просмотра и поиска следов WCF. Инструмент разработан специально для следов файлов, генерируемых <xref:System.Diagnostics.XmlWriterTraceListener>WCF и выписанных с помощью. На следующем рисунке показаны различные компоненты, задействованные с трассировке.  
  
 ![Обработка исключений и неисправностей](./media/wcfc-tracinginchannelsc.gif "wcfc_TracingInChannelsc")  
  
### <a name="tracing-from-a-custom-channel"></a>Трассировка из пользовательского канала  
 Пользовательские каналы должны записывать сообщения трассировки, чтобы помочь с диагностикой проблем, когда невозможно применить отладчик на запущенном приложении. Это предполагает две высокоуровневые задачи: создание экземпляра класса <xref:System.Diagnostics.TraceSource> и вызов его методов для записи трассировок.  
  
 При создании экземпляра класса <xref:System.Diagnostics.TraceSource> указываемая строка становится именем источника. Данное имя используется для настройки (включения/отключения/установки уровня трассировки) источника трассировки. Оно также отображается непосредственно в выводе трассировки. Пользовательские каналы должны использовать уникальное имя источника, чтобы при чтении вывода трассировки можно быть понять, откуда поступают данные трассировки. Для имени источника трассировки принято использовать имя сборки, записывающей информацию. Например, WCF использует System.ServiceModel в качестве источника информации, записанной из сборки System.ServiceModel.  
  
 После создания источника трассировки вызываются его методы <xref:System.Diagnostics.TraceSource.TraceData%2A>, <xref:System.Diagnostics.TraceSource.TraceEvent%2A> или <xref:System.Diagnostics.TraceSource.TraceInformation%2A>, чтобы внести записи трассировки в прослушиватели трассировки. Для каждой внесенной записи трассировки необходимо классифицировать тип события как один из типов, определенный в <xref:System.Diagnostics.TraceEventType>. Данная классификация и установка уровня трассировки определяют, выводится ли запись трассировки прослушивателю. Например, установка в конфигурации уровней трассировки `Warning` позволяет записывать трассировки `Warning`, `Error` и `Critical`, но блокировать записи «Данные» и «Подробно». Ниже приведен пример создания источника трассировки и внесения записи на уровне «Данные».  
  
```csharp
using System.Diagnostics;  
//...  
TraceSource udpSource = new TraceSource("Microsoft.Samples.Udp");  
//...  
udpsource.TraceInformation("UdpInputChannel received a message");  
```  
  
> [!IMPORTANT]
> Настоятельно рекомендуется указать имя источника трассировки, являющееся уникальным для пользовательского канала, чтобы при считывании выходных данных трассировки было понятно, откуда они поступили.  
  
#### <a name="integrating-with-the-trace-viewer"></a>Интеграция со средством просмотра трассировки  
 Следы, генерируемые вашим каналом, могут быть высвобождаемы в формате, читаемом [инструментом Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md) с помощью <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> в качестве слушателя трассировки. Этим обычно не занимают разработчики каналов. Скорее, именно пользователю приложения (или человеку, устранять приложение) необходимо настроить слушателя этого следа в файл конфигурации приложения. Например, следующая конфигурация выполняет вывод данных трассировки из пространства имен <xref:System.ServiceModel?displayProperty=nameWithType> и `Microsoft.Samples.Udp` в файл с именем `TraceEventsFile.e2e`:  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <!-- configure System.ServiceModel trace source -->  
      <source name="System.ServiceModel" switchValue="Verbose"
              propagateActivity="true">  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
      <!-- configure Microsoft.Samples.Udp trace source -->  
      <source name="Microsoft.Samples.Udp" switchValue="Verbose" >  
        <listeners>  
          <add name="e2e" />  
        </listeners>  
      </source>  
    </sources>  
    <!--   
    Define a shared trace listener that outputs to TraceFile.e2e  
    The listener name is e2e   
    -->  
    <sharedListeners>  
      <add name="e2e" type="System.Diagnostics.XmlWriterTraceListener"  
        initializeData=".\TraceFile.e2e"/>  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
</configuration>  
```  
  
#### <a name="tracing-structured-data"></a>Трассировка структурированных данных  
 В классе <xref:System.Diagnostics.TraceSource?displayProperty=nameWithType> имеется метод <xref:System.Diagnostics.TraceSource.TraceData%2A>, который принимает один или несколько объектов для включения в запись трассировки. Как правило, метод <xref:System.Object.ToString%2A?displayProperty=nameWithType> вызывается на каждом объекте, и результирующая строка записывается как часть записи. При использовании <xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType> для вывода данных трассировки можно передавать класс <xref:System.Xml.XPath.IXPathNavigable?displayProperty=nameWithType> в виде объекта данных в <xref:System.Diagnostics.TraceSource.TraceData%2A>. Результирующая запись трассировки содержит данные XML, предоставленные <xref:System.Xml.XPath.XPathNavigator?displayProperty=nameWithType>. Ниже приведен пример записи с данными приложения XML.  
  
```xml  
<E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">  
  <System xmlns="...">  
    <EventID>12</EventID>  
    <Type>3</Type>  
    <SubType Name="Information">0</SubType>  
    <Level>8</Level>  
    <TimeCreated SystemTime="2006-01-13T22:58:03.0654832Z" />  
    <Source Name="Microsoft.ServiceModel.Samples.Udp" />  
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />  
    <Execution  ProcessName="UdpTestConsole"
                ProcessID="3348" ThreadID="4" />  
    <Channel />  
    <Computer>COMPUTER-LT01</Computer>  
  </System>  
<!-- XML application data -->  
  <ApplicationData>  
  <TraceData>  
   <DataItem>  
   <TraceRecord
     Severity="Information"  
     xmlns="…">  
        <TraceIdentifier>some trace id</TraceIdentifier>  
        <Description>EndReceive called</Description>  
        <AppDomain>UdpTestConsole.exe</AppDomain>  
        <Source>UdpInputChannel</Source>  
      </TraceRecord>  
    </DataItem>  
  </TraceData>  
  </ApplicationData>  
</E2ETraceEvent>  
```  
  
 Зритель трассировки WCF понимает схему `TraceRecord` элемента, показанного ранее, и извлекает данные из своих элементов ребенка и отображает их в таблентном формате. Канал должен использовать эту схему при трассировке структурированных данных приложения, чтобы пользователи средства Svctraceviewer.exe могли считывать данные.
