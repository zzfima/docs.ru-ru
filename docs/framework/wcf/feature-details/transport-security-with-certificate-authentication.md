---
title: Безопасность транспорта с проверкой подлинности с использованием сертификатов
ms.date: 03/30/2017
dev_langs:
- csharp
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
ms.openlocfilehash: ad2f0922afbd94e1699b383cf2fc9762771b637d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184332"
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="1ddc8-102">Безопасность транспорта с проверкой подлинности с использованием сертификатов</span><span class="sxs-lookup"><span data-stu-id="1ddc8-102">Transport Security with Certificate Authentication</span></span>

<span data-ttu-id="1ddc8-103">В этой статье обсуждается использование сертификатов X.509 для проверки подлинности сервера и клиента при использовании транспортной безопасности.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-103">This article discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="1ddc8-104">Дополнительные сведения о сертификатах X.509 см. в разделе [Сертификаты открытого ключа X.509](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span><span class="sxs-lookup"><span data-stu-id="1ddc8-104">For more information about X.509 certificates see [X.509 Public Key Certificates](/windows/desktop/SecCertEnroll/about-x-509-public-key-certificates).</span></span> <span data-ttu-id="1ddc8-105">Сертификаты должны выдаваться сертификационным органом, который часто является сторонним эмитентом сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="1ddc8-106">В домене Windows Server для выдачи сертификатов клиентским компьютерам домена можно использовать службу сертификации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="1ddc8-107">В этом сценарии служба размещена в службах IIS, которые используют протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-107">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="1ddc8-108">В службе задано использование сертификата SSL (X.509), чтобы клиенты могли проверять подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-108">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="1ddc8-109">В клиенте также задано использование сертификата X.509, что позволяет службе проверять подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-109">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="1ddc8-110">Клиент должен доверять сертификату сервера, а сервер ― сертификату клиента.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-110">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="1ddc8-111">Фактическая механика проверки личности службы и клиента выходит за рамки данной статьи.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-111">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this article.</span></span> <span data-ttu-id="1ddc8-112">Для получения дополнительной информации смотрите [цифровую подпись](https://en.wikipedia.org/wiki/Digital_signature) в Википедии.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-112">For more information, see [Digital Signature](https://en.wikipedia.org/wiki/Digital_signature) on Wikipedia.</span></span>
  
 <span data-ttu-id="1ddc8-113">В этом сценарии реализуется шаблон обмена сообщениями «запрос-ответ», показанный на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-113">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="1ddc8-114">![Безопасный перевод с помощью сертификатов](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="1ddc8-114">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="1ddc8-115">Для получения дополнительной информации об использовании сертификата [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)с услугой [см.](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="1ddc8-115">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="1ddc8-116">В следующей таблице описываются различные особенности этого сценария.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-116">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="1ddc8-117">Характеристика</span><span class="sxs-lookup"><span data-stu-id="1ddc8-117">Characteristic</span></span>|<span data-ttu-id="1ddc8-118">Описание</span><span class="sxs-lookup"><span data-stu-id="1ddc8-118">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="1ddc8-119">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="1ddc8-119">Security Mode</span></span>|<span data-ttu-id="1ddc8-120">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="1ddc8-120">Transport</span></span>|  
|<span data-ttu-id="1ddc8-121">Совместимость</span><span class="sxs-lookup"><span data-stu-id="1ddc8-121">Interoperability</span></span>|<span data-ttu-id="1ddc8-122">С существующими службами и клиентами веб-служб.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-122">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="1ddc8-123">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="1ddc8-123">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="1ddc8-124">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="1ddc8-124">Authentication (Client)</span></span>|<span data-ttu-id="1ddc8-125">Да (с использованием SSL-сертификата)</span><span class="sxs-lookup"><span data-stu-id="1ddc8-125">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="1ddc8-126">Да (с использованием сертификата X.509)</span><span class="sxs-lookup"><span data-stu-id="1ddc8-126">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="1ddc8-127">Целостность данных</span><span class="sxs-lookup"><span data-stu-id="1ddc8-127">Data Integrity</span></span>|<span data-ttu-id="1ddc8-128">Да</span><span class="sxs-lookup"><span data-stu-id="1ddc8-128">Yes</span></span>|  
|<span data-ttu-id="1ddc8-129">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="1ddc8-129">Data Confidentiality</span></span>|<span data-ttu-id="1ddc8-130">Да</span><span class="sxs-lookup"><span data-stu-id="1ddc8-130">Yes</span></span>|  
|<span data-ttu-id="1ddc8-131">Транспортировка</span><span class="sxs-lookup"><span data-stu-id="1ddc8-131">Transport</span></span>|<span data-ttu-id="1ddc8-132">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1ddc8-132">HTTPS</span></span>|  
|<span data-ttu-id="1ddc8-133">Привязка</span><span class="sxs-lookup"><span data-stu-id="1ddc8-133">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="1ddc8-134">Настройка службы</span><span class="sxs-lookup"><span data-stu-id="1ddc8-134">Configure the Service</span></span>  
 <span data-ttu-id="1ddc8-135">Поскольку в этом сценарии служба размещается в службах IIS, он настраивается с помощью файла web.config.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-135">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="1ddc8-136">В следующем примере содержимого файла web.config показано, как настроить в <xref:System.ServiceModel.WSHttpBinding> использование безопасности транспорта и учетных данных клиента X.509.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-136">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <protocolMapping>  
      <add scheme="https" binding="wsHttpBinding" />  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttp binding with Transport security mode and clientCredentialType as Certificate -->  
        <binding>  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>
           <serviceDebug includeExceptionDetailInFaults="True" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="configure-the-client"></a><span data-ttu-id="1ddc8-137">Настройка клиента</span><span class="sxs-lookup"><span data-stu-id="1ddc8-137">Configure the Client</span></span>  
 <span data-ttu-id="1ddc8-138">Настроить клиент можно в коде или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-138">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="1ddc8-139">В следующем примере показано, как настроить клиент в коде.</span><span class="sxs-lookup"><span data-stu-id="1ddc8-139">The following example shows how to configure the client in code.</span></span>  
  
```csharp
// Create the binding.  
var myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.
var ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
var cc =  
   new CalculatorClient(myBinding, ea);  
  
// The client must specify a certificate trusted by the server.  
cc.ClientCredentials.ClientCertificate.SetCertificate(  
    StoreLocation.CurrentUser,  
    StoreName.My,  
    X509FindType.FindBySubjectName,  
    "contoso.com");  
  
// Begin using the client.  
Console.WriteLine(cc.Add(100, 1111));  
//...  
cc.Close();  
```  
  
 <span data-ttu-id="1ddc8-140">Также можно настроить клиент в файле App.config, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1ddc8-140">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address=" https://localhost/CalculatorService/service.svc "
                behaviorConfiguration="endpointCredentialBehavior"  
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="contoso.com"  
                               storeLocation="CurrentUser"  
                               storeName="My"  
                               x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as Certificate -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  </system.serviceModel>  
  
<startup><supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.0"/></startup></configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1ddc8-141">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ddc8-141">See also</span></span>

- [<span data-ttu-id="1ddc8-142">Обзор безопасности</span><span class="sxs-lookup"><span data-stu-id="1ddc8-142">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="1ddc8-143">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="1ddc8-143">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
