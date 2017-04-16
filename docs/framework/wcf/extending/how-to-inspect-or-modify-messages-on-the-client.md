---
title: "Практическое руководство. Проверка или изменение сообщений на клиенте | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Практическое руководство. Проверка или изменение сообщений на клиенте
Реализация интерфейса <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName> и его вставка в среду выполнения клиента позволяет проверять или изменять входящие или исходящие сообщения клиента [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  Для получения дополнительной информации см. [Расширение клиентов](../../../../docs/framework/wcf/extending/extending-clients.md).  Эквивалентную функцию в службе выполняет интерфейс <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>.  Полный пример кода приведен в образце [Инспекторы сообщений](../../../../docs/framework/wcf/samples/message-inspectors.md).  
  
### Проверка или изменение сообщений  
  
1.  Реализовать интерфейс <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>.  
  
2.  Реализуйте интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName> или <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> в зависимости от области, в которую нужно вставить инспектор сообщений клиентов.  Интерфейс <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName> позволяет изменять поведение на уровне конечной точки.  Интерфейс <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> позволяет изменять поведение на уровне контракта.  
  
3.  Вставьте поведение до вызова метода <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName> или метода <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName> фабрики каналов <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName>.  Дополнительные сведения см. в разделе [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## Пример  
 В следующих примерах кода показаны, по порядку:  
  
-   реализация инспектора клиента;  
  
-   поведение конечной точки, вставляющее инспектор;  
  
-   Класс <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> \- это производный класс, позволяющий добавить поведение в файл конфигурации.  
  
-   Файл конфигурации, добавляющий поведение конечной точки, которая вставляет пользовательский инспектор сообщений в среду выполнения клиента.  
  
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
  
```vb  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
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
  
## См. также  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [Настройка и расширение среды выполнения с помощью поведений](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)