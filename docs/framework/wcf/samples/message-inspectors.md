---
title: Инспекторы сообщений
ms.date: 03/30/2017
ms.assetid: 9bd1f305-ad03-4dd7-971f-fa1014b97c9b
ms.openlocfilehash: 7b8cc0f8e8aa0544c531566a8fe35f54a3914896
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977297"
---
# <a name="message-inspectors"></a><span data-ttu-id="e43a8-102">Инспекторы сообщений</span><span class="sxs-lookup"><span data-stu-id="e43a8-102">Message Inspectors</span></span>
<span data-ttu-id="e43a8-103">В этом образце демонстрируется, как реализовать и настроить инспекторы сообщений клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-103">This sample demonstrates how to implement and configure client and service message inspectors.</span></span>  
  
 <span data-ttu-id="e43a8-104">Инспектор сообщений - это объект расширяемости, который можно использовать программно или посредством конфигурации в среде выполнения клиента модели служб и среде выполнения распределения для проверки и изменения сообщений перед их получением или отправкой.</span><span class="sxs-lookup"><span data-stu-id="e43a8-104">A message inspector is an extensibility object that can be used in the service model's client runtime and dispatch runtime programmatically or through configuration and that can inspect and alter messages after they are received or before they are sent.</span></span>  
  
 <span data-ttu-id="e43a8-105">В этом образце реализуется базовый механизм проверки сообщений клиента и службы, который проверяет входящие сообщения на основе набора настраиваемых документов XML-схемы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-105">This sample implements a basic client and service message validation mechanism that validates incoming messages against a set of configurable XML Schema documents.</span></span> <span data-ttu-id="e43a8-106">Обратите внимание, что в этом образце сообщения проверяются не для всех операций.</span><span class="sxs-lookup"><span data-stu-id="e43a8-106">Note that this sample does not validate messages for each operation.</span></span> <span data-ttu-id="e43a8-107">Данное упрощение сделано преднамеренно.</span><span class="sxs-lookup"><span data-stu-id="e43a8-107">This is an intentional simplification.</span></span>  
  
## <a name="message-inspector"></a><span data-ttu-id="e43a8-108">Инспектор сообщений</span><span class="sxs-lookup"><span data-stu-id="e43a8-108">Message Inspector</span></span>  
 <span data-ttu-id="e43a8-109">Инспекторы сообщений клиента реализуют интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector>, а инспекторы сообщений службы - интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-109">Client message inspectors implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> interface and service message inspectors implement the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> interface.</span></span> <span data-ttu-id="e43a8-110">Реализации можно объединить в один класс для создания инспектора сообщений, работающего на обеих сторонах.</span><span class="sxs-lookup"><span data-stu-id="e43a8-110">The implementations can be combined into a single class to form a message inspector that works for both sides.</span></span> <span data-ttu-id="e43a8-111">В данном образце реализуется такой комбинированный инспектор сообщений.</span><span class="sxs-lookup"><span data-stu-id="e43a8-111">This sample implements such a combined message inspector.</span></span> <span data-ttu-id="e43a8-112">Инспектор создается, передавая набор схем, на основе которых проверяются входящие и исходящие сообщения, и позволяет разработчику определить, следует ли проверять входящие или исходящие сообщения, а также использовать ли режим диспетчеризации или режим клиента, который влияет на обработку ошибок, как описано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e43a8-112">The inspector is constructed passing in a set of schemas against which incoming and outgoing messages are validated and allows the developer to specify whether incoming or outgoing messages are validated and whether the inspector is in dispatch or client mode, which affects the error handling as discussed later in this topic.</span></span>  
  
