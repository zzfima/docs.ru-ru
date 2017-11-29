---
title: "Безопасность сообщений с использованием клиента Windows без согласования учетных данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 943e3f32334bbf5746d3730f34371793bbd2754c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a><span data-ttu-id="4d85c-102">Безопасность сообщений с использованием клиента Windows без согласования учетных данных</span><span class="sxs-lookup"><span data-stu-id="4d85c-102">Message Security with a Windows Client without Credential Negotiation</span></span>
<span data-ttu-id="4d85c-103">В следующем сценарии показаны клиент и служба [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], защищенные протоколом Kerberos.</span><span class="sxs-lookup"><span data-stu-id="4d85c-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and service secured by the Kerberos protocol.</span></span>  
  
 <span data-ttu-id="4d85c-104">Клиент и служба находятся в одном и том же домене или в доверенных доменах.</span><span class="sxs-lookup"><span data-stu-id="4d85c-104">Both the service and the client are in the same domain or trusted domains.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d85c-105">Разница между этот сценарий и [безопасность сообщений с клиентом Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) является этот сценарий не выполняет согласование учетных данных службы с помощью службы перед отправкой сообщения приложения.</span><span class="sxs-lookup"><span data-stu-id="4d85c-105">The difference between this scenario and [Message Security with a Windows Client](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md) is that this scenario does not negotiate the service credential with the service prior to sending the application message.</span></span> <span data-ttu-id="4d85c-106">И так как для этого требуется протокол Kerberos, для этого сценария необходима среда домена Windows.</span><span class="sxs-lookup"><span data-stu-id="4d85c-106">Additionally, because this requires the Kerberos protocol, this scenario requires a Windows domain environment.</span></span>  
  
 <span data-ttu-id="4d85c-107">![Безопасность без согласования учетных данных сообщений](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span><span class="sxs-lookup"><span data-stu-id="4d85c-107">![Message security without credential negotiation](../../../../docs/framework/wcf/feature-details/media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f9baa-2439-4ef9-92f4-43c242d85d0d")</span></span>  
  
|<span data-ttu-id="4d85c-108">Характеристика</span><span class="sxs-lookup"><span data-stu-id="4d85c-108">Characteristic</span></span>|<span data-ttu-id="4d85c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4d85c-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="4d85c-110">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="4d85c-110">Security Mode</span></span>|<span data-ttu-id="4d85c-111">Сообщение</span><span class="sxs-lookup"><span data-stu-id="4d85c-111">Message</span></span>|  
|<span data-ttu-id="4d85c-112">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="4d85c-112">Interoperability</span></span>|<span data-ttu-id="4d85c-113">Да, WS-Security с клиентами, совместимыми с профилем маркера Kerberos</span><span class="sxs-lookup"><span data-stu-id="4d85c-113">Yes, WS-Security with Kerberos token-profile compatible clients</span></span>|  
|<span data-ttu-id="4d85c-114">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="4d85c-114">Authentication (Server)</span></span>|<span data-ttu-id="4d85c-115">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="4d85c-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="4d85c-116">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="4d85c-116">Authentication (Client)</span></span>|<span data-ttu-id="4d85c-117">Взаимная проверка подлинности сервера и клиента</span><span class="sxs-lookup"><span data-stu-id="4d85c-117">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="4d85c-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="4d85c-118">Integrity</span></span>|<span data-ttu-id="4d85c-119">Да</span><span class="sxs-lookup"><span data-stu-id="4d85c-119">Yes</span></span>|  
|<span data-ttu-id="4d85c-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="4d85c-120">Confidentiality</span></span>|<span data-ttu-id="4d85c-121">Да</span><span class="sxs-lookup"><span data-stu-id="4d85c-121">Yes</span></span>|  
|<span data-ttu-id="4d85c-122">Transport</span><span class="sxs-lookup"><span data-stu-id="4d85c-122">Transport</span></span>|<span data-ttu-id="4d85c-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="4d85c-123">HTTP</span></span>|  
|<span data-ttu-id="4d85c-124">Привязка</span><span class="sxs-lookup"><span data-stu-id="4d85c-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="4d85c-125">Служба</span><span class="sxs-lookup"><span data-stu-id="4d85c-125">Service</span></span>  
 <span data-ttu-id="4d85c-126">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="4d85c-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4d85c-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="4d85c-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="4d85c-128">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d85c-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="4d85c-129">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="4d85c-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4d85c-130">Код</span><span class="sxs-lookup"><span data-stu-id="4d85c-130">Code</span></span>  
 <span data-ttu-id="4d85c-131">В следующем коде создается конечная точка службы, которая использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="4d85c-131">The following code creates a service endpoint that uses message security.</span></span> <span data-ttu-id="4d85c-132">Этот код отключает согласование учетных данных службы и установку маркера контекста безопасности (SCT).</span><span class="sxs-lookup"><span data-stu-id="4d85c-132">The code disables service credential negotiation, and the establishment of a security context token (SCT).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d85c-133">Для использования типа учетных данных Windows без согласования учетная запись пользователя службы должна иметь доступ к имени участника-службы (SPN), зарегистрированному с доменом Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d85c-133">To use the Windows credential type without negotiation, the service's user account must have access to service principal name (SPN) that is registered with the Active Directory domain.</span></span> <span data-ttu-id="4d85c-134">Для этого существуют два способа:</span><span class="sxs-lookup"><span data-stu-id="4d85c-134">You can do this in two ways:</span></span>  
  
1.  <span data-ttu-id="4d85c-135">Используйте учетную запись `NetworkService` или `LocalSystem` для запуска службы.</span><span class="sxs-lookup"><span data-stu-id="4d85c-135">Use the `NetworkService` or `LocalSystem` account to run your service.</span></span> <span data-ttu-id="4d85c-136">Поскольку у этих учетных записей есть право доступа к SPN компьютера, устанавливаемому при присоединении компьютера к домену Active Directory, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] автоматически создает соответствующий элемент SPN в конечной точке службы в метаданных службы (языке описания веб-служб или языке WSDL).</span><span class="sxs-lookup"><span data-stu-id="4d85c-136">Because those accounts have access to the machine SPN that is established when the machine joins the Active Directory domain, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically generates the proper SPN element inside the service's endpoint in the service's metadata (Web Services Description Language, or WSDL).</span></span>  
  
2.  <span data-ttu-id="4d85c-137">Запустите службу из любой учетной записи домена Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d85c-137">Use an arbitrary Active Directory domain account to run your service.</span></span> <span data-ttu-id="4d85c-138">В этом случае потребуется установить SPN для учетной записи домена.</span><span class="sxs-lookup"><span data-stu-id="4d85c-138">In this case, you need to establish an SPN for that domain account.</span></span> <span data-ttu-id="4d85c-139">Это можно сделать, например, с помощью средства Setspn.exe.</span><span class="sxs-lookup"><span data-stu-id="4d85c-139">One way of doing this is to use the Setspn.exe utility tool.</span></span> <span data-ttu-id="4d85c-140">Создав SPN для учетной записи службы, задайте [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] публиковать это SPN в клиентах службы через метаданные (WSDL).</span><span class="sxs-lookup"><span data-stu-id="4d85c-140">Once the SPN is created for the service's account, configure [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to publish that SPN to the service's clients through its metadata (WSDL).</span></span> <span data-ttu-id="4d85c-141">Это можно сделать, настроив удостоверение конечной точки для предоставляемой конечной точки либо в файле конфигурации приложения, либо в коде.</span><span class="sxs-lookup"><span data-stu-id="4d85c-141">This is done by setting the endpoint identity for the exposed endpoint, either though an application configuration file or code.</span></span> <span data-ttu-id="4d85c-142">В следующем примере описывается программный способ публикации удостоверения.</span><span class="sxs-lookup"><span data-stu-id="4d85c-142">The following example publishes the identity programmatically.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4d85c-143">Имена участников-служб, протокол Kerberos и Active Directory в разделе [техническое дополнение Kerberos для Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="4d85c-143"> SPNs, the Kerberos protocol, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4d85c-144">удостоверения конечной точки в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="4d85c-144"> endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
 [!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
 [!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]  
  
### <a name="configuration"></a><span data-ttu-id="4d85c-145">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4d85c-145">Configuration</span></span>  
 <span data-ttu-id="4d85c-146">Вместо кода можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="4d85c-146">The following configuration can be used instead of the code.</span></span>  
  
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
  
## <a name="client"></a><span data-ttu-id="4d85c-147">Клиент</span><span class="sxs-lookup"><span data-stu-id="4d85c-147">Client</span></span>  
 <span data-ttu-id="4d85c-148">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="4d85c-148">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="4d85c-149">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="4d85c-149">Do one of the following:</span></span>  
  
-   <span data-ttu-id="4d85c-150">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="4d85c-150">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="4d85c-151">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="4d85c-151">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="4d85c-152">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4d85c-152">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="4d85c-153">Например:</span><span class="sxs-lookup"><span data-stu-id="4d85c-153">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="4d85c-154">Код</span><span class="sxs-lookup"><span data-stu-id="4d85c-154">Code</span></span>  
 <span data-ttu-id="4d85c-155">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="4d85c-155">The following code configures the client.</span></span> <span data-ttu-id="4d85c-156">Для режима безопасности задано значение Message, типу учетных данных клиента присвоено значение Windows.</span><span class="sxs-lookup"><span data-stu-id="4d85c-156">The security mode is set to Message, and the client credential type is set to Windows.</span></span> <span data-ttu-id="4d85c-157">Обратите внимание: свойствам <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> и <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> задается значение `false`.</span><span class="sxs-lookup"><span data-stu-id="4d85c-157">Note that the <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> and <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> properties are set to `false`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d85c-158">Для использования типа учетных данных Windows без согласования требуется настроить SPN учетной записи службы до начала обмена данными со службой.</span><span class="sxs-lookup"><span data-stu-id="4d85c-158">To use Windows credential type without negotiation, the client must be configured with the service's account SPN prior to commencing the communication with the service.</span></span> <span data-ttu-id="4d85c-159">Клиент использует имя SPN, чтобы получить маркер Kerberos для проверки подлинности и обеспечения безопасности обмена данными со службой.</span><span class="sxs-lookup"><span data-stu-id="4d85c-159">The client uses the SPN to get the Kerberos token to authenticate and secure the communication with the service.</span></span> <span data-ttu-id="4d85c-160">В следующем образце показано, как настроить SPN службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="4d85c-160">The following sample shows how to configure the client with the service's SPN.</span></span> <span data-ttu-id="4d85c-161">Если вы используете [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания клиента, имя участника-службы для службы автоматически распространяется на клиент из метаданных службы (WSDL), если содержит метаданные службы Эти сведения.</span><span class="sxs-lookup"><span data-stu-id="4d85c-161">If you are using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the client, the service's SPN will be automatically propagated to the client from the service's metadata (WSDL), if the service's metadata contains that information.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4d85c-162"> том, как настроить службу для включения ее имени участника-службы в метаданные, см. в подразделе «Служба» далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="4d85c-162"> how to configure the service to include its SPN in the service's metadata, see the "Service" section later in this topic .</span></span>  
>   
>  <span data-ttu-id="4d85c-163">Дополнительные сведения о имена участников-служб, Kerberos и Active Directory см. в разделе [техническое дополнение Kerberos для Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span><span class="sxs-lookup"><span data-stu-id="4d85c-163">For more information about SPNs, Kerberos, and Active Directory, see [Kerberos Technical Supplement for Windows](http://go.microsoft.com/fwlink/?LinkId=88330).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4d85c-164">удостоверения конечной точки в разделе [режимы проверки подлинности SecurityBindingElement](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) раздела.</span><span class="sxs-lookup"><span data-stu-id="4d85c-164"> endpoint identities, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) topic.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
 [!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]  
  
### <a name="configuration"></a><span data-ttu-id="4d85c-165">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="4d85c-165">Configuration</span></span>  
 <span data-ttu-id="4d85c-166">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="4d85c-166">The following code configures the client.</span></span> <span data-ttu-id="4d85c-167">Обратите внимание, что [ \<servicePrincipalName >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) элемент должен иметь значение для сопоставления имени участника-службы для службы, зарегистрированное для учетной записи службы в домене Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4d85c-167">Note that the [\<servicePrincipalName>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) element must be set to match the service's SPN as registered for the service's account in the Active Directory domain.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4d85c-168">См. также</span><span class="sxs-lookup"><span data-stu-id="4d85c-168">See Also</span></span>  
 [<span data-ttu-id="4d85c-169">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="4d85c-169">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="4d85c-170">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="4d85c-170">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="4d85c-171">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="4d85c-171">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
