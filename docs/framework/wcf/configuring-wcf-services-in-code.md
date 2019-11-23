---
title: Настройка служб WCF в коде
ms.date: 03/30/2017
ms.assetid: 193c725d-134f-4d31-a8f8-4e575233bff6
ms.openlocfilehash: c6bcf08511470d28e1087108d95e477683b0338b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320633"
---
# <a name="configuring-wcf-services-in-code"></a>Настройка служб WCF в коде
Windows Communication Foundation (WCF) позволяет разработчикам настраивать службы с помощью файлов конфигурации или кода.  Файлы конфигурации используются, если необходимо настроить службу после ее развертывания. При использовании файлов конфигурации ИТ-работнику требуется только обновить файл конфигурации без необходимости выполнять повторную компиляцию. Файлы конфигурации, однако, могут быть сложными и требовать больших усилий при обслуживании. Отсутствует поддержка отладки файлов конфигурации, и ссылки на элементы конфигурации осуществляются по именам, что усложняет работу и способствует совершению ошибок при создании файлов конфигурации. WCF также позволяет настраивать службы в коде. В более ранних версиях WCF (4,0 и более ранних версий) Настройка служб в коде была непростой в собственных сценариях, класс <xref:System.ServiceModel.ServiceHost> позволял вам настроить конечные точки и поведения до вызова ServiceHost. Open. Однако в сценариях с размещением в Интернете нет прямого доступа к классу <xref:System.ServiceModel.ServiceHost>. Чтобы настроить службу, размещенную в сети, приходилось создавать класс `System.ServiceModel.ServiceHostFactory`, который создавал <xref:System.ServiceModel.Activation.ServiceHostFactory> и выполнял необходимые настройки. Начиная с .NET 4,5, WCF предоставляет более простой способ настройки автономных и размещенных в Интернете служб в коде.  
  
## <a name="the-configure-method"></a>Метод Configure  
 Просто определите открытый статический метод с именем `Configure` со следующей сигнатурой в классе реализации службы.  
  
```csharp  
public static void Configure(ServiceConfiguration config)  
```  
  
 Метод принимает экземпляр <xref:System.ServiceModel.ServiceConfiguration>, что позволяет разработчикам добавлять конечные точки и расширения функциональности. Этот метод вызывается WCF перед открытием узла службы. Если он задан, то никакие параметры конфигурации службы, определенные в файле app.config или web.config, не учитываются.  
  
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
            return $"You entered: {value}";
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
  
 Параметры в разделе <`protocolMappings`> используются только в том случае, если конечные точки приложения не добавляются в <xref:System.ServiceModel.ServiceConfiguration> программным способом. При необходимости можно загрузить конфигурацию службы из файла конфигурации приложения по умолчанию, вызвав <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A>, а затем изменить параметры. Класс <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration> также позволяет загрузить конфигурацию из централизованной конфигурации. В следующем примере кода показано, как это реализовать.  
  
```csharp
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
> Обратите внимание, что <xref:System.ServiceModel.ServiceConfiguration.LoadFromConfiguration%2A> игнорирует параметры <`host`> в теге <`service`>.`system.serviceModel` По сути <`host`> — это конфигурация узла, а не конфигурация службы, которая загружается перед выполнением метода Configure.  
  
## <a name="see-also"></a>См. также:

- [Настройка служб с использованием файлов конфигурации](configuring-services-using-configuration-files.md)
- [Настройка поведения клиентов](configuring-client-behaviors.md)
- [Упрощенная конфигурация](simplified-configuration.md)
- [Конфигурация](./samples/configuration-sample.md)
- [Активация на основе конфигурации в IIS и WAS](./feature-details/configuration-based-activation-in-iis-and-was.md)
- [Конфигурация и поддержка метаданных](./extending/configuration-and-metadata-support.md)
- [Конфигурация](./diagnostics/exceptions-reference/configuration.md)
- [Практическое руководство. Указание привязки службы в конфигурации](how-to-specify-a-service-binding-in-configuration.md)
- [Практическое руководство. Создание конечной точки службы в конфигурации](./feature-details/how-to-create-a-service-endpoint-in-configuration.md)
- [Практическое руководство. Публикация метаданных для службы с использованием файла конфигурации](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [Практическое руководство. Указание привязки клиента в конфигурации](how-to-specify-a-client-binding-in-configuration.md)