```csharp
public class SchemaValidationMessageInspector : IClientMessageInspector, IDispatchMessageInspector  
{  
    XmlSchemaSet schemaSet;  
    bool validateRequest;  
    bool validateReply;  
    bool isClientSide;  
    [ThreadStatic]  
    bool isRequest;  
  
    public SchemaValidationMessageInspector(XmlSchemaSet schemaSet,  
         bool validateRequest, bool validateReply, bool isClientSide)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = validateReply;  
        this.validateRequest = validateRequest;  
        this.isClientSide = isClientSide;  
    }  
```  
  
 <span data-ttu-id="e43a8-113">Любой инспектор сообщений службы (диспетчера) должен реализовывать два метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector>: <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> и <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-113">Any service (dispatcher) message inspector must implement the two <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector> methods <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29>.</span></span>  
  
 <span data-ttu-id="e43a8-114">Метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> вызывается диспетчером при получении сообщения, обработке сообщения стеком каналов и назначении сообщения службе, но перед его десериализацией и отправкой операции.</span><span class="sxs-lookup"><span data-stu-id="e43a8-114"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> is invoked by the dispatcher when a message has been received, processed by the channel stack and assigned to a service, but before it is deserialized and dispatched to an operation.</span></span> <span data-ttu-id="e43a8-115">Если входящее сообщение было зашифровано, оно поступает в инспектор сообщений в расшифрованном виде.</span><span class="sxs-lookup"><span data-stu-id="e43a8-115">If the incoming message was encrypted, the message is already decrypted when it reaches the message inspector.</span></span> <span data-ttu-id="e43a8-116">Метод получает сообщение `request`, переданное в качестве ссылочного параметра, который позволяет проверить, изменить или заменить сообщение при необходимости.</span><span class="sxs-lookup"><span data-stu-id="e43a8-116">The method gets the `request` message passed as a reference parameter, which allows the message to be inspected, manipulated or replaced as required.</span></span> <span data-ttu-id="e43a8-117">Возвращаемое значение может быть любым объектом и используется как объект состояния корреляции, передаваемый методу <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> при возврате службой ответа на текущее сообщение.</span><span class="sxs-lookup"><span data-stu-id="e43a8-117">The return value can be any object and is used as a correlation state object that is passed to <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> when the service returns a reply to the current message.</span></span> <span data-ttu-id="e43a8-118">В этом образце метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> делегирует проверку сообщения закрытому локальному методу `ValidateMessageBody` и не возвращает объект состояния корреляции.</span><span class="sxs-lookup"><span data-stu-id="e43a8-118">In this sample, <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> delegates the inspection (validation) of the message to the private, local method `ValidateMessageBody` and returns no correlation state object.</span></span> <span data-ttu-id="e43a8-119">Этот метод гарантирует, что службе не будут передаваться недопустимые сообщения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-119">This method ensures that no invalid messages pass into the service.</span></span>  
  
```csharp  
object IDispatchMessageInspector.AfterReceiveRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel, System.ServiceModel.InstanceContext instanceContext)  
{  
    if (validateRequest)  
    {  
        // inspect the message. If a validation error occurs,  
        // the thrown fault exception bubbles up.  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="e43a8-120">Метод <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> вызывается, когда ответ готов для отправки клиенту или, в случае односторонних сообщений, после обработки входящего сообщения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-120"><xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%28System.ServiceModel.Channels.Message%40%2CSystem.Object%29> is invoked whenever a reply is ready to be sent back to a client, or in the case of one-way messages, when the incoming message has been processed.</span></span> <span data-ttu-id="e43a8-121">Это позволяет симметрично вызывать необходимые расширения независимо от шаблона обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="e43a8-121">This allows extensions to count on being called symmetrically, regardless of MEP.</span></span> <span data-ttu-id="e43a8-122">Как и в случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, сообщение передается в качестве ссылочного параметра и может быть проверено, изменено или заменено.</span><span class="sxs-lookup"><span data-stu-id="e43a8-122">As with <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, the message is passed as a reference parameter and can be inspected, modified or replaced.</span></span> <span data-ttu-id="e43a8-123">Проверка сообщения, выполняемая в этом образце, повторно делегируется методу `ValidMessageBody`, но в данном случае процедура обработки ошибок проверки немного отличается.</span><span class="sxs-lookup"><span data-stu-id="e43a8-123">The validation of the message that is performed in this sample is again delegated to the `ValidMessageBody` method, but the handling of validation errors is slightly different in this case.</span></span>  
  
 <span data-ttu-id="e43a8-124">При возникновении ошибки проверки метод `ValidateMessageBody` вызывает исключения, унаследованные от <xref:System.ServiceModel.FaultException>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-124">If a validation error occurs on the service, the `ValidateMessageBody` method throws <xref:System.ServiceModel.FaultException>-derived exceptions.</span></span> <span data-ttu-id="e43a8-125">В случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A> эти исключения могут размещаться в инфраструктуре модели служб, где они автоматически преобразуются в ошибки SOAP и передаются клиенту.</span><span class="sxs-lookup"><span data-stu-id="e43a8-125">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.AfterReceiveRequest%2A>, these exceptions can be put into the service model infrastructure where they are automatically transformed into SOAP faults and relayed to the client.</span></span> <span data-ttu-id="e43a8-126">В случае метода <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A> исключения <xref:System.ServiceModel.FaultException> не следует размещать в инфраструктуре, поскольку преобразование исключений ошибок, вызванных службой, происходит перед вызовом инспектора сообщений.</span><span class="sxs-lookup"><span data-stu-id="e43a8-126">In <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector.BeforeSendReply%2A>, <xref:System.ServiceModel.FaultException> exceptions must not be put into the infrastructure, because the transformation of fault exceptions thrown by the service occurs before the message inspector is called.</span></span> <span data-ttu-id="e43a8-127">Поэтому следующая реализация перехватывает известное исключение `ReplyValidationFault` и заменяет ответное сообщение явным сообщением об ошибке.</span><span class="sxs-lookup"><span data-stu-id="e43a8-127">Therefore the following implementation catches the known `ReplyValidationFault` exception and replaces the reply message with an explicit fault message.</span></span> <span data-ttu-id="e43a8-128">Этот метод гарантирует, что реализацией службы не будут возвращаться недопустимые сообщения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-128">This method ensures that no invalid messages are returned by the service implementation.</span></span>  
  
```csharp  
void IDispatchMessageInspector.BeforeSendReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        // Inspect the reply, catch a possible validation error   
        try  
        {  
            ValidateMessageBody(ref reply, false);  
        }  
        catch (ReplyValidationFault fault)  
        {  
            // if a validation error occurred, the message is replaced  
            // with the validation fault.  
            reply = Message.CreateMessage(reply.Version,   
                    fault.CreateMessageFault(), reply.Headers.Action);  
        }  
    }  
