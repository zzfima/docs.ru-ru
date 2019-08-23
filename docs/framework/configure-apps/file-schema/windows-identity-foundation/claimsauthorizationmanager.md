---
title: <claimsAuthorizationManager>
ms.date: 03/30/2017
ms.assetid: 9354eee3-f692-4ad6-8427-3169686b8bcc
author: BrucePerlerMS
ms.openlocfilehash: 74ca031f7017d51adaa7a71593f537b64abbeae6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942891"
---
# <a name="claimsauthorizationmanager"></a><span data-ttu-id="d0e2f-101">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="d0e2f-101">\<claimsAuthorizationManager></span></span>
<span data-ttu-id="d0e2f-102">Регистрирует диспетчер авторизации утверждений для входящих утверждений.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-102">Registers a claims authorization manager for the incoming claims.</span></span>  
  
 <span data-ttu-id="d0e2f-103">\<> System. identityModel</span><span class="sxs-lookup"><span data-stu-id="d0e2f-103">\<system.identityModel></span></span>  
<span data-ttu-id="d0e2f-104">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d0e2f-104">\<identityConfiguration></span></span>  
<span data-ttu-id="d0e2f-105">\<claimsAuthorizationManager ></span><span class="sxs-lookup"><span data-stu-id="d0e2f-105">\<claimsAuthorizationManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0e2f-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d0e2f-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <claimsAuthorizationManager type = xs:string>  
      <optionalConfigurationElements />  
    </claimsAuthorizationManager>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0e2f-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d0e2f-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d0e2f-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0e2f-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d0e2f-109">Attributes</span></span>  
  
|<span data-ttu-id="d0e2f-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d0e2f-110">Attribute</span></span>|<span data-ttu-id="d0e2f-111">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e2f-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d0e2f-112">type</span><span class="sxs-lookup"><span data-stu-id="d0e2f-112">type</span></span>|<span data-ttu-id="d0e2f-113">Пользовательский тип, производный от <xref:System.Security.Claims.ClaimsAuthorizationManager> класса.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-113">A custom type that derives from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class.</span></span> <span data-ttu-id="d0e2f-114">Дополнительные сведения об указании `type` атрибута см. в разделе [ссылки на пользовательские типы](../windows-workflow-foundation/index.md).</span><span class="sxs-lookup"><span data-stu-id="d0e2f-114">For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0e2f-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d0e2f-115">Child Elements</span></span>  
 <span data-ttu-id="d0e2f-116">`type` <xref:System.Security.Claims.ClaimsAuthenticationManager> Если атрибут отсутствует или атрибут <xref:System.Security.Claims.ClaimsAuthorizationManager> ссылаетсянакласс,элементнепринимаетдочерниеэлементы,однакоклассы,производныеот,могутопределятьдочерниеэлементыконфигурации.`<claimsAuthorizationManager>` `type`</span><span class="sxs-lookup"><span data-stu-id="d0e2f-116">If there is no `type` attribute, or if the `type` attribute references the <xref:System.Security.Claims.ClaimsAuthenticationManager> class, the `<claimsAuthorizationManager>` element does not take child elements; however, classes derived from <xref:System.Security.Claims.ClaimsAuthorizationManager> can define child configuration elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d0e2f-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d0e2f-117">Parent Elements</span></span>  
  
