---
title: DiscoveryClient и DynamicEndpoint
ms.date: 03/30/2017
ms.assetid: 7cd418f0-0eab-48d1-a493-7eb907867ec3
ms.openlocfilehash: c6d87a04a6787725ad7c4546650485af932882b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185185"
---
# <a name="discoveryclient-and-dynamicendpoint"></a><span data-ttu-id="20243-102">DiscoveryClient и DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="20243-102">DiscoveryClient and DynamicEndpoint</span></span>
<span data-ttu-id="20243-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> и <xref:System.ServiceModel.Discovery.DynamicEndpoint> представляют собой два класса, используемые на стороне клиента для поиска служб.</span><span class="sxs-lookup"><span data-stu-id="20243-103"><xref:System.ServiceModel.Discovery.DiscoveryClient> and <xref:System.ServiceModel.Discovery.DynamicEndpoint> are two classes used on the client side to search for services.</span></span> <span data-ttu-id="20243-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> предоставляет список служб, соответствующих конкретному набору требований, и позволяет подключиться к службам.</span><span class="sxs-lookup"><span data-stu-id="20243-104"><xref:System.ServiceModel.Discovery.DiscoveryClient> provides you with a list of services that match a specific set of criteria and allows you to connect to the services.</span></span> <span data-ttu-id="20243-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> выполняет те же функции и, кроме того, автоматически подключается к одной из найденных служб.</span><span class="sxs-lookup"><span data-stu-id="20243-105"><xref:System.ServiceModel.Discovery.DynamicEndpoint> performs the same operation and in addition, automatically connects to one of the services that was found.</span></span> <span data-ttu-id="20243-106">Все конечные точки могут быть преобразованы в <xref:System.ServiceModel.Discovery.DynamicEndpoint>, условие поиска также может быть добавлено в конфигурацию, поэтому <xref:System.ServiceModel.Discovery.DynamicEndpoint> полезен в случаях, когда в решении необходима функция обнаружения, но изменения логики клиента нежелательны (нужно лишь изменить конечные точки).</span><span class="sxs-lookup"><span data-stu-id="20243-106">Any endpoint can be made into a <xref:System.ServiceModel.Discovery.DynamicEndpoint>, the search criteria can also be added in configuration, thus <xref:System.ServiceModel.Discovery.DynamicEndpoint> is useful when you need discovery in your solution but do not want to modify the client logic – you only need to modify the endpoints.</span></span> <span data-ttu-id="20243-107">С другой стороны, <xref:System.ServiceModel.Discovery.DiscoveryClient> можно использовать для более точного контроля над операцией поиска.</span><span class="sxs-lookup"><span data-stu-id="20243-107"><xref:System.ServiceModel.Discovery.DiscoveryClient> on the other hand can be used to gain finer control over your search operation.</span></span> <span data-ttu-id="20243-108">Использование и преимущества каждого класса уточняются далее.</span><span class="sxs-lookup"><span data-stu-id="20243-108">The uses and benefits of each are elaborated below.</span></span>  
  
