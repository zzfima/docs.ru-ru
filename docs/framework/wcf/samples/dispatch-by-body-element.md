---
title: "Передача по элементу тела сообщения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f64a3c04-62b4-47b2-91d9-747a3af1659f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c3624290176d93519ae420a98a7e93534d910fa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="dispatch-by-body-element"></a><span data-ttu-id="0d31c-102">Передача по элементу тела сообщения</span><span class="sxs-lookup"><span data-stu-id="0d31c-102">Dispatch by Body Element</span></span>
<span data-ttu-id="0d31c-103">В образце демонстрируется реализация альтернативного алгоритма для присвоения операциям входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="0d31c-103">This sample demonstrates how to implement an alternate algorithm for assigning incoming messages to operations.</span></span>  
  
 <span data-ttu-id="0d31c-104">По умолчанию диспетчер модели службы выбирает соответствующий метод обработки для входящего сообщения, основанный на заголовке "Действие" механизма WS-Addressing сообщения или аналогичной информации запроса HTTP SOAP.</span><span class="sxs-lookup"><span data-stu-id="0d31c-104">By default, the service model dispatcher selects the appropriate handling method for an incoming message based on the message's WS-Addressing "Action" header or the equivalent information in the HTTP SOAP request.</span></span>  
  
 <span data-ttu-id="0d31c-105">Некоторые стеки веб-служб SOAP 1.1 не соответствуют рекомендациям WS-I Basic Profile 1.1, поэтому не распределяют сообщения, основываясь не на URI действия, а на полном XML-имени первого элемента внутри тела SOAP.</span><span class="sxs-lookup"><span data-stu-id="0d31c-105">Some SOAP 1.1 Web services stacks that do not follow the WS-I Basic Profile 1.1 guidelines do not dispatch messages based on the Action URI, but rather based on the XML qualified name of the first element inside the SOAP body.</span></span> <span data-ttu-id="0d31c-106">Аналогично, клиентская сторона этих стеков может отправлять сообщения с пустым или произвольным заголовком HTTP SoapAction, который разрешен спецификацией SOAP 1.1.</span><span class="sxs-lookup"><span data-stu-id="0d31c-106">Likewise, the client side of these stacks might send messages with an empty or arbitrary HTTP SoapAction header, which was permitted by the SOAP 1.1 specification.</span></span>  
  
 <span data-ttu-id="0d31c-107">Чтобы изменить способ отправки сообщений методам, образец реализует интерфейс расширения <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> для события `DispatchByBodyElementOperationSelector`.</span><span class="sxs-lookup"><span data-stu-id="0d31c-107">To change the way messages are dispatched to methods, the sample implements the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> extensibility interface on the `DispatchByBodyElementOperationSelector`.</span></span> <span data-ttu-id="0d31c-108">Этот класс выбирает операции, основываясь на первом элементе тела сообщения.</span><span class="sxs-lookup"><span data-stu-id="0d31c-108">This class selects operations based on the first element of the message body.</span></span>  
  
 <span data-ttu-id="0d31c-109">Конструктор класса ожидает словарь, который заполняется парами `XmlQualifiedName` и строками, в котором полные имена указывают имя первого дочернего элемента тела SOAP, а строки указывают на имя соответствующей операции.</span><span class="sxs-lookup"><span data-stu-id="0d31c-109">The class constructor expects a dictionary populated with pairs of `XmlQualifiedName` and strings, whereby the qualified names indicate the name of the first child of the SOAP body and the strings indicate the matching operation name.</span></span> <span data-ttu-id="0d31c-110">`defaultOperationName` - это имя операции, которая принимает все сообщения, которые не были найдены в этом словаре.</span><span class="sxs-lookup"><span data-stu-id="0d31c-110">The `defaultOperationName` is the name of the operation that receives all messages that cannot be matched against this dictionary:</span></span>  
  
