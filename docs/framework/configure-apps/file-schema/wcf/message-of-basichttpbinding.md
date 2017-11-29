---
title: "&lt;message&gt; для &lt;basicHttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
caps.latest.revision: "23"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 014e7d5ca9d6bc379edb82a71d52dccb73fa23f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-of-ltbasichttpbindinggt"></a><span data-ttu-id="311ba-102">&lt;message&gt; для &lt;basicHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="311ba-102">&lt;message&gt; of &lt;basicHttpBinding&gt;</span></span>
<span data-ttu-id="311ba-103">Определяет параметры безопасности уровня сообщений [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="311ba-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="311ba-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="311ba-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="311ba-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="311ba-105">\<bindings></span></span>  
<span data-ttu-id="311ba-106">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="311ba-106">\<basicHttpBinding></span></span>  
<span data-ttu-id="311ba-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="311ba-107">\<binding></span></span>  
<span data-ttu-id="311ba-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="311ba-108">\<security></span></span>  
<span data-ttu-id="311ba-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="311ba-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="311ba-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="311ba-110">Syntax</span></span>  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="311ba-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="311ba-111">Attributes and Elements</span></span>  
 <span data-ttu-id="311ba-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="311ba-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="311ba-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="311ba-113">Attributes</span></span>  
  
|<span data-ttu-id="311ba-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="311ba-114">Attribute</span></span>|<span data-ttu-id="311ba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="311ba-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="311ba-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="311ba-116">algorithmSuite</span></span>|<span data-ttu-id="311ba-117">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="311ba-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="311ba-118">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="311ba-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="311ba-119">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="311ba-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="311ba-120">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="311ba-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="311ba-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="311ba-121">clientCredentialType</span></span>|<span data-ttu-id="311ba-122">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="311ba-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="311ba-123">Значение по умолчанию — `UserName`.</span><span class="sxs-lookup"><span data-stu-id="311ba-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="311ba-124">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="311ba-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="311ba-125">Значение</span><span class="sxs-lookup"><span data-stu-id="311ba-125">Value</span></span>|<span data-ttu-id="311ba-126">Описание</span><span class="sxs-lookup"><span data-stu-id="311ba-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="311ba-127">UserName</span><span class="sxs-lookup"><span data-stu-id="311ba-127">UserName</span></span>|<span data-ttu-id="311ba-128">-Требует подлинности клиента на сервер с использованием имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="311ba-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="311ba-129">Эти учетные данные должны быть определены с помощью [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="311ba-129">This credential needs to be specified using the [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md).</span></span><br /><span data-ttu-id="311ba-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]не поддерживает передачу дайджеста пароля или получение ключей с использованием паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="311ba-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="311ba-131">Таким образом, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] принудительно обеспечивает безопасность транспорта при использовании имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="311ba-131">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="311ba-132">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="311ba-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="311ba-133">Сертификат</span><span class="sxs-lookup"><span data-stu-id="311ba-133">Certificate</span></span>|<span data-ttu-id="311ba-134">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="311ba-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="311ba-135">В этом случае необходимо указать с помощью учетных данных клиента [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) и [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="311ba-135">The client credential in this case needs to be specified using [\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) and the [\<clientCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="311ba-136">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="311ba-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="311ba-137">В этом случае необходимо указать с помощью учетных данных службы <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемент поведения и указав службу сертификатов с помощью [ \<serviceCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="311ba-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="311ba-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="311ba-138">Child Elements</span></span>  
 <span data-ttu-id="311ba-139">Нет</span><span class="sxs-lookup"><span data-stu-id="311ba-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="311ba-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="311ba-140">Parent Elements</span></span>  
  
|<span data-ttu-id="311ba-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="311ba-141">Element</span></span>|<span data-ttu-id="311ba-142">Описание</span><span class="sxs-lookup"><span data-stu-id="311ba-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="311ba-143">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="311ba-143">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|<span data-ttu-id="311ba-144">Определяет возможности безопасности для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="311ba-144">Defines the security capabilities for the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="311ba-145">Пример</span><span class="sxs-lookup"><span data-stu-id="311ba-145">Example</span></span>  
 <span data-ttu-id="311ba-146">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="311ba-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="311ba-147">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="311ba-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="311ba-148">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="311ba-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="311ba-149">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="311ba-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="311ba-150">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="311ba-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
        <endpoint address=""  
                  binding="basicHttpBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <basicHttpBinding>  
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a><span data-ttu-id="311ba-151">См. также</span><span class="sxs-lookup"><span data-stu-id="311ba-151">See Also</span></span>  
 <xref:System.ServiceModel.BasicHttpMessageSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>  
 <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>  
 [<span data-ttu-id="311ba-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="311ba-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="311ba-153">Привязки</span><span class="sxs-lookup"><span data-stu-id="311ba-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="311ba-154">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="311ba-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="311ba-155">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="311ba-155">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="311ba-156">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="311ba-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