## <a name="discoveryclient"></a><span data-ttu-id="20243-109">DiscoveryClient</span><span class="sxs-lookup"><span data-stu-id="20243-109">DiscoveryClient</span></span>  
 <span data-ttu-id="20243-110">Класс <xref:System.ServiceModel.Discovery.DiscoveryClient> определяет синхронный и асинхронный методы Find, а также события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.</span><span class="sxs-lookup"><span data-stu-id="20243-110">The <xref:System.ServiceModel.Discovery.DiscoveryClient> defines synchronous and asynchronous Find methods, <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events.</span></span>  <span data-ttu-id="20243-111">Он также определяет синхронные и асинхронные методы Resolve и событие <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>.</span><span class="sxs-lookup"><span data-stu-id="20243-111">It also defines synchronous and asynchronous Resolve methods and a <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted> event.</span></span> <span data-ttu-id="20243-112">Методы <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> служат для поиска служб.</span><span class="sxs-lookup"><span data-stu-id="20243-112">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> or <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> methods to search for services.</span></span> <span data-ttu-id="20243-113">Оба эти метода принимают экземпляр <xref:System.ServiceModel.Discovery.FindCriteria>, что позволяет указать имя типа контракта, область действия, максимальное количество запрошенных результатов и область сопоставления результатов.</span><span class="sxs-lookup"><span data-stu-id="20243-113">Both of these methods take a <xref:System.ServiceModel.Discovery.FindCriteria> instance that allows you to specify contract type names, scopes, maximum number of results requested, and scope matching rules.</span></span> <span data-ttu-id="20243-114">События <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> могут использоваться при вызове метода <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="20243-114">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> and <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> events can be used when calling the <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> method.</span></span> <span data-ttu-id="20243-115">Событие <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> инициируется каждый раз, когда <xref:System.ServiceModel.Discovery.DiscoveryClient> получает ответ от службы.</span><span class="sxs-lookup"><span data-stu-id="20243-115"><xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> is fired whenever the <xref:System.ServiceModel.Discovery.DiscoveryClient> receives a response from a service.</span></span> <span data-ttu-id="20243-116">Оно может быть использовано для отображения индикатора выполнения, показывающего ход выполнения операции поиска.</span><span class="sxs-lookup"><span data-stu-id="20243-116">It can be used to display a progress bar showing the progress of the find operation.</span></span> <span data-ttu-id="20243-117">Оно также может быть использовано для обработки запросов поиска при их поступлении.</span><span class="sxs-lookup"><span data-stu-id="20243-117">It can also be used to act on find responses as they are received.</span></span> <span data-ttu-id="20243-118">Событие <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> вызывается при завершении операции поиска.</span><span class="sxs-lookup"><span data-stu-id="20243-118">The <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> event is fired when the find operation completes.</span></span> <span data-ttu-id="20243-119">Это может произойти при получении максимального количества ответов или по истечении времени, определенного свойством <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>.</span><span class="sxs-lookup"><span data-stu-id="20243-119">This may happen because the maximum number of responses has been received or if the <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A> has elapsed.</span></span> <span data-ttu-id="20243-120">При завершении операции поиска результаты возвращаются в экземпляре <xref:System.ServiceModel.Discovery.FindResponse>.</span><span class="sxs-lookup"><span data-stu-id="20243-120">When the find operation completes the results are returned in a <xref:System.ServiceModel.Discovery.FindResponse> instance.</span></span> <span data-ttu-id="20243-121">Объект <xref:System.ServiceModel.Discovery.FindResponse> содержит коллекцию объектов <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, содержащих адреса, имена типов контрактов, расширения, URI-прослушивания, области сопоставления служб.</span><span class="sxs-lookup"><span data-stu-id="20243-121">The <xref:System.ServiceModel.Discovery.FindResponse> contains a collection of <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata> which contains the addresses, contract type names, extensions, listen URIs, and scopes of the matching services.</span></span> <span data-ttu-id="20243-122">Далее эти сведения могут быть использованы для соединения и вызова одной из сопоставленных служб.</span><span class="sxs-lookup"><span data-stu-id="20243-122">You can then use this information to connect to and call one of the matching services.</span></span> <span data-ttu-id="20243-123">В следующем примере показано, как позвонить в System.ServiceModel.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) метод и использовать возвращенные метаданные для вызова найденной службы.</span><span class="sxs-lookup"><span data-stu-id="20243-123">The following example shows how to call the System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) method and use the returned metadata to call the found service.</span></span> <span data-ttu-id="20243-124">Преимущество использования <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> заключается в том, что вы можете кэшировать список конечных точек, которые вы нашли, и использовать их позже.</span><span class="sxs-lookup"><span data-stu-id="20243-124">A benefit of using <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> is that you can cache the list of endpoints you’ve found and use them at a later time.</span></span> <span data-ttu-id="20243-125">Этот кэш позволяет создать логику для обработки различных условий отказа.</span><span class="sxs-lookup"><span data-stu-id="20243-125">With this cache, you can build custom logic to handle various failure conditions.</span></span>  
  
```csharp
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
FindCriteria criteria = new FindCriteria(typeof(ICalculatorService));  
FindResponse fr = dc.Find(criteria);  
  
if (fr.Endpoints.Count > 0)  
{  
   EndpointAddress ep = fr.Endpoints[0].Address;  
   CalculatorServiceClient client = new CalculatorServiceClient();  
  
    // Connect to the discovered service endpoint  
   client.Endpoint.Address = endpointAddress;  
   Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
   double value1 = 100.00D;  
   double value2 = 15.99D;  
  
   // Call the Add service operation.  
   double result = client.Add(value1, value2);  
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
}  
else  
   Console.WriteLine("No matching endpoints found");  
```  
  
 <span data-ttu-id="20243-126">В следующем примере описано асинхронное выполнение операции поиска.</span><span class="sxs-lookup"><span data-stu-id="20243-126">The following example shows how to perform a find operation asynchronously.</span></span>  
  
