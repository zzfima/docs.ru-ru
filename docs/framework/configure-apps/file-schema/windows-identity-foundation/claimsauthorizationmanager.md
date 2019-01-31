---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 59d47eda97e97629408ece12a1d1dfbe804feb3e
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55268107"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="eec5c-101">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="eec5c-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="eec5c-102">Регистрирует диспетчера авторизации утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="eec5c-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="eec5c-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="eec5c-103">\<system.identityModel></span></span>  
<span data-ttu-id="eec5c-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="eec5c-104">\<identityConfiguration></span></span>  
<span data-ttu-id="eec5c-105">\<claimsAuthorizationManager></span><span class="sxs-lookup"><span data-stu-id="eec5c-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec5c-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eec5c-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eec5c-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="eec5c-107">Attributes and Elements</span></span>  
 <span data-ttu-id="eec5c-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="eec5c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eec5c-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="eec5c-109">Attributes</span></span>  
  
|<span data-ttu-id="eec5c-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="eec5c-110">Attribute</span></span>|<span data-ttu-id="eec5c-111">Описание</span><span class="sxs-lookup"><span data-stu-id="eec5c-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eec5c-112">type</span><span class="sxs-lookup"><span data-stu-id="eec5c-112">type</span></span>|<span data-ttu-id="eec5c-113">Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="eec5c-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="eec5c-114">Дополнительные сведения о способах указания `type` атрибут, см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="eec5c-114">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eec5c-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="eec5c-115">Child Elements</span></span>  
 <span data-ttu-id="eec5c-116">Если не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класс, `<claimsAuthorizationManager>` элемент выполняет только дочерние элементы; тем не менее, классы, производные от <xref:System.Security.Claims.ClaimsAuthorizationManager> можно определить дочерние элементы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eec5c-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eec5c-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="eec5c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="eec5c-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="eec5c-118">Element</span></span>|<span data-ttu-id="eec5c-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="eec5c-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eec5c-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="eec5c-120">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="eec5c-121">Указывает параметры уровня службы идентификации.</span><span class="sxs-lookup"><span data-stu-id="eec5c-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eec5c-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="eec5c-122">Remarks</span></span>  
 <span data-ttu-id="eec5c-123">Поведение по умолчанию, предоставляемых <xref:System.Security.Claims.ClaimsAuthorizationManager> класса всегда разрешает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="eec5c-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="eec5c-124">Если не `type` атрибут указан или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthorizationManager> класс, `<claimsAuthorizationManager>` элемент выполняет только дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="eec5c-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="eec5c-125">Можно указать `type` атрибут для регистрации типа производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, чтобы реализовать пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="eec5c-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="eec5c-126">Производные классы могут поддерживает настройку с помощью дочерних элементов `<claimsAuthorizationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов.</span><span class="sxs-lookup"><span data-stu-id="eec5c-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="eec5c-127">В схеме, определенной для дочерних элементов зависит от конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="eec5c-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eec5c-128">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса, чтобы обеспечить управление доступом на основе утверждений в коде, конфигурация удостоверения, на который ссылается `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политику, которая используется для выполнения решения об авторизации.</span><span class="sxs-lookup"><span data-stu-id="eec5c-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="eec5c-129">Это справедливо, даже в сценариях, которые не являются пассивных сценариях Web, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб.</span><span class="sxs-lookup"><span data-stu-id="eec5c-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="eec5c-130">Если приложение не пассивное веб-приложение, `<claimsAuthorizationManager>` элемента (и политики его дочерние элементы, если он имеется) являются только параметры, применяемые на конфигурацию удостоверения, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="eec5c-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="eec5c-131">Все остальные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="eec5c-131">All other settings are ignored.</span></span> <span data-ttu-id="eec5c-132">Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="eec5c-132">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="eec5c-133">Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="eec5c-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eec5c-134">Пример</span><span class="sxs-lookup"><span data-stu-id="eec5c-134">Example</span></span>  
 <span data-ttu-id="eec5c-135">Следующий код XML показывает конфигурацию для авторизации утверждений диспетчер, который реализует политику, состоящий из пар ресурс действие, каждый из которых указывает логическое комбинации утверждения, запрашивающая сторона должна иметь для выполнения действия в ресурсе.</span><span class="sxs-lookup"><span data-stu-id="eec5c-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="eec5c-136">Код, который реализует диспетчера авторизации утверждений, может использовать эту политику можно найти в `ClaimsBasedAuthorization` образца.</span><span class="sxs-lookup"><span data-stu-id="eec5c-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
```xml  
<system.identityModel>  
    <identityConfiguration>  
      <claimsAuthorizationManager type="ClaimsAuthorizationLibrary.MyClaimsAuthorizationManager, ClaimsAuthorizationLibrary">  
        <policy resource="http://localhost:28491/Developers.aspx" action="GET">  
          <or>  
            <claim claimType="http://schemas.microsoft.com/ws/2008/06/identity/claims/role" claimValue="developer" />  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
          </or>  
        </policy>  
        <policy resource="http://localhost:28491/Administrators.aspx" action="GET">  
          <and>  
            <claim claimType="http://schemas.xmlsoap.org/claims/Group" claimValue="Administrator" />  
            <claim claimType="http://schemas.xmlsoap.org/ws/2005/05/identity/claims/country" claimValue="USA" />  
          </and>  
        </policy>  
        <policy resource="http://localhost:28491/Default.aspx" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/" action="GET">  
        </policy>  
        <policy resource="http://localhost:28491/Claims.aspx" action="GET">  
        </policy>  
      </claimsAuthorizationManager>  
    <identityConfiguration>  
<system.identityModel>  
```
