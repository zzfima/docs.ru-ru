---
title: "Настройка служб WCF в коде"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c05cc5947a36bbe8573c5308cdfbbe3f6c990815
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="configuring-wcf-services-in-code"></a>Настройка служб WCF в коде
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] позволяет разработчикам настраивать службы с помощью файлов конфигурации или кода.  Файлы конфигурации используются, если необходимо настроить службу после ее развертывания. При использовании файлов конфигурации ИТ-работнику требуется только обновить файл конфигурации без необходимости выполнять повторную компиляцию. Файлы конфигурации, однако, могут быть сложными и требовать больших усилий при обслуживании. Отсутствует поддержка отладки файлов конфигурации, и ссылки на элементы конфигурации осуществляются по именам, что усложняет работу и способствует совершению ошибок при создании файлов конфигурации. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] также позволяет настраивать службы в коде. В предыдущих версиях [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] (4.0 и ранее) настройка служб легко выполнялась в коде в случае сценариев резидентных служб, класс <xref:System.ServiceModel.ServiceHost> позволял настроить конечные точки и поведение до вызова метода ServiceHost.Open. Однако в сценариях с размещением в Интернете нет прямого доступа к классу <xref:System.ServiceModel.ServiceHost>. Чтобы настроить службу, размещенную в сети, приходилось создавать класс `System.ServiceModel.ServiceHostFactory`, который создавал <xref:System.ServiceModel.Activation.ServiceHostFactory> и выполнял необходимые настройки. Начиная с версии .NET 4.5, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] предоставляет более простой способ настройки как для резидентных служб, так и для служб, размещаемых в сети.  
  
## <a name="the-configure-method"></a>Метод конфигурации  
 Просто определите открытый статический метод с именем `Configure` со следующей сигнатурой в классе реализации службы.  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Метод принимает экземпляр <xref:System.ServiceModel.ServiceConfiguration>, что позволяет разработчикам добавлять конечные точки и расширения функциональности. Этот метод вызывается [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] перед открытием узла службы. Если он задан, то никакие параметры конфигурации службы, определенные в файле app.config или web.config, не учитываются.  
  
 В следующем фрагменте кода показано, как определить метод `Configure` и добавить конечную точку службы, поведение конечной точки и расширения функциональности служб.  
  
```csharp  
public class Service1 : IService1  
    {  
        public static void Configure(ServiceConfiguration config)  
        {  
            ServiceEndpoint se = new ServiceEndpoint(new ContractDescription("IService1"), new BasicHttpBinding(), new EndpointAddress("basic"));  
            se.Behaviors.Add(new MyEndpointBehavior());  
            config.AddServiceEndpoint(se);  
  
            config.Description.Behaviors.Add(new ServiceMetadataBehavior { HttpGetEnabled = true });  
            config.Description.Behaviors.Add(new ServiceDebugBehavior { IncludeExceptionDetailInFaults = true });  
        }  
  
        public string GetData(int value)  
        {  
            return string.Format("You entered: {0}", value);  
        }  
  
        public CompositeType GetDataUsingDataContract(CompositeType composite)  
        {  
            if (composite == null)  
            {  
                throw new ArgumentNullException("composite");  
            }  
            if (composite.BoolValue)  
            {  
                composite.StringValue += "Suffix";  
            }  
            return composite;  
        }  
    }  
```  
  
 Чтобы включить для службы протокол (например, HTTPS), следует явно добавить конечную точку, использующую протокол, или автоматически добавить конечные точки с помощью привязки ServiceConfiguration.EnableProtocol, которая добавляет конечную точку для каждого базового адреса, совместимого с использованием определенного протокола и каждого контракта службы. В следующем примере кода показывается, как использовать метод ServiceConfiguration.EnableProtocol:  
  
```csharp  
public class Service1 : IService1   
{   
    public string GetData(int value);   
    public static void Configure(ServiceConfiguration config)   
    {   
        // Enable "Add Service Reference" support   
       config.Description.Behaviors.Add( new ServiceMetadataBehavior { HttpGetEnabled = true });   
       // set up support for http, https, net.tcp, net.pipe   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new BasicHttpBinding());   
       config.EnableProtocol(new NetTcpBinding());   
       config.EnableProtocol(new NetNamedPipeBinding());   
       // add an extra BasicHttpBinding endpoint at http:///basic   
       config.AddServiceEndpoint(typeof(IService1), new BasicHttpBinding(),"basic");   
    }   
}   
```  
  
 Параметры в <`protocolMappings`> раздела используются только в том случае, если добавляются конечные точки приложения не <xref:System.ServiceModel.ServiceConfiguration> программными средствами. При необходимости можно загрузить конфигурацию службы из файла конфигурации приложения по умолчанию путем вызова <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> и измените параметры. Класс <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> также позволяет загрузить конфигурацию из централизованной конфигурации. В следующем примере кода показано, как это реализовать.  
  
```  
public class Service1 : IService1   
{   
    public void DoWork();   
    public static void Configure(ServiceConfiguration config)   
    {   
          config.LoadFromConfiguration(ConfigurationManager.OpenMappedExeConfiguration(new ExeConfigurationFileMap { ExeConfigFilename = @"c:\sharedConfig\MyConfig.config" }, ConfigurationUserLevel.None));   
    }   
}  
```  
  
> [!IMPORTANT]
>  Обратите внимание, что <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> игнорирует <`host`> Параметры <`service`> тег <`system.serviceModel`>. По существу <`host`> — о конфигурации узла, не конфигурации службы и он получает загрузить до выполнения метода Настройка.  
  
## <a name="see-also"></a>См. также  
 [Настройка служб с использованием файлов конфигурации](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 [Настройка поведения клиентов](../../../docs/framework/wcf/configuring-client-behaviors.md)  
 [Упрощенная конфигурация](../../../docs/framework/wcf/simplified-configuration.md)  
 [Активация на основе конфигурации](../../../docs/framework/wcf/samples/configuration-based-activation.md)  
 [Конфигурация](../../../docs/framework/wcf/samples/configuration-sample.md)  
 [Активация на основе конфигурации в IIS и WAS](../../../docs/framework/wcf/feature-details/configuration-based-activation-in-iis-and-was.md)  
 [Конфигурация и поддержка метаданных](../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)  
 [Конфигурация](../../../docs/framework/wcf/diagnostics/exceptions-reference/configuration.md)  
 [Практическое руководство. Указание привязки службы в конфигурации](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [Как: создать конечную точку службы в конфигурации](../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [Как: публикация метаданных для службы с помощью файла конфигурации](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [Практическое руководство. Указание привязки клиента в конфигурации](../../../docs/framework/wcf/how-to-specify-a-client-binding-in-configuration.md)
