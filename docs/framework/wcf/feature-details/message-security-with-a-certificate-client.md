---
title: Безопасность сообщений при использовании клиентом сертификата
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 99770573-c815-4428-a38c-e4335c8bd7ce
ms.openlocfilehash: a027577f5118f9a5b2f3eeaa29ddfde20851a8f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530857"
---
# <a name="message-security-with-a-certificate-client"></a><span data-ttu-id="6f7b1-102">Безопасность сообщений при использовании клиентом сертификата</span><span class="sxs-lookup"><span data-stu-id="6f7b1-102">Message Security with a Certificate Client</span></span>
<span data-ttu-id="6f7b1-103">В следующем сценарии показаны клиент Windows Communication Foundation (WCF) и служба, защищенные с помощью режима безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-103">The following scenario shows a Windows Communication Foundation (WCF) client and service secured using message security mode.</span></span> <span data-ttu-id="6f7b1-104">Проверка подлинности клиента и службы выполняется с помощью сертификатов.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-104">Both the client and the service are authenticated with certificates.</span></span> <span data-ttu-id="6f7b1-105">Дополнительные сведения см. в разделе [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-105">For more information, see [Distributed Application Security](../../../../docs/framework/wcf/feature-details/distributed-application-security.md).</span></span>  
  
 <span data-ttu-id="6f7b1-106">Образец приложения, см. в разделе [сертификат безопасности сообщений](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-106">For a sample application, see [Message Security Certificate](../../../../docs/framework/wcf/samples/message-security-certificate.md).</span></span>  
  
 <span data-ttu-id="6f7b1-107">![Клиент с сертификатом](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span><span class="sxs-lookup"><span data-stu-id="6f7b1-107">![Client with certificate](../../../../docs/framework/wcf/feature-details/media/clientwithcertificate.gif "ClientWithCertificate")</span></span>  
  
|<span data-ttu-id="6f7b1-108">Характеристика</span><span class="sxs-lookup"><span data-stu-id="6f7b1-108">Characteristic</span></span>|<span data-ttu-id="6f7b1-109">Описание</span><span class="sxs-lookup"><span data-stu-id="6f7b1-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="6f7b1-110">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="6f7b1-110">Security Mode</span></span>|<span data-ttu-id="6f7b1-111">Сообщение</span><span class="sxs-lookup"><span data-stu-id="6f7b1-111">Message</span></span>|  
|<span data-ttu-id="6f7b1-112">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="6f7b1-112">Interoperability</span></span>|<span data-ttu-id="6f7b1-113">Только WCF</span><span class="sxs-lookup"><span data-stu-id="6f7b1-113">WCF only</span></span>|  
|<span data-ttu-id="6f7b1-114">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="6f7b1-114">Authentication (Server)</span></span>|<span data-ttu-id="6f7b1-115">Использование сертификатов служб</span><span class="sxs-lookup"><span data-stu-id="6f7b1-115">Using service certificate</span></span>|  
|<span data-ttu-id="6f7b1-116">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="6f7b1-116">Authentication (Client)</span></span>|<span data-ttu-id="6f7b1-117">Использование сертификатов клиента</span><span class="sxs-lookup"><span data-stu-id="6f7b1-117">Using client certificate</span></span>|  
|<span data-ttu-id="6f7b1-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="6f7b1-118">Integrity</span></span>|<span data-ttu-id="6f7b1-119">Да</span><span class="sxs-lookup"><span data-stu-id="6f7b1-119">Yes</span></span>|  
|<span data-ttu-id="6f7b1-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="6f7b1-120">Confidentiality</span></span>|<span data-ttu-id="6f7b1-121">Да</span><span class="sxs-lookup"><span data-stu-id="6f7b1-121">Yes</span></span>|  
|<span data-ttu-id="6f7b1-122">Transport</span><span class="sxs-lookup"><span data-stu-id="6f7b1-122">Transport</span></span>|<span data-ttu-id="6f7b1-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="6f7b1-123">HTTP</span></span>|  
|<span data-ttu-id="6f7b1-124">Привязка</span><span class="sxs-lookup"><span data-stu-id="6f7b1-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="6f7b1-125">Служба</span><span class="sxs-lookup"><span data-stu-id="6f7b1-125">Service</span></span>  
 <span data-ttu-id="6f7b1-126">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6f7b1-127">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6f7b1-128">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="6f7b1-129">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="6f7b1-130">Код</span><span class="sxs-lookup"><span data-stu-id="6f7b1-130">Code</span></span>  
 <span data-ttu-id="6f7b1-131">В следующем коде показано создание конечной точки службы, которая использует безопасность сообщений для установления защищенного контекста.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-131">The following code shows how to create a service endpoint that uses message security to establish a secure context.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#10)]
 [!code-vb[C_SecurityScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#10)]  
  
### <a name="configuration"></a><span data-ttu-id="6f7b1-132">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="6f7b1-132">Configuration</span></span>  
 <span data-ttu-id="6f7b1-133">Вместо кода можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-133">The following configuration can be used instead of the code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"  
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="MessageAndCerficiateClient"   
                  name="SecuredByClientCertificate"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator">  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="6f7b1-134">Клиент</span><span class="sxs-lookup"><span data-stu-id="6f7b1-134">Client</span></span>  
 <span data-ttu-id="6f7b1-135">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-135">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="6f7b1-136">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-136">Do one of the following:</span></span>  
  
-   <span data-ttu-id="6f7b1-137">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-137">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="6f7b1-138">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-138">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="6f7b1-139">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-139">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="6f7b1-140">Например:</span><span class="sxs-lookup"><span data-stu-id="6f7b1-140">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="6f7b1-141">Код</span><span class="sxs-lookup"><span data-stu-id="6f7b1-141">Code</span></span>  
 <span data-ttu-id="6f7b1-142">Следующий код служит для создания клиента.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-142">The following code creates the client.</span></span> <span data-ttu-id="6f7b1-143">Привязка осуществляется к безопасности режима сообщений, и типу учетных данных клиента присваивается значение `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-143">The binding is to message mode security, and the client credential type is set to `Certificate`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#17](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#17)]
 [!code-vb[C_SecurityScenarios#17](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#17)]  
  
### <a name="configuration"></a><span data-ttu-id="6f7b1-144">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="6f7b1-144">Configuration</span></span>  
 <span data-ttu-id="6f7b1-145">В следующей конфигурации задается сертификат клиента с помощью поведения конечной точки.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-145">The following configuration specifies the client certificate using an endpoint behavior.</span></span> <span data-ttu-id="6f7b1-146">Дополнительные сведения см. в разделе [Работа с сертификатами](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-146">For more information about certificates, see [Working with Certificates](../../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span> <span data-ttu-id="6f7b1-147">В коде также используется <`identity`> элемент для указания доменных имен (DNS) из ожидаемой идентификации сервера.</span><span class="sxs-lookup"><span data-stu-id="6f7b1-147">The code also uses an <`identity`> element to specify a Domain Name System (DNS) of the expected server identity.</span></span> <span data-ttu-id="6f7b1-148">Дополнительные сведения об удостоверении см. в разделе [службы идентификации и проверки подлинности](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="6f7b1-148">For more information about identity, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="endpointCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
               storeLocation="LocalMachine"  
              x509FindType="FindBySubjectName" />  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="endpointCredentialsBehavior"  
                binding="wsHttpBinding"  
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="Contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f7b1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="6f7b1-149">See also</span></span>
- [<span data-ttu-id="6f7b1-150">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="6f7b1-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="6f7b1-151">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="6f7b1-151">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="6f7b1-152">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="6f7b1-152">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [<span data-ttu-id="6f7b1-153">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="6f7b1-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
