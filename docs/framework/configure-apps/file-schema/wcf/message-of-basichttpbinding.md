---
title: <message> из <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: bce80d96b1bcec0d580f2de3fe88d5fd6ad0a3b5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400266"
---
# <a name="message-of-basichttpbinding"></a><span data-ttu-id="4c9e4-102">\<> сообщений от \<BasicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="4c9e4-102">\<message> of \<basicHttpBinding></span></span>
<span data-ttu-id="4c9e4-103">Определяет параметры безопасности на [ \<](basichttpbinding.md)уровне сообщений для > BasicHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-103">Defines the settings for message-level security of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
<span data-ttu-id="4c9e4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="4c9e4-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="4c9e4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="4c9e4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> basicHttpBinding**](basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)</span></span>\
<span data-ttu-id="4c9e4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="4c9e4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="4c9e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-basichttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="4c9e4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)</span></span>\
<span data-ttu-id="4c9e4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> сообщения**</span><span class="sxs-lookup"><span data-stu-id="4c9e4-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c9e4-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4c9e4-111">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4c9e4-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4c9e4-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4c9e4-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4c9e4-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4c9e4-114">Attributes</span></span>  
  
|<span data-ttu-id="4c9e4-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4c9e4-115">Attribute</span></span>|<span data-ttu-id="4c9e4-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4c9e4-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4c9e4-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="4c9e4-117">algorithmSuite</span></span>|<span data-ttu-id="4c9e4-118">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="4c9e4-119">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="4c9e4-120">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="4c9e4-121">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-121">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="4c9e4-122">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="4c9e4-122">clientCredentialType</span></span>|<span data-ttu-id="4c9e4-123">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-123">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="4c9e4-124">Значение по умолчанию — `UserName`.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-124">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="4c9e4-125">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="4c9e4-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4c9e4-126">Значение</span><span class="sxs-lookup"><span data-stu-id="4c9e4-126">Value</span></span>|<span data-ttu-id="4c9e4-127">Описание</span><span class="sxs-lookup"><span data-stu-id="4c9e4-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4c9e4-128">UserName</span><span class="sxs-lookup"><span data-stu-id="4c9e4-128">UserName</span></span>|<span data-ttu-id="4c9e4-129">— Требует, чтобы клиент прошел проверку подлинности на сервере с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-129">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="4c9e4-130">Эти учетные данные необходимо указать с помощью [ \<> ClientCredentials](clientcredentials.md).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-130">This credential needs to be specified using the [\<clientCredentials>](clientcredentials.md).</span></span><br /><span data-ttu-id="4c9e4-131">— WCF не поддерживает отправку дайджеста пароля или получение ключей с помощью паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-131">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="4c9e4-132">Поэтому WCF обеспечивает защиту транспорта при использовании учетных данных имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-132">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="4c9e4-133">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-133">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="4c9e4-134">Сертификат</span><span class="sxs-lookup"><span data-stu-id="4c9e4-134">Certificate</span></span>|<span data-ttu-id="4c9e4-135">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-135">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="4c9e4-136">Учетные данные клиента в этом случае необходимо указать с помощью [ \<](clientcredentials.md) [ \<](clientcertificate-of-servicecredentials.md)> ClientCredentials и > clientCertificate.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-136">The client credential in this case needs to be specified using [\<clientCredentials>](clientcredentials.md) and the [\<clientCertificate>](clientcertificate-of-servicecredentials.md).</span></span> <span data-ttu-id="4c9e4-137">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-137">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="4c9e4-138">Учетные данные службы в этом случае необходимо указать с помощью <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемента Behavior, указав сертификат службы с помощью [ \<> serviceCertificate](servicecertificate-of-servicecredentials.md).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-138">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the [\<serviceCertificate>](servicecertificate-of-servicecredentials.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4c9e4-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4c9e4-139">Child Elements</span></span>  
 <span data-ttu-id="4c9e4-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="4c9e4-140">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4c9e4-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4c9e4-141">Parent Elements</span></span>  
  
|<span data-ttu-id="4c9e4-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="4c9e4-142">Element</span></span>|<span data-ttu-id="4c9e4-143">Описание</span><span class="sxs-lookup"><span data-stu-id="4c9e4-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4c9e4-144">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="4c9e4-144">\<security></span></span>](security-of-basichttpbinding.md)|<span data-ttu-id="4c9e4-145">Определяет возможности безопасности для [ \<> BasicHttpBinding](basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4c9e4-145">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4c9e4-146">Пример</span><span class="sxs-lookup"><span data-stu-id="4c9e4-146">Example</span></span>  
 <span data-ttu-id="4c9e4-147">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-147">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="4c9e4-148">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-148">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="4c9e4-149">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-149">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="4c9e4-150">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-150">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="4c9e4-151">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="4c9e4-151">The same binding and security details are specified in the client configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
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
    <!-- This configuration defines the SecurityMode as Message and
         the clientCredentialType as Certificate. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
               is in the user's Trusted People store, then it will be trusted without performing a
               validation of the certificate's issuer chain. This setting is used here for convenience so that the
               sample can be run without having to have certificates issued by a certification authority (CA).
               This setting is less secure than the default, ChainTrust. The security implications of this
               setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="4c9e4-152">См. также</span><span class="sxs-lookup"><span data-stu-id="4c9e4-152">See also</span></span>

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [<span data-ttu-id="4c9e4-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4c9e4-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4c9e4-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="4c9e4-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="4c9e4-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="4c9e4-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4c9e4-156">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="4c9e4-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4c9e4-157">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="4c9e4-157">\<binding></span></span>](../../../misc/binding.md)
