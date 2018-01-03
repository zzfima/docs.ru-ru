---
title: "Элемент &lt;serviceAuthorization&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18cddad5-ddcb-4839-a0ac-1d6f6ab783ca
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9572cea14b7c15893459133aa75e9fa62b10d4f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceauthorizationgt-element"></a><span data-ttu-id="2340d-102">Элемент &lt;serviceAuthorization&gt;</span><span class="sxs-lookup"><span data-stu-id="2340d-102">&lt;serviceAuthorization&gt; element</span></span>
<span data-ttu-id="2340d-103">Задает параметры авторизации доступа к операциям службы.</span><span class="sxs-lookup"><span data-stu-id="2340d-103">Specifies settings that authorize access to service operations</span></span>  
  
 <span data-ttu-id="2340d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="2340d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2340d-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="2340d-105">\<behaviors></span></span>  
<span data-ttu-id="2340d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="2340d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="2340d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2340d-107">\<behavior></span></span>  
<span data-ttu-id="2340d-108">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="2340d-108">\<serviceAuthorization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2340d-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2340d-109">Syntax</span></span>  
  
```xml  
<serviceAuthorization  
     impersonateCallerForAllOperations="Boolean"  
      principalPermissionMode="None/UseWindowsGroups/UseAspNetRoles/Custom"  
      roleProviderName="String"  
      serviceAuthorizationManagerType="String" />  
      <authorizationPolicies>  
         <add policyType="String" />  
      </authorizationPolicies>  
</serviceAuthorization>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2340d-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2340d-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2340d-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2340d-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2340d-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2340d-112">Attributes</span></span>  
  
|<span data-ttu-id="2340d-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2340d-113">Attribute</span></span>|<span data-ttu-id="2340d-114">Описание</span><span class="sxs-lookup"><span data-stu-id="2340d-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2340d-115">impersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="2340d-115">impersonateCallerForAllOperations</span></span>|<span data-ttu-id="2340d-116">Логическое значение, которое определяет, должны ли все операции службы олицетворять вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="2340d-116">A Boolean value that specifies if all the operations in the service impersonate the caller.</span></span> <span data-ttu-id="2340d-117">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="2340d-117">The default is `false`.</span></span><br /><br /> <span data-ttu-id="2340d-118">Если конкретная операция службы олицетворяет вызывающий объект, контекст потока переключается на контекст вызывающего объекта перед выполнением указанной службы.</span><span class="sxs-lookup"><span data-stu-id="2340d-118">When a specific service operation impersonates the caller, the thread context is switched to the caller context before executing the specified service.</span></span>|  
|<span data-ttu-id="2340d-119">principalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="2340d-119">principalPermissionMode</span></span>|<span data-ttu-id="2340d-120">Определяет участников, используемых для выполнения операций на сервере.</span><span class="sxs-lookup"><span data-stu-id="2340d-120">Sets the principal used to carry out operations on the server.</span></span> <span data-ttu-id="2340d-121">В эти значения входят:</span><span class="sxs-lookup"><span data-stu-id="2340d-121">Values include the following:</span></span><br /><br /> <span data-ttu-id="2340d-122">— None</span><span class="sxs-lookup"><span data-stu-id="2340d-122">-   None</span></span><br /><span data-ttu-id="2340d-123">-«Usewindowsgroups»</span><span class="sxs-lookup"><span data-stu-id="2340d-123">-   UseWindowsGroups</span></span><br /><span data-ttu-id="2340d-124">-UseAspNetRoles</span><span class="sxs-lookup"><span data-stu-id="2340d-124">-   UseAspNetRoles</span></span><br /><span data-ttu-id="2340d-125">-Custom</span><span class="sxs-lookup"><span data-stu-id="2340d-125">-   Custom</span></span><br /><br /> <span data-ttu-id="2340d-126">Значение по умолчанию - «UseWindowsGroups».</span><span class="sxs-lookup"><span data-stu-id="2340d-126">The default value is UseWindowsGroups.</span></span> <span data-ttu-id="2340d-127">Это значение типа <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span><span class="sxs-lookup"><span data-stu-id="2340d-127">The value is of type <xref:System.ServiceModel.Description.PrincipalPermissionMode>.</span></span> <span data-ttu-id="2340d-128">Дополнительные сведения об использовании этого атрибута см. в разделе [как: ограничение доступа с использованием класса PrincipalPermissionAttribute](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span><span class="sxs-lookup"><span data-stu-id="2340d-128">For more information on using this attribute, see [How to: Restrict Access with the PrincipalPermissionAttribute Class](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md).</span></span>|  
|<span data-ttu-id="2340d-129">roleProviderName</span><span class="sxs-lookup"><span data-stu-id="2340d-129">roleProviderName</span></span>|<span data-ttu-id="2340d-130">Строка, указывающая имя поставщика роли, который предоставляет сведения о роли для приложения Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="2340d-130">A string that specifies the name of the role provider, which provides role information for a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="2340d-131">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="2340d-131">The default is an empty string.</span></span>|  
|<span data-ttu-id="2340d-132">ServiceAuthorizationManagerType</span><span class="sxs-lookup"><span data-stu-id="2340d-132">ServiceAuthorizationManagerType</span></span>|<span data-ttu-id="2340d-133">Строка, содержащая имя типа диспетчера авторизации служб.</span><span class="sxs-lookup"><span data-stu-id="2340d-133">A string containing the type of the service authorization manager.</span></span> <span data-ttu-id="2340d-134">Дополнительные сведения см. в разделе <xref:System.ServiceModel.ServiceAuthorizationManager>.</span><span class="sxs-lookup"><span data-stu-id="2340d-134">For more information, see <xref:System.ServiceModel.ServiceAuthorizationManager>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2340d-135">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2340d-135">Child Elements</span></span>  
  
|<span data-ttu-id="2340d-136">Элемент</span><span class="sxs-lookup"><span data-stu-id="2340d-136">Element</span></span>|<span data-ttu-id="2340d-137">Описание</span><span class="sxs-lookup"><span data-stu-id="2340d-137">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2340d-138">authorizationPolicies</span><span class="sxs-lookup"><span data-stu-id="2340d-138">authorizationPolicies</span></span>|<span data-ttu-id="2340d-139">Содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова`add`.</span><span class="sxs-lookup"><span data-stu-id="2340d-139">Contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="2340d-140">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="2340d-140">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="2340d-141">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="2340d-141">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2340d-142">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="2340d-142">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="2340d-143">Дополнительные сведения см. в разделе <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="2340d-143">For more information, see <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2340d-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2340d-144">Parent Elements</span></span>  
  
|<span data-ttu-id="2340d-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="2340d-145">Element</span></span>|<span data-ttu-id="2340d-146">Описание:</span><span class="sxs-lookup"><span data-stu-id="2340d-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2340d-147">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="2340d-147">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="2340d-148">Содержит коллекцию параметров для поведения службы.</span><span class="sxs-lookup"><span data-stu-id="2340d-148">Contains a collection of settings for the behavior of a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2340d-149">Примечания</span><span class="sxs-lookup"><span data-stu-id="2340d-149">Remarks</span></span>  
 <span data-ttu-id="2340d-150">Этот раздел содержит элементы, влияющие на авторизацию, поставщики пользовательских ролей и олицетворение.</span><span class="sxs-lookup"><span data-stu-id="2340d-150">This section contains elements affecting authorization, custom role providers, and impersonation.</span></span>  
  
 <span data-ttu-id="2340d-151">Атрибут `principalPermissionMode` указывает группы пользователей, которые следует использовать при авторизации использования защищенного метода.</span><span class="sxs-lookup"><span data-stu-id="2340d-151">The `principalPermissionMode` attribute specifies the groups of users to use when authorizing use of a protected method.</span></span> <span data-ttu-id="2340d-152">Значение по умолчанию - `UseWindowsGroups`. Оно указывает, что при попытке доступа к ресурсу поиск удостоверения выполняется в таких группах Windows, как «Администраторы» или «Пользователи».</span><span class="sxs-lookup"><span data-stu-id="2340d-152">The default value is `UseWindowsGroups` and specifies that Windows groups, such as "Administrators" or "Users," are searched for an identity trying to access a resource.</span></span> <span data-ttu-id="2340d-153">Можно также указать `UseAspNetRoles` для использования поставщика пользовательской роли, который настроен в \<system.web > элемента, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="2340d-153">You can also specify `UseAspNetRoles` to use a custom role provider that is configured under the \<system.web> element, as shown in the following code.</span></span>  
  
```xml  
<system.web>  
  <membership defaultProvider="SqlProvider"   
   userIsOnlineTimeWindow="15">  
     <providers>  
       <clear />  
       <add   
          name="SqlProvider"   
          type="System.Web.Security.SqlMembershipProvider"   
          connectionStringName="SqlConn"  
          applicationName="MembershipProvider"  
          enablePasswordRetrieval="false"  
          enablePasswordReset="false"  
          requiresQuestionAndAnswer="false"  
          requiresUniqueEmail="true"  
          passwordFormat="Hashed" />  
     </providers>  
   </membership>  
  <!-- Other configuration code not shown.-->  
