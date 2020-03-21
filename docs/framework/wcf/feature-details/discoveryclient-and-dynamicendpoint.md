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
# <a name="discoveryclient-and-dynamicendpoint"></a>DiscoveryClient и DynamicEndpoint
<xref:System.ServiceModel.Discovery.DiscoveryClient> и <xref:System.ServiceModel.Discovery.DynamicEndpoint> представляют собой два класса, используемые на стороне клиента для поиска служб. <xref:System.ServiceModel.Discovery.DiscoveryClient> предоставляет список служб, соответствующих конкретному набору требований, и позволяет подключиться к службам. <xref:System.ServiceModel.Discovery.DynamicEndpoint> выполняет те же функции и, кроме того, автоматически подключается к одной из найденных служб. Все конечные точки могут быть преобразованы в <xref:System.ServiceModel.Discovery.DynamicEndpoint>, условие поиска также может быть добавлено в конфигурацию, поэтому <xref:System.ServiceModel.Discovery.DynamicEndpoint> полезен в случаях, когда в решении необходима функция обнаружения, но изменения логики клиента нежелательны (нужно лишь изменить конечные точки). С другой стороны, <xref:System.ServiceModel.Discovery.DiscoveryClient> можно использовать для более точного контроля над операцией поиска. Использование и преимущества каждого класса уточняются далее.  
  
## <a name="discoveryclient"></a>DiscoveryClient  
 Класс <xref:System.ServiceModel.Discovery.DiscoveryClient> определяет синхронный и асинхронный методы Find, а также события <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged>.  Он также определяет синхронные и асинхронные методы Resolve и событие <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveCompleted>. Методы <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A> служат для поиска служб. Оба эти метода принимают экземпляр <xref:System.ServiceModel.Discovery.FindCriteria>, что позволяет указать имя типа контракта, область действия, максимальное количество запрошенных результатов и область сопоставления результатов. События <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> и <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> могут использоваться при вызове метода <xref:System.ServiceModel.Discovery.DiscoveryClient.FindAsync%2A>. Событие <xref:System.ServiceModel.Discovery.DiscoveryClient.FindProgressChanged> инициируется каждый раз, когда <xref:System.ServiceModel.Discovery.DiscoveryClient> получает ответ от службы. Оно может быть использовано для отображения индикатора выполнения, показывающего ход выполнения операции поиска. Оно также может быть использовано для обработки запросов поиска при их поступлении. Событие <xref:System.ServiceModel.Discovery.DiscoveryClient.FindCompleted> вызывается при завершении операции поиска. Это может произойти при получении максимального количества ответов или по истечении времени, определенного свойством <xref:System.ServiceModel.Discovery.FindCriteria.Duration%2A>. При завершении операции поиска результаты возвращаются в экземпляре <xref:System.ServiceModel.Discovery.FindResponse>. Объект <xref:System.ServiceModel.Discovery.FindResponse> содержит коллекцию объектов <xref:System.ServiceModel.Discovery.EndpointDiscoveryMetadata>, содержащих адреса, имена типов контрактов, расширения, URI-прослушивания, области сопоставления служб. Далее эти сведения могут быть использованы для соединения и вызова одной из сопоставленных служб. В следующем примере показано, как позвонить в System.ServiceModel.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria) метод и использовать возвращенные метаданные для вызова найденной службы. Преимущество использования <xref:System.ServiceModel.Discovery.DiscoveryClient.Find(System.ServiceModel.Discovery.FindCriteria)> заключается в том, что вы можете кэшировать список конечных точек, которые вы нашли, и использовать их позже. Этот кэш позволяет создать логику для обработки различных условий отказа.  
  
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
  
 В следующем примере описано асинхронное выполнение операции поиска.  
  
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
  
 Для поиска службы по ее адресу конечной точки используйте методы <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A> и <xref:System.ServiceModel.Discovery.DiscoveryClient.ResolveAsync%28System.ServiceModel.Discovery.ResolveCriteria%29>. Это может оказаться полезным в тех случаях, когда конечная точка не может быть адресована через сеть. Метод Resolve принимает экземпляр <xref:System.ServiceModel.Discovery.ResolveCriteria>, что позволяет задать разрешаемый адрес конечной точки, максимальную продолжительность операции разрешения, набор расширений. В следующем примере показано, каким образом производится разрешение службы с помощью метода <xref:System.ServiceModel.Discovery.DiscoveryClient.Resolve%2A>.  
  
```csharp  
DiscoveryClient dc = new DiscoveryClient(new UdpDiscoveryEndpoint());  
ResolveCriteria criteria = new ResolveCriteria(endpointAddress);  
ResolveResponse response = dc.Resolve(criteria);  
EndpointAddress newEp = response.EndpointDiscoveryMetadata.Address;  
```  
  
## <a name="dynamicendpoint"></a>DynamicEndpoint  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>является стандартной конечнейточкой (Для получения дополнительной информации, [см. Standard Endpoints](../../../../docs/framework/wcf/feature-details/standard-endpoints.md)), который выполняет открытие и автоматически выбирает соответствующую службу. Необходимо всего лишь создать <xref:System.ServiceModel.Discovery.DynamicEndpoint>, передав ей искомый контракт и используемую привязку, и передать экземпляр <xref:System.ServiceModel.Discovery.DynamicEndpoint> клиенту WCF. В следующем примере показано создание и использование <xref:System.ServiceModel.Discovery.DynamicEndpoint> для вызова службы калькулятора. Поиск выполняется при каждом открытии клиента. Любая конечная точка, определенная <xref:System.ServiceModel.Discovery.DynamicEndpoint> в конфигурации, также может быть преобразована в `kind ="dynamicEndpoint"` элемент конфигурации конечных точек.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Обнаружение с помощью областей](../../../../docs/framework/wcf/samples/discovery-with-scopes-sample.md)
- [Основные](../../../../docs/framework/wcf/samples/basic-sample.md)