```  
class DispatchByBodyElementOperationSelector : IDispatchOperationSelector  
{  
    Dictionary<XmlQualifiedName, string> dispatchDictionary;  
    string defaultOperationName;  
  
    public DispatchByBodyElementOperationSelector(Dictionary<XmlQualifiedName,string> dispatchDictionary, string defaultOperationName)  
    {  
        this.dispatchDictionary = dispatchDictionary;  
        this.defaultOperationName = defaultOperationName;  
    }  
```  
  
 <span data-ttu-id="0d31c-111">Реализации <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> являются очень простыми в построении, так как есть только один метод в интерфейсе: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d31c-111"><xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementations are very straightforward to build as there is only one method on the interface: <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A>.</span></span> <span data-ttu-id="0d31c-112">Этот метод отвечает за проверку входящих сообщений и возврат строки, которая равна имени метода контракта службы для текущей конечной точки.</span><span class="sxs-lookup"><span data-stu-id="0d31c-112">The job of this method is to inspect an incoming message and to return a string that equals the name of a method on the service contract for the current endpoint.</span></span>  
  
 <span data-ttu-id="0d31c-113">В этом образце селектор операций приобретает класс <xref:System.Xml.XmlDictionaryReader> для тела входящего сообщения, используя метод <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d31c-113">In this sample, the operation selector acquires an <xref:System.Xml.XmlDictionaryReader> for the incoming message's body using <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A>.</span></span> <span data-ttu-id="0d31c-114">Этот метод уже расположил средство чтения на первом дочернем элементе тела сообщения, поэтому достаточно получить имя текущего элемента, универсальный код ресурса (URI) пространства имен и объединить их в `XmlQualifiedName`, чтобы затем использовать для поиска соответствующей операции в словаре, хранящемся в селекторе операций.</span><span class="sxs-lookup"><span data-stu-id="0d31c-114">This method already positions the reader on the first child of the message's body so that it is sufficient to get the current element's name and namespace URI and combine them into an `XmlQualifiedName` that is then used for looking up the corresponding operation from the dictionary held by the operation selector.</span></span>  
  
```  
public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
{  
    XmlDictionaryReader bodyReader = message.GetReaderAtBodyContents();  
    XmlQualifiedName lookupQName = new  
       XmlQualifiedName(bodyReader.LocalName, bodyReader.NamespaceURI);  
    message = CreateMessageCopy(message,bodyReader);  
    if (dispatchDictionary.ContainsKey(lookupQName))  
    {  
         return dispatchDictionary[lookupQName];  
    }  
    else  
    {  
        return defaultOperationName;  
    }  
}  
```  
  
 <span data-ttu-id="0d31c-115">Доступ к телу сообщения с помощью метода <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> или любого другого метода, который обеспечивает доступ к содержимому тела сообщения, приводит к тому, что сообщение помечается как "read", то есть дальнейшая обработка сообщения является недопустимой.</span><span class="sxs-lookup"><span data-stu-id="0d31c-115">Accessing the message body with <xref:System.ServiceModel.Channels.Message.GetReaderAtBodyContents%2A> or any of the other methods that provide access to the message's body content causes the message to be marked as "read", which means that the message is invalid for any further processing.</span></span> <span data-ttu-id="0d31c-116">Поэтому селектор операций создает копию входящего сообщения с помощью метода, который показан в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="0d31c-116">Therefore, the operation selector creates a copy of the incoming message with the method shown in the following code.</span></span> <span data-ttu-id="0d31c-117">Поскольку позиция средства чтения не изменялась во время проверки, новое созданное сообщение может ссылаться на нее. В это сообщение также копируются свойства и заголовки сообщения, результаты которого являются точной копией исходного сообщения.</span><span class="sxs-lookup"><span data-stu-id="0d31c-117">Because the reader's position has not been changed during the inspection, it can be referenced by the newly created message to which the message properties and the message headers are also copied, which results in an exact clone of the original message:</span></span>  
  
```  
private Message CreateMessageCopy(Message message,   
                                     XmlDictionaryReader body)  
{  
    Message copy = Message.CreateMessage(message.Version,message.Headers.Action,body);  
    copy.Headers.CopyHeaderFrom(message,0);  
    copy.Properties.CopyProperties(message.Properties);  
    return copy;  
}  
```  
  
