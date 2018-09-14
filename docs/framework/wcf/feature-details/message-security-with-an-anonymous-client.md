---
title: Безопасность сообщений с анонимным клиентом
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: d3e8269fc05caf70f4329ce8f13a3633a8982c0b
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "45520856"
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="bcf14-102">Безопасность сообщений с анонимным клиентом</span><span class="sxs-lookup"><span data-stu-id="bcf14-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="bcf14-103">В следующем сценарии показаны клиент и служба, защищенные механизмом безопасности сообщений Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bcf14-103">The following scenario shows a client and service secured by Windows Communication Foundation (WCF) message security.</span></span> <span data-ttu-id="bcf14-104">Задача, поставленная при разработке, заключается в использовании безопасности сообщений, а не безопасности транспорта, чтобы в будущем возможно было использование более глубокой модели, использующей утверждения.</span><span class="sxs-lookup"><span data-stu-id="bcf14-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> <span data-ttu-id="bcf14-105">Дополнительные сведения об использовании сложные утверждения для авторизации см. в разделе [управление утверждениями и авторизацией с моделью идентификации](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span><span class="sxs-lookup"><span data-stu-id="bcf14-105">For more information about using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="bcf14-106">Образец приложения, см. в разделе [сообщения безопасности Анонимный](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span><span class="sxs-lookup"><span data-stu-id="bcf14-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="bcf14-107">![Безопасность с анонимным клиентом сообщений](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="bcf14-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="bcf14-108">Характеристика</span><span class="sxs-lookup"><span data-stu-id="bcf14-108">Characteristic</span></span>|<span data-ttu-id="bcf14-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bcf14-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bcf14-110">Режим безопасности</span><span class="sxs-lookup"><span data-stu-id="bcf14-110">Security Mode</span></span>|<span data-ttu-id="bcf14-111">Сообщение</span><span class="sxs-lookup"><span data-stu-id="bcf14-111">Message</span></span>|  
|<span data-ttu-id="bcf14-112">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="bcf14-112">Interoperability</span></span>|<span data-ttu-id="bcf14-113">Только WCF</span><span class="sxs-lookup"><span data-stu-id="bcf14-113">WCF only</span></span>|  
|<span data-ttu-id="bcf14-114">Проверка подлинности (сервера)</span><span class="sxs-lookup"><span data-stu-id="bcf14-114">Authentication (Server)</span></span>|<span data-ttu-id="bcf14-115">Первоначальное согласование возможно только после проверки подлинности сервера, но не клиента</span><span class="sxs-lookup"><span data-stu-id="bcf14-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="bcf14-116">Проверка подлинности (клиента)</span><span class="sxs-lookup"><span data-stu-id="bcf14-116">Authentication (Client)</span></span>|<span data-ttu-id="bcf14-117">Нет</span><span class="sxs-lookup"><span data-stu-id="bcf14-117">None</span></span>|  
|<span data-ttu-id="bcf14-118">Целостность</span><span class="sxs-lookup"><span data-stu-id="bcf14-118">Integrity</span></span>|<span data-ttu-id="bcf14-119">Да, используется общий контекст безопасности</span><span class="sxs-lookup"><span data-stu-id="bcf14-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="bcf14-120">Конфиденциальность</span><span class="sxs-lookup"><span data-stu-id="bcf14-120">Confidentiality</span></span>|<span data-ttu-id="bcf14-121">Да, используется общий контекст безопасности</span><span class="sxs-lookup"><span data-stu-id="bcf14-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="bcf14-122">Transport</span><span class="sxs-lookup"><span data-stu-id="bcf14-122">Transport</span></span>|<span data-ttu-id="bcf14-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="bcf14-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="bcf14-124">Служба</span><span class="sxs-lookup"><span data-stu-id="bcf14-124">Service</span></span>  
 <span data-ttu-id="bcf14-125">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="bcf14-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="bcf14-126">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="bcf14-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="bcf14-127">Создайте автономную службу, используя код без конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcf14-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="bcf14-128">Создайте службу, используя предоставленную конфигурацию, но не определяйте конечные точки.</span><span class="sxs-lookup"><span data-stu-id="bcf14-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bcf14-129">Код</span><span class="sxs-lookup"><span data-stu-id="bcf14-129">Code</span></span>  
 <span data-ttu-id="bcf14-130">В следующем коде показано, как создать конечную точку службы, которая использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="bcf14-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="bcf14-131">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="bcf14-131">Configuration</span></span>  
 <span data-ttu-id="bcf14-132">Вместо кода можно использовать следующую конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="bcf14-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="bcf14-133">Элемент поведения службы используется для указания сертификата, который используется для проверки подлинности службы для клиента.</span><span class="sxs-lookup"><span data-stu-id="bcf14-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="bcf14-134">Элемент службы должен задавать поведение с помощью атрибута `behaviorConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="bcf14-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="bcf14-135">Элемент привязки указывает, что типу учетных данных клиента присвоено значение `None`, позволяя анонимному клиенту использовать службу.</span><span class="sxs-lookup"><span data-stu-id="bcf14-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="bcf14-136">Клиент</span><span class="sxs-lookup"><span data-stu-id="bcf14-136">Client</span></span>  
 <span data-ttu-id="bcf14-137">Предполагается, что представленные ниже код и конфигурация выполняются независимо.</span><span class="sxs-lookup"><span data-stu-id="bcf14-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="bcf14-138">Выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="bcf14-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="bcf14-139">Создайте автономный клиент, используя код (и код клиента).</span><span class="sxs-lookup"><span data-stu-id="bcf14-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="bcf14-140">Создайте клиент, который не определяет никаких адресов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="bcf14-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="bcf14-141">Вместо этого используйте конструктор клиента, который принимает в качестве аргумента имя конфигурации.</span><span class="sxs-lookup"><span data-stu-id="bcf14-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="bcf14-142">Например:</span><span class="sxs-lookup"><span data-stu-id="bcf14-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="bcf14-143">Код</span><span class="sxs-lookup"><span data-stu-id="bcf14-143">Code</span></span>  
 <span data-ttu-id="bcf14-144">В следующем примере кода создается экземпляр клиента.</span><span class="sxs-lookup"><span data-stu-id="bcf14-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="bcf14-145">Привязка использует безопасность режима сообщений, и тип учетных данных клиента задан как None.</span><span class="sxs-lookup"><span data-stu-id="bcf14-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="bcf14-146">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="bcf14-146">Configuration</span></span>  
 <span data-ttu-id="bcf14-147">Следующий код служит для настройки клиента.</span><span class="sxs-lookup"><span data-stu-id="bcf14-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bcf14-148">См. также</span><span class="sxs-lookup"><span data-stu-id="bcf14-148">See Also</span></span>  
 [<span data-ttu-id="bcf14-149">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="bcf14-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="bcf14-150">Защита распределенных приложений</span><span class="sxs-lookup"><span data-stu-id="bcf14-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="bcf14-151">Безопасность сообщений с возможностью анонимного доступа</span><span class="sxs-lookup"><span data-stu-id="bcf14-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="bcf14-152">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="bcf14-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="bcf14-153">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="bcf14-153">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