</system.web>  
```  
  
 <span data-ttu-id="2340d-154">В следующем примере показано использование элемента `roleProviderName` с атрибутом `principalPermissionMode`.</span><span class="sxs-lookup"><span data-stu-id="2340d-154">The following code shows the `roleProviderName` used with the `principalPermissionMode` attribute.</span></span>  
  
```xml  
<behaviors>  
   <behavior name="ServiceBehaviour">  
     <serviceAuthorization principalPermissionMode ="UseAspNetRoles"   
                           roleProviderName ="SqlProvider" />  
   </behavior>   
<!-- Other configuration code not shown. -->  
</behaviors>  
```  
  
 <span data-ttu-id="2340d-155">Подробный пример использования этого элемента конфигурации см. в разделе [авторизации доступа к операциям службы](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) и [политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2340d-155">For a detailed example of using this configuration element, see [Authorizing Access to Service Operations](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md) and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2340d-156">См. также</span><span class="sxs-lookup"><span data-stu-id="2340d-156">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 [<span data-ttu-id="2340d-157">Поведения безопасности</span><span class="sxs-lookup"><span data-stu-id="2340d-157">Security Behaviors</span></span>](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [<span data-ttu-id="2340d-158">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="2340d-158">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="2340d-159">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="2340d-159">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="2340d-160">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="2340d-160">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 [<span data-ttu-id="2340d-161">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="2340d-161">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