```  
  
 <span data-ttu-id="e43a8-129">Инспектор сообщений клиента очень похож на инспектор сообщений службы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-129">The client message inspector is very similar.</span></span> <span data-ttu-id="e43a8-130">На основе <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> необходимо реализовать два метода: <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> и <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-130">The two methods that must be implemented from <xref:System.ServiceModel.Dispatcher.IClientMessageInspector> are <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.AfterReceiveReply%2A> and <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A>.</span></span>  
  
 <span data-ttu-id="e43a8-131">Метод <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> вызывается при создании сообщения клиентским приложением или модулем форматирования операций.</span><span class="sxs-lookup"><span data-stu-id="e43a8-131"><xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> is invoked when the message has been composed either by the client application or by the operation formatter.</span></span> <span data-ttu-id="e43a8-132">Как и в случае инспекторов сообщений диспетчера, сообщение может быть просто проверено или полностью заменено.</span><span class="sxs-lookup"><span data-stu-id="e43a8-132">As with the dispatcher message inspectors, the message can just be inspected or entirely replaced.</span></span> <span data-ttu-id="e43a8-133">В этом образце инспектор выполняет делегирование тому же локальному вспомогательному методу `ValidateMessageBody`, который используется для инспекторов сообщений диспетчера.</span><span class="sxs-lookup"><span data-stu-id="e43a8-133">In this sample, the inspector delegates to the same local `ValidateMessageBody` helper method that is also used for the dispatch message inspectors.</span></span>  
  
 <span data-ttu-id="e43a8-134">Различие в поведении между проверкой клиента и службы (как указано в конструкторе) заключается в том, что проверка клиента вызывает локальные исключения, которые размещаются в пользовательском коде, поскольку они возникают локально и не по причине сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-134">The behavioral difference between the client and service validation (as specified in the constructor) is that the client validation throws local exceptions that are put into the user code because they occur locally and not because of a service failure.</span></span> <span data-ttu-id="e43a8-135">Как правило, инспекторы диспетчера службы выдают сообщения об ошибках, а инспекторы клиента - исключения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-135">Generally, the rule is that service dispatcher inspectors throw faults and that client inspectors throw exceptions.</span></span>  
  
 <span data-ttu-id="e43a8-136">Эта реализация <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> гарантирует, что службе не будут передаваться недопустимые сообщения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-136">This <xref:System.ServiceModel.Dispatcher.IClientMessageInspector.BeforeSendRequest%2A> implementation ensures that no invalid messages are sent to the service.</span></span>  
  
```csharp  
object IClientMessageInspector.BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
{  
    if (validateRequest)  
    {  
        ValidateMessageBody(ref request, true);  
    }  
    return null;  
}  
```  
  
 <span data-ttu-id="e43a8-137">Реализация `AfterReceiveReply` гарантирует, что полученные от службы недопустимые сообщения не будут передаваться пользовательскому коду клиента.</span><span class="sxs-lookup"><span data-stu-id="e43a8-137">The `AfterReceiveReply` implementation ensures that no invalid messages received from the service are relayed to the client user code.</span></span>  
  
```csharp  
void IClientMessageInspector.AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
{  
    if (validateReply)  
    {  
        ValidateMessageBody(ref reply, false);  
    }  
}  
```  
  
 <span data-ttu-id="e43a8-138">Ключевым элементом данного инспектора сообщений является метод `ValidateMessageBody`.</span><span class="sxs-lookup"><span data-stu-id="e43a8-138">The heart of this particular message inspector is the `ValidateMessageBody` method.</span></span> <span data-ttu-id="e43a8-139">Для выполнения работы он обертывает проверяющее средство чтения <xref:System.Xml.XmlReader> вокруг поддерева содержимого тела переданного сообщения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-139">To perform its work, it wraps a validating <xref:System.Xml.XmlReader> around the body content sub-tree of the passed message.</span></span> <span data-ttu-id="e43a8-140">Средство чтения заполняется набором схем, которые содержит инспектор сообщений, и обратный вызов проверки настраивается на делегат, относящийся к обработчику `InspectionValidationHandler`, который определен наряду с данным методом.</span><span class="sxs-lookup"><span data-stu-id="e43a8-140">The reader is populated with the set of schemas that the message inspector holds and the validation callback is set to a delegate referring to the `InspectionValidationHandler` that is defined alongside this method.</span></span> <span data-ttu-id="e43a8-141">Для выполнения проверки сообщение считывается и буферизуется в поддерживаемом потоком памяти объекте <xref:System.Xml.XmlDictionaryWriter>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-141">To perform the validation, the message is then read and spooled into a memory stream-backed <xref:System.Xml.XmlDictionaryWriter>.</span></span> <span data-ttu-id="e43a8-142">При возникновении ошибки или предупреждения в процессе проверки вызывается метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="e43a8-142">If a validation error or warning occurs in the process, the callback method is invoked.</span></span>  
  
 <span data-ttu-id="e43a8-143">При отсутствии ошибок создается новое сообщение, копирующее свойства и заголовки из исходного сообщения и использующее уже проверенный набор сведений в потоке памяти, который обернут объектом <xref:System.Xml.XmlDictionaryReader> и добавлен в заменяющее сообщение.</span><span class="sxs-lookup"><span data-stu-id="e43a8-143">If no error occurs, a new message is constructed that copies the properties and headers from the original message and uses the now-validated infoset in the memory stream, which is wrapped by an <xref:System.Xml.XmlDictionaryReader> and added to the replacement message.</span></span>  
  
```csharp  
void ValidateMessageBody(ref System.ServiceModel.Channels.Message message, bool isRequest)  
{  
    if (!message.IsFault)  
    {  
        XmlDictionaryReaderQuotas quotas =   
                new XmlDictionaryReaderQuotas();  
        XmlReader bodyReader =   
            message.GetReaderAtBodyContents().ReadSubtree();  
        XmlReaderSettings wrapperSettings =   
                              new XmlReaderSettings();  
        wrapperSettings.CloseInput = true;  
        wrapperSettings.Schemas = schemaSet;  
        wrapperSettings.ValidationFlags =   
                                XmlSchemaValidationFlags.None;  
        wrapperSettings.ValidationType = ValidationType.Schema;  
        wrapperSettings.ValidationEventHandler += new   
           ValidationEventHandler(InspectionValidationHandler);  
        XmlReader wrappedReader = XmlReader.Create(bodyReader,   
                                            wrapperSettings);  
  
        // pull body into a memory backed writer to validate  
        this.isRequest = isRequest;  
        MemoryStream memStream = new MemoryStream();  
        XmlDictionaryWriter xdw =  
              XmlDictionaryWriter.CreateBinaryWriter(memStream);  
        xdw.WriteNode(wrappedReader, false);  
        xdw.Flush(); memStream.Position = 0;  
        XmlDictionaryReader xdr =   
        XmlDictionaryReader.CreateBinaryReader(memStream, quotas);  
  
        // reconstruct the message with the validated body  
        Message replacedMessage =   
            Message.CreateMessage(message.Version, null, xdr);  
        replacedMessage.Headers.CopyHeadersFrom(message.Headers);  
        replacedMessage.Properties.CopyProperties(message.Properties);  
        message = replacedMessage;  
    }  
}  
```  
  
 <span data-ttu-id="e43a8-144">Метод `InspectionValidationHandler` вызывается проверяющим объектом <xref:System.Xml.XmlReader> при каждом возникновении ошибки или предупреждения проверки схемы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-144">The `InspectionValidationHandler` method is called by the validating <xref:System.Xml.XmlReader> whenever a schema validation error or warning occurs.</span></span> <span data-ttu-id="e43a8-145">Следующая реализация работает только с ошибками и не учитывает все предупреждения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-145">The following implementation only works with errors and ignores all warnings.</span></span>  
  
 <span data-ttu-id="e43a8-146">При первом рассмотрении может показаться возможной вставка проверяющего объекта <xref:System.Xml.XmlReader> в сообщение с инспектором сообщений, чтобы проверка происходила по мере обработки сообщения без его буферизации.</span><span class="sxs-lookup"><span data-stu-id="e43a8-146">On first consideration, it might seem possible to inject a validating <xref:System.Xml.XmlReader> into the message with the message inspector and let the validation happen as the message is processed and without buffering the message.</span></span> <span data-ttu-id="e43a8-147">Однако это означает, что по мере обнаружения недопустимых XML-узлов данный обратный вызов создает исключения проверки в некоторой области инфраструктуры модели служб или пользовательского кода, приводящие к непредсказуемому поведению.</span><span class="sxs-lookup"><span data-stu-id="e43a8-147">That, however, means that this callback throws the validation exceptions somewhere into the service model infrastructure or the user code as invalid XML nodes are detected, resulting in unpredictable behavior.</span></span> <span data-ttu-id="e43a8-148">Подход на основе буферизации полностью ограждает пользовательский код от недопустимых сообщений.</span><span class="sxs-lookup"><span data-stu-id="e43a8-148">The buffering approach shields the user code from invalid messages, entirely.</span></span>  
  
 <span data-ttu-id="e43a8-149">Как отмечалось ранее, исключения, вызываемые обработчиком на стороне клиента и на стороне службы различаются.</span><span class="sxs-lookup"><span data-stu-id="e43a8-149">As previously discussed, the exceptions thrown by the handler differ between the client and the service.</span></span> <span data-ttu-id="e43a8-150">На стороне службы исключения наследуются от <xref:System.ServiceModel.FaultException>, на стороне клиента исключения являются регулярными пользовательскими исключениями.</span><span class="sxs-lookup"><span data-stu-id="e43a8-150">On the service, the exceptions are derived from <xref:System.ServiceModel.FaultException>, on the client the exceptions are regular custom exceptions.</span></span>  
  
```csharp  
        void InspectionValidationHandler(object sender, ValidationEventArgs e)  
{  
    if (e.Severity == XmlSeverityType.Error)  
    {  
        // We are treating client and service side validation errors  
        // differently here. Client side errors cause exceptions  
        // and are thrown straight up to the user code. Service side  
        // validations cause faults.  
        if (isClientSide)  
        {  
            if (isRequest)  
            {  
                throw new RequestClientValidationException(e.Message);  
            }  
            else  
            {  
                throw new ReplyClientValidationException(e.Message);  
            }  
        }  
        else  
        {  
            if (isRequest)  
            {  
                // this fault is caught by the ServiceModel   
                // infrastructure and turned into a fault reply.  
                throw new RequestValidationFault(e.Message);  
             }  
             else  
             {  
                // this fault is caught and turned into a fault message  
                // in BeforeSendReply in this class  
                throw new ReplyValidationFault(e.Message);  
              }  
          }  
      }  
    }  
