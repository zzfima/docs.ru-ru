---
title: "Вызов службы в стиле REST из службы WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b056e2c4dad46429462b377994919b46109cb9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="calling-a-rest-style-service-from-a-wcf-service"></a><span data-ttu-id="4df88-102">Вызов службы в стиле REST из службы WCF</span><span class="sxs-lookup"><span data-stu-id="4df88-102">Calling a REST-style service from a WCF service</span></span>
<span data-ttu-id="4df88-103">При вызове REST-службы из обычной (на основе SOAP) службы WCF контекст операции в методе службы (со сведениями о входящем запросе) переопределяет контекст, который должен использоваться исходящим запросом.</span><span class="sxs-lookup"><span data-stu-id="4df88-103">When calling a REST-style service from a regular (SOAP-based) WCF service, the operation context on the service method (which contains information about the incoming request) overrides the context which should be used by the outgoing request.</span></span> <span data-ttu-id="4df88-104">В результате запросы HTTP GET превращаются в запросы HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="4df88-104">This causes HTTP GET requests to change to HTTP POST requests.</span></span> <span data-ttu-id="4df88-105">Чтобы заставить службу WCF использовать правильный контекст для вызова REST-службы, создайте новый объект <xref:System.ServiceModel.OperationContextScope> и вызовите REST-службу из области контекста операции.</span><span class="sxs-lookup"><span data-stu-id="4df88-105">To force the WCF service to use the right context for calling the REST-style service, create a new <xref:System.ServiceModel.OperationContextScope> and call the REST-style service from inside the operation context scope.</span></span> <span data-ttu-id="4df88-106">В этом разделе описано создание простого примера, иллюстрирующего данный способ.</span><span class="sxs-lookup"><span data-stu-id="4df88-106">This topic will describe how to create a simple sample that illustrates this technique.</span></span>  
  
## <a name="define-the-rest-style-service-contract"></a><span data-ttu-id="4df88-107">Определите контракт REST-службы</span><span class="sxs-lookup"><span data-stu-id="4df88-107">Define the REST-style service contract</span></span>  
 <span data-ttu-id="4df88-108">Определите простой контракт службы для REST-службы.</span><span class="sxs-lookup"><span data-stu-id="4df88-108">Define a simple  REST-style service contract:</span></span>  
  
```csharp
[ServiceContract]
public interface IRestInterface  
{  
    [OperationContract, WebGet]
    int Add(int x, int y);
    
    [OperationContract, WebGet]
    string Echo(string input);
}
```
  
## <a name="implement-the-rest-style-service-contract"></a><span data-ttu-id="4df88-109">Реализуйте контракт REST-службы</span><span class="sxs-lookup"><span data-stu-id="4df88-109">Implement the REST-style service contract</span></span>  
 <span data-ttu-id="4df88-110">Реализуйте контракт REST-службы.</span><span class="sxs-lookup"><span data-stu-id="4df88-110">Implement the REST-style service contract:</span></span>  
  
```csharp
public class RestService : IRestInterface
{
    public int Add(int x, int y)
    {
        return x + y;
    }
    
    public string Echo(string input)
    {
        return input;
    }
}
```
  
## <a name="define-the-wcf-service-contract"></a><span data-ttu-id="4df88-111">Определите контракт службы WCF</span><span class="sxs-lookup"><span data-stu-id="4df88-111">Define the WCF service contract</span></span>  
 <span data-ttu-id="4df88-112">Определите контракт службы WCF, которая будет использоваться для вызова REST-службы.</span><span class="sxs-lookup"><span data-stu-id="4df88-112">Define a WCF service contract  that will be used to call the REST-style service:</span></span>  
  
```csharp
[ServiceContract]
public interface INormalInterface
{
    [OperationContract]
    int CallAdd(int x, int y);
    
    [OperationContract]
    string CallEcho(string input);
}
```  
  
## <a name="implement-the-wcf-service-contract"></a><span data-ttu-id="4df88-113">Реализуйте контракт службы WCF</span><span class="sxs-lookup"><span data-stu-id="4df88-113">Implement the WCF service contract</span></span>  
 <span data-ttu-id="4df88-114">Реализуйте контракт службы WCF.</span><span class="sxs-lookup"><span data-stu-id="4df88-114">Implement the WCF service contract:</span></span>  
  
```csharp
public class NormalService : INormalInterface  
{  
    static MyRestClient client = new MyRestClient(RestServiceBaseAddress);  
    public int CallAdd(int x, int y)  
    {  
        return client.Add(x, y);  
    }  
    
    public string CallEcho(string input)  
    {  
        return client.Echo(input);  
    }  
}  
```  
  
## <a name="create-the-client-proxy-for-the-rest-style-service"></a><span data-ttu-id="4df88-115">Создайте клиентский прокси-класс для REST-службы</span><span class="sxs-lookup"><span data-stu-id="4df88-115">Create the client proxy for the REST-style service</span></span>  
 <span data-ttu-id="4df88-116">С помощью <!--zz<xref:System.ServiceModel.ClientBase%60>--> `System.ServiceModel.ClientBase` реализовать прокси клиента.</span><span class="sxs-lookup"><span data-stu-id="4df88-116">Using <!--zz<xref:System.ServiceModel.ClientBase%60>--> `System.ServiceModel.ClientBase` implement the client proxy.</span></span> <span data-ttu-id="4df88-117">Для каждого вызываемого метода создается и используется для вызова операции новая <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="4df88-117">For each method called, a new <xref:System.ServiceModel.OperationContextScope> is created and used to call the operation.</span></span>  
  
