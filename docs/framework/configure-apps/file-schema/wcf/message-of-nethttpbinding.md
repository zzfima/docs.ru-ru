---
title: '&lt;сообщение&gt; для &lt;netHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
ms.openlocfilehash: 6e4cd2c000d577e26b54e09f24279e0fd74afcf1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltmessagegt-of-ltnethttpbindinggt"></a><span data-ttu-id="a7f06-102">&lt;сообщение&gt; для &lt;netHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="a7f06-102">&lt;message&gt; of &lt;netHttpBinding&gt;</span></span>
<span data-ttu-id="a7f06-103">Определяет параметры безопасности уровня сообщений [ \<basicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="a7f06-103">Defines the settings for message-level security of the [\<basicHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).</span></span>  
  
 <span data-ttu-id="a7f06-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a7f06-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="a7f06-105">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="a7f06-105">\<bindings></span></span>  
<span data-ttu-id="a7f06-106">\<Привязка netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="a7f06-106">\<netHttpBinding></span></span>  
<span data-ttu-id="a7f06-107">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a7f06-107">\<binding></span></span>  
<span data-ttu-id="a7f06-108">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="a7f06-108">\<security></span></span>  
<span data-ttu-id="a7f06-109">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="a7f06-109">\<message></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7f06-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7f06-110">Syntax</span></span>  
  
```xml  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7f06-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a7f06-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a7f06-112">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a7f06-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7f06-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a7f06-113">Attributes</span></span>  
  
|<span data-ttu-id="a7f06-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a7f06-114">Attribute</span></span>|<span data-ttu-id="a7f06-115">Описание</span><span class="sxs-lookup"><span data-stu-id="a7f06-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a7f06-116">algorithmSuite</span><span class="sxs-lookup"><span data-stu-id="a7f06-116">algorithmSuite</span></span>|<span data-ttu-id="a7f06-117">Задает алгоритмы шифрования сообщений и ключей.</span><span class="sxs-lookup"><span data-stu-id="a7f06-117">Sets the message encryption and key-wrap algorithms.</span></span> <span data-ttu-id="a7f06-118">Этот атрибут имеет тип <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, который задает алгоритмы и размеры ключей.</span><span class="sxs-lookup"><span data-stu-id="a7f06-118">This attribute is of type <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>, which specifies the algorithms and the key sizes.</span></span> <span data-ttu-id="a7f06-119">Эти алгоритмы соответствуют алгоритмам, заданным в спецификации языка политики безопасности (WS-SecurityPolicy).</span><span class="sxs-lookup"><span data-stu-id="a7f06-119">These algorithms map to those specified in the Security Policy Language (WS-SecurityPolicy) specification.</span></span><br /><br /> <span data-ttu-id="a7f06-120">Значение по умолчанию — `Basic256`.</span><span class="sxs-lookup"><span data-stu-id="a7f06-120">The default value is `Basic256`.</span></span>|  
|<span data-ttu-id="a7f06-121">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="a7f06-121">clientCredentialType</span></span>|<span data-ttu-id="a7f06-122">Задает тип учетных данных, используемых при проверке подлинности клиента с помощью безопасности на уровне сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7f06-122">Specifies the type of credential to be used when performing client authentication using message-based security.</span></span> <span data-ttu-id="a7f06-123">Значение по умолчанию — `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a7f06-123">The default is `UserName`.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="a7f06-124">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="a7f06-124">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="a7f06-125">Значение</span><span class="sxs-lookup"><span data-stu-id="a7f06-125">Value</span></span>|<span data-ttu-id="a7f06-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a7f06-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a7f06-127">UserName</span><span class="sxs-lookup"><span data-stu-id="a7f06-127">UserName</span></span>|<span data-ttu-id="a7f06-128">-Требует подлинности клиента на сервер с использованием имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="a7f06-128">-   Requires the client be authenticated to the server with a UserName credential.</span></span> <span data-ttu-id="a7f06-129">Эти учетные данные должны быть указаны с помощью элемента <`clientCredentials`>.</span><span class="sxs-lookup"><span data-stu-id="a7f06-129">This credential needs to be specified using the <`clientCredentials`> element.</span></span><br /><span data-ttu-id="a7f06-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] не поддерживает передачу дайджеста пароля или получение ключей с использованием паролей и использование таких ключей для обеспечения безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7f06-130">-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] does not support sending a password digest or deriving keys using passwords and using such keys for message security.</span></span> <span data-ttu-id="a7f06-131">Таким образом, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] принудительно обеспечивает безопасность транспорта при использовании имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="a7f06-131">Therefore, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] enforces that the transport be secured when using UserName credentials.</span></span> <span data-ttu-id="a7f06-132">Для `basicHttpBinding` это требует настройки канала SSL.</span><span class="sxs-lookup"><span data-stu-id="a7f06-132">For the `basicHttpBinding`, this requires setting up an SSL channel.</span></span>|  
|<span data-ttu-id="a7f06-133">Сертификат</span><span class="sxs-lookup"><span data-stu-id="a7f06-133">Certificate</span></span>|<span data-ttu-id="a7f06-134">Требует, чтобы при подключении к серверу проверка подлинности клиента проводилась с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="a7f06-134">Requires that the client be authenticated to the server using a certificate.</span></span> <span data-ttu-id="a7f06-135">В этом случае учетные данные клиента должны быть определены с помощью элементов <`clientCredentials`> и <`clientCertificate`>.</span><span class="sxs-lookup"><span data-stu-id="a7f06-135">The client credential in this case needs to be specified using <`clientCredentials`> and the <`clientCertificate`>.</span></span> <span data-ttu-id="a7f06-136">Кроме того, при использовании режима безопасности сообщений клиенту должен быть предоставлен сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="a7f06-136">In addition, when using message security mode, the client needs to be provisioned with the service certificate.</span></span> <span data-ttu-id="a7f06-137">В этом случае необходимо указать с помощью учетных данных службы <xref:System.ServiceModel.Description.ClientCredentials> класса или `ClientCredentials` элемент поведения и указав службу сертификатов с помощью \<serviceCertificate > элемента serviceCredentials.</span><span class="sxs-lookup"><span data-stu-id="a7f06-137">The service credential in this case needs to be specified using <xref:System.ServiceModel.Description.ClientCredentials> class or `ClientCredentials` behavior element and specifying the service certificate using the \<serviceCertificate> element of serviceCredentials.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7f06-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a7f06-138">Child Elements</span></span>  
 <span data-ttu-id="a7f06-139">Нет</span><span class="sxs-lookup"><span data-stu-id="a7f06-139">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a7f06-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a7f06-140">Parent Elements</span></span>  
  
