---
title: "Как программно добавить возможность обнаружения к службе и клиенту WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f94d99542a07711f618bc02316e6f61f6df647d8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="97bee-102">Как программно добавить возможность обнаружения к службе и клиенту WCF</span><span class="sxs-lookup"><span data-stu-id="97bee-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="97bee-103">В этом разделе описано, как сделать службу [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] доступной для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="97bee-103">This topic explains how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span> <span data-ttu-id="97bee-104">Он основан на [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) образца.</span><span class="sxs-lookup"><span data-stu-id="97bee-104">It is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="97bee-105">Настройка образца службы существующего резидентного размещения для обнаружения</span><span class="sxs-lookup"><span data-stu-id="97bee-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1.  <span data-ttu-id="97bee-106">Откройте решение резидентного размещения в среде [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97bee-106">Open the Self-Host solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="97bee-107">Образец находится в каталоге TechnologySamples\Basic\Service\Hosting\SelfHost.</span><span class="sxs-lookup"><span data-stu-id="97bee-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2.  <span data-ttu-id="97bee-108">Добавьте ссылку на проект службы `System.ServiceModel.Discovery.dll`.</span><span class="sxs-lookup"><span data-stu-id="97bee-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="97bee-109">Может появиться сообщение об ошибке «System.</span><span class="sxs-lookup"><span data-stu-id="97bee-109">You may see an error message saying "System.</span></span> <span data-ttu-id="97bee-110">ServiceModel.Discovery.dll или одна из его зависимостей требует более поздней версии [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] отличные от указанных в проект...»</span><span class="sxs-lookup"><span data-stu-id="97bee-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] than the one specified in the project …"</span></span> <span data-ttu-id="97bee-111">Если вы видите это сообщение, щелкните правой кнопкой мыши проект в обозревателе решений и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="97bee-111">If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="97bee-112">В **свойства проекта** окна, убедитесь, что **требуемой версии .NET Framework** — [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="97bee-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3.  <span data-ttu-id="97bee-113">Откройте файл Service.cs и добавьте следующую инструкцию `using`.</span><span class="sxs-lookup"><span data-stu-id="97bee-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  <span data-ttu-id="97bee-114">В методе `Main()` в инструкции `using` добавьте экземпляр <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> в узел службы.</span><span class="sxs-lookup"><span data-stu-id="97bee-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
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
  
     <span data-ttu-id="97bee-115"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> указывает, что служба, к которой оно применяется, доступна для обнаружения.</span><span class="sxs-lookup"><span data-stu-id="97bee-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5.  <span data-ttu-id="97bee-116">Добавьте <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в узел службы сразу после кода, добавляющего <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span><span class="sxs-lookup"><span data-stu-id="97bee-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="97bee-117">Этот код указывает, что сообщения об обнаружении должны отправляться стандартной конечной точке обнаружения UDP.</span><span class="sxs-lookup"><span data-stu-id="97bee-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="97bee-118">Создание клиентского приложения, использующего обнаружение при вызове службы</span><span class="sxs-lookup"><span data-stu-id="97bee-118">To create a client application that uses discovery to call the service</span></span>  
  
1.  <span data-ttu-id="97bee-119">Добавьте в решение новое консольное приложение с именем `DiscoveryClientApp`.</span><span class="sxs-lookup"><span data-stu-id="97bee-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2.  <span data-ttu-id="97bee-120">Добавьте ссылку на сборки `System.ServiceModel.dll` и `System.ServiceModel.Discovery.dll`.</span><span class="sxs-lookup"><span data-stu-id="97bee-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3.  <span data-ttu-id="97bee-121">Скопируйте файлы GeneratedClient.cs и App.config из существующего проекта клиента в новый проект DiscoveryClientApp.</span><span class="sxs-lookup"><span data-stu-id="97bee-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="97bee-122">Для этого щелкните правой кнопкой мыши файлы в **обозревателе решений**выберите **копирования**и выберите **DiscoveryClientApp** проекта, щелкните правой кнопкой мыши и выберите **Вставить**.</span><span class="sxs-lookup"><span data-stu-id="97bee-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4.  <span data-ttu-id="97bee-123">Откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="97bee-123">Open Program.cs.</span></span>  
  
