---
title: Безопасность сообщений с использованием клиента Windows без согласования учетных данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 7f46ea28fe0827e7919b62550492d66a51a125fc
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2018
ms.locfileid: "44705720"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="7ea39-102">Безопасность сообщений с использованием клиента Windows без согласования учетных данных</span><span class="sxs-lookup"><span data-stu-id="7ea39-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="7ea39-103">В следующем сценарии показаны клиент Windows Communication Foundation (WCF) и служба, защищенные протоколом Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7ea39-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="7ea39-104">Клиент и служба находятся в одном и том же домене или в доверенных доменах.</span><span class="sxs-lookup"><span data-stu-id="7ea39-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea39-105">Разница между этот сценарий и [безопасность сообщений с клиентом Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) — это то, что этот сценарий не выполняет согласование учетных данных службы перед отправкой сообщения приложения.</span><span class="sxs-lookup"><span data-stu-id="7ea39-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="7ea39-106">И так как для этого требуется протокол Kerberos, для этого сценария необходима среда домена Windows.</span><span class="sxs-lookup"><span data-stu-id="7ea39-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="7ea39-107">![Безопасность без согласования учетных данных сообщений](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="7ea39-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="7ea39-108">Характеристика</span><span class="sxs-lookup"><span data-stu-id="7ea39-108">Characteristic</span></span>|<span data-ttu-id="7ea39-109">Описание</span><span class="sxs-lookup"><span data-stu-id="7ea39-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="7ea39-110">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="7ea39-110">Security Mode</span></span>|<span data-ttu-id="7ea39-111">Сообщение</span><span class="sxs-lookup"><span data-stu-id="7ea39-111">Message</span></span>|  
|<span data-ttu-id="7ea39-112">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="7ea39-112">Interoperability</span></span>|<span data-ttu-id="7ea39-113">Да, WS-Security с клиентами, совместимыми с профилем маркера Kerberos</span><span class="sxs-lookup"><span data-stu-id="7ea39-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="7ea39-114">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="7ea39-114">Authentication (Server)</span></span>|<span data-ttu-id="7ea39-115">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="7ea39-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="7ea39-116">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="7ea39-116">Authentication (Client)</span></span>|<span data-ttu-id="7ea39-117">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="7ea39-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="7ea39-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="7ea39-118">Integrity</span></span>|<span data-ttu-id="7ea39-119">Да</span><span class="sxs-lookup"><span data-stu-id="7ea39-119">Yes</span></span>|  
|<span data-ttu-id="7ea39-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="7ea39-120">Confidentiality</span></span>|<span data-ttu-id="7ea39-121">Да</span><span class="sxs-lookup"><span data-stu-id="7ea39-121">Yes</span></span>|  
|<span data-ttu-id="7ea39-122">Transport</span><span class="sxs-lookup"><span data-stu-id="7ea39-122">Transport</span></span>|<span data-ttu-id="7ea39-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="7ea39-123">HTTP</span></span>|  
|<span data-ttu-id="7ea39-124">Привязка</span><span class="sxs-lookup"><span data-stu-id="7ea39-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="7ea39-125">Служба</span><span class="sxs-lookup"><span data-stu-id="7ea39-125">Service</span></span>  
 <span data-ttu-id="7ea39-126">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="7ea39-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7ea39-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7ea39-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7ea39-128">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7ea39-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="7ea39-129">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="7ea39-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7ea39-130">Код</span><span class="sxs-lookup"><span data-stu-id="7ea39-130">Code</span></span>  
 <span data-ttu-id="7ea39-131">В следующем коде создается конечная точка службы, которая использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="7ea39-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="7ea39-132">Этот код отключает согласование учетных данных службы и установку маркера контекста безопасности (SCT).</span><span class="sxs-lookup"><span data-stu-id="7ea39-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea39-133">Для использования типа учетных данных Windows без согласования учетная запись пользователя службы должна иметь доступ к имени участника-службы (SPN), зарегистрированному с доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea39-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="7ea39-134">Для этого существуют два способа:</span><span class="sxs-lookup"><span data-stu-id="7ea39-134">You can do this in two ways:</span></span>  
  