```csharp
static void FindServiceAsync()  
{  
   DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());
   dc.FindCompleted += new EventHandler<FindCompletedEventArgs>( discoveryClient_FindCompleted);  
   dc.FindProgressChanged += new EventHandler<FindProgressChangedEventArgs>(discoveryClient_FindProgressChanged);  
   dc.FindAsync(new FindCriteria(typeof(ICalculatorService)));
}
static void discoveryClient_FindProgressChanged(object sender, FindProgressChangedEventArgs e)  
{  
   Console.WriteLine("Found service at: " + e.EndpointDiscoveryMetadata.Address  
}
  
static void discoveryClient_FindCompleted(object sender, FindCompletedEventArgs e)  
{
      if (e.Result.Endpoints.Count > 0)  
            {  
                EndpointAddress ep = e.Result.Endpoints[0].Address;  
                CalculatorServiceClient client = new CalculatorServiceClient();  
  
                // Connect to the discovered service endpoint  
                client.Endpoint.Address = ep;  
                Console.WriteLine("Invoking CalculatorService at {0}", ep);  
  
                double value1 = 100.00D;  
                double value2 = 15.99D;  
  
                double result = client.Add(value1, value2);  
                Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
            }  
            else  
                Console.WriteLine("No matching endpoints found");  
  
        }  
```
  
 <span data-ttu-id="20243-127">Для поиска службы по ее адресу конечной точки используйте методы <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> и <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29>.</span><span class="sxs-lookup"><span data-stu-id="20243-127">Use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> and <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29> methods to locate a service based on its endpoint address.</span></span> <span data-ttu-id="20243-128">Это может оказаться полезным в тех случаях, когда конечная точка не может быть адресована через сеть.</span><span class="sxs-lookup"><span data-stu-id="20243-128">This is useful when the endpoint address is not network addressable.</span></span> <span data-ttu-id="20243-129">Метод Resolve принимает экземпляр <xref:System.ServiceModel.Discovery.ResolveCriteria>, что позволяет задать разрешаемый адрес конечной точки, максимальную продолжительность операции разрешения, набор расширений.</span><span class="sxs-lookup"><span data-stu-id="20243-129">The Resolve methods take an instance of <xref:System.ServiceModel.Discovery.ResolveCriteria> which allows you to specify the endpoint address of the service you are resolving, the maximum duration of the resolve operation, and a set of extensions.</span></span> <span data-ttu-id="20243-130">В следующем примере показано, каким образом производится разрешение службы с помощью метода <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A>.</span><span class="sxs-lookup"><span data-stu-id="20243-130">The following example shows how to use the <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> method to resolve a service.</span></span>  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a><span data-ttu-id="20243-131">DynamicEndpoint</span><span class="sxs-lookup"><span data-stu-id="20243-131">DynamicEndpoint</span></span>  
 <span data-ttu-id="20243-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint>является стандартной конечнейточкой (Для получения дополнительной информации, [см. Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)), который выполняет открытие и автоматически выбирает соответствующую службу.</span><span class="sxs-lookup"><span data-stu-id="20243-132"><xref:System.ServiceModel.Discovery.DynamicEndpoint> is a standard endpoint (For more information, see [Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)) which performs discovery and automatically selects a matching service.</span></span> <span data-ttu-id="20243-133">Необходимо всего лишь создать <xref:System.ServiceModel.Discovery.DynamicEndpoint>, передав ей искомый контракт и используемую привязку, и передать экземпляр <xref:System.ServiceModel.Discovery.DynamicEndpoint> клиенту WCF.</span><span class="sxs-lookup"><span data-stu-id="20243-133">Just create a <xref:System.ServiceModel.Discovery.DynamicEndpoint> passing in the contract to search for and the binding to use and pass the <xref:System.ServiceModel.Discovery.DynamicEndpoint> instance to the WCF client.</span></span> <span data-ttu-id="20243-134">В следующем примере показано создание и использование <xref:System.ServiceModel.Discovery.DynamicEndpoint> для вызова службы калькулятора.</span><span class="sxs-lookup"><span data-stu-id="20243-134">The following example shows how to create and use a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to call the calculator service.</span></span> <span data-ttu-id="20243-135">Поиск выполняется при каждом открытии клиента.</span><span class="sxs-lookup"><span data-stu-id="20243-135">The discovery is performed every time the client is opened.</span></span> <span data-ttu-id="20243-136">Любая конечная точка, определенная <xref:System.ServiceModel.Discovery.DynamicEndpoint> в конфигурации, также может быть преобразована в `kind ="dynamicEndpoint"` элемент конфигурации конечных точек.</span><span class="sxs-lookup"><span data-stu-id="20243-136">Any endpoint defined in configuration can also be turned into a <xref:System.ServiceModel.Discovery.DynamicEndpoint> by adding the `kind ="dynamicEndpoint"` attribute to the endpoint configuration element.</span></span>  
  
```csharp  
DynamicEndpoint dynamicEndpoint = new DynamicEndpoint(ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());  
CalculatorServiceClient client = new CalculatorServiceClient(dynamicEndpoint);  
  
Console.WriteLine("Invoking CalculatorService");  
Console.WriteLine();  
  
double value1 = 100.00D;  
double value2 = 15.99D;  
  
double result = client.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
```  
  
## <a name="see-also"></a><span data-ttu-id="20243-137">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20243-137">See also</span></span>

- [<span data-ttu-id="20243-138">Обнаружение с помощью областей</span><span class="sxs-lookup"><span data-stu-id="20243-138">Discovery with Scopes</span></span>](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [<span data-ttu-id="20243-139">Основные</span><span class="sxs-lookup"><span data-stu-id="20243-139">Basic</span></span>](../../../../docs/framework/wcf/samples/basic-sample.md)