5.  <span data-ttu-id="97bee-124">Добавьте следующие инструкции `using`.</span><span class="sxs-lookup"><span data-stu-id="97bee-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  <span data-ttu-id="97bee-125">Добавьте статический метод с именем `FindCalculatorServiceAddress()` в класс `Program`.</span><span class="sxs-lookup"><span data-stu-id="97bee-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="97bee-126">Этот метод использует обнаружение для поиска службы `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="97bee-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7.  <span data-ttu-id="97bee-127">Внутри метода `FindCalculatorServiceAddress` создайте новый экземпляр <xref:System.ServiceModel.Discovery.DiscoveryClient>, передав <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> в конструктор.</span><span class="sxs-lookup"><span data-stu-id="97bee-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="97bee-128">Это указывает [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], что классу <xref:System.ServiceModel.Discovery.DiscoveryClient> следует использовать стандартную конечную точку обнаружения UDP для отправки и получения сообщений об обнаружении.</span><span class="sxs-lookup"><span data-stu-id="97bee-128">This tells [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8.  <span data-ttu-id="97bee-129">В следующей строке вызовите метод <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> и укажите экземпляр <xref:System.ServiceModel.Discovery.FindCriteria>, содержащий контракт службы, который необходимо найти.</span><span class="sxs-lookup"><span data-stu-id="97bee-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="97bee-130">В данном случае укажите `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="97bee-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="97bee-131">После вызова <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> проверьте наличие хотя бы одной соответствующей службы и верните <xref:System.ServiceModel.EndpointAddress> первой из найденных.</span><span class="sxs-lookup"><span data-stu-id="97bee-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="97bee-132">В противном случае верните значение `null`.</span><span class="sxs-lookup"><span data-stu-id="97bee-132">Otherwise return `null`.</span></span>  
  
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
  
10. <span data-ttu-id="97bee-133">Добавьте статический метод с именем `InvokeCalculatorService` в класс `Program`.</span><span class="sxs-lookup"><span data-stu-id="97bee-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="97bee-134">Этот метод использует для вызова службы калькулятора адрес конечной точки, возвращенной из `FindCalculatorServiceAddress`.</span><span class="sxs-lookup"><span data-stu-id="97bee-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="97bee-135">Внутри метода `InvokeCalculatorService` создайте экземпляр класса `CalculatorServiceClient`.</span><span class="sxs-lookup"><span data-stu-id="97bee-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="97bee-136">Этот класс определяется [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) образца.</span><span class="sxs-lookup"><span data-stu-id="97bee-136">This class is defined by the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="97bee-137">Он был сформирован с помощью программы Svcutil.exe.</span><span class="sxs-lookup"><span data-stu-id="97bee-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="97bee-138">В следующей строке укажите адрес конечной точки клиента в адресе конечной точки, возвращенном методом `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="97bee-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="97bee-139">Сразу после кода предыдущего шага вызовите методы, доступные через службу калькулятора.</span><span class="sxs-lookup"><span data-stu-id="97bee-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
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
  
14. <span data-ttu-id="97bee-140">Добавьте в метод `Main()` класса `Program` код для вызова `FindCalculatorServiceAddress`.</span><span class="sxs-lookup"><span data-stu-id="97bee-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="97bee-141">В следующей строке вызовите метод `InvokeCalculatorService()` и передайте конечной точке адрес, возвращенный методом `FindCalculatorServiceAddress()`.</span><span class="sxs-lookup"><span data-stu-id="97bee-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="97bee-142">Тестирование приложения</span><span class="sxs-lookup"><span data-stu-id="97bee-142">To test the application</span></span>  
  
1.  <span data-ttu-id="97bee-143">Откройте командную строку с правами администратора и запустите программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="97bee-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2.  <span data-ttu-id="97bee-144">Откройте окно командной строки и запустите программу Discoveryclientapp.exe.</span><span class="sxs-lookup"><span data-stu-id="97bee-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3.  <span data-ttu-id="97bee-145">Результатом выполнения service.exe должен быть следующий вывод.</span><span class="sxs-lookup"><span data-stu-id="97bee-145">The output from service.exe should look like the following output.</span></span>  
  
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
  
4.  <span data-ttu-id="97bee-146">Результатом выполнения Discoveryclientapp.exe должен быть следующий вывод.</span><span class="sxs-lookup"><span data-stu-id="97bee-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="97bee-147">Пример</span><span class="sxs-lookup"><span data-stu-id="97bee-147">Example</span></span>  
 <span data-ttu-id="97bee-148">Ниже приведен полный листинг кода для данного образца.</span><span class="sxs-lookup"><span data-stu-id="97bee-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="97bee-149">Поскольку этот код основан на [резидентной](http://go.microsoft.com/fwlink/?LinkId=145523) примера перечислены только те файлы, которые будут изменены.</span><span class="sxs-lookup"><span data-stu-id="97bee-149">Because this code is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="97bee-150">Пример резидентного размещения, в разделе [инструкции по установке](http://go.microsoft.com/fwlink/?LinkId=145522).</span><span class="sxs-lookup"><span data-stu-id="97bee-150"> the Self-Host sample, see [Setup Instructions](http://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
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

## <a name="see-also"></a><span data-ttu-id="97bee-151">См. также</span><span class="sxs-lookup"><span data-stu-id="97bee-151">See Also</span></span>  
 [<span data-ttu-id="97bee-152">Общие сведения об обнаружении WCF</span><span class="sxs-lookup"><span data-stu-id="97bee-152">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="97bee-153">Модель объектов обнаружения WCF</span><span class="sxs-lookup"><span data-stu-id="97bee-153">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
