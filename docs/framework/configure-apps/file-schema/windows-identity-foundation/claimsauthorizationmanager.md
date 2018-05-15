---
title: '&lt;claimsAuthorizationManager&gt;'
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 06824e20286f8905ad3a8ac9d2b4a30366a6ec10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltclaimsauthorizationmanagergt"></a><span data-ttu-id="9cb35-102">&lt;claimsAuthorizationManager&gt;</span><span class="sxs-lookup"><span data-stu-id="9cb35-102">&lt;claimsAuthorizationManager&gt;</span></span>
<span data-ttu-id="9cb35-103">Регистрирует диспетчера авторизации утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="9cb35-103">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="9cb35-104">\<system.identityModel ></span><span class="sxs-lookup"><span data-stu-id="9cb35-104">\<system.identityModel></span></span>  
<span data-ttu-id="9cb35-105">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9cb35-105">\<identityConfiguration></span></span>  
<span data-ttu-id="9cb35-106">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="9cb35-106">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cb35-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9cb35-107">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9cb35-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9cb35-108">Attributes and Elements</span></span>  
 <span data-ttu-id="9cb35-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9cb35-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9cb35-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9cb35-110">Attributes</span></span>  
  
|<span data-ttu-id="9cb35-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9cb35-111">Attribute</span></span>|<span data-ttu-id="9cb35-112">Описание</span><span class="sxs-lookup"><span data-stu-id="9cb35-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9cb35-113">type</span><span class="sxs-lookup"><span data-stu-id="9cb35-113">type</span></span>|<span data-ttu-id="9cb35-114">Пользовательский тип, который является производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="9cb35-114">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="9cb35-115">Дополнительные сведения о способах указания `type` см. в разделе [ссылок на пользовательские типы](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="9cb35-115">For more information about how to specify the `type` attribute, see [Custom Type References](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9cb35-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9cb35-116">Child Elements</span></span>  
 <span data-ttu-id="9cb35-117">При наличии не `type` атрибут, или если `type` ссылки на атрибуты <xref:System.Security.Claims.ClaimsAuthenticationManager> класса `<claimsAuthorizationManager>` элемент не принимает дочерних элементов; Однако классы, производные от <xref:System.Security.Claims.ClaimsAuthorizationManager> можно определить дочерние элементы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9cb35-117">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9cb35-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9cb35-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9cb35-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9cb35-119">Element</span></span>|<span data-ttu-id="9cb35-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9cb35-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9cb35-121">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="9cb35-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="9cb35-122">Указывает параметры уровня службы удостоверений.</span><span class="sxs-lookup"><span data-stu-id="9cb35-122">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cb35-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="9cb35-123">Remarks</span></span>  
 <span data-ttu-id="9cb35-124">Поведение по умолчанию, предоставленные с помощью <xref:System.Security.Claims.ClaimsAuthorizationManager> класса всегда разрешает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="9cb35-124">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="9cb35-125">Если не `type` указан атрибут или если `type` атрибут задает <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, `<claimsAuthorizationManager>` элемент не принимает дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="9cb35-125">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="9cb35-126">Можно указать `type` атрибут, чтобы зарегистрировать тип производным от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса, чтобы реализовать пользовательское поведение.</span><span class="sxs-lookup"><span data-stu-id="9cb35-126">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="9cb35-127">Производные классы могут поддерживать конфигурацию с помощью дочерних элементов `<claimsAuthorizationManager>` элемент путем переопределения <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> метод для обработки этих элементов.</span><span class="sxs-lookup"><span data-stu-id="9cb35-127">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="9cb35-128">Схемы, определенных для дочерних элементов зависит от конструктора класса.</span><span class="sxs-lookup"><span data-stu-id="9cb35-128">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9cb35-129">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> или <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса для обеспечения контроля доступа на основе утверждений в коде, на который ссылается конфигурация удостоверений `<federationConfiguration>` элемент настраивает диспетчера авторизации утверждений и политики, которая используется, чтобы сделать решения об авторизации.</span><span class="sxs-lookup"><span data-stu-id="9cb35-129">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="9cb35-130">Это верно даже в случаях, не пассивный сценариях веб-, например приложений Windows Communication Foundation (WCF) или приложение, которое не является веб сервера.</span><span class="sxs-lookup"><span data-stu-id="9cb35-130">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="9cb35-131">Если приложение не пассивное веб-приложение `<claimsAuthorizationManager>` элемент (и политики его дочерние элементы, если он имеется) указанное удостоверение конфигурации являются только параметры, применяемые.</span><span class="sxs-lookup"><span data-stu-id="9cb35-131">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="9cb35-132">Все остальные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="9cb35-132">All other settings are ignored.</span></span> <span data-ttu-id="9cb35-133">Дополнительные сведения см. в разделе [ \<federationConfiguration >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="9cb35-133">For more information, see the [\<federationConfiguration>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="9cb35-134">Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="9cb35-134">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cb35-135">Пример</span><span class="sxs-lookup"><span data-stu-id="9cb35-135">Example</span></span>  
 <span data-ttu-id="9cb35-136">Следующий код XML показывает конфигурацию для авторизации утверждений диспетчер, который реализует политики состоит из пары действие ресурса, каждый из которых определяет логическое сочетания утверждения, запрашивающая сторона должна иметь для выполнения действия с ресурсом.</span><span class="sxs-lookup"><span data-stu-id="9cb35-136">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="9cb35-137">Код, который реализует диспетчера авторизации утверждений, может использовать эту политику можно найти в `ClaimsBasedAuthorization` образца.</span><span class="sxs-lookup"><span data-stu-id="9cb35-137">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
