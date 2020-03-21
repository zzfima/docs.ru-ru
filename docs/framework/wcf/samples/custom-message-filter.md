---
title: Пользовательский фильтр сообщений
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 896407a218073eba53676baa4bcbd125593c80ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183888"
---
# <a name="custom-message-filter"></a><span data-ttu-id="ede76-102">Пользовательский фильтр сообщений</span><span class="sxs-lookup"><span data-stu-id="ede76-102">Custom Message Filter</span></span>
<span data-ttu-id="ede76-103">В этом примере показано, как заменить фильтры сообщений, которые Windows Communication Foundation (WCF) использует для отправки сообщений в конечные точки.</span><span class="sxs-lookup"><span data-stu-id="ede76-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ede76-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="ede76-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ede76-105">При поступлении на сервер первого сообщения из канала сервер должен определить, какие конечные точки, связанные с данным URI, должны получить сообщение.</span><span class="sxs-lookup"><span data-stu-id="ede76-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="ede76-106">Этот процесс контролируется объектами <xref:System.ServiceModel.Dispatcher.MessageFilter> присоединенными к диспетчеру <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="ede76-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="ede76-107">У каждой конечной точки службы имеется один диспетчер <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span><span class="sxs-lookup"><span data-stu-id="ede76-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="ede76-108">У диспетчера <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> имеются как фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>, так и фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="ede76-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="ede76-109">Объединение этих двух фильтров является фильтром сообщений, используемым для данной конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ede76-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="ede76-110">По умолчанию фильтр <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> для конечной точки соответствует любому сообщению, передаваемому по адресу, который соответствует адресу <xref:System.ServiceModel.EndpointAddress> конечной точки службы.</span><span class="sxs-lookup"><span data-stu-id="ede76-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="ede76-111">По умолчанию <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> конечная точка проверяет действие входящего сообщения и сопоставляет любое сообщение с действием, которое соответствует одному из `IsInitiating` = `true` действий операций конечной точки контракта службы (рассматриваются только действия).</span><span class="sxs-lookup"><span data-stu-id="ede76-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="ede76-112">В результате по умолчанию соответствие фильтру для конечной точки обеспечивается, только если в заголовках "To" обоих сообщений задан адрес <xref:System.ServiceModel.EndpointAddress> конечной точки и действие сообщения соответствует одному из действий операции конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ede76-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="ede76-113">Эти фильтры можно изменить с помощью поведения.</span><span class="sxs-lookup"><span data-stu-id="ede76-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="ede76-114">В этом образце служба создает интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior>, который заменяет фильтры <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> и <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> в диспетчере <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span><span class="sxs-lookup"><span data-stu-id="ede76-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="ede76-115">Определяется два фильтра адресов:</span><span class="sxs-lookup"><span data-stu-id="ede76-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="ede76-116">Поведение `FilteringEndpointBehavior` делается настраиваемым и предусматривает два различных варианта.</span><span class="sxs-lookup"><span data-stu-id="ede76-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="ede76-117">Вариант 1 соответствует только адресам, в которых содержится буква 'e' (и которые имеют любое действие), а вариант 2 соответствует только адресам, в которых отсутствует буква 'e':</span><span class="sxs-lookup"><span data-stu-id="ede76-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="ede76-118">В файле конфигурации служба регистрирует новое поведение:</span><span class="sxs-lookup"><span data-stu-id="ede76-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 <span data-ttu-id="ede76-119">Затем служба создает конфигурации `endpointBehavior` для каждого варианта:</span><span class="sxs-lookup"><span data-stu-id="ede76-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
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
  
 <span data-ttu-id="ede76-120">Наконец, конечная точка службы ссылается на одну из конфигураций `behaviorConfigurations`:</span><span class="sxs-lookup"><span data-stu-id="ede76-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="ede76-121">Реализация клиентского приложения является прямолинейной; она создает два канала к URI службы (передавая заданное значение в качестве второго параметра (`via`) методу <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29>) и отправляет одно сообщение по каждому каналу, но использует в каждом случае различные адреса конечной точки.</span><span class="sxs-lookup"><span data-stu-id="ede76-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="ede76-122">В результате исходящие сообщения клиента имеют разные адреса назначения в поле "To" и сервер реагирует соответствующим образом, как показано в выходных данных клиента:</span><span class="sxs-lookup"><span data-stu-id="ede76-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="ede76-123">Переключение варианта в файле конфигурации сервера приводит к перестановке фильтров, и на клиенте наблюдается противоположное поведение (доставка сообщения по адресу `urn:e` является успешной, а доставка сообщения по адресу `urn:a` — неудачной).</span><span class="sxs-lookup"><span data-stu-id="ede76-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="ede76-124">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="ede76-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ede76-125">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="ede76-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="ede76-126">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="ede76-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ede76-127">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="ede76-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ede76-128">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="ede76-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="ede76-129">Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="ede76-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="ede76-130">Чтобы запустить образец в одномашинной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="ede76-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="ede76-131">Чтобы запустить образец в конфигурации кросс-машины, следуйте инструкциям в [Запуске Windows Communication Foundation Образцы](../../../../docs/framework/wcf/samples/running-the-samples.md) и изменить следующую строку в Client.cs.</span><span class="sxs-lookup"><span data-stu-id="ede76-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="ede76-132">Замените localhost именем сервера.</span><span class="sxs-lookup"><span data-stu-id="ede76-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
