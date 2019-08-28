---
title: Практическое руководство. Создание пользовательского диспетчера авторизации для службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Communication Foundation, extending
- OperationRequirement class
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
ms.openlocfilehash: ffdfe41db05eb5f2dd55a233f8ed646401777d0f
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040299"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="3b1a5-102">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="3b1a5-102">How to: Create a Custom Authorization Manager for a Service</span></span>

<span data-ttu-id="3b1a5-103">Инфраструктура модели удостоверений в Windows Communication Foundation (WCF) поддерживает расширяемую модель авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="3b1a5-104">Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="3b1a5-105">Диспетчер авторизации проверяет утверждения в контексте <xref:System.IdentityModel.Policy.AuthorizationContext> для принятия решений об авторизации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>

<span data-ttu-id="3b1a5-106">По умолчанию решения об авторизации принимаются классом <xref:System.ServiceModel.ServiceAuthorizationManager>; однако эти решения можно переопределить, создав пользовательский диспетчер авторизации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="3b1a5-107">Чтобы создать пользовательский диспетчер авторизации, создайте класс, наследующий от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, и реализуйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="3b1a5-108">Решения об авторизации принимаются в методе <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, который возвращает `true`, если доступ предоставлен, и `false`, если в доступе отказано.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>

<span data-ttu-id="3b1a5-109">Если решение об авторизации зависит от содержимого тела сообщения, используйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>

<span data-ttu-id="3b1a5-110">В связи с вопросами производительности при возможности следует внести изменения в приложение, чтобы решение об авторизации не требовало доступа к телу сообщения.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>

<span data-ttu-id="3b1a5-111">Пользовательский диспетчер авторизации для службы можно зарегистрировать в коде или конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>

### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="3b1a5-112">Создание пользовательского диспетчера авторизации</span><span class="sxs-lookup"><span data-stu-id="3b1a5-112">To create a custom authorization manager</span></span>

1. <span data-ttu-id="3b1a5-113">Создайте класс, производный от класса <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>

    [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
    [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]

2. <span data-ttu-id="3b1a5-114">Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .</span><span class="sxs-lookup"><span data-stu-id="3b1a5-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>

    <span data-ttu-id="3b1a5-115">Для принятия решения об авторизации используйте метод <xref:System.ServiceModel.OperationContext>, передаваемый в метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>

    <span data-ttu-id="3b1a5-116">В следующем примере кода метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> используется для поиска пользовательского утверждения `http://www.contoso.com/claims/allowedoperation` и принятия решения об авторизации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>

    [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
    [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]

### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="3b1a5-117">Регистрация пользовательского диспетчера авторизации с помощью кода</span><span class="sxs-lookup"><span data-stu-id="3b1a5-117">To register a custom authorization manager using code</span></span>

1. <span data-ttu-id="3b1a5-118">Создайте экземпляр пользовательского диспетчера авторизации и назначьте его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>

    <span data-ttu-id="3b1a5-119">Доступ к поведению <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> возможен с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>

    <span data-ttu-id="3b1a5-120">В следующем примере кода регистрируется пользовательский диспетчер авторизации `MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>

    [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
    [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]

### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="3b1a5-121">Регистрация пользовательского диспетчера авторизации с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="3b1a5-121">To register a custom authorization manager using configuration</span></span>

1. <span data-ttu-id="3b1a5-122">Откройте файл конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-122">Open the configuration file for the service.</span></span>

2. <span data-ttu-id="3b1a5-123">Добавьте [> ServiceAuthorization в > поведения. \<](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="3b1a5-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>

    <span data-ttu-id="3b1a5-124">В > `serviceAuthorizationManagerType` ServiceAuthorization добавьте атрибут и присвойте ему значение типа, представляющего пользовательский диспетчер авторизации. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="3b1a5-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>

3. <span data-ttu-id="3b1a5-125">Добавьте привязку, обеспечивающую безопасность связи между клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-125">Add a binding that secures the communication between the client and service.</span></span>

    <span data-ttu-id="3b1a5-126">Привязка, выбранная для этой связи, определяет утверждения, добавляемые в контекст <xref:System.IdentityModel.Policy.AuthorizationContext> и используемые пользовательским диспетчером авторизации для принятия решений об авторизации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="3b1a5-127">Дополнительные сведения о привязках, предоставляемых системой, см. в разделе [привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="3b1a5-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>

4. <span data-ttu-id="3b1a5-128">Свяжите поведение с конечной точкой службы, добавив `behaviorConfiguration` [ \<элемент > службы](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) и задав для атрибута значение атрибута Name для [ \<элемента > поведения](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="3b1a5-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    <span data-ttu-id="3b1a5-129">Дополнительные сведения о настройке конечной точки службы см. в [разделе как Создайте конечную точку службы в](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>

    <span data-ttu-id="3b1a5-130">В следующем примере кода регистрируется пользовательский диспетчер авторизации `Samples.MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>

    ```xml
    <configuration>
      <system.serviceModel>
        <services>
          <service
              name="Microsoft.ServiceModel.Samples.CalculatorService"
              behaviorConfiguration="CalculatorServiceBehavior">
            <host>
              <baseAddresses>
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
              </baseAddresses>
            </host>
            <endpoint address=""
                      binding="wsHttpBinding_Calculator"
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />
          </service>
        </services>
        <bindings>
          <WSHttpBinding>
           <binding name = "wsHttpBinding_Calculator">
             <security mode="Message">
               <message clientCredentialType="Windows"/>
             </security>
            </binding>
          </WSHttpBinding>
        </bindings>
        <behaviors>
          <serviceBehaviors>
            <behavior name="CalculatorServiceBehavior">
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />
             </behavior>
         </serviceBehaviors>
       </behaviors>
      </system.serviceModel>
    </configuration>
    ```

    > [!WARNING]
    > <span data-ttu-id="3b1a5-131">Обратите внимание, что при указании serviceAuthorizationManagerType строка должна содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="3b1a5-132">запятая и имя сборки, в которой определен тип.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="3b1a5-133">Если опустить имя сборки, WCF попытается загрузить тип из System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>

## <a name="example"></a><span data-ttu-id="3b1a5-134">Пример</span><span class="sxs-lookup"><span data-stu-id="3b1a5-134">Example</span></span>

<span data-ttu-id="3b1a5-135">В следующем образце кода показана базовая реализация класса <xref:System.ServiceModel.ServiceAuthorizationManager>, которая содержит переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="3b1a5-136">В этом примере кода производится проверка <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие пользовательского утверждения и возвращается `true`, если ресурс для этого пользовательского утверждения соответствует значению действия из контекста <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="3b1a5-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="3b1a5-137">Более полную реализацию <xref:System.ServiceModel.ServiceAuthorizationManager> класса см. в разделе [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="3b1a5-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>

[!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
[!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]

## <a name="see-also"></a><span data-ttu-id="3b1a5-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3b1a5-138">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="3b1a5-139">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="3b1a5-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
