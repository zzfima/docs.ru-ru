---
title: Пользовательский фильтр сообщений
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 79edba14eff5403591cf43592415d923dbd321be
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716828"
---
# <a name="custom-message-filter"></a><span data-ttu-id="b2656-102">Пользовательский фильтр сообщений</span><span class="sxs-lookup"><span data-stu-id="b2656-102">Custom Message Filter</span></span>
<span data-ttu-id="b2656-103">В этом примере показано, как заменить фильтры сообщений, которые Windows Communication Foundation (WCF) используют для отправки сообщений конечным точкам.</span><span class="sxs-lookup"><span data-stu-id="b2656-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2656-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b2656-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b2656-105">При поступлении на сервер первого сообщения из канала сервер должен определить, какие конечные точки, связанные с данным URI, должны получить сообщение.</span><span class="sxs-lookup"><span data-stu-id="b2656-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="b2656-106">Этот процесс контролируется объектами <xref:System.ServiceModel.Dispatcher.MessageFilter> присоединенными к диспетчеру <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="b2656-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="b2656-107">У каждой конечной точки службы имеется один диспетчер <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="b2656-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="b2656-108">У диспетчера <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> имеются как фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>, так и фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2656-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="b2656-109">Объединение этих двух фильтров является фильтром сообщений, используемым для данной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b2656-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="b2656-110">По умолчанию фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> для конечной точки соответствует любому сообщению, передаваемому по адресу, который соответствует адресу <xref:System.ServiceModel.EndpointAddress> конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="b2656-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="b2656-111">По умолчанию <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> для конечной точки проверяет действие входящего сообщения и соответствует любому сообщению с действием, которое соответствует одному из действий операций контракта конечной точки службы (только `IsInitiating`=`true`ных действий).</span><span class="sxs-lookup"><span data-stu-id="b2656-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="b2656-112">В результате по умолчанию соответствие фильтру для конечной точки обеспечивается, только если в заголовках "To" обоих сообщений задан адрес <xref:System.ServiceModel.EndpointAddress> конечной точки и действие сообщения соответствует одному из действий операции конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b2656-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="b2656-113">Эти фильтры можно изменить с помощью поведения.</span><span class="sxs-lookup"><span data-stu-id="b2656-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="b2656-114">В этом образце служба создает интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, который заменяет фильтры <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> и <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> в диспетчере <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span><span class="sxs-lookup"><span data-stu-id="b2656-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="b2656-115">Определяется два фильтра адресов:</span><span class="sxs-lookup"><span data-stu-id="b2656-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="b2656-116">Поведение `FilteringEndpointBehavior` делается настраиваемым и предусматривает два различных варианта.</span><span class="sxs-lookup"><span data-stu-id="b2656-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="b2656-117">Вариант 1 соответствует только адресам, в которых содержится буква 'e' (и которые имеют любое действие), а вариант 2 соответствует только адресам, в которых отсутствует буква 'e':</span><span class="sxs-lookup"><span data-stu-id="b2656-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="b2656-118">В файле конфигурации служба регистрирует новое поведение:</span><span class="sxs-lookup"><span data-stu-id="b2656-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>      
```  
  
 <span data-ttu-id="b2656-119">Затем служба создает конфигурации `endpointBehavior` для каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="b2656-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 <span data-ttu-id="b2656-120">Наконец, конечная точка службы ссылается на одну из конфигураций `behaviorConfigurations`:</span><span class="sxs-lookup"><span data-stu-id="b2656-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""   
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"   
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="b2656-121">Реализация клиентского приложения является прямолинейной; она создает два канала к URI службы (передавая заданное значение в качестве второго параметра (`via`) методу <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29>) и отправляет одно сообщение по каждому каналу, но использует в каждом случае различные адреса конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b2656-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="b2656-122">В результате исходящие сообщения клиента имеют разные адреса назначения в поле "To" и сервер реагирует соответствующим образом, как показано в выходных данных клиента:</span><span class="sxs-lookup"><span data-stu-id="b2656-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="b2656-123">Переключение варианта в файле конфигурации сервера приводит к перестановке фильтров, и на клиенте наблюдается противоположное поведение (доставка сообщения по адресу `urn:e` является успешной, а доставка сообщения по адресу `urn:a` — неудачной).</span><span class="sxs-lookup"><span data-stu-id="b2656-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""   
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"   
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="b2656-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="b2656-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b2656-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="b2656-125">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b2656-126">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="b2656-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b2656-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="b2656-127">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b2656-128">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="b2656-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b2656-129">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b2656-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="b2656-130">Чтобы запустить пример в конфигурации с одним компьютером, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b2656-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b2656-131">Чтобы запустить пример в конфигурации с несколькими компьютерами, следуйте инструкциям в разделе [Запуск примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md) и измените следующую строку в Client.cs.</span><span class="sxs-lookup"><span data-stu-id="b2656-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="b2656-132">Замените localhost именем сервера.</span><span class="sxs-lookup"><span data-stu-id="b2656-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