## <a name="adding-an-operation-selector-to-a-service"></a><span data-ttu-id="0d31c-118">Добавление селектора операции в службу</span><span class="sxs-lookup"><span data-stu-id="0d31c-118">Adding an Operation Selector to a Service</span></span>  
 <span data-ttu-id="0d31c-119">Селекторы службы операции отправки являются расширениями для диспетчера [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0d31c-119">Service dispatch operation selectors are extensions to the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] dispatcher.</span></span> <span data-ttu-id="0d31c-120">Для выбранных методов на канале обратного вызова дуплексных контрактов также есть селекторы операций клиента, которые работают схоже с описанными здесь селекторами операции отправки, но которые не представлены в этом образце в явном виде.</span><span class="sxs-lookup"><span data-stu-id="0d31c-120">For selecting methods on the callback channel of duplex contracts, there are also client operation selectors, which work very much like the dispatch operation selectors described here, but which are not explicitly covered in this sample.</span></span>  
  
 <span data-ttu-id="0d31c-121">Подобно большинству расширений моделей служб, селекторы операций отправки добавляются диспетчеру с использованием поведения.</span><span class="sxs-lookup"><span data-stu-id="0d31c-121">Like most service model extensions, dispatch operation selectors are added to the dispatcher using behaviors.</span></span> <span data-ttu-id="0d31c-122">Объект *поведение* является объектом конфигурации, который либо добавляет одно или несколько расширений для среды выполнения распределения (или в клиентскую среду выполнения) или в противном случае, изменяет его параметры.</span><span class="sxs-lookup"><span data-stu-id="0d31c-122">A *behavior* is a configuration object, which either adds one or more extensions to the dispatch runtime (or to the client runtime) or otherwise changes its settings.</span></span>  
  
 <span data-ttu-id="0d31c-123">Поскольку селекторы операций имеют область контрактов, реализуется поведение <xref:System.ServiceModel.Description.IContractBehavior>.</span><span class="sxs-lookup"><span data-stu-id="0d31c-123">Because operation selectors have contract scope, the appropriate behavior to implement here is the <xref:System.ServiceModel.Description.IContractBehavior>.</span></span> <span data-ttu-id="0d31c-124">Поскольку интерфейс реализован для производного класса <xref:System.Attribute>, как показано в коде, поведение может быть добавлено декларативно в любой контракт службы.</span><span class="sxs-lookup"><span data-stu-id="0d31c-124">Because the interface is implemented on a <xref:System.Attribute> derived class as shown in the following code, the behavior can be declaratively added to any service contract.</span></span> <span data-ttu-id="0d31c-125">Если класс <xref:System.ServiceModel.ServiceHost> уже открыт и среда выполнения распределения построена, все поведение, обнаруженное в качестве атрибутов в контрактах, операциях и реализациях служб или в качестве элемента в конфигурации службы, автоматически добавляется и впоследствии запрашивается для участия в расширениях или изменении конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0d31c-125">Whenever a <xref:System.ServiceModel.ServiceHost> is opened and the dispatch runtime is built, all behaviors found either as attributes on contracts, operations, and service implementations or as element in the service configuration are automatically added and subsequently asked to contribute extensions or modify the default configuration.</span></span>  
  
 <span data-ttu-id="0d31c-126">Для краткости следующий фрагмент кода показывает только реализацию метода <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, который оказывает результирующее воздействие на изменение конфигурации для диспетчера в этом образце.</span><span class="sxs-lookup"><span data-stu-id="0d31c-126">For brevity, the following code excerpt only shows the implementation of the method <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A>, which effects the configuration changes for the dispatcher in this sample.</span></span> <span data-ttu-id="0d31c-127">Другие методы не показаны, поскольку они возвращаются вызывающему объекту без выполнения какой-либо работы.</span><span class="sxs-lookup"><span data-stu-id="0d31c-127">The other methods are not shown because they return to the caller without doing any work.</span></span>  
  
```  
[AttributeUsage(AttributeTargets.Class|AttributeTargets.Interface)]  
class DispatchByBodyElementBehaviorAttribute : Attribute, IContractBehavior  
{  
    // public void AddBindingParameters(...)   
    // public void ApplyClientBehavior(...)  
    // public void Validate(...)  
```  
  
 <span data-ttu-id="0d31c-128">Реализация метода <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> настраивает словарь поиска для селектора операций путем итераций среди элементов класса <xref:System.ServiceModel.Description.OperationDescription> в конечной точке службы <xref:System.ServiceModel.Description.ContractDescription>.</span><span class="sxs-lookup"><span data-stu-id="0d31c-128">First, the <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%2A> implementation sets up the lookup dictionary for the operation selector by iterating over the <xref:System.ServiceModel.Description.OperationDescription> elements in the service endpoint's <xref:System.ServiceModel.Description.ContractDescription>.</span></span> <span data-ttu-id="0d31c-129">Затем каждое описание операции проверяется на присутствие поведения `DispatchBodyElementAttribute` и реализации интерфейса <xref:System.ServiceModel.Description.IOperationBehavior>, который тоже определен в этом образце.</span><span class="sxs-lookup"><span data-stu-id="0d31c-129">Then, each operation description is inspected for the presence of the `DispatchBodyElementAttribute` behavior, an implementation of <xref:System.ServiceModel.Description.IOperationBehavior> that is also defined in this sample.</span></span> <span data-ttu-id="0d31c-130">До тех пор пока этот класс является поведением, он пассивен и не принимает активного участия в изменении конфигурации среды времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="0d31c-130">While this class is also a behavior, it is passive and does not actively contribute any configuration changes to the dispatch runtime.</span></span> <span data-ttu-id="0d31c-131">Любой из его методов возвращается вызывающему объекту без выполнения каких-либо действий.</span><span class="sxs-lookup"><span data-stu-id="0d31c-131">All of its methods return to the caller without taking any actions.</span></span> <span data-ttu-id="0d31c-132">Существует только поведение операции; в результате могут быть ассоциированы с соответствующими операциями только метаданные, необходимые для нового механизма диспетчеризации - полное имя элемента тела, на котором выбрано вхождение операции.</span><span class="sxs-lookup"><span data-stu-id="0d31c-132">The operation behavior only exists so that the metadata required for the new dispatch mechanism, namely the qualified name of the body element on whose occurrence an operation is selected, can be associated with the respective operations.</span></span>  
  
 <span data-ttu-id="0d31c-133">Если такое поведение найдено, создается пара значений "полное XML-имя" (свойство `QName`) и "имя операции" (свойство `Name`), которая добавляется в словарь.</span><span class="sxs-lookup"><span data-stu-id="0d31c-133">If such a behavior is found, a value pair created from the XML qualified name (`QName` property) and the operation name (`Name` property) is added to the dictionary.</span></span>  
  
 <span data-ttu-id="0d31c-134">Как только словарь заполняется, с использованием этой информации строится новый селектор `DispatchByBodyElementOperationSelector` и задается как селектор операций для данной среды выполнения распределения.</span><span class="sxs-lookup"><span data-stu-id="0d31c-134">Once the dictionary is populated, a new `DispatchByBodyElementOperationSelector` is constructed with this information and set as the operation selector of the dispatch runtime:</span></span>  
  
```  
public void ApplyDispatchBehavior(ContractDescription contractDescription, ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.DispatchRuntime dispatchRuntime)  
{  
    Dictionary<XmlQualifiedName,string> dispatchDictionary =   
                     new Dictionary<XmlQualifiedName,string>();  
    foreach( OperationDescription operationDescription in   
                              contractDescription.Operations )  
    {  
        DispatchBodyElementAttribute dispatchBodyElement =   
   operationDescription.Behaviors.Find<DispatchBodyElementAttribute>();  
        if ( dispatchBodyElement != null )  
        {  
             dispatchDictionary.Add(dispatchBodyElement.QName,   
                              operationDescription.Name);  
        }  
    }  
    dispatchRuntime.OperationSelector =   
            new DispatchByBodyElementOperationSelector(  
               dispatchDictionary,   
               dispatchRuntime.UnhandledDispatchOperation.Name);  
    }  
}  
```  
  
## <a name="implementing-the-service"></a><span data-ttu-id="0d31c-135">Реализация службы</span><span class="sxs-lookup"><span data-stu-id="0d31c-135">Implementing the Service</span></span>  
 <span data-ttu-id="0d31c-136">Реализованное в этом образце поведение непосредственно влияет на то, как сообщения из канала связи интерпретируется и отправляется, что является функцией контракта службы.</span><span class="sxs-lookup"><span data-stu-id="0d31c-136">The behavior implemented in this sample directly affects how messages from the wire are interpreted and dispatched, which is a function of the service contract.</span></span> <span data-ttu-id="0d31c-137">В результате поведение должно быть объявлено на уровне контракта службы в реализации любой службы, которая выбирает его для своего использования.</span><span class="sxs-lookup"><span data-stu-id="0d31c-137">Consequently, the behavior should be declared on the service contract level in any service implementation that chooses to use it.</span></span>  
  
 <span data-ttu-id="0d31c-138">Образец службы проекта применяет `DispatchByBodyElementBehaviorAttribute` поведения для контракта `IDispatchedByBody` контракту службы каждой из двух операций `OperationForBodyA()` и `OperationForBodyB()` с `DispatchBodyElementAttribute` поведение операции.</span><span class="sxs-lookup"><span data-stu-id="0d31c-138">The sample project service applies the `DispatchByBodyElementBehaviorAttribute` contract behavior to the `IDispatchedByBody` service contract and labels each of the two operations `OperationForBodyA()` and `OperationForBodyB()` with a `DispatchBodyElementAttribute` operation behavior.</span></span> <span data-ttu-id="0d31c-139">Когда открыт узел службы, который реализует этот контракт, эти метаданные используются конструктором диспетчера в соответствии с приведенным описанием.</span><span class="sxs-lookup"><span data-stu-id="0d31c-139">When a service host for a service that implements this contract is opened, this metadata is picked up by the dispatcher builder as previously described.</span></span>  
  
 <span data-ttu-id="0d31c-140">Поскольку селектор операции при направлении принимает во внимание только элемент тела сообщений и игнорирует заголовок "Действие", требуется указать среде выполнения не проверять заголовок "Действие" возвращаемых ответов путем присвоения подстановочного знака "*" свойству `ReplyAction` класса <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="0d31c-140">Because the operation selector dispatches solely based on the message body element and ignores the "Action", it is required to tell the runtime not to check the "Action" header on the returned replies by assigning the wildcard "*" to the `ReplyAction` property of <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="0d31c-141">Кроме того, он может иметь операцию по умолчанию, который имеет свойство «Действие» присвоен подстановочный знак «\*».</span><span class="sxs-lookup"><span data-stu-id="0d31c-141">Furthermore, it is required to have a default operation that has the "Action" property set to the wildcard "\*".</span></span> <span data-ttu-id="0d31c-142">Операция по умолчанию получает все сообщения, которые не могут быть отправлены и не имеют `DispatchBodyElementAttribute`.</span><span class="sxs-lookup"><span data-stu-id="0d31c-142">The default operation receives all messages which cannot be dispatched and does not have a `DispatchBodyElementAttribute`:</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
                            DispatchByBodyElementBehavior]  
