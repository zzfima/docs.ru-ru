---
title: <message> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 5bc953b4a1fad90aec5db507469368e7b21bb7e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105460"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="458d7-102">\<сообщение > из \<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="458d7-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="458d7-103">Определяет параметры безопасности уровня сообщений для [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="458d7-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="458d7-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="458d7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="458d7-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="458d7-105">\<bindings></span></span>  
<span data-ttu-id="458d7-106">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="458d7-106">\<netHttpBinding></span></span>  
<span data-ttu-id="458d7-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="458d7-107">\<binding></span></span>  
<span data-ttu-id="458d7-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="458d7-108">\<security></span></span>  
<span data-ttu-id="458d7-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="458d7-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="458d7-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="458d7-110">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="458d7-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="458d7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="458d7-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="458d7-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="458d7-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="458d7-113">Attributes</span></span>  
  
|<span data-ttu-id="458d7-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="458d7-114">Attribute</span></span>|<span data-ttu-id="458d7-115">Описание</span><span class="sxs-lookup"><span data-stu-id="458d7-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="458d7-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="458d7-116">algorithmSuite</span></span>|<span data-ttu-id="458d7-117">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="458d7-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="458d7-118">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="458d7-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="458d7-119">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="458d7-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="458d7-120">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="458d7-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="458d7-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="458d7-121">clientCredentialType</span></span>|<span data-ttu-id="458d7-122">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="458d7-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="458d7-123">Значение по умолчанию — `UserName`.</span><span class="sxs-lookup"><span data-stu-id="458d7-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="458d7-124">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="458d7-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="458d7-125">Значение</span><span class="sxs-lookup"><span data-stu-id="458d7-125">Value</span></span>|<span data-ttu-id="458d7-126">Описание</span><span class="sxs-lookup"><span data-stu-id="458d7-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="458d7-127">UserName</span><span class="sxs-lookup"><span data-stu-id="458d7-127">UserName</span></span>|<span data-ttu-id="458d7-128">— Требует проверки подлинности клиента на сервер с помощью имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="458d7-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="458d7-129">Эти учетные данные должны быть определены с помощью <`clientCredentials`> элемента.</span><span class="sxs-lookup"><span data-stu-id="458d7-129">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="458d7-130">-WCF не поддерживает передачу хэш-кода пароля или получение ключей с помощью паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="458d7-130">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="458d7-131">Таким образом WCF обеспечивает, что безопасность транспорта при использовании учетных данных UserName.</span><span class="sxs-lookup"><span data-stu-id="458d7-131">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="458d7-132">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="458d7-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="458d7-133">Сертификат</span><span class="sxs-lookup"><span data-stu-id="458d7-133">Certificate</span></span>|<span data-ttu-id="458d7-134">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="458d7-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="458d7-135">Учетные данные клиента в этом случае должны быть определены с помощью <`clientCredentials`> и <`clientCertificate`>.</span><span class="sxs-lookup"><span data-stu-id="458d7-135">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="458d7-136">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="458d7-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="458d7-137">Учетные данные службы в этом случае должны быть определены с помощью <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемент поведения и указав службы сертификат, с помощью \<serviceCertificate > элемента serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="458d7-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="458d7-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="458d7-138">Child Elements</span></span>  
 <span data-ttu-id="458d7-139">Нет</span><span class="sxs-lookup"><span data-stu-id="458d7-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="458d7-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="458d7-140">Parent Elements</span></span>  
  
|<span data-ttu-id="458d7-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="458d7-141">Element</span></span>|<span data-ttu-id="458d7-142">Описание</span><span class="sxs-lookup"><span data-stu-id="458d7-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="458d7-143"><`security`> элемента <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="458d7-143"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="458d7-144">Определяет возможности безопасности для <`netHttpBinding`> элемента.</span><span class="sxs-lookup"><span data-stu-id="458d7-144">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="458d7-145">Пример</span><span class="sxs-lookup"><span data-stu-id="458d7-145">Example</span></span>  
 <span data-ttu-id="458d7-146">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="458d7-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="458d7-147">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="458d7-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="458d7-148">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="458d7-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="458d7-149">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="458d7-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="458d7-150">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="458d7-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
      <!-- This configuration defines the SecurityMode as Message and
           the clientCredentialType as Certificate. -->
      <binding name="Binding1" >
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
  
## <a name="see-also"></a><span data-ttu-id="458d7-151">См. также</span><span class="sxs-lookup"><span data-stu-id="458d7-151">See also</span></span>

- [<span data-ttu-id="458d7-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="458d7-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="458d7-153">Привязки</span><span class="sxs-lookup"><span data-stu-id="458d7-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="458d7-154">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="458d7-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="458d7-155">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="458d7-155">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="458d7-156">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="458d7-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