```csharp
public class MyRestClient : ClientBase<IRestInterface>, IRestInterface
{
    public MyRestClient(string address)
        : base(new WebHttpBinding(), new EndpointAddress(address))
    {
        this.Endpoint.Behaviors.Add(new WebHttpBehavior());
    }

    public int Add(int x, int y)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Add(x, y);
        }
    }

    public string Echo(string input)
    {
        using (new OperationContextScope(this.InnerChannel))
        {
            return base.Channel.Echo(input);
        }
    }
}
```  
  
## <a name="host-and-call-the-services"></a><span data-ttu-id="4df88-118">Размещение и вызов служб</span><span class="sxs-lookup"><span data-stu-id="4df88-118">Host and call the services</span></span>  
 <span data-ttu-id="4df88-119">Разместите обе службы в консольном приложении, добавив необходимые конечные точки и поведение.</span><span class="sxs-lookup"><span data-stu-id="4df88-119">Host both services in a console app, adding the needed endpoints and behaviors.</span></span> <span data-ttu-id="4df88-120">Затем вызовите обычную службу WCF.</span><span class="sxs-lookup"><span data-stu-id="4df88-120">And then call the regular WCF service:</span></span>  
  
```csharp
public static void Main()
{
    ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));
    restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());
    restHost.Open();

    ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));
    normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");
    normalHost.Open();

    Console.WriteLine("Hosts opened");

    ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));
    INormalInterface proxy = factory.CreateChannel();

    Console.WriteLine(proxy.CallAdd(123, 456));
    Console.WriteLine(proxy.CallEcho("Hello world"));
}
```  
  
## <a name="complete-code-listing"></a><span data-ttu-id="4df88-121">Полный листинг кода</span><span class="sxs-lookup"><span data-stu-id="4df88-121">Complete code listing</span></span>  
 <span data-ttu-id="4df88-122">Ниже полностью приведен код примера, представленного в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="4df88-122">The following is a complete listing of the sample implemented in this topic:</span></span>  
  
```csharp
public class CallingRESTSample  
{  
    static readonly string RestServiceBaseAddress = "http://" + Environment.MachineName + ":8008/Service";  
    static readonly string NormalServiceBaseAddress = "http://" + Environment.MachineName + ":8000/Service";  

    [ServiceContract]  
    public interface IRestInterface  
    {  
        [OperationContract, WebGet]  
        int Add(int x, int y);  
        [OperationContract, WebGet]  
        string Echo(string input);  
    }  

    [ServiceContract]  
    public interface INormalInterface  
    {  
        [OperationContract]  
        int CallAdd(int x, int y);  
        [OperationContract]  
        string CallEcho(string input);  
    }  

    public class RestService : IRestInterface  
    {  
        public int Add(int x, int y)  
        {  
            return x + y;  
        }  

        public string Echo(string input)  
        {  
            return input;  
        }  
    }  

    public class MyRestClient : ClientBase<IRestInterface>, IRestInterface  
    {  
        public MyRestClient(string address)  
            : base(new WebHttpBinding(), new EndpointAddress(address))  
        {  
            this.Endpoint.Behaviors.Add(new WebHttpBehavior());  
        }  

        public int Add(int x, int y)  
        {  
            using (new OperationContextScope(this.InnerChannel))  
            {  
                return base.Channel.Add(x, y);  
            }  
        }  

        public string Echo(string input)  
        {  
            using (new OperationContextScope(this.InnerChannel))  
            {  
                return base.Channel.Echo(input);  
            }  
        }  
    }  

    public class NormalService : INormalInterface  
    {  
        static MyRestClient client = new MyRestClient(RestServiceBaseAddress);  
        public int CallAdd(int x, int y)  
        {  
            return client.Add(x, y);  
        }  

        public string CallEcho(string input)  
        {  
            return client.Echo(input);  
        }  
    }
    
    public static void Main()  
    {  
        ServiceHost restHost = new ServiceHost(typeof(RestService), new Uri(RestServiceBaseAddress));  
        restHost.AddServiceEndpoint(typeof(IRestInterface), new WebHttpBinding(), "").Behaviors.Add(new WebHttpBehavior());  
        restHost.Open();  

        ServiceHost normalHost = new ServiceHost(typeof(NormalService), new Uri(NormalServiceBaseAddress));  
        normalHost.AddServiceEndpoint(typeof(INormalInterface), new BasicHttpBinding(), "");  
        normalHost.Open();  

        Console.WriteLine("Hosts opened");  

        ChannelFactory<INormalInterface> factory = new ChannelFactory<INormalInterface>(new BasicHttpBinding(), new EndpointAddress(NormalServiceBaseAddress));  
        INormalInterface proxy = factory.CreateChannel();  

        Console.WriteLine(proxy.CallAdd(123, 456));  
        Console.WriteLine(proxy.CallEcho("Hello world"));  
    }  
}
```
  
## <a name="see-also"></a><span data-ttu-id="4df88-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4df88-123">See Also</span></span>  
 [<span data-ttu-id="4df88-124">Практическое руководство. Создание базовой веб-службы HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="4df88-124">How to: Create a Basic WCF Web HTTP Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)  
 [<span data-ttu-id="4df88-125">Объектная модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="4df88-125">WCF Web HTTP Programming Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)
