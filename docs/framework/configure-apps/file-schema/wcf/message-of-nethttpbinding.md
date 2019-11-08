---
title: <message> из <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 62b1793d18ddc8edc1f55b02137c4e0a9f7327d2
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738957"
---
# <a name="message-of-nethttpbinding"></a><span data-ttu-id="dd6b7-102">> сообщения \<\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="dd6b7-102">\<message> of \<netHttpBinding></span></span>
<span data-ttu-id="dd6b7-103">Определяет параметры безопасности на уровне сообщений [\<netHttpBinding >](nethttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="dd6b7-103">Defines the settings for message-level security of the [\<netHttpBinding>](nethttpbinding.md).</span></span>  
  
<span data-ttu-id="dd6b7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dd6b7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dd6b7-105">&nbsp;&nbsp;[ **\<System. serviceModel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="dd6b7-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="dd6b7-106">привязки &nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="dd6b7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="dd6b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd6b7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="dd6b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Binding** ></span><span class="sxs-lookup"><span data-stu-id="dd6b7-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="dd6b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<security >** ](security-of-nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="dd6b7-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)</span></span>\
<span data-ttu-id="dd6b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**сообщение >**</span><span class="sxs-lookup"><span data-stu-id="dd6b7-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd6b7-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd6b7-111">Syntax</span></span>  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd6b7-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dd6b7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="dd6b7-113">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-113">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd6b7-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dd6b7-114">Attributes</span></span>  
  
|<span data-ttu-id="dd6b7-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dd6b7-115">Attribute</span></span>|<span data-ttu-id="dd6b7-116">Описание</span><span class="sxs-lookup"><span data-stu-id="dd6b7-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="dd6b7-117">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="dd6b7-117">algorithmSuite</span></span>|<span data-ttu-id="dd6b7-118">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-118">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="dd6b7-119">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-119">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="dd6b7-120">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="dd6b7-120">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="dd6b7-121">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-121">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="dd6b7-122">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="dd6b7-122">clientCredentialType</span></span>|<span data-ttu-id="dd6b7-123">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-123">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="dd6b7-124">Значение по умолчанию: `UserName`.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-124">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="dd6b7-125">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="dd6b7-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="dd6b7-126">значения</span><span class="sxs-lookup"><span data-stu-id="dd6b7-126">Value</span></span>|<span data-ttu-id="dd6b7-127">Описание</span><span class="sxs-lookup"><span data-stu-id="dd6b7-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd6b7-128">UserName</span><span class="sxs-lookup"><span data-stu-id="dd6b7-128">UserName</span></span>|<span data-ttu-id="dd6b7-129">— Требует, чтобы клиент прошел проверку подлинности на сервере с учетными данными пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-129">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="dd6b7-130">Эти учетные данные необходимо указать с помощью элемента >`clientCredentials`<.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-130">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="dd6b7-131">— WCF не поддерживает отправку дайджеста пароля или получение ключей с помощью паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-131">-   WCF does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="dd6b7-132">Поэтому WCF обеспечивает защиту транспорта при использовании учетных данных имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-132">Therefore, WCF enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="dd6b7-133">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-133">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="dd6b7-134">Сертификат</span><span class="sxs-lookup"><span data-stu-id="dd6b7-134">Certificate</span></span>|<span data-ttu-id="dd6b7-135">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-135">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="dd6b7-136">Учетные данные клиента в этом случае необходимо указать с помощью <`clientCredentials`> и`clientCertificate`< >.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-136">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="dd6b7-137">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-137">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="dd6b7-138">Учетные данные службы в этом случае необходимо указать с помощью <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемента поведения, указав сертификат службы с помощью \<serviceCertificate > элемента serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-138">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dd6b7-139">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dd6b7-139">Child Elements</span></span>  
 <span data-ttu-id="dd6b7-140">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="dd6b7-140">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dd6b7-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dd6b7-141">Parent Elements</span></span>  
  
|<span data-ttu-id="dd6b7-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="dd6b7-142">Element</span></span>|<span data-ttu-id="dd6b7-143">Описание</span><span class="sxs-lookup"><span data-stu-id="dd6b7-143">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd6b7-144"><`security`> элемента <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="dd6b7-144"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="dd6b7-145">Определяет возможности безопасности для элемента <`netHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-145">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd6b7-146">Пример</span><span class="sxs-lookup"><span data-stu-id="dd6b7-146">Example</span></span>  
 <span data-ttu-id="dd6b7-147">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-147">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="dd6b7-148">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-148">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="dd6b7-149">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-149">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="dd6b7-150">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-150">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="dd6b7-151">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="dd6b7-151">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dd6b7-152">См. также</span><span class="sxs-lookup"><span data-stu-id="dd6b7-152">See also</span></span>

- [<span data-ttu-id="dd6b7-153">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dd6b7-153">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="dd6b7-154">Привязки</span><span class="sxs-lookup"><span data-stu-id="dd6b7-154">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="dd6b7-155">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="dd6b7-155">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="dd6b7-156">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="dd6b7-156">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="dd6b7-157">> привязки \<</span><span class="sxs-lookup"><span data-stu-id="dd6b7-157">\<binding></span></span>](bindings.md)
