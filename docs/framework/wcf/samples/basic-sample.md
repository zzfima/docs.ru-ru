---
title: Базовый образец
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 2ea5af0a1c05b5632632b2619c0ee4813696d2fc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738180"
---
# <a name="basic-sample"></a>Базовый образец

В этом образце показано, как сделать службу обнаруживаемой, а также как искать и вызывать обнаруживаемую службу. Этот образец состоит из двух проектов: службы и клиента.

> [!NOTE]
> Этот образец реализует возможность обнаружения в коде.  Пример, в котором реализуется обнаружение в конфигурации, см. в разделе [Configuration](../../../../docs/framework/wcf/samples/configuration-sample.md).

## <a name="service"></a>Service

Это простая реализация службы калькулятора. Код обнаружения можно найти в `Main`, где к узлу службы добавляется <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> и добавляется <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>, как показано в следующем примере кода.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new
      WSHttpBinding(), String.Empty);

    // Make the service discoverable over UDP multicast
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    serviceHost.Open();
    // ...
}
```

## <a name="client"></a>Клиент

Клиент использует <xref:System.ServiceModel.Discovery.DynamicEndpoint> для определения местоположения службы. Стандартная конечная точка <xref:System.ServiceModel.Discovery.DynamicEndpoint> вычисляет конечную точку службы, когда открывается клиент. В этом случае <xref:System.ServiceModel.Discovery.DynamicEndpoint> ищет службу на основе контракта службы. Конечная точка <xref:System.ServiceModel.Discovery.DynamicEndpoint> ведет поиск по <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> по умолчанию. Когда конечная точка службы найдена, клиент подключается к этой службе по заданной привязке.

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

Клиент определяет метод `InvokeCalculatorService`, который использует класс <xref:System.ServiceModel.Discovery.DiscoveryClient> для поиска служб. Класс <xref:System.ServiceModel.Discovery.DynamicEndpoint> наследует от класса <xref:System.ServiceModel.Description.ServiceEndpoint>, чтобы он мог быть передан в метод `InvokeCalculatorService`. В примере затем используется конечная точка <xref:System.ServiceModel.Discovery.DynamicEndpoint> для создания экземпляра `CalculatorServiceClient` и вызываются различные операции службы калькулятора.

```csharp
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)
{
   // Create a client
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);

   Console.WriteLine("Invoking CalculatorService");
   Console.WriteLine();

   double value1 = 100.00D;
   double value2 = 15.99D;

   // Call the Add service operation.
   double result = client.Add(value1, value2);
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

   // Call the Subtract service operation.
   result = client.Subtract(value1, value2);
   Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

   // Call the Multiply service operation.
   result = client.Multiply(value1, value2);
   Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

   // Call the Divide service operation.
   result = client.Divide(value1, value2);
   Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
   Console.WriteLine();

   //Closing the client gracefully closes the connection and cleans up resources
   client.Close();
}
```

#### <a name="to-use-this-sample"></a>Использование этого образца

1. В этом образце используются конечные точки HTTP, и для работы этого образца необходимо добавить соответствующие списки управления доступом по URL-адресу. Дополнительные сведения см. в разделе [Настройка HTTP и HTTPS](../feature-details/configuring-http-and-https.md). Нужные списки управления доступом будут добавлены после выполнения следующей команды с повышенными привилегиями. Если команда не работает, следует указать домен и имя пользователя в следующих аргументах. `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. С помощью Visual Studio 2012 откройте файл Basic. sln и создайте пример.

3. Запустите приложение service.exe.

4. После запуска службы запустите client.exe.

5. Заметьте, что клиенту удалось найти службу, не зная ее адреса.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