|<span data-ttu-id="a7f06-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="a7f06-141">Element</span></span>|<span data-ttu-id="a7f06-142">Описание</span><span class="sxs-lookup"><span data-stu-id="a7f06-142">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7f06-143"><`security`> элемента <`netHttpBinding`></span><span class="sxs-lookup"><span data-stu-id="a7f06-143"><`security`> element of <`netHttpBinding`></span></span>|<span data-ttu-id="a7f06-144">Определяет возможности безопасности для элемента <`netHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="a7f06-144">Defines the security capabilities for the <`netHttpBinding`> Element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a7f06-145">Пример</span><span class="sxs-lookup"><span data-stu-id="a7f06-145">Example</span></span>  
 <span data-ttu-id="a7f06-146">В образце демонстрируется реализация приложения, которое использует basicHttpBinding и безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="a7f06-146">This sample demonstrates how to implement an application that uses the basicHttpBinding and message security.</span></span> <span data-ttu-id="a7f06-147">В следующем примере конфигурации для службы в определении конечной точки задаются привязка basicHttpBinding и ссылки на конфигурацию привязки с именем `Binding1`.</span><span class="sxs-lookup"><span data-stu-id="a7f06-147">In the following configuration example for a service, the endpoint definition specifies the basicHttpBinding and references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="a7f06-148">Сертификат, используемый службой для своей проверки подлинности при подключении к клиенту, установлен в разделе `behaviors` файла конфигурации в элементе `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="a7f06-148">The certificate that the service uses to authenticate itself to the client is set in the `behaviors` section of the configuration file under the `serviceCredentials` element.</span></span> <span data-ttu-id="a7f06-149">Режим проверки, применяемый к сертификату, который клиент использует для своей проверки подлинности при подключении к службе, также установлен в разделе `behaviors` в элементе `clientCertificate`.</span><span class="sxs-lookup"><span data-stu-id="a7f06-149">The validation mode that applies to the certificate that the client uses to authenticate itself to the service is also set in the `behaviors` section under the `clientCertificate` element.</span></span>  
  
 <span data-ttu-id="a7f06-150">Та же привязка и данные безопасности задаются в файле конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="a7f06-150">The same binding and security details are specified in the client configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a7f06-151">См. также</span><span class="sxs-lookup"><span data-stu-id="a7f06-151">See Also</span></span>  
 [<span data-ttu-id="a7f06-152">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a7f06-152">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="a7f06-153">Привязки</span><span class="sxs-lookup"><span data-stu-id="a7f06-153">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a7f06-154">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="a7f06-154">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="a7f06-155">Использование привязок для настройки служб Windows Communication Foundation и клиентов</span><span class="sxs-lookup"><span data-stu-id="a7f06-155">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="a7f06-156">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="a7f06-156">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