public interface IDispatchedByBody  
{  
    [OperationContract(ReplyAction="*"),   
     DispatchBodyElement("bodyA","http://tempuri.org")]  
    Message OperationForBodyA(Message msg);  
    [OperationContract(ReplyAction = "*"),   
     DispatchBodyElement("bodyB", "http://tempuri.org")]  
    Message OperationForBodyB(Message msg);  
    [OperationContract(Action="*", ReplyAction="*")]  
    Message DefaultOperation(Message msg);  
}  
```  
  
 <span data-ttu-id="0d31c-143">Реализация образца службы очень проста.</span><span class="sxs-lookup"><span data-stu-id="0d31c-143">The sample service implementation is straightforward.</span></span> <span data-ttu-id="0d31c-144">Каждый метод упаковывает принятое сообщение в сообщение ответа и возвращает его обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="0d31c-144">Every method wraps the received message into a reply message and echoes it back to the client.</span></span>  
  
## <a name="running-and-building-the-sample"></a><span data-ttu-id="0d31c-145">Построение и запуск образца</span><span class="sxs-lookup"><span data-stu-id="0d31c-145">Running and Building the Sample</span></span>  
 <span data-ttu-id="0d31c-146">При выполнении образца содержимое тела ответов операции отображается в окне консоли клиента аналогично приведенному (форматированному) результату работы.</span><span class="sxs-lookup"><span data-stu-id="0d31c-146">When you run the sample, the body content of the operation responses are displayed in the client console window similar to the following (formatted) output.</span></span>  
  
 <span data-ttu-id="0d31c-147">Клиент отправляет службе три сообщения с элементами содержимого тела `bodyA`, `bodyB` и `bodyX` соответственно.</span><span class="sxs-lookup"><span data-stu-id="0d31c-147">The client sends three messages to the service whose body content element is named `bodyA`, `bodyB`, and `bodyX`, respectively.</span></span> <span data-ttu-id="0d31c-148">Как отложилось из предыдущего описания и как показывает контракт службы, входящее сообщение с элементом `bodyA` отправляется методу `OperationForBodyA()`.</span><span class="sxs-lookup"><span data-stu-id="0d31c-148">As can be deferred from the previous description and the service contract shown, the incoming message with the `bodyA` element is dispatched to the `OperationForBodyA()` method.</span></span> <span data-ttu-id="0d31c-149">Поскольку отсутствует явный целевой объект, чтобы определить сообщение с телом элемента `bodyX`, сообщение отправляется операции `DefaultOperation()`.</span><span class="sxs-lookup"><span data-stu-id="0d31c-149">Because there is no explicit dispatch target for the message with the `bodyX` body element, the message is dispatched to the `DefaultOperation()`.</span></span> <span data-ttu-id="0d31c-150">Каждая из операций службы упаковывает полученное тело сообщения в элемент для данного метода и возвращает его. Это сделано для четкой корреляции входных и сообщений для этого образца.</span><span class="sxs-lookup"><span data-stu-id="0d31c-150">Each of the service operations wraps the received message body into an element specific to the method and returns it, which is done to correlate input and output messages clearly for this sample:</span></span>  
  
```xml  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyA xmlns="http://tempuri.org">  
   <q:bodyA xmlns:q="http://tempuri.org">test</q:bodyA>  
</replyBodyA>  
<?xml version="1.0" encoding="IBM437"?>  
<replyBodyB xmlns="http://tempuri.org">  
  <q:bodyB xmlns:q="http://tempuri.org">test</q:bodyB>  
</replyBodyB>  
<?xml version="1.0" encoding="IBM437"?>  
<replyDefault xmlns="http://tempuri.org">  
   <q:bodyX xmlns:q="http://tempuri.org">test</q:bodyX>  
</replyDefault>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0d31c-151">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="0d31c-151">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0d31c-152">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d31c-152">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0d31c-153">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d31c-153">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="0d31c-154">Для запуска образца в конфигурации одного или нескольких компьютерах, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0d31c-154">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d31c-155">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="0d31c-155">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0d31c-156">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="0d31c-156">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0d31c-157">Если этот каталог не существует, перейдите на страницу [Примеры Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все примеры [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0d31c-157">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0d31c-158">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="0d31c-158">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\AdvancedDispatchByBody`  
  
## <a name="see-also"></a><span data-ttu-id="0d31c-159">См. также</span><span class="sxs-lookup"><span data-stu-id="0d31c-159">See Also</span></span>
