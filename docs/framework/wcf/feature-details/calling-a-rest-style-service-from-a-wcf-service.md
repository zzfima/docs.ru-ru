---
title: "Вызов службы в стиле REST из службы WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 77df81d8-7f53-4daf-8d2d-bf7996e94d5a
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Вызов службы в стиле REST из службы WCF
При вызове REST\-службы из обычной \(на основе SOAP\) службы WCF контекст операции в методе службы \(со сведениями о входящем запросе\) переопределяет контекст, который должен использоваться исходящим запросом.  В результате запросы HTTP GET превращаются в запросы HTTP POST.  Чтобы заставить службу WCF использовать правильный контекст для вызова REST\-службы, создайте новый объект <xref:System.ServiceModel.OperationContextScope> и вызовите REST\-службу из области контекста операции.  В этом разделе описано создание простого примера, иллюстрирующего данный способ.  
  
## Определите контракт REST\-службы  
 Определите простой контракт службы для REST\-службы.  
  
```  
[ServiceContract]  
        public interface IRestInterface  
        {  
            [OperationContract, WebGet]  
            int Add(int x, int y);  
            [OperationContract, WebGet]  
            string Echo(string input);  
        }  
```  
  
## Реализуйте контракт REST\-службы  
 Реализуйте контракт REST\-службы.  
  
```  
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
  
## Определите контракт службы WCF  
 Определите контракт службы WCF, которая будет использоваться для вызова REST\-службы.  
  
```  
[ServiceContract]  
 public interface INormalInterface  
 {  
     [OperationContract]  
     int CallAdd(int x, int y);  
     [OperationContract]  
     string CallEcho(string input);  
 }  
```  
  
## Реализуйте контракт службы WCF  
 Реализуйте контракт службы WCF.  
  
```  
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
  
## Создайте клиентский прокси\-класс для REST\-службы  
 Используя <xref:System.ServiceModel.ClientBase%60>, реализуйте клиентский прокси\-класс.  Для каждого вызываемого метода создается и используется для вызова операции новая <xref:System.ServiceModel.OperationContextScope>.  
  
```  
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
  
## Размещение и вызов служб  
 Разместите обе службы в консольном приложении, добавив необходимые конечные точки и поведение.  Затем вызовите обычную службу WCF.  
  
```  
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
  
## Полный листинг кода  
 Ниже полностью приведен код примера, представленного в данном разделе.  
  
```  
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
  
## См. также  
 [Как создать простую веб\-службу WCF HTTP](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md)   
 [Объектная модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-object-model.md)