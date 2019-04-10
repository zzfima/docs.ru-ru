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
ms.openlocfilehash: e3d0143cd68bc94c6ff07e65ca5a3c8971b45f23
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337842"
---
# <a name="how-to-create-a-custom-authorization-manager-for-a-service"></a><span data-ttu-id="34b1f-102">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="34b1f-102">How to: Create a Custom Authorization Manager for a Service</span></span>
<span data-ttu-id="34b1f-103">Инфраструктура модели удостоверения в Windows Communication Foundation (WCF) поддерживает модель расширяемый авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="34b1f-103">The Identity Model infrastructure in Windows Communication Foundation (WCF) supports an extensible claims-based authorization model.</span></span> <span data-ttu-id="34b1f-104">Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-104">Claims are extracted from tokens and optionally processed by custom authorization policies and then placed into an <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="34b1f-105">Диспетчер авторизации проверяет утверждения в контексте <xref:System.IdentityModel.Policy.AuthorizationContext> для принятия решений об авторизации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-105">An authorization manager examines the claims in the <xref:System.IdentityModel.Policy.AuthorizationContext> to make authorization decisions.</span></span>  
  
 <span data-ttu-id="34b1f-106">По умолчанию решения об авторизации принимаются классом <xref:System.ServiceModel.ServiceAuthorizationManager>; однако эти решения можно переопределить, создав пользовательский диспетчер авторизации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-106">By default, authorization decisions are made by the <xref:System.ServiceModel.ServiceAuthorizationManager> class; however these decisions can be overridden by creating a custom authorization manager.</span></span> <span data-ttu-id="34b1f-107">Чтобы создать пользовательский диспетчер авторизации, создайте класс, наследующий от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, и реализуйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-107">To create a custom authorization manager, create a class that derives from <xref:System.ServiceModel.ServiceAuthorizationManager> and implement <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="34b1f-108">Решения об авторизации принимаются в методе <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, который возвращает `true`, если доступ предоставлен, и `false`, если в доступе отказано.</span><span class="sxs-lookup"><span data-stu-id="34b1f-108">Authorization decisions are made in the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method, which returns `true` when access is granted and `false` when access is denied.</span></span>  
  
 <span data-ttu-id="34b1f-109">Если решение об авторизации зависит от содержимого тела сообщения, используйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-109">If the authorization decision depends on the contents of the message body, use the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A> method.</span></span>  
  
 <span data-ttu-id="34b1f-110">В связи с вопросами производительности при возможности следует внести изменения в приложение, чтобы решение об авторизации не требовало доступа к телу сообщения.</span><span class="sxs-lookup"><span data-stu-id="34b1f-110">Because of performance issues, if possible you should redesign your application so that the authorization decision does not require access to the message body.</span></span>  
  
 <span data-ttu-id="34b1f-111">Пользовательский диспетчер авторизации для службы можно зарегистрировать в коде или конфигурации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-111">Registration of the custom authorization manager for a service can be done in code or configuration.</span></span>  
  
### <a name="to-create-a-custom-authorization-manager"></a><span data-ttu-id="34b1f-112">Создание пользовательского диспетчера авторизации</span><span class="sxs-lookup"><span data-stu-id="34b1f-112">To create a custom authorization manager</span></span>  
  
1. <span data-ttu-id="34b1f-113">Создайте класс, производный от класса <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-113">Derive a class from the <xref:System.ServiceModel.ServiceAuthorizationManager> class.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2. <span data-ttu-id="34b1f-114">Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> .</span><span class="sxs-lookup"><span data-stu-id="34b1f-114">Override the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method.</span></span>  
  
     <span data-ttu-id="34b1f-115">Для принятия решения об авторизации используйте метод <xref:System.ServiceModel.OperationContext>, передаваемый в метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-115">Use the <xref:System.ServiceModel.OperationContext> that is passed to the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29> method to make authorization decisions.</span></span>  
  
     <span data-ttu-id="34b1f-116">В следующем примере кода метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> используется для поиска пользовательского утверждения `http://www.contoso.com/claims/allowedoperation` и принятия решения об авторизации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-116">The following code example uses the <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> method to find the custom claim `http://www.contoso.com/claims/allowedoperation` to make an authorization decision.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### <a name="to-register-a-custom-authorization-manager-using-code"></a><span data-ttu-id="34b1f-117">Регистрация пользовательского диспетчера авторизации с помощью кода</span><span class="sxs-lookup"><span data-stu-id="34b1f-117">To register a custom authorization manager using code</span></span>  
  
