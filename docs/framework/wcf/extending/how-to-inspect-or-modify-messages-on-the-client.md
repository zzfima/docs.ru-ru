---
title: Практическое руководство. Проверка или изменение сообщений на клиенте
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: db1a99d2ed1f765e39815e6b6c70d6ada1db1d15
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185539"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a>Практическое руководство. Проверка или изменение сообщений на клиенте
Вы можете проверить или изменить входящие или исходящие сообщения <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> через клиента WCF, реализовав и вставив их в время выполнения клиента. Для получения дополнительной [информации см.](extending-clients.md) Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>. Для полного примера кода [см.](../samples/message-inspectors.md)  
  
### <a name="to-inspect-or-modify-messages"></a>Проверка или изменение сообщений  
  
1. Реализуйте интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>.  
  
2. Реализуйте интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> в зависимости от области, в которую нужно вставить инспектор сообщений клиентов. <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>позволяет изменить поведение на уровне конечных точек. <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>позволяет изменить поведение на уровне контракта.  
  
3. Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType> или метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType> фабрики каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>. Для получения подробной информации [см.](configuring-and-extending-the-runtime-with-behaviors.md)  
  
## <a name="example"></a>Пример  
 В следующих примерах кода показаны, по порядку:  
  
- реализация инспектора клиента;  
  
- поведение конечной точки, вставляющее инспектор;  
  
- Класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> - это производный класс, позволяющий добавить поведение в файл конфигурации.  
  
- Файл конфигурации, добавляющий поведение конечной точки, которая вставляет пользовательский инспектор сообщений в среду выполнения клиента.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Настройка и расширение среды выполнения с помощью поведений](configuring-and-extending-the-runtime-with-behaviors.md)