|<span data-ttu-id="d0e2f-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="d0e2f-118">Element</span></span>|<span data-ttu-id="d0e2f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d0e2f-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0e2f-120">\<identityConfiguration ></span><span class="sxs-lookup"><span data-stu-id="d0e2f-120">\<identityConfiguration></span></span>](identityconfiguration.md)|<span data-ttu-id="d0e2f-121">Задает параметры удостоверений уровня службы.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-121">Specifies service-level identity settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0e2f-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="d0e2f-122">Remarks</span></span>  
 <span data-ttu-id="d0e2f-123">Поведение по умолчанию, предоставляемое <xref:System.Security.Claims.ClaimsAuthorizationManager> классом, всегда разрешает входящие утверждения.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-123">The default behavior provided through the <xref:System.Security.Claims.ClaimsAuthorizationManager> class always authorizes the incoming claims.</span></span> <span data-ttu-id="d0e2f-124">Если атрибут не указан или `type` <xref:System.Security.Claims.ClaimsAuthorizationManager> атрибут`<claimsAuthorizationManager>` указывает класс, элемент не принимает дочерние элементы. `type`</span><span class="sxs-lookup"><span data-stu-id="d0e2f-124">If no `type` attribute is specified or if the `type` attribute specifies the <xref:System.Security.Claims.ClaimsAuthorizationManager> class, the `<claimsAuthorizationManager>` element does not take child elements.</span></span> <span data-ttu-id="d0e2f-125">Можно указать `type` атрибут для регистрации типа, производного <xref:System.Security.Claims.ClaimsAuthorizationManager> от класса, для реализации пользовательского поведения.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-125">You can specify the `type` attribute to register a type derived from the <xref:System.Security.Claims.ClaimsAuthorizationManager> class to implement custom behavior.</span></span> <span data-ttu-id="d0e2f-126">Производные классы могут поддерживать конфигурацию через дочерние `<claimsAuthorizationManager>` элементы элемента путем <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> переопределения метода для работы с этими элементами.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-126">Derived classes can support configuration through child elements of the `<claimsAuthorizationManager>` element by overriding the <xref:System.Security.Claims.ClaimsAuthorizationManager.LoadCustomConfiguration%2A> method to handle these elements.</span></span> <span data-ttu-id="d0e2f-127">Схема, определенная для дочерних элементов, находится в конструкторе класса.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-127">The schema defined for the child elements is up to the designer of the class.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d0e2f-128">При использовании <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> класса или для предоставления управления доступом на основе утверждений в коде конфигурация удостоверений `<federationConfiguration>` , на которую ссылается элемент, настраивает диспетчер авторизации утверждений и политику, которая используется для создания решения по авторизации.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-128">When using the <xref:System.IdentityModel.Services.ClaimsPrincipalPermission> or the <xref:System.IdentityModel.Services.ClaimsPrincipalPermissionAttribute> class to provide claims-based access control in your code, the identity configuration that is referenced by the `<federationConfiguration>` element configures the claims authorization manager and policy that is used to make authorization decisions.</span></span> <span data-ttu-id="d0e2f-129">Это справедливо даже в сценариях, которые не являются пассивными веб-сценариями, например Windows Communication Foundation приложений (WCF) или приложение, не основанное на веб-интерфейсе.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-129">This is true, even in scenarios that are not passive Web scenarios, for example Windows Communication Foundation (WCF) applications or an application that is not Web-based.</span></span> <span data-ttu-id="d0e2f-130">Если приложение не является пассивным веб-приложением, то `<claimsAuthorizationManager>` к нему применяются только те элементы (и дочерние элемент политики, если таковые имеются) конфигурации удостоверения, на которую указывает ссылка.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-130">If the application is not a passive Web application, the `<claimsAuthorizationManager>` element (and its child policy elements, if present) of the referenced identity configuration are the only settings applied.</span></span> <span data-ttu-id="d0e2f-131">Все остальные параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-131">All other settings are ignored.</span></span> <span data-ttu-id="d0e2f-132">Дополнительные сведения см. в [ \<](federationconfiguration.md) описании элемента federationConfiguration >.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-132">For more information, see the [\<federationConfiguration>](federationconfiguration.md) element.</span></span>  
  
 <span data-ttu-id="d0e2f-133">Этот элемент задает <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-133">This element sets the <xref:System.IdentityModel.Configuration.IdentityConfiguration.ClaimsAuthorizationManager%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0e2f-134">Пример</span><span class="sxs-lookup"><span data-stu-id="d0e2f-134">Example</span></span>  
 <span data-ttu-id="d0e2f-135">В следующем коде XML показана конфигурация для диспетчера авторизации утверждений, который реализует политику, состоящую из пар действий с ресурсами, каждый из которых указывает логические комбинации утверждений, которые должен обладать запрашивающей стороны для выполнения действия с ресурсом.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-135">The following XML shows the configuration for a claims authorization manager that implements policy composed of resource-action pairs each of which specifies boolean combinations of the claims that a requestor must possess to perform the action on the resource.</span></span> <span data-ttu-id="d0e2f-136">Код, реализующий диспетчер авторизации утверждений, который может использовать эту политику, можно найти в `ClaimsBasedAuthorization` примере.</span><span class="sxs-lookup"><span data-stu-id="d0e2f-136">The code that implements the claims authorization manager capable of using this policy can be found in the `ClaimsBasedAuthorization` sample.</span></span>  
  
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
