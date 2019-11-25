---
title: Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets
ms.date: 03/30/2017
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
ms.openlocfilehash: 8f8cf715269fd0ed67e2265eee4139a509f70cd1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977127"
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="f60e5-102">Практическое руководство. Создание службы WCF, обменивающейся данными через WebSockets</span><span class="sxs-lookup"><span data-stu-id="f60e5-102">How to: Create a WCF Service that Communicates over WebSockets</span></span>
<span data-ttu-id="f60e5-103">Службы и клиенты WCF могут использовать привязку <xref:System.ServiceModel.NetHttpBinding> для обмена данными через WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f60e5-103">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="f60e5-104">WebSockets будет использоваться в тех случаях, когда <xref:System.ServiceModel.NetHttpBinding> распознает, что в контракте службы определен контракт обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f60e5-104">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="f60e5-105">В этом разделе описано, как реализовать службу WCF и клиент, использующий <xref:System.ServiceModel.NetHttpBinding> для обмена данными через WebSockets.</span><span class="sxs-lookup"><span data-stu-id="f60e5-105">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="f60e5-106">Определение службы</span><span class="sxs-lookup"><span data-stu-id="f60e5-106">Define the Service</span></span>  
  
1. <span data-ttu-id="f60e5-107">Определите контракт обратного вызова</span><span class="sxs-lookup"><span data-stu-id="f60e5-107">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="f60e5-108">Этот контракт будет реализован клиентским приложением, чтобы служба могла отправлять сообщения обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="f60e5-108">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2. <span data-ttu-id="f60e5-109">Определите контракт службы и укажите интерфейс `IStockQuoteCallback` в качестве контракта обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f60e5-109">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3. <span data-ttu-id="f60e5-110">Реализуйте контракт службы.</span><span class="sxs-lookup"><span data-stu-id="f60e5-110">Implement the service contract.</span></span>  
  
    ```csharp
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  

            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="f60e5-111">Операция службы `StartSendingQuotes` реализуется как асинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="f60e5-111">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="f60e5-112">Получим канал обратного вызова через `OperationContext` и, если канал открыт, выполним через него асинхронный вызов.</span><span class="sxs-lookup"><span data-stu-id="f60e5-112">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4. <span data-ttu-id="f60e5-113">Настройка службы</span><span class="sxs-lookup"><span data-stu-id="f60e5-113">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />        
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />        
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="f60e5-114">Файл конфигурации службы построен на конечных точках WCF по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f60e5-114">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="f60e5-115">Раздел `<protocolMapping>` служит для указания того, что привязка `NetHttpBinding` должна быть использована для созданных конечных точек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f60e5-115">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="f60e5-116">Определение клиента</span><span class="sxs-lookup"><span data-stu-id="f60e5-116">Define the Client</span></span>  
  
1. <span data-ttu-id="f60e5-117">Реализация контракта обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f60e5-117">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="f60e5-118">Контракт обратного вызова реализуется в виде асинхронного метода.</span><span class="sxs-lookup"><span data-stu-id="f60e5-118">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1. <span data-ttu-id="f60e5-119">Реализация клиентского кода.</span><span class="sxs-lookup"><span data-stu-id="f60e5-119">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();              
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="f60e5-120">CallbackHandler здесь повторен только для ясности.</span><span class="sxs-lookup"><span data-stu-id="f60e5-120">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="f60e5-121">Клиентское приложение создает новый InstanceContext и реализацию интерфейса обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f60e5-121">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="f60e5-122">Затем оно создает экземпляр прокси-класса, отправляя ссылку вновь созданному InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="f60e5-122">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="f60e5-123">Когда клиент вызывает службу, служба вызывает клиента через заданный контракт обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="f60e5-123">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2. <span data-ttu-id="f60e5-124">Настройка клиента</span><span class="sxs-lookup"><span data-stu-id="f60e5-124">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>   
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="f60e5-125">Никаких особых изменений в клиентскую конфигурацию вносить не нужно, просто укажите конечную точку на стороне клиента с помощью `NetHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="f60e5-125">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f60e5-126">Пример</span><span class="sxs-lookup"><span data-stu-id="f60e5-126">Example</span></span>  
 <span data-ttu-id="f60e5-127">Ниже приведен полный код, используемый в данном разделе.</span><span class="sxs-lookup"><span data-stu-id="f60e5-127">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```csharp
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  https://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />        
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />        
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();              
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!--App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>   
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f60e5-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f60e5-128">See also</span></span>

- [<span data-ttu-id="f60e5-129">Синхронные и асинхронные операции</span><span class="sxs-lookup"><span data-stu-id="f60e5-129">Synchronous and Asynchronous Operations</span></span>](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
- [<span data-ttu-id="f60e5-130">Использование NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="f60e5-130">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)
