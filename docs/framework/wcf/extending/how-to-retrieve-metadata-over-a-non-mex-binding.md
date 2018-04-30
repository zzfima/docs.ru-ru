---
title: Как получить метаданные через привязку, не использующую MEX
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2292e124-81b2-4317-b881-ce9c1ec66ecb
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b469a08ad9759a2d5213f13256ec2def96107acc
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c1c2e-102">Как получить метаданные через привязку, не использующую MEX</span><span class="sxs-lookup"><span data-stu-id="c1c2e-102">How to: Retrieve Metadata Over a non-MEX Binding</span></span>
<span data-ttu-id="c1c2e-103">В этом разделе описывается получение метаданных из конечной точки MEX через привязку, не использующую MEX.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-103">This topic describes how to retrieve metadata from a MEX endpoint over a non-MEX binding.</span></span> <span data-ttu-id="c1c2e-104">Код в этом образце, основан на [конечной точки метаданных защиты пользовательских](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) образца.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-104">The code in this sample is based on the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample.</span></span>  
  
### <a name="to-retrieve-metadata-over-a-non-mex-binding"></a><span data-ttu-id="c1c2e-105">Получение метаданных через привязку, не использующую MEX</span><span class="sxs-lookup"><span data-stu-id="c1c2e-105">To retrieve metadata over a non-MEX binding</span></span>  
  
1.  <span data-ttu-id="c1c2e-106">Определите привязку, используемую конечной точкой MEX.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-106">Determine the binding used by the MEX endpoint.</span></span> <span data-ttu-id="c1c2e-107">Для служб [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] определить привязку MEX можно, обратившись к файлу конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-107">For [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services, you can determine the MEX binding by accessing the service's configuration file.</span></span> <span data-ttu-id="c1c2e-108">В этом случае привязка MEX определяется в следующей конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-108">In this case, the MEX binding is defined in the following service configuration.</span></span>  
  
    ```xml  
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
  
2.  <span data-ttu-id="c1c2e-109">В файле конфигурации клиента настройте такую же пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-109">In the client configuration file, configure the same custom binding.</span></span> <span data-ttu-id="c1c2e-110">В данном случае для клиента также определено поведение `clientCredentials` - для предоставления сертификата, который будет использоваться для проверки его подлинности службой при запросе метаданных от конечной точки MEX.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-110">Here the client also defines a `clientCredentials` behavior to provide a certificate to use to authenticate to the service when requesting metadata from the MEX endpoint.</span></span> <span data-ttu-id="c1c2e-111">При использовании Svcutil.exe для запроса метаданных через пользовательскую привязку необходимо добавить конфигурацию конечной точки MEX в файл конфигурации для Svcutil.exe (Svcutil.exe.config), причем имя конфигурации конечной точки должно соответствовать схеме URI адреса конечной точки MEX, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-111">When using Svcutil.exe to request metadata over a custom binding, you should add the MEX endpoint configuration to the configuration file for Svcutil.exe (Svcutil.exe.config), and the name of the endpoint configuration should match the URI scheme of the address of the MEX endpoint, as shown in the following code.</span></span>  
  
    ```xml  
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
  
3.  <span data-ttu-id="c1c2e-112">Создайте объект `MetadataExchangeClient` и вызовите метод `GetMetadata`.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-112">Create a `MetadataExchangeClient` and call `GetMetadata`.</span></span> <span data-ttu-id="c1c2e-113">Существует два способа это сделать: указать пользовательскую привязку в конфигурации или указать пользовательскую привязку в коде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-113">There are two ways to do this: you can specify the custom binding in configuration, or you can specify the custom binding in code, as shown in the following example.</span></span>  
  
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
  
4.  <span data-ttu-id="c1c2e-114">Создайте объект `WsdlImporter` и вызовите метод `ImportAllEndpoints`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-114">Create a `WsdlImporter` and call `ImportAllEndpoints`, as shown in the following code.</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(mexSet);  
    ServiceEndpointCollection endpoints = importer.ImportAllEndpoints();  
    ```  
  
5.  <span data-ttu-id="c1c2e-115">На данном этапе имеется коллекция конечных точек службы.</span><span class="sxs-lookup"><span data-stu-id="c1c2e-115">At this point, you have a collection of service endpoints.</span></span> <span data-ttu-id="c1c2e-116">Дополнительные сведения об импорте метаданных см. в разделе [как: Импорт метаданных в конечные точки службы](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="c1c2e-116">For more information about importing metadata, see [How to: Import Metadata into Service Endpoints](../../../../docs/framework/wcf/feature-details/how-to-import-metadata-into-service-endpoints.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c2e-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c1c2e-117">See Also</span></span>  
 [<span data-ttu-id="c1c2e-118">Метаданные</span><span class="sxs-lookup"><span data-stu-id="c1c2e-118">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)