1.  <span data-ttu-id="7ea39-135">Используйте учетную запись `NetworkService` или `LocalSystem` для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="7ea39-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="7ea39-136">Так как эти учетные записи имеют доступ к SPN компьютера, определяются, когда компьютер присоединяется к домену Active Directory, WCF автоматически создает соответствующий элемент SPN внутри конечной точки службы в метаданных службы (Web Services Description Язык или язык WSDL).</span><span class="sxs-lookup"><span data-stu-id="7ea39-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, WCF automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2.  <span data-ttu-id="7ea39-137">Запустите службу из любой учетной записи домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea39-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="7ea39-138">В этом случае потребуется установить SPN для учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="7ea39-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="7ea39-139">Это можно сделать, например, с помощью средства Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="7ea39-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="7ea39-140">Создав SPN для учетной записи службы, Настройка WCF, чтобы публиковать это SPN в клиентах службы через ее метаданные (WSDL).</span><span class="sxs-lookup"><span data-stu-id="7ea39-140">Once the SPN is created for the service's account, configure WCF to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="7ea39-141">Это можно сделать, настроив удостоверение конечной точки для предоставляемой конечной точки либо в файле конфигурации приложения, либо в коде.</span><span class="sxs-lookup"><span data-stu-id="7ea39-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="7ea39-142">В следующем примере описывается программный способ публикации удостоверения.</span><span class="sxs-lookup"><span data-stu-id="7ea39-142">The following example publishes the identity programmatically.</span></span>  
  
 <span data-ttu-id="7ea39-143">Дополнительные сведения об именах SPN, протокол Kerberos и Active Directory, см. в разделе [Kerberos технические дополнения для Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="7ea39-143">For more information about SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="7ea39-144">Дополнительные сведения об удостоверениях конечных точек см. в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="7ea39-144">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="7ea39-145">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="7ea39-145">Configuration</span></span>  
 <span data-ttu-id="7ea39-146">Вместо кода можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="7ea39-146">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors />  
    <services>  
      <service behaviorConfiguration="" name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="KerberosBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator"   
                  listenUri="net.tcp://localhost/metadata" >  
         <identity>  
            <servicePrincipalName value="service_spn_name" />  
         </identity>  
        </endpoint>  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="KerberosBinding">  
          <security>  
            <message negotiateServiceCredential="false"   
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="7ea39-147">Клиент</span><span class="sxs-lookup"><span data-stu-id="7ea39-147">Client</span></span>  
 <span data-ttu-id="7ea39-148">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="7ea39-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="7ea39-149">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="7ea39-149">Do one of the following:</span></span>  
  
-   <span data-ttu-id="7ea39-150">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="7ea39-150">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="7ea39-151">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="7ea39-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="7ea39-152">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7ea39-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="7ea39-153">Например:</span><span class="sxs-lookup"><span data-stu-id="7ea39-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="7ea39-154">Код</span><span class="sxs-lookup"><span data-stu-id="7ea39-154">Code</span></span>  
 <span data-ttu-id="7ea39-155">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="7ea39-155">The following code configures the client.</span></span> <span data-ttu-id="7ea39-156">Для режима безопасности задано значение Message, типу учетных данных клиента присвоено значение Windows.</span><span class="sxs-lookup"><span data-stu-id="7ea39-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="7ea39-157">Обратите внимание: свойствам <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> и <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> задается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="7ea39-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7ea39-158">Для использования типа учетных данных Windows без согласования требуется настроить SPN учетной записи службы до начала обмена данными со службой.</span><span class="sxs-lookup"><span data-stu-id="7ea39-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="7ea39-159">Клиент использует имя SPN, чтобы получить маркер Kerberos для проверки подлинности и обеспечения безопасности обмена данными со службой.</span><span class="sxs-lookup"><span data-stu-id="7ea39-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="7ea39-160">В следующем образце показано, как настроить SPN службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="7ea39-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="7ea39-161">Если вы используете [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента, SPN службы будут автоматически распространяться клиенту из метаданных службы (WSDL), если содержит метаданные службы Эти сведения.</span><span class="sxs-lookup"><span data-stu-id="7ea39-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> <span data-ttu-id="7ea39-162">Дополнительные сведения о том, как настроить службу для включения имени участника-службы в метаданных службы см. в разделе «Служба» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7ea39-162">For more information about how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="7ea39-163">Дополнительные сведения о SPN, Kerberos и Active Directory, см. в разделе [Kerberos технические дополнения для Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="7ea39-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](https://go.microsoft.com/fwlink/?LinkId=88330).</span></span> <span data-ttu-id="7ea39-164">Дополнительные сведения об удостоверениях конечных точек см. в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="7ea39-164">For more information about endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="7ea39-165">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="7ea39-165">Configuration</span></span>  
 <span data-ttu-id="7ea39-166">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="7ea39-166">The following code configures the client.</span></span> <span data-ttu-id="7ea39-167">Обратите внимание, что [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) должно быть присвоено соответствовать SPN службы, установленному для учетной записи службы в домене Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7ea39-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Windows"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://localhost/Calculator"   
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <servicePrincipalName value="service_spn_name" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7ea39-168">См. также</span><span class="sxs-lookup"><span data-stu-id="7ea39-168">See Also</span></span>  
 [<span data-ttu-id="7ea39-169">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="7ea39-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="7ea39-170">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="7ea39-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="7ea39-171">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="7ea39-171">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