```  
  
## <a name="behavior"></a><span data-ttu-id="e43a8-151">Поведение</span><span class="sxs-lookup"><span data-stu-id="e43a8-151">Behavior</span></span>  
 <span data-ttu-id="e43a8-152">Инспекторы сообщений являются расширениями среды выполнения клиента или среды выполнения распределения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-152">Message inspectors are extensions to the client runtime or the dispatch runtime.</span></span> <span data-ttu-id="e43a8-153">Такие расширения настраиваются с помощью *поведений*.</span><span class="sxs-lookup"><span data-stu-id="e43a8-153">Such extensions are configured using *behaviors*.</span></span> <span data-ttu-id="e43a8-154">Поведение - это класс, изменяющий поведение среды выполнения модели служб путем изменения конфигурации по умолчанию или добавления в нее расширений (например, инспекторов сообщений).</span><span class="sxs-lookup"><span data-stu-id="e43a8-154">A behavior is a class that changes the behavior of the service model runtime by changing the default configuration or adding extensions (such as message inspectors) to it.</span></span>  
  
 <span data-ttu-id="e43a8-155">Следующий класс `SchemaValidationBehavior` является поведением, которое используется для добавления инспектора сообщений, создаваемого в данном образце, в среду выполнения клиента или среду выполнения распределения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-155">The following `SchemaValidationBehavior` class is the behavior used to add this sample's message inspector to the client or dispatch runtime.</span></span> <span data-ttu-id="e43a8-156">В обоих случаях реализация достаточно проста.</span><span class="sxs-lookup"><span data-stu-id="e43a8-156">The implementation is rather basic in both cases.</span></span> <span data-ttu-id="e43a8-157">В случае <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> и <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A> инспектор сообщений создается и добавляется в коллекцию <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> соответствующей среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-157">In <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyClientBehavior%2A> and <xref:System.ServiceModel.Description.IEndpointBehavior.ApplyDispatchBehavior%2A>, the message inspector is created and added to the <xref:System.ServiceModel.Dispatcher.ClientRuntime.MessageInspectors%2A> collection of the respective runtime.</span></span>  
  
```csharp
public class SchemaValidationBehavior : IEndpointBehavior  
{  
    XmlSchemaSet schemaSet;   
    bool validateRequest;   
    bool validateReply;  
  
