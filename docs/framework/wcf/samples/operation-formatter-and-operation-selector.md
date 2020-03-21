---
title: Модуль форматирования и селектор операции
ms.date: 03/30/2017
ms.assetid: 1c27e9fe-11f8-4377-8140-828207b98a0e
ms.openlocfilehash: 9d1bc0afa54f89e064eab3f3e45da60c8d10de38
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144283"
---
# <a name="operation-formatter-and-operation-selector"></a><span data-ttu-id="cbd4f-102">Модуль форматирования и селектор операции</span><span class="sxs-lookup"><span data-stu-id="cbd4f-102">Operation Formatter and Operation Selector</span></span>
<span data-ttu-id="cbd4f-103">Этот пример демонстрирует, как точки разъема Windows Communication Foundation (WCF) могут использоваться для предоставления данных сообщений в другом формате, чем ожидает WCF.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-103">This sample demonstrates how Windows Communication Foundation (WCF) extensibility points can be used to allow message data in a different format from what WCF expects.</span></span> <span data-ttu-id="cbd4f-104">По умолчанию WCF будет ожидать, что параметры `soap:body` метода будут включены в элемент.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-104">By default, WCF formatters expect method parameters to be included under the `soap:body` element.</span></span> <span data-ttu-id="cbd4f-105">В этом образце показано, как реализовать пользовательский модуль форматирования операций, который анализирует параметры из строки HTTP-запроса GET и вызывает методы с использованием этих данных.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-105">The sample shows how to implement a custom operation formatter that parses parameter data from an HTTP GET query string instead and invokes methods using that data.</span></span>  
  
 <span data-ttu-id="cbd4f-106">Образец основан на [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), `ICalculator` который реализует контракт на обслуживание.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-106">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="cbd4f-107">Он показывает, каким образом можно изменить сообщения Add, Subtract, Multiply и Divide, чтобы они использовали HTTP-запросы GET в качестве запросов клиента серверу и HTTP-запросы POST с сообщениями POX в качестве ответов сервера клиенту.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-107">It shows how Add, Subtract, Multiply, and Divide messages can be changed to use HTTP GET for client-to-server requests and HTTP POST with POX messages for server-to-client responses.</span></span>  
  
 <span data-ttu-id="cbd4f-108">Для этого в образце имеются следующие элементы.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-108">To do so, the sample provides the following:</span></span>  
  
- <span data-ttu-id="cbd4f-109">Класс `QueryStringFormatter`, который реализует интерфейсы <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> и <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> для клиента и сервера соответственно и обрабатывает данные в строке запроса.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-109">`QueryStringFormatter`, which implements <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> and <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> for the client and server, respectively, and processes the data in the query string.</span></span>  
  
- <span data-ttu-id="cbd4f-110">Класс `UriOperationSelector`, который реализует интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> на сервере для выполнения диспетчеризации операций в зависимости от имени операции в запросе GET.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-110">`UriOperationSelector`, which implements <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> on the server to perform operation dispatch based on the operation name in the GET request.</span></span>  
  
- <span data-ttu-id="cbd4f-111">Поведение конечной точки `EnableHttpGetRequestsBehavior` (и соответствующая конфигурация), которое добавляет в среду выполнения селектор нужной операции.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-111">`EnableHttpGetRequestsBehavior` endpoint behavior (and corresponding configuration), which adds the necessary operation selector to the runtime.</span></span>  
  
- <span data-ttu-id="cbd4f-112">Показано, как включить в среду выполнения новый модуль форматирования операций.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-112">Shows how to insert a new operation formatter into the runtime.</span></span>  
  
