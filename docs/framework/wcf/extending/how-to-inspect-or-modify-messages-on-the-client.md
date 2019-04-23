---
title: Практическое руководство. Проверка или изменение сообщений на клиенте
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: 67fa0e092e6494ff55d71e666b5137cfc9a3069e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59343302"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a><span data-ttu-id="f2f36-102">Практическое руководство. Проверка или изменение сообщений на клиенте</span><span class="sxs-lookup"><span data-stu-id="f2f36-102">How to: Inspect or Modify Messages on the Client</span></span>
<span data-ttu-id="f2f36-103">Вы может проверять или изменять входящие или исходящие сообщения между клиентом WCF путем реализации <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> и его вставки в среду выполнения клиента.</span><span class="sxs-lookup"><span data-stu-id="f2f36-103">You can inspect or modify the incoming or outgoing messages across a WCF client by implementing a <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> and inserting it into the client runtime.</span></span> <span data-ttu-id="f2f36-104">Дополнительные сведения см. в разделе [расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md).</span><span class="sxs-lookup"><span data-stu-id="f2f36-104">For more information, see [Extending Clients](../../../../docs/framework/wcf/extending/extending-clients.md).</span></span> <span data-ttu-id="f2f36-105">Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2f36-105">The equivalent feature on the service is the <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2f36-106">Полный пример кода см. в разделе [инспекторы сообщений](../../../../docs/framework/wcf/samples/message-inspectors.md) образца.</span><span class="sxs-lookup"><span data-stu-id="f2f36-106">For a complete code example see the [Message Inspectors](../../../../docs/framework/wcf/samples/message-inspectors.md) sample.</span></span>  
  
### <a name="to-inspect-or-modify-messages"></a><span data-ttu-id="f2f36-107">Проверка или изменение сообщений</span><span class="sxs-lookup"><span data-stu-id="f2f36-107">To inspect or modify messages</span></span>  
  
1. <span data-ttu-id="f2f36-108">Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2f36-108">Implement the <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> interface.</span></span>  
  
2. <span data-ttu-id="f2f36-109">Реализуйте интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> в зависимости от области, в которую нужно вставить инспектор сообщений клиентов.</span><span class="sxs-lookup"><span data-stu-id="f2f36-109">Implement a <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> or <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> depending upon the scope at which you want to insert the client message inspector.</span></span> <span data-ttu-id="f2f36-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> позволяет изменять поведение на уровне конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f2f36-110"><xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> allows you to change behavior at the endpoint level.</span></span> <span data-ttu-id="f2f36-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> позволяет изменять поведение на уровне контракта.</span><span class="sxs-lookup"><span data-stu-id="f2f36-111"><xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> allows you to change behavior at the contract level.</span></span>  
  
3. <span data-ttu-id="f2f36-112">Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> или метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> фабрики каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2f36-112">Insert the behavior prior to calling the <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> method on the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="f2f36-113">Дополнительные сведения см. в разделе [настройку и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="f2f36-113">For details, see [Configuring and Extending the Runtime with Behaviors](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2f36-114">Пример</span><span class="sxs-lookup"><span data-stu-id="f2f36-114">Example</span></span>  
 <span data-ttu-id="f2f36-115">В следующих примерах кода показаны, по порядку:</span><span class="sxs-lookup"><span data-stu-id="f2f36-115">The following code examples show, in order:</span></span>  
  
-   <span data-ttu-id="f2f36-116">реализация инспектора клиента;</span><span class="sxs-lookup"><span data-stu-id="f2f36-116">A client inspector implementation.</span></span>  
  
-   <span data-ttu-id="f2f36-117">поведение конечной точки, вставляющее инспектор;</span><span class="sxs-lookup"><span data-stu-id="f2f36-117">An endpoint behavior that inserts the inspector.</span></span>  
  
-   <span data-ttu-id="f2f36-118">Класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> - это производный класс, позволяющий добавить поведение в файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f2f36-118">A <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>- derived class that allows you to add the behavior in a configuration file.</span></span>  
  
-   <span data-ttu-id="f2f36-119">Файл конфигурации, добавляющий поведение конечной точки, которая вставляет пользовательский инспектор сообщений в среду выполнения клиента.</span><span class="sxs-lookup"><span data-stu-id="f2f36-119">A configuration file that adds the endpoint behavior which inserts the client message inspector into the client runtime.</span></span>  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
```  
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"
                      behaviorConfiguration="clientInspectorsAdded"
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f2f36-120">См. также</span><span class="sxs-lookup"><span data-stu-id="f2f36-120">See also</span></span>

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [<span data-ttu-id="f2f36-121">Настройка и расширение среды выполнения с помощью поведений</span><span class="sxs-lookup"><span data-stu-id="f2f36-121">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