    public SchemaValidationBehavior(XmlSchemaSet schemaSet, bool   
                           inspectRequest, bool inspectReply)  
    {  
        this.schemaSet = schemaSet;  
        this.validateReply = inspectReply;  
        this.validateRequest = inspectRequest;  
    }  
    #region IEndpointBehavior Members  
  
    public void AddBindingParameters(ServiceEndpoint endpoint,   
       System.ServiceModel.Channels.BindingParameterCollection   
                                            bindingParameters)  
    {  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint,   
            System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                      validateRequest, validateReply, true);  
            clientRuntime.MessageInspectors.Add(inspector);  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint,   
         System.ServiceModel.Dispatcher.EndpointDispatcher   
                                          endpointDispatcher)  
    {  
        SchemaValidationMessageInspector inspector =   
           new SchemaValidationMessageInspector(schemaSet,   
                        validateRequest, validateReply, false);  
   endpointDispatcher.DispatchRuntime.MessageInspectors.Add(inspector);  
    }  
  
   public void Validate(ServiceEndpoint endpoint)  
   {  
   }  
  
    #endregion  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="e43a8-158">Данное конкретное поведение не дублируется как атрибут, поэтому его нельзя декларативно добавить в тип контракта типа службы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-158">This particular behavior does not double as an attribute and therefore cannot be added declaratively onto a contract type of a service type.</span></span> <span data-ttu-id="e43a8-159">Это решение было принято намеренно, поскольку коллекцию схем нельзя загрузить в объявление атрибута, а обращение к размещению дополнительной конфигурации (например, к параметрам приложения) в этом атрибуте означает создание элемента конфигурации, не согласованного с остальной конфигурацией модели служб.</span><span class="sxs-lookup"><span data-stu-id="e43a8-159">This is a by-design decision made because the schema collection cannot be loaded in an attribute declaration and referring to an extra configuration location (for instance to the application settings) in this attribute means creating a configuration element that is not consistent with the rest of the service model configuration.</span></span> <span data-ttu-id="e43a8-160">Поэтому данное поведение можно добавить только императивно посредством кода и посредством расширения конфигурации модели служб.</span><span class="sxs-lookup"><span data-stu-id="e43a8-160">Therefore, this behavior can only be added imperatively through code and through a service model configuration extension.</span></span>  
  