- <span data-ttu-id="cbd4f-113">В этом образце служба и клиент являются консольными приложениями (EXE).</span><span class="sxs-lookup"><span data-stu-id="cbd4f-113">In this sample, both the client and the service are console applications (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="cbd4f-114">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-114">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="key-concepts"></a><span data-ttu-id="cbd4f-115">Основные понятия</span><span class="sxs-lookup"><span data-stu-id="cbd4f-115">Key Concepts</span></span>  
 <span data-ttu-id="cbd4f-116">`QueryStringFormatter`- Значение операции является компонентом в WCF, который отвечает за преобразование сообщения в массив объектов параметров и массив объектов параметра в сообщение.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-116">`QueryStringFormatter` - The operation formatter is the component in WCF that is responsible for converting a message into an array of parameter objects and an array of parameter objects into a message.</span></span> <span data-ttu-id="cbd4f-117">Эта задача выполняется на клиенте с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> и на сервере с помощью интерфейса <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-117">This is done on the client using the <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> interface and on the server with the <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface.</span></span> <span data-ttu-id="cbd4f-118">Эти интерфейсы позволяют пользователям получать сообщения запросов и ответов из методов `Serialize` и `Deserialize`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-118">These interfaces enable users to get the request and response messages from the `Serialize` and `Deserialize` methods.</span></span>  
  
 <span data-ttu-id="cbd4f-119">В этом образце класс `QueryStringFormatter` реализует оба эти интерфейса и реализуется на стороне клиента и сервера.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-119">In this sample, `QueryStringFormatter` implements both of these interfaces and is implemented on the client and server.</span></span>  
  
 <span data-ttu-id="cbd4f-120">Запрос:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-120">Request:</span></span>  
  
- <span data-ttu-id="cbd4f-121">В этом образце класс <xref:System.ComponentModel.TypeConverter> используется для преобразования параметров в сообщении запроса в строки и обратно.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-121">The sample uses the <xref:System.ComponentModel.TypeConverter> class to convert parameter data in the request message to and from strings.</span></span> <span data-ttu-id="cbd4f-122">Если объект для определенного типа <xref:System.ComponentModel.TypeConverter> недоступен, модуль форматирования в этом образце создает исключение.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-122">If a <xref:System.ComponentModel.TypeConverter> is not available for a specific type, the sample formatter throws an exception.</span></span>  
  
- <span data-ttu-id="cbd4f-123">В методе `IClientMessageFormatter.SerializeRequest` на стороне клиента модуль форматирования создает код URI для соответствующего адреса назначения и добавляет имя операции в качестве суффикса.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-123">In the `IClientMessageFormatter.SerializeRequest` method on the client, the formatter creates a URI with the appropriate To address and appends the operation name as a suffix.</span></span> <span data-ttu-id="cbd4f-124">Это имя используется для перенаправления на соответствующую операцию на сервере.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-124">This name is used to dispatch to the appropriate operation on the server.</span></span> <span data-ttu-id="cbd4f-125">После этого массив объектов параметров сериализуется в строку запроса кода URI с использованием имен и значений параметров, преобразованных классом <xref:System.ComponentModel.TypeConverter>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-125">It then takes the array of parameter objects and serializes the parameter data to the URI query string using parameter names and the values converted by the <xref:System.ComponentModel.TypeConverter> class.</span></span> <span data-ttu-id="cbd4f-126">Свойства <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> и <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> задаются данному URI.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-126">The <xref:System.ServiceModel.Channels.MessageHeaders.To%2A> and <xref:System.ServiceModel.Channels.MessageProperties.Via%2A> properties are then set to this URI.</span></span> <span data-ttu-id="cbd4f-127">Значение <xref:System.ServiceModel.Channels.MessageProperties> доступно через свойство <xref:System.ServiceModel.Channels.Message.Properties%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-127"><xref:System.ServiceModel.Channels.MessageProperties> is accessed through the <xref:System.ServiceModel.Channels.Message.Properties%2A> property.</span></span>  
  
- <span data-ttu-id="cbd4f-128">В методе `IDispatchMessageFormatter.DeserializeRequest` на сервере модуль форматирования извлекает код URI `Via` в свойствах сообщения входящего запроса.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-128">In the `IDispatchMessageFormatter.DeserializeRequest` method on the server, the formatter retrieves the `Via` URI in the incoming request message properties.</span></span> <span data-ttu-id="cbd4f-129">Модуль форматирования преобразует пары "имя-значение" в строке запроса URI в имена и значения параметров и подставляет эти имена и значения параметров в массив передаваемых методу параметров.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-129">It parses the name-value pairs in the URI query string into parameter names and values and uses the parameter names and values to populate the array of parameters passed into the method.</span></span> <span data-ttu-id="cbd4f-130">Обратите внимание, что диспетчеризация по операциям уже произошла, поэтому в данном методе суффикс имени операции игнорируется.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-130">Note that operation dispatch has already occurred, so the operation name suffix is ignored in this method.</span></span>  
  
 <span data-ttu-id="cbd4f-131">Ответ:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-131">Response:</span></span>  
  
- <span data-ttu-id="cbd4f-132">В этом образце HTTP-метод GET используется только для запросов.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-132">In this sample, HTTP GET is used only for the request.</span></span> <span data-ttu-id="cbd4f-133">Модуль форматирования делегирует отправку ответа исходному модулю форматирования, который бы использовался для создания XML-сообщения.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-133">The formatter delegates the sending of the response to the original formatter that would have been used to generate an XML message.</span></span> <span data-ttu-id="cbd4f-134">Одна из целей этого образца заключается в том, чтобы показать, как можно реализовать такой делегирующий модуль форматирования.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-134">One of the goals of this sample is to show how such a delegating formatter can be implemented.</span></span>  
  
### <a name="uripathsuffixoperationselector-class"></a><span data-ttu-id="cbd4f-135">Класс UriPathSuffixOperationSelector</span><span class="sxs-lookup"><span data-stu-id="cbd4f-135">UriPathSuffixOperationSelector Class</span></span>  
 <span data-ttu-id="cbd4f-136">Интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> позволяет пользователям реализовывать собственную логику определения операции, которой должно перенаправляться то или иное сообщение.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-136">The <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> interface enables users to implement their own logic for which operation a particular message should be dispatched.</span></span>  
  
 <span data-ttu-id="cbd4f-137">В этом образце необходимо реализовать на сервере класс `UriPathSuffixOperationSelector`, чтобы выбирать нужную операцию, поскольку имя операции включается в код URI HTTP-запроса GET, а не в заголовок действия в сообщении.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-137">In this sample, `UriPathSuffixOperationSelector` must be implemented on the server to select the appropriate operation because the operation name is included in the HTTP GET URI rather than an action header in the message.</span></span> <span data-ttu-id="cbd4f-138">В этом образце разрешены только имена операций, указываемые с учетом регистра.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-138">The sample is set up to allow only case-insensitive operation names.</span></span>  
  
 <span data-ttu-id="cbd4f-139">Метод `SelectOperation` принимает входящее сообщение и ищет в свойствах сообщения код URI `Via`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-139">The `SelectOperation` method takes the incoming message and looks up the `Via` URI in its message properties.</span></span> <span data-ttu-id="cbd4f-140">Он извлекает из кода URI суффикс имени операции, ищет во внутренней таблице имя операции, которой следует перенаправить сообщение, и возвращает имя операции.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-140">It extracts the operation name suffix from the URI, looks up an internal table to get the operation name that the message should be dispatched to, and returns that operation name.</span></span>  
  
### <a name="enablehttpgetrequestsbehavior-class"></a><span data-ttu-id="cbd4f-141">Класс EnableHttpGetRequestsBehavior</span><span class="sxs-lookup"><span data-stu-id="cbd4f-141">EnableHttpGetRequestsBehavior Class</span></span>  
 <span data-ttu-id="cbd4f-142">Компонент `UriPathSuffixOperationSelector` можно настраивать программным образом или с помощью поведения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-142">The `UriPathSuffixOperationSelector` component can be set up programmatically or through an endpoint behavior.</span></span> <span data-ttu-id="cbd4f-143">В этом образце реализовано поведение `EnableHttpGetRequestsBehavior`, которое задано в файле конфигурации приложения службы.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-143">The sample implements the `EnableHttpGetRequestsBehavior` behavior, which is specified in service’s application configuration file.</span></span>  
  
 <span data-ttu-id="cbd4f-144">На сервере:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-144">On the server:</span></span>  
  
 <span data-ttu-id="cbd4f-145">Свойству <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> присвоена реализация <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-145">The <xref:System.ServiceModel.Dispatcher.DispatchRuntime.OperationSelector%2A> is set to the <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector> implementation.</span></span>  
  
 <span data-ttu-id="cbd4f-146">По умолчанию WCF использует фильтр точного соответствия адреса.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-146">By default, WCF uses an exact-match address filter.</span></span> <span data-ttu-id="cbd4f-147">Код URI входящего сообщения содержит суффикс имени операции, за которым следует строка запроса, содержащая данные параметров, поэтому поведение также изменяет фильтр адресов, чтобы он срабатывал по совпадению префикса.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-147">The URI on the incoming message contains an operation name suffix followed by a query string that contains parameter data, so the endpoint behavior also changes the address filter to be a prefix match filter.</span></span> <span data-ttu-id="cbd4f-148">Для этой цели<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> он использует WCF.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-148">It uses the WCF<xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> for this purpose.</span></span>  
  
### <a name="installing-operation-formatters"></a><span data-ttu-id="cbd4f-149">Установка модулей форматирования операций</span><span class="sxs-lookup"><span data-stu-id="cbd4f-149">Installing operation formatters</span></span>  
 <span data-ttu-id="cbd4f-150">Поведения операций, которые задают модули форматирования, являются уникальными.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-150">Operation behaviors that specify formatters are unique.</span></span> <span data-ttu-id="cbd4f-151">Одно такое поведение всегда реализуется по умолчанию для каждой операции, чтобы создать нужный модуль форматирования операции.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-151">One such behavior is always implemented by default for every operation to create the necessary operation formatter.</span></span> <span data-ttu-id="cbd4f-152">Однако такие поведения очень похожи на поведения других операций; их невозможно идентифицировать по каким-либо другим атрибутам.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-152">However, these behaviors look like just another operation behavior; they are not identifiable by any other attribute.</span></span> <span data-ttu-id="cbd4f-153">Для установки поведения замены реализация должна искать определенные поведения formatter, установленные по загрузчиком типа WCF по умолчанию, и либо заменить его, либо добавить совместимое поведение для запуска после поведения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-153">To install a replacement behavior, the implementation must look for specific formatter behaviors that are installed by the WCF type loader by default and either replace it or add a compatible behavior to run after the default behavior.</span></span>  
  
 <span data-ttu-id="cbd4f-154">Эти поведения модулей форматирования операций можно задать программным образом перед вызовом <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> или путем задания поведения операции, которое выполняется после поведения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-154">These operation formatters behaviors can be set up programmatically prior to calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A?displayProperty=nameWithType> or by specifying an operation behavior that is executed after the default one.</span></span> <span data-ttu-id="cbd4f-155">Однако его невозможно легко настроить с помощью поведения конечной точки (а следовательно с помощью конфигурации), поскольку модель поведений не допускает замены поведения другими поведениями или иного изменения дерева описаний.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-155">However, it cannot easily be set up by an endpoint behavior (and therefore by configuration) because the behavior model does not allow a behavior to replace other behaviors or otherwise modify the description tree.</span></span>  
  
 <span data-ttu-id="cbd4f-156">На клиенте:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-156">On the client:</span></span>  
  
 <span data-ttu-id="cbd4f-157">Реализацию <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> нужно осуществлять таким образом, чтобы этот модуль форматирования мог преобразовывать запросы в HTTP-запросы GET и делегировать создание ответов исходному модулю форматирования.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-157">The <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter> implementation must be implemented so that it can convert the requests into HTTP GET requests and delegate to the original formatter for responses.</span></span> <span data-ttu-id="cbd4f-158">Для этого вызывается вспомогательный метод `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-158">This is done by calling the `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method.</span></span>  
  
 <span data-ttu-id="cbd4f-159">Это необходимо сделать до вызова метода `CreateChannel`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-159">This must be done before calling `CreateChannel`.</span></span>  
  
```csharp  
void ReplaceFormatterBehavior(OperationDescription operationDescription, EndpointAddress address)  
{  
    // Remove the DataContract behavior if it is present.  
    IOperationBehavior formatterBehavior = operationDescription.Behaviors.Remove<DataContractSerializerOperationBehavior>();  
    if (formatterBehavior == null)  
    {  
        // Remove the XmlSerializer behavior if it is present.  
        formatterBehavior = operationDescription.Behaviors.Remove<XmlSerializerOperationBehavior>();  
        ...  
    }  
  
    // Remember what the innerFormatterBehavior was.  
    DelegatingFormatterBehavior delegatingFormatterBehavior = new DelegatingFormatterBehavior(address);  
    delegatingFormatterBehavior.InnerFormatterBehavior = formatterBehavior;  
   operationDescription.Behaviors.Add(delegatingFormatterBehavior);  
}  
```  
  
 <span data-ttu-id="cbd4f-160">На сервере:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-160">On the server:</span></span>  
  
- <span data-ttu-id="cbd4f-161">Интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> нужно реализовать таким образом, чтобы этот модуль форматирования мог считывать HTTP-запросы GET и делегировать создание ответов исходному модулю форматирования.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-161">The <xref:System.ServiceModel.Dispatcher.IDispatchMessageFormatter> interface must be implemented so that it can read HTTP GET requests and delegate to the original formatter for writing responses.</span></span> <span data-ttu-id="cbd4f-162">Это делается путем вызова того же вспомогательного метода `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior`, что и для клиента (см. предыдущий пример кода).</span><span class="sxs-lookup"><span data-stu-id="cbd4f-162">This is done by calling the same `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` helper method as the client (see the previous code sample).</span></span>  
  
- <span data-ttu-id="cbd4f-163">Это необходимо сделать до вызова метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-163">This must be done before <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> is called.</span></span> <span data-ttu-id="cbd4f-164">В этом образце показано, каким образом можно вручную изменить модуль форматирования перед вызовом метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-164">In this sample, we show how the formatter is manually modified before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span> <span data-ttu-id="cbd4f-165">Того же результата можно достичь, создав для класса <xref:System.ServiceModel.ServiceHost> производный класс, который вызывает `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` перед открытием (примеры см. в документации по размещению).</span><span class="sxs-lookup"><span data-stu-id="cbd4f-165">Another way to achieve the same thing is to derive a class from <xref:System.ServiceModel.ServiceHost> that makes the calls to `EnableHttpGetRequestsBehavior.ReplaceFormatterBehavior` before opening (please see hosting documentation and samples for examples).</span></span>  
  
### <a name="user-experience"></a><span data-ttu-id="cbd4f-166">Возможности для пользователя</span><span class="sxs-lookup"><span data-stu-id="cbd4f-166">User experience</span></span>  
 <span data-ttu-id="cbd4f-167">На сервере:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-167">On the server:</span></span>  
  
- <span data-ttu-id="cbd4f-168">Серверную реализацию `ICalculator` изменять не требуется.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-168">The server `ICalculator` implementation does not need to change.</span></span>  
  
- <span data-ttu-id="cbd4f-169">В файле App.config службы следует задавать пользовательскую привязку POX, которая устанавливает для атрибута `messageVersion` элемента `textMessageEncoding` значение `None`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-169">The App.config for the service must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="cbd4f-170">Кроме того, в файле App.config службы необходимо задать пользовательское поведение `EnableHttpGetRequestsBehavior`, добавив его в раздел расширений поведения.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-170">The App.config for the service also must specify the custom `EnableHttpGetRequestsBehavior` by adding it to the behavior extensions section and using it.</span></span>  
  
    ```xml  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="enableHttpGetRequestsBehavior">  
          <enableHttpGetRequests />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
    <extensions>  
      <behaviorExtensions>  
        <!-- Enabling HTTP GET requests: Behavior Extension -->  
        <add
          name="enableHttpGetRequests"           type="Microsoft.ServiceModel.Samples.EnableHttpGetRequestsBehaviorElement, QueryStringFormatter, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
    ```  
  
- <span data-ttu-id="cbd4f-171">Перед вызовом метода <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A> необходимо добавить модули форматирования операций.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-171">Add operation formatters before calling <xref:System.ServiceModel.Channels.CommunicationObject.Open%2A>.</span></span>  
  
 <span data-ttu-id="cbd4f-172">На клиенте:</span><span class="sxs-lookup"><span data-stu-id="cbd4f-172">On the client:</span></span>  
  
- <span data-ttu-id="cbd4f-173">Изменять клиентскую реализацию не требуется.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-173">The client implementation does not need to change.</span></span>  
  
- <span data-ttu-id="cbd4f-174">В файле App.config клиента следует задать пользовательскую привязку POX, которая устанавливает для атрибута `messageVersion` элемента `textMessageEncoding` значение `None`.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-174">The App.config for the client must use a custom POX binding that sets the `messageVersion` attribute of the `textMessageEncoding` element to `None`.</span></span> <span data-ttu-id="cbd4f-175">Отличие от службы заключается в том, что клиент должен включить ручную адресацию, чтобы можно было изменять исходящий адрес назначения.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-175">One difference from the service is that the client must enable manual addressing so that the outgoing To address can be modified.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="poxBinding">  
          <textMessageEncoding messageVersion="None" />  
          <httpTransport manualAddressing="True" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
- <span data-ttu-id="cbd4f-176">В файле App.config клиента должно быть задано то же пользовательское поведение `EnableHttpGetRequestsBehavior`, что и на сервере.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-176">The App.config for the client must specify the same custom `EnableHttpGetRequestsBehavior` as the server.</span></span>  
  
- <span data-ttu-id="cbd4f-177">Перед вызовом метода <xref:System.ServiceModel.ChannelFactory%601.CreateChannel> необходимо добавить модули форматирования операций.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-177">Add operation formatters before calling <xref:System.ServiceModel.ChannelFactory%601.CreateChannel>.</span></span>  
  
 <span data-ttu-id="cbd4f-178">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-178">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="cbd4f-179">Все четыре операции (Add, Subtract, Multiply и Divide) должны выполняться успешно.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-179">All four operations (Add, Subtract, Multiply, and Divide) must succeed.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="cbd4f-180">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-180">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbd4f-181">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="cbd4f-181">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="cbd4f-182">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-182">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbd4f-183">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="cbd4f-183">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Formatters\QueryStringFormatter`  
  
##### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cbd4f-184">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cbd4f-184">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="cbd4f-185">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbd4f-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="cbd4f-186">Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbd4f-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="cbd4f-187">Чтобы запустить образец в одно- или кросс-машинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="cbd4f-187">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
