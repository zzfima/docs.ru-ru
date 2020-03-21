---
title: Как программно добавить возможность обнаружения к службе и клиенту WCF
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: dd96bc168413eef99260a5251e74971aa1309ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184885"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a>Как программно добавить возможность обнаружения к службе и клиенту WCF
Эта тема объясняет, как сделать сервис Windows Communication Foundation (WCF) обнаруживаемым. Он основан на примере [Self-Host.](https://go.microsoft.com/fwlink/?LinkId=145523)  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>Настройка образца службы существующего резидентного размещения для обнаружения  
  
1. Откройте решение Self-Host в Visual Studio 2012. Образец находится в каталоге TechnologySamples\Basic\Service\Hosting\SelfHost.  
  
2. Добавьте ссылку на проект службы `System.ServiceModel.Discovery.dll`. Вы можете увидеть сообщение об ошибке с надписью "Система. ServiceModel.Discovery.dll или одна из его зависимостей требует более поздней версии рамочной .NET, чем та, которая указана в проекте ..." Если вы видите это сообщение, нажмите правой кнопкой мыши проекта в Solution Explorer и выберите **Свойства**. В окне **свойств проектов** убедитесь, [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]что **целевая рамка** — это .  
  
3. Откройте файл Service.cs и добавьте следующую инструкцию `using`.  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. В методе `Main()` в инструкции `using` добавьте экземпляр <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> в узел службы.  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
  
            // ...  
        }  
    }  
    ```  
  
     <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> указывает, что служба, к которой оно применяется, доступна для обнаружения.  
  
5. Добавьте <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в узел службы сразу после кода, добавляющего <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Этот код указывает, что сообщения об обнаружении должны отправляться стандартной конечной точке обнаружения UDP.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>Создание клиентского приложения, использующего обнаружение при вызове службы  
  
1. Добавьте в решение новое консольное приложение с именем `DiscoveryClientApp`.  
  
2. Добавьте ссылку на сборки `System.ServiceModel.dll` и `System.ServiceModel.Discovery.dll`.  
  
3. Скопируйте файлы GeneratedClient.cs и App.config из существующего проекта клиента в новый проект DiscoveryClientApp. Для этого нажмите правой кнопкой мыши файлы в **Solution Explorer**, выберите **Copy**, а затем выберите проект **DiscoveryClientApp,** нажмите правой кнопкой мыши и выберите **Пасту**.  
  
4. Откройте файл Program.cs.  
  
5. Добавьте следующие операторы `using`.  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. Добавьте статический метод с именем `FindCalculatorServiceAddress()` в класс `Program`.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Этот метод использует обнаружение для поиска службы `CalculatorService`.  
  
7. Внутри метода `FindCalculatorServiceAddress` создайте новый экземпляр <xref:System.ServiceModel.Discovery.DiscoveryClient>, передав <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в конструктор.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     Это говорит WCF, что <xref:System.ServiceModel.Discovery.DiscoveryClient> класс должен использовать стандартную конечную точку открытия UDP для отправки и получения сообщений об открытии.  
  
8. В следующей строке вызовите метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> и укажите экземпляр <xref:System.ServiceModel.Discovery.FindCriteria>, содержащий контракт службы, который необходимо найти. В данном случае укажите `ICalculator`.  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. После вызова <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> проверьте наличие хотя бы одной соответствующей службы и верните <xref:System.ServiceModel.EndpointAddress> первой из найденных. В противном случае верните значение `null`.  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. Добавьте статический метод с именем `InvokeCalculatorService` в класс `Program`.  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     Этот метод использует для вызова службы калькулятора адрес конечной точки, возвращенной из `FindCalculatorServiceAddress`.  
  
11. Внутри метода `InvokeCalculatorService` создайте экземпляр класса `CalculatorServiceClient`. Этот класс определяется выборкой [Self-Host.](https://go.microsoft.com/fwlink/?LinkId=145523) Он был сформирован с помощью программы Svcutil.exe.  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. В следующей строке укажите адрес конечной точки клиента в адресе конечной точки, возвращенном методом `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. Сразу после кода предыдущего шага вызовите методы, доступные через службу калькулятора.  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
    ```  
  
14. Добавьте в метод `Main()` класса `Program` код для вызова `FindCalculatorServiceAddress`.  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. В следующей строке вызовите метод `InvokeCalculatorService()` и передайте конечной точке адрес, возвращенный методом `FindCalculatorServiceAddress()`.  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>Тестирование приложения  
  
1. Откройте командную строку с правами администратора и запустите программу Service.exe.  
  
2. Откройте окно командной строки и запустите программу Discoveryclientapp.exe.  
  
3. Результатом выполнения service.exe должен быть следующий вывод.  
  
    ```output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4. Результатом выполнения Discoveryclientapp.exe должен быть следующий вывод.  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен полный листинг кода для данного образца. Поскольку этот код основан на примере [Self-Host,](https://go.microsoft.com/fwlink/?LinkId=145523) перечислены только те файлы, которые изменены. Для получения дополнительной [информации](https://go.microsoft.com/fwlink/?LinkId=145522)о образце Self-Host см.  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a>См. также раздел

- [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Модель объектов обнаружения WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
