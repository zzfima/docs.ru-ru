---
title: Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 6459e3f0cf0ab72af8027bd6802a0e7aa574aece
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635783"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a>Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata

В этой статье объясняется, как настроить пользовательский привязку обмена WS-Metadata. Фонд связи Windows (WCF) включает в себя четыре системно-определяемые привязки метаданных, но вы можете публиковать метаданные с помощью любой необходимой привязки. В этой статье показано, как публиковать `wsHttpBinding`метаданные с помощью . Эта привязка позволяет предоставлять метаданные безопасным способом. Код в этой статье основан на [начало](../samples/getting-started-sample.md).  
  
### <a name="using-a-configuration-file"></a>Использование файла конфигурации  
  
1. В файле конфигурации службы добавьте поведение службы, содержащее тег `serviceMetadata`:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. Добавьте в тег службы, ссылающийся на новое поведение, атрибут `behaviorConfiguration`:  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. Добавьте конечную точку метаданных, указав mex в качестве адреса, `wsHttpBinding` как привязку и <xref:System.ServiceModel.Description.IMetadataExchange> как контракт:  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. Чтобы проверить правильное работу конечная точка обмена метаданными, добавьте тег конечных точек в файл конфигурации клиента:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. В методе клиента Main() создайте новый экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient>, задайте его свойство <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> как `true`, вызовите <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>, а затем выполните итерацию через коллекцию возвращенных метаданных:  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a>Настройка кодом  
  
1. Создайте экземпляр привязки <xref:System.ServiceModel.WSHttpBinding>:  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. Создайте экземпляр <xref:System.ServiceModel.ServiceHost>:  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. Добавьте конечную точку службы и экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. Добавьте конечную точку обмена метаданными, указав ранее созданную <xref:System.ServiceModel.WSHttpBinding>:  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. Чтобы проверить правильность работы конечной точки обмена метаданными, добавьте тег конечной точки в файл конфигурации клиента:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. В методе клиента Main() создайте новый экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient>, задайте его свойство <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> как `true`, вызовите <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>, а затем выполните итерацию через коллекцию возвращенных метаданных:  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a>См. также

- [Поведение публикации метаданных](../samples/metadata-publishing-behavior.md)
- [Извлечение метаданных](../samples/retrieve-metadata.md)
- [Метаданные](../feature-details/metadata.md)
- [Публикация метаданных](../feature-details/publishing-metadata.md)
- [Публикация конечных точек метаданных](../publishing-metadata-endpoints.md)
