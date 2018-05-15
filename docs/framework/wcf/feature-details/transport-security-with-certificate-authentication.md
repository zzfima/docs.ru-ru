---
title: Безопасность транспорта с проверкой подлинности с использованием сертификатов
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: 3d726b71-4d8b-4581-a3bb-02b9af51d11b
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: a4f29d9ac34437431a95a247ef1e7aa5c9084c36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transport-security-with-certificate-authentication"></a><span data-ttu-id="ab4ba-102">Безопасность транспорта с проверкой подлинности с использованием сертификатов</span><span class="sxs-lookup"><span data-stu-id="ab4ba-102">Transport Security with Certificate Authentication</span></span>
<span data-ttu-id="ab4ba-103">В этом разделе рассматривается проверка подлинности сервера и клиента при использовании безопасности транспорта с помощью сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-103">This topic discusses using X.509 certificates for server and client authentication when using transport security.</span></span> <span data-ttu-id="ab4ba-104">Дополнительные сведения о X.509 см. [сертификаты открытого ключа X.509](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).</span><span class="sxs-lookup"><span data-stu-id="ab4ba-104">For more information about X.509 certificates see [X.509 Public Key Certificates](http://msdn.microsoft.com/library/bb540819\(VS.85\).aspx).</span></span> <span data-ttu-id="ab4ba-105">Сертификаты должны быть выданы центром сертификации, который часто сторонним издателем сертификатов.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-105">Certificates must be issued by a certification authority, which is often a third-party issuer of certificates.</span></span> <span data-ttu-id="ab4ba-106">В домене Windows Server для выдачи сертификатов клиентским компьютерам домена можно использовать службу сертификации Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-106">On a Windows Server domain, Active Directory Certificate Services can be used to issue certificates to client computers on the domain.</span></span> <span data-ttu-id="ab4ba-107">Дополнительные сведения см. [служб сертификатов Windows 2008 R2](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="ab4ba-107">For more information see [Windows 2008 R2 Certificate Services](http://go.microsoft.com/fwlink/?LinkID=209949&clcid=0x409).</span></span> <span data-ttu-id="ab4ba-108">В этом сценарии служба размещена в службах IIS, которые используют протокол SSL.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-108">In this scenario, the service is hosted under Internet Information Services (IIS) which is configured with Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="ab4ba-109">В службе задано использование сертификата SSL (X.509), чтобы клиенты могли проверять подлинность сервера.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-109">The service is configured with an SSL (X.509) certificate to allow clients to verify the identity of the server.</span></span> <span data-ttu-id="ab4ba-110">В клиенте также задано использование сертификата X.509, что позволяет службе проверять подлинность клиента.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-110">The client is also configured with an X.509 certificate that allows the service to verify the identity of the client.</span></span> <span data-ttu-id="ab4ba-111">Клиент должен доверять сертификату сервера, а сервер ― сертификату клиента.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-111">The server’s certificate must be trusted by the client and the client’s certificate must be trusted by the server.</span></span> <span data-ttu-id="ab4ba-112">Фактический механизм проверки подлинности друг друга службой и клиентом в данном разделе не обсуждается.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-112">The actual mechanics of how the service and client verifies each other’s identity is beyond the scope of this topic.</span></span> <span data-ttu-id="ab4ba-113">Дополнительные сведения см. [цифровой подписи в Википедии](http://go.microsoft.com/fwlink/?LinkId=253157).</span><span class="sxs-lookup"><span data-stu-id="ab4ba-113">For more information see [Digital Signature on Wikipedia](http://go.microsoft.com/fwlink/?LinkId=253157).</span></span>  
  
 <span data-ttu-id="ab4ba-114">В этом сценарии реализуется шаблон обмена сообщениями «запрос-ответ», показанный на следующей схеме.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-114">This scenario implements a request/reply message pattern as illustrated by the following diagram.</span></span>  
  
 <span data-ttu-id="ab4ba-115">![Безопасная передача с помощью сертификатов](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span><span class="sxs-lookup"><span data-stu-id="ab4ba-115">![Secure transfer using certificates](../../../../docs/framework/wcf/feature-details/media/8f7b8968-899f-4538-a9e8-0eaa872a291c.gif "8f7b8968-899f-4538-a9e8-0eaa872a291c")</span></span>  
  
 <span data-ttu-id="ab4ba-116">Дополнительные сведения об использовании сертификата со службой см. в разделе [работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) и [как: Настройка порта с SSL-сертификата](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="ab4ba-116">For more information about using a certificate with a service, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md) and [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span> <span data-ttu-id="ab4ba-117">В следующей таблице описываются различные особенности этого сценария.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-117">The following table describes the various characteristics of the scenario.</span></span>  
  
|<span data-ttu-id="ab4ba-118">Характеристика</span><span class="sxs-lookup"><span data-stu-id="ab4ba-118">Characteristic</span></span>|<span data-ttu-id="ab4ba-119">Описание</span><span class="sxs-lookup"><span data-stu-id="ab4ba-119">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="ab4ba-120">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="ab4ba-120">Security Mode</span></span>|<span data-ttu-id="ab4ba-121">Transport</span><span class="sxs-lookup"><span data-stu-id="ab4ba-121">Transport</span></span>|  
|<span data-ttu-id="ab4ba-122">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="ab4ba-122">Interoperability</span></span>|<span data-ttu-id="ab4ba-123">С существующими службами и клиентами веб-служб.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-123">With existing Web service clients and services.</span></span>|  
|<span data-ttu-id="ab4ba-124">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="ab4ba-124">Authentication (Server)</span></span><br /><br /> <span data-ttu-id="ab4ba-125">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="ab4ba-125">Authentication (Client)</span></span>|<span data-ttu-id="ab4ba-126">Да (с использованием SSL-сертификата)</span><span class="sxs-lookup"><span data-stu-id="ab4ba-126">Yes (using an SSL certificate)</span></span><br /><br /> <span data-ttu-id="ab4ba-127">Да (с использованием сертификата X.509)</span><span class="sxs-lookup"><span data-stu-id="ab4ba-127">Yes (using an X.509 certificate)</span></span>|  
|<span data-ttu-id="ab4ba-128">Целостность данных</span><span class="sxs-lookup"><span data-stu-id="ab4ba-128">Data Integrity</span></span>|<span data-ttu-id="ab4ba-129">Да</span><span class="sxs-lookup"><span data-stu-id="ab4ba-129">Yes</span></span>|  
|<span data-ttu-id="ab4ba-130">Конфиденциальность данных</span><span class="sxs-lookup"><span data-stu-id="ab4ba-130">Data Confidentiality</span></span>|<span data-ttu-id="ab4ba-131">Да</span><span class="sxs-lookup"><span data-stu-id="ab4ba-131">Yes</span></span>|  
|<span data-ttu-id="ab4ba-132">Transport</span><span class="sxs-lookup"><span data-stu-id="ab4ba-132">Transport</span></span>|<span data-ttu-id="ab4ba-133">HTTPS</span><span class="sxs-lookup"><span data-stu-id="ab4ba-133">HTTPS</span></span>|  
|<span data-ttu-id="ab4ba-134">Привязка</span><span class="sxs-lookup"><span data-stu-id="ab4ba-134">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="configure-the-service"></a><span data-ttu-id="ab4ba-135">Настройка службы</span><span class="sxs-lookup"><span data-stu-id="ab4ba-135">Configure the Service</span></span>  
 <span data-ttu-id="ab4ba-136">Поскольку в этом сценарии служба размещается в службах IIS, он настраивается с помощью файла web.config.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-136">Since the service in this scenario is hosted under IIS, it is configured with a web.config file.</span></span> <span data-ttu-id="ab4ba-137">В следующем примере содержимого файла web.config показано, как настроить в <xref:System.ServiceModel.WSHttpBinding> использование безопасности транспорта и учетных данных клиента X.509.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-137">The following web.config shows how to configure the <xref:System.ServiceModel.WSHttpBinding> to use transport security and X.509 client credentials.</span></span>  
  
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
  
## <a name="configure-the-client"></a><span data-ttu-id="ab4ba-138">Настройка клиента</span><span class="sxs-lookup"><span data-stu-id="ab4ba-138">Configure the Client</span></span>  
 <span data-ttu-id="ab4ba-139">Настроить клиент можно в коде или в файле app.config.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-139">The client can be configured in code or in an app.config file.</span></span> <span data-ttu-id="ab4ba-140">В следующем примере показано, как настроить клиент в коде.</span><span class="sxs-lookup"><span data-stu-id="ab4ba-140">The following example shows how to configure the client in code.</span></span>  
  
```vb  
// Create the binding.  
WSHttpBinding myBinding = new WSHttpBinding();  
myBinding.Security.Mode = SecurityMode.Transport;  
myBinding.Security.Transport.ClientCredentialType =  
   HttpClientCredentialType.Certificate;  
  
// Create the endpoint address. Note that the machine name   
// must match the subject or DNS field of the X.509 certificate  
// used to authenticate the service.   
EndpointAddress ea = new  
   EndpointAddress("https://localhost/CalculatorService/service.svc");  
  
// Create the client. The code for the calculator   
// client is not shown here. See the sample applications  
// for examples of the calculator code.  
CalculatorClient cc =  
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
  
 <span data-ttu-id="ab4ba-141">Также можно настроить клиент в файле App.config, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="ab4ba-141">Alternatively you can configure the client in an App.config file as shown in the following example:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ab4ba-142">См. также</span><span class="sxs-lookup"><span data-stu-id="ab4ba-142">See Also</span></span>  
 [<span data-ttu-id="ab4ba-143">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="ab4ba-143">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="ab4ba-144">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="ab4ba-144">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
