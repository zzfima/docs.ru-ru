---
title: "Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4202c0471c681257fa1ab1153d363e59615e10c2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a>Практическое руководство. Настройка пользовательской привязки для обмена WS-Metadata
В этом разделе объясняется, как настроить пользовательскую привязку обмена WS-Metadata. [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] включает в себя четыре привязки метаданных, определенные системой, однако для публикации метаданных можно использовать любую привязку. В этой теме рассказывается, как опубликовать метаданные с помощью `wsHttpBinding`. Эта привязка позволяет предоставлять метаданные безопасным способом. Код в этой статье, основан на [Приступая к работе](../../../../docs/framework/wcf/samples/getting-started-sample.md).  
  
### <a name="using-a-configuration-file"></a>Использование файла конфигурации  
  
1.  В файле конфигурации службы добавьте поведение службы, содержащее тег `serviceMetadata`:  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  Добавьте в тег службы, ссылающийся на новое поведение, атрибут `behaviorConfiguration`:  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3.  Добавьте конечную точку метаданных, указав mex в качестве адреса, `wsHttpBinding` как привязку и <xref:System.ServiceModel.Description.IMetadataExchange> как контракт:  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4.  Чтобы проверить правильность работы конечной точки обмена метаданными, добавьте тег конечной точки в файл конфигурации клиента:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5.  В методе клиента Main() создайте новый экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient>, задайте его свойство <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> как `true`, вызовите <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>, а затем выполните итерацию через коллекцию возвращенных метаданных:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a>Настройка кодом  
  
1.  Создать <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> экземпляр привязки:  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2.  Создайте экземпляр <xref:System.ServiceModel.ServiceHost>:  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3.  Добавьте конечную точку службы и экземпляр <xref:System.ServiceModel.Description.ServiceMetadataBehavior>:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4.  Добавить конечную точку обмена метаданными, указав <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> созданную ранее:  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5.  Чтобы проверить правильность работы конечной точки обмена метаданными, добавьте тег конечной точки в файл конфигурации клиента:  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6.  В методе клиента Main() создайте новый экземпляр <xref:System.ServiceModel.Description.MetadataExchangeClient>, задайте его свойство <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> как `true`, вызовите <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>, а затем выполните итерацию через коллекцию возвращенных метаданных:  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a>См. также  
 [Поведение публикации метаданных](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)  
 [Получение метаданных](../../../../docs/framework/wcf/samples/retrieve-metadata.md)  
 [Метаданные](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Публикация метаданных](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [Публикация конечных точек метаданных](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