1. <span data-ttu-id="34b1f-118">Создайте экземпляр пользовательского диспетчера авторизации и назначьте его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-118">Create an instance of the custom authorization manager and assign it to the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A> property.</span></span>  
  
     <span data-ttu-id="34b1f-119">Доступ к поведению <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> возможен с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-119">The <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> can be accessed using <xref:System.ServiceModel.ServiceHostBase.Authorization%2A> property.</span></span>  
  
     <span data-ttu-id="34b1f-120">В следующем примере кода регистрируется пользовательский диспетчер авторизации `MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="34b1f-120">The following code example registers the `MyServiceAuthorizationManager` custom authorization manager.</span></span>  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### <a name="to-register-a-custom-authorization-manager-using-configuration"></a><span data-ttu-id="34b1f-121">Регистрация пользовательского диспетчера авторизации с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="34b1f-121">To register a custom authorization manager using configuration</span></span>  
  
1. <span data-ttu-id="34b1f-122">Откройте файл конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="34b1f-122">Open the configuration file for the service.</span></span>  
  
2. <span data-ttu-id="34b1f-123">Добавить [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span><span class="sxs-lookup"><span data-stu-id="34b1f-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).</span></span>  
  
     <span data-ttu-id="34b1f-124">Чтобы [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), добавьте `serviceAuthorizationManagerType` атрибут и присвойте ему значение типа, представляющего пользовательский диспетчер авторизации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-124">To the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md), add a `serviceAuthorizationManagerType` attribute and set its value to the type that represents the custom authorization manager.</span></span>  
  
3. <span data-ttu-id="34b1f-125">Добавьте привязку, обеспечивающую безопасность связи между клиентом и службой.</span><span class="sxs-lookup"><span data-stu-id="34b1f-125">Add a binding that secures the communication between the client and service.</span></span>  
  
     <span data-ttu-id="34b1f-126">Привязка, выбранная для этой связи, определяет утверждения, добавляемые в контекст <xref:System.IdentityModel.Policy.AuthorizationContext> и используемые пользовательским диспетчером авторизации для принятия решений об авторизации.</span><span class="sxs-lookup"><span data-stu-id="34b1f-126">The binding that is chosen for this communication determines the claims that are added to the <xref:System.IdentityModel.Policy.AuthorizationContext>, which the custom authorization manager uses to make authorization decisions.</span></span> <span data-ttu-id="34b1f-127">Дополнительные сведения о предоставляемых системой привязок см. в разделе [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="34b1f-127">For more details about the system-provided bindings, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
4. <span data-ttu-id="34b1f-128">Свяжите поведение с конечной точкой службы, добавив [ \<службы >](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) элемент и установите для параметра `behaviorConfiguration` значение атрибута имени для атрибута [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="34b1f-128">Associate the behavior to a service endpoint, by adding a [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) element and set the value of the `behaviorConfiguration` attribute to the value of the name attribute for the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>  
  
     <span data-ttu-id="34b1f-129">Дополнительные сведения о настройке конечной точки службы, см. в разделе [как: Создать конечную точку службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="34b1f-129">For more information about configuring a service endpoint, see [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
     <span data-ttu-id="34b1f-130">В следующем примере кода регистрируется пользовательский диспетчер авторизации `Samples.MyServiceAuthorizationManager`.</span><span class="sxs-lookup"><span data-stu-id="34b1f-130">The following code example registers the custom authorization manager `Samples.MyServiceAuthorizationManager`.</span></span>  
  
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
    >  <span data-ttu-id="34b1f-131">Обратите внимание, что при указании serviceAuthorizationManagerType строка должна содержать полное имя типа.</span><span class="sxs-lookup"><span data-stu-id="34b1f-131">Note that when you specify the serviceAuthorizationManagerType, the string must contain the fully qualified type name.</span></span> <span data-ttu-id="34b1f-132">запятая и имя сборки, в которой определен тип.</span><span class="sxs-lookup"><span data-stu-id="34b1f-132">a comma, and the name of the assembly in which the type is defined.</span></span> <span data-ttu-id="34b1f-133">Если опустить имя сборки, WCF попытается загрузить тип из System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="34b1f-133">If you leave out the assembly name, WCF will attempt to load the type from System.ServiceModel.dll.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34b1f-134">Пример</span><span class="sxs-lookup"><span data-stu-id="34b1f-134">Example</span></span>  
 <span data-ttu-id="34b1f-135">В следующем образце кода показана базовая реализация класса <xref:System.ServiceModel.ServiceAuthorizationManager>, которая содержит переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-135">The following code example demonstrates a basic implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class that includes overriding the <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> method.</span></span> <span data-ttu-id="34b1f-136">В этом примере кода производится проверка <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие пользовательского утверждения и возвращается `true`, если ресурс для этого пользовательского утверждения соответствует значению действия из контекста <xref:System.ServiceModel.OperationContext>.</span><span class="sxs-lookup"><span data-stu-id="34b1f-136">The example code examines the <xref:System.IdentityModel.Policy.AuthorizationContext> for a custom claim and returns `true` when the resource for that custom claim matches the action value from the <xref:System.ServiceModel.OperationContext>.</span></span> <span data-ttu-id="34b1f-137">Для более полная реализация <xref:System.ServiceModel.ServiceAuthorizationManager> , представлена в разделе [политики авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="34b1f-137">For a more complete implementation of a <xref:System.ServiceModel.ServiceAuthorizationManager> class, see [Authorization Policy](../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="34b1f-138">См. также</span><span class="sxs-lookup"><span data-stu-id="34b1f-138">See also</span></span>

- <xref:System.ServiceModel.ServiceAuthorizationManager>
- [<span data-ttu-id="34b1f-139">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="34b1f-139">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)
