---
title: Как программно добавить возможность обнаружения к службе и клиенту WCF
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c0da3598b115df4f135ac3fab516447df85e258
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a>Как программно добавить возможность обнаружения к службе и клиенту WCF
В этом разделе описано, как сделать службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] доступной для обнаружения. Он основан на [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) образца.  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>Настройка образца службы существующего резидентного размещения для обнаружения  
  
1.  Откройте решение резидентного размещения в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]. Образец находится в каталоге TechnologySamples\Basic\Service\Hosting\SelfHost.  
  
2.  Добавьте ссылку на проект службы `System.ServiceModel.Discovery.dll`. Может появиться сообщение об ошибке «System. ServiceModel.Discovery.dll или одна из его зависимостей требует более поздней версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] отличные от указанных в проект...» Если вы видите это сообщение, щелкните правой кнопкой мыши проект в обозревателе решений и выберите **свойства**. В **свойства проекта** окна, убедитесь, что **требуемой версии .NET Framework** — [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
3.  Откройте файл Service.cs и добавьте следующую инструкцию `using`.  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  В методе `Main()` в инструкции `using` добавьте экземпляр <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> в узел службы.  
  
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
  
5.  Добавьте <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в узел службы сразу после кода, добавляющего <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Этот код указывает, что сообщения об обнаружении должны отправляться стандартной конечной точке обнаружения UDP.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>Создание клиентского приложения, использующего обнаружение при вызове службы  
  
1.  Добавьте в решение новое консольное приложение с именем `DiscoveryClientApp`.  
  
2.  Добавьте ссылку на сборки `System.ServiceModel.dll` и `System.ServiceModel.Discovery.dll`.  
  
3.  Скопируйте файлы GeneratedClient.cs и App.config из существующего проекта клиента в новый проект DiscoveryClientApp. Для этого щелкните правой кнопкой мыши файлы в **обозревателе решений**выберите **копирования**и выберите **DiscoveryClientApp** проекта, щелкните правой кнопкой мыши и выберите **Вставить**.  
  
4.  Откройте файл Program.cs.  
  
5.  Добавьте следующие инструкции `using`.  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  Добавьте статический метод с именем `FindCalculatorServiceAddress()` в класс `Program`.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Этот метод использует обнаружение для поиска службы `CalculatorService`.  
  
7.  Внутри метода `FindCalculatorServiceAddress` создайте новый экземпляр <xref:System.ServiceModel.Discovery.DiscoveryClient>, передав <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в конструктор.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     Это указывает [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], что классу <xref:System.ServiceModel.Discovery.DiscoveryClient> следует использовать стандартную конечную точку обнаружения UDP для отправки и получения сообщений об обнаружении.  
  
8.  В следующей строке вызовите метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> и укажите экземпляр <xref:System.ServiceModel.Discovery.FindCriteria>, содержащий контракт службы, который необходимо найти. В данном случае укажите `ICalculator`.  
  
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
  
11. Внутри метода `InvokeCalculatorService` создайте экземпляр класса `CalculatorServiceClient`. Этот класс определяется [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) образца. Он был сформирован с помощью программы Svcutil.exe.  
  
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
  
1.  Откройте командную строку с правами администратора и запустите программу Service.exe.  
  
2.  Откройте окно командной строки и запустите программу Discoveryclientapp.exe.  
  
3.  Результатом выполнения service.exe должен быть следующий вывод.  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  Результатом выполнения Discoveryclientapp.exe должен быть следующий вывод.  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Пример  
 Ниже приведен полный листинг кода для данного образца. Поскольку этот код основан на [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) примера перечислены только те файлы, которые будут изменены. Дополнительные сведения об образце резидентной см. в разделе [инструкции по установке](http://go.microsoft.com/fwlink/?LinkId=145522).  
  
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

## <a name="see-also"></a>См. также  
 [Общие сведения об обнаружении WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [Объектная модель обнаружения WCF](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