## <a name="adding-the-message-inspector-through-configuration"></a><span data-ttu-id="e43a8-161">Добавление инспектора сообщений с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="e43a8-161">Adding the Message Inspector through Configuration</span></span>  
 <span data-ttu-id="e43a8-162">Для настройки пользовательского поведения в конечной точке в файле конфигурации приложения модели службы требуются разработчики для создания *элемента расширения* конфигурации, представленного классом, производным от <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-162">For configuring a custom behavior on an endpoint in the application configuration file, the service model requires implementers to create a configuration *extension element* represented by a class derived from <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>.</span></span> <span data-ttu-id="e43a8-163">Это расширение затем необходимо добавить в раздел конфигурации модели служб для расширений, как показано для следующего расширения, рассматриваемого в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="e43a8-163">This extension must then be added to the service model's configuration section for extensions as shown for the following extension discussed in this section.</span></span>  
  
```xml  
<system.serviceModel>  
…  
   <extensions>  
      <behaviorExtensions>  
        <add name="schemaValidator" type="Microsoft.ServiceModel.Samples.SchemaValidationBehaviorExtensionElement, MessageInspectors, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
      </behaviorExtensions>  
    </extensions>  
…  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e43a8-164">Расширения можно добавить в файл конфигурации приложения или ASP.NET, что является наиболее распространенным вариантом, либо в файл конфигурации компьютера.</span><span class="sxs-lookup"><span data-stu-id="e43a8-164">Extensions can be added in the application or ASP.NET configuration file, which is the most common choice, or in the machine configuration file.</span></span>  
  
 <span data-ttu-id="e43a8-165">При добавлении расширения в область конфигурации можно добавить поведение в конфигурацию поведения, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e43a8-165">When the extension is added to a configuration scope, the behavior can be added to a behavior configuration as it is shown in the following code.</span></span> <span data-ttu-id="e43a8-166">Конфигурации поведения являются элементами многократного использования, которые можно по мере необходимости применять к нескольким конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="e43a8-166">Behavior configurations are reusable elements that can be applied to multiple endpoints as required.</span></span> <span data-ttu-id="e43a8-167">Поскольку настраиваемое здесь конкретное поведение реализует интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, оно допустимо только в соответствующем разделе файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e43a8-167">Because the particular behavior to be configured here implements <xref:System.ServiceModel.Description.IEndpointBehavior>, it is only valid in the respective configuration section in the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
   <behaviors>  
      …  
     <endpointBehaviors>  
        <behavior name="HelloServiceEndpointBehavior">  
          <schemaValidator validateRequest="True" validateReply="True">  
            <schemas>  
              <add location="messages.xsd" />    
            </schemas>  
          </schemaValidator>  
        </behavior>  
      </endpointBehaviors>  
      …  
    </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="e43a8-168">Элемент `<schemaValidator>`, настраивающий инспектор сообщений, поддерживается классом `SchemaValidationBehaviorExtensionElement`.</span><span class="sxs-lookup"><span data-stu-id="e43a8-168">The `<schemaValidator>` element that configures the message inspector is backed by the `SchemaValidationBehaviorExtensionElement` class.</span></span> <span data-ttu-id="e43a8-169">Класс предоставляет два открытых свойства логического типа: `ValidateRequest` и `ValidateReply`.</span><span class="sxs-lookup"><span data-stu-id="e43a8-169">The class exposes two Boolean public properties named `ValidateRequest` and `ValidateReply`.</span></span> <span data-ttu-id="e43a8-170">Оба свойства отмечены атрибутом <xref:System.Configuration.ConfigurationPropertyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="e43a8-170">Both of these are marked with a <xref:System.Configuration.ConfigurationPropertyAttribute>.</span></span> <span data-ttu-id="e43a8-171">Этот атрибут представляет собой связь между свойствами кода и XML-атрибутами, которые можно увидеть заданными для предыдущего XML-элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e43a8-171">This attribute constitutes the link between the code properties and the XML attributes that can be seen on the preceding XML configuration element.</span></span> <span data-ttu-id="e43a8-172">Кроме того, в классе имеется свойство `Schemas`, дополнительно отмеченное атрибутом <xref:System.Configuration.ConfigurationCollectionAttribute> и принадлежащее к типу `SchemaCollection`, которое также является частью этого образца, но исключено из данного документа для краткости изложения.</span><span class="sxs-lookup"><span data-stu-id="e43a8-172">The class also has a property `Schemas` that is additionally marked with the <xref:System.Configuration.ConfigurationCollectionAttribute> and is of the type `SchemaCollection`, which is also part of this sample but omitted from this document for brevity.</span></span> <span data-ttu-id="e43a8-173">Это свойство вместе с коллекцией и классом элемента коллекции `SchemaConfigElement` поддерживает элемент `<schemas>` в предыдущем фрагменте конфигурации и позволяет добавить коллекцию схем в набор проверки.</span><span class="sxs-lookup"><span data-stu-id="e43a8-173">This property along with the collection and the collection element class `SchemaConfigElement` backs the `<schemas>` element in the preceding configuration snippet and allows adding a collection of schemas to the validation set.</span></span>  
  
 <span data-ttu-id="e43a8-174">Переопределенный метод `CreateBehavior` преобразует данные конфигурации в объект поведения при их оценке средой выполнения во время построения клиента или конечной точки.</span><span class="sxs-lookup"><span data-stu-id="e43a8-174">The overridden `CreateBehavior` method turns the configuration data into a behavior object when the runtime evaluates the configuration data as it builds a client or an endpoint.</span></span>  
  
```csharp
public class SchemaValidationBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public SchemaValidationBehaviorExtensionElement()  
    {  
    }  
  
    public override Type BehaviorType   
    {   
        get  
        {  
            return typeof(SchemaValidationBehavior);  
        }   
    }  
  
    protected override object CreateBehavior()  
    {  
        XmlSchemaSet schemaSet = new XmlSchemaSet();  
        foreach (SchemaConfigElement schemaCfg in this.Schemas)  
        {  
            Uri baseSchema = new   
                Uri(AppDomain.CurrentDomain.BaseDirectory);  
            string location = new   
                Uri(baseSchema,schemaCfg.Location).ToString();  
            XmlSchema schema =   
                XmlSchema.Read(new XmlTextReader(location), null);  
            schemaSet.Add(schema);  
        }  
     return new   
     SchemaValidationBehavior(schemaSet,ValidateRequest,ValidateReply);  
    }  
  
