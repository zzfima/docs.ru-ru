---
title: "Как получить метаданные через привязку, не использующую MEX | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Как получить метаданные через привязку, не использующую MEX
В этом разделе описывается получение метаданных из конечной точки MEX через привязку, не использующую MEX.Код в этом образце основан на образце [Пользовательская конечная точка защищенных метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).  
  
### Получение метаданных через привязку, не использующую MEX  
  
1.  Определите привязку, используемую конечной точкой MEX.Для служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] определить привязку MEX можно, обратившись к файлу конфигурации службы.В этом случае привязка MEX определяется в следующей конфигурации службы.  
  
    ```  
    <services>  
        <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
                behaviorConfiguration="CalculatorServiceBehavior">  
         <!-- Use the base address provided by the host. -->  
         <endpoint address=""  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding2"  
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
         <endpoint address="mex"  
           binding="wsHttpBinding"  
           bindingConfiguration="Binding1"  
           contract="IMetadataExchange" />  
         </service>  
     </services>  
     <bindings>  
       <wsHttpBinding>  
         <binding name="Binding1">  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
         <binding name="Binding2">  
           <reliableSession inactivityTimeout="00:01:00" enabled="true" />  
           <security mode="Message">  
             <message clientCredentialType="Certificate" />  
           </security>  
         </binding>  
       </wsHttpBinding>  
     </bindings>  
    ```  
  
2.  В файле конфигурации клиента настройте такую же пользовательскую привязку.В данном случае для клиента также определено поведение `clientCredentials` — для предоставления сертификата, который будет использоваться для проверки его подлинности службой при запросе метаданных от конечной точки MEX.При использовании Svcutil.exe для запроса метаданных через пользовательскую привязку необходимо добавить конфигурацию конечной точки MEX в файл конфигурации для Svcutil.exe \(Svcutil.exe.config\), причем имя конфигурации конечной точки должно соответствовать схеме URI адреса конечной точки MEX, как показано в следующем коде.  
  
    ```  
    <system.serviceModel>  
      <client>  
        <endpoint name="http"  
                  binding="wsHttpBinding"  
                  bindingConfiguration="Binding1"  
                  behaviorConfiguration="ClientCertificateBehavior"  
                  contract="IMetadataExchange" />  
      </client>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="Binding1">  
            <security mode="Message">  
              <message clientCredentialType="Certificate"/>  
            </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="ClientCertificateBehavior">  
            <clientCredentials>  
              <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName" />  
              <serviceCertificate>  
                <authentication certificateValidationMode="PeerOrChainTrust" />  
              </serviceCertificate>  
            </clientCredentials>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>    
    </system.serviceModel>  
    ```  
  
3.  Создайте объект `MetadataExchangeClient` и вызовите метод `GetMetadata`.Существует два способа это сделать: указать пользовательскую привязку в конфигурации или указать пользовательскую привязку в коде, как показано в следующем примере.  
  
    ```  
    // The custom binding is specified in configuration.  
    EndpointAddress mexAddress = new EndpointAddress("http://localhost:8000/ServiceModelSamples/Service/mex");  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("http");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mexSet = mexClient.GetMetadata(mexAddress);  
  
    // The custom binding is specified in code.  
    // Specify the Metadata Exchange binding and its security mode.  
    WSHttpBinding mexBinding = new WSHttpBinding(SecurityMode.Message);  
    mexBinding.Security.Message.ClientCredentialType = MessageCredentialType.Certificate;  
  
    // Create a MetadataExchangeClient and set the certificate details.  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(mexBinding);  
    mexClient.SoapCredentials.ClientCertificate.SetCertificate(  
        StoreLocation.CurrentUser, StoreName.My,  
        X509FindType.FindBySubjectName, "client.com");  
    mexClient.SoapCredentials.ServiceCertificate.Authentication.  
        CertificateValidationMode =  
        X509CertificateValidationMode.PeerOrChainTrust;  
    mexClient.SoapCredentials.ServiceCertificate.SetDefaultCertificate(  
        StoreLocation.CurrentUser, StoreName.TrustedPeople,  
        X509FindType.FindBySubjectName, "localhost");  
    MetadataExchangeClient mexClient2 = new MetadataExchangeClient(customBinding);  
    mexClient2.ResolveMetadataReferences = true;  
    MetadataSet mexSet2 = mexClient2.GetMetadata(mexAddress);  
    ```  
  
4.  Создайте объект `WsdlImporter` и вызовите метод `ImportAllEndpoints`, как показано в следующем коде.  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  На данном этапе имеется коллекция конечных точек службы.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об импорте метаданных см. в разделе [Практическое руководство. Импорт метаданных в конечные точки службы](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).  
  
## См. также  
 [Метаданные](../../../../docs/framework/wcf/feature-details/metadata.md)