[ConfigurationProperty("validateRequest",DefaultValue=false,IsRequired=false)]  
public bool ValidateRequest  
{  
    get { return (bool)base["validateRequest"]; }  
    set { base["validateRequest"] = value; }  
}  
  
[ConfigurationProperty("validateReply", DefaultValue = false, IsRequired = false)]  
        public bool ValidateReply  
        {  
            get { return (bool)base["validateReply"]; }  
            set { base["validateReply"] = value; }  
        }  
  
     //Declare the Schema collection property.  
     //Note: the "IsDefaultCollection = false" instructs   
     //.NET Framework to build a nested section of   
     //the kind <Schema> ...</Schema>.  
    [ConfigurationProperty("schemas", IsDefaultCollection = true)]  
    [ConfigurationCollection(typeof(SchemasCollection),  
        AddItemName = "add",  
        ClearItemsName = "clear",  
        RemoveItemName = "remove")]  
    public SchemasCollection Schemas  
    {  
        get  
        {  
            SchemasCollection SchemasCollection =  
            (SchemasCollection)base["schemas"];  
            return SchemasCollection;  
        }  
    }  
}  
```  
  
## <a name="adding-message-inspectors-imperatively"></a><span data-ttu-id="e43a8-175">Императивное добавление инспекторов сообщений</span><span class="sxs-lookup"><span data-stu-id="e43a8-175">Adding Message Inspectors Imperatively</span></span>  
 <span data-ttu-id="e43a8-176">Помимо использования атрибутов (что не поддерживается в данном образце по указанной ранее причине) и конфигурации, поведения можно довольно легко добавить в среду выполнения клиента и службы с помощью императивного кода.</span><span class="sxs-lookup"><span data-stu-id="e43a8-176">Except through attributes (which is not supported in this sample for the reason cited previously) and configuration, behaviors can quite easily be added to a client and service runtime using imperative code.</span></span> <span data-ttu-id="e43a8-177">В данном образце это выполняется в клиентском приложении для тестирования инспектора сообщений клиента.</span><span class="sxs-lookup"><span data-stu-id="e43a8-177">In this sample, this is done in the client application to test the client message inspector.</span></span> <span data-ttu-id="e43a8-178">Класс `GenericClient` наследуется от класса <xref:System.ServiceModel.ClientBase%601>, который предоставляет конфигурацию конечной точки пользовательскому коду.</span><span class="sxs-lookup"><span data-stu-id="e43a8-178">The `GenericClient` class is derived from <xref:System.ServiceModel.ClientBase%601>, which exposes the endpoint configuration to the user code.</span></span> <span data-ttu-id="e43a8-179">Перед неявным открытием клиента конфигурацию конечной точки можно изменить, например, путем добавления поведений, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="e43a8-179">Before the client is implicitly opened the endpoint configuration can be changed, for instance by adding behaviors as shown in the following code.</span></span> <span data-ttu-id="e43a8-180">Добавление поведения на стороне службы в значительной мере аналогично показанному в данном разделе способу, относящемуся к клиенту, и должно выполняться перед открытием узла службы.</span><span class="sxs-lookup"><span data-stu-id="e43a8-180">Adding the behavior on the service is largely equivalent to the client technique shown here and must be performed before the service host is opened.</span></span>  
  
```csharp  
try  
{  
    Console.WriteLine("*** Call 'Hello' with generic client, with client behavior");  
    GenericClient client = new GenericClient();  
  
    // Configure client programmatically, adding behavior  
    XmlSchema schema = XmlSchema.Read(new StreamReader("messages.xsd"),   
                                                          null);  
    XmlSchemaSet schemaSet = new XmlSchemaSet();  
    schemaSet.Add(schema);  
    client.Endpoint.Behaviors.Add(new   
                SchemaValidationBehavior(schemaSet, true, true));  
  
    Console.WriteLine("--- Sending valid client request:");  
    GenericCallValid(client, helloAction);  
    Console.WriteLine("--- Sending invalid client request:");  
    GenericCallInvalid(client, helloAction);  
  
    client.Close();  
}  
catch (Exception e)  
{  
    DumpException(e);  
}  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e43a8-181">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="e43a8-181">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e43a8-182">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e43a8-182">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="e43a8-183">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e43a8-183">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="e43a8-184">Чтобы запустить пример в конфигурации с одним или несколькими компьютерами, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="e43a8-184">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e43a8-185">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="e43a8-185">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e43a8-186">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="e43a8-186">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="e43a8-187">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="e43a8-187">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e43a8-188">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e43a8-188">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageInspectors`  
