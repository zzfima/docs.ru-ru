---
title: '&lt;add&gt; для &lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 5f4afe0a0a72d7f45dd0ed38cbcc7a0d89d17d44
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54148465"
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a><span data-ttu-id="80c1a-102">&lt;add&gt; для &lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="80c1a-102">&lt;add&gt; of &lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="80c1a-103">Задает политику авторизации для преобразования требований.</span><span class="sxs-lookup"><span data-stu-id="80c1a-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="80c1a-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="80c1a-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="80c1a-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="80c1a-105">\<behaviors></span></span>  
<span data-ttu-id="80c1a-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="80c1a-106">\<behavior></span></span>  
<span data-ttu-id="80c1a-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="80c1a-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="80c1a-108">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="80c1a-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="80c1a-109">\<add></span><span class="sxs-lookup"><span data-stu-id="80c1a-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80c1a-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="80c1a-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="80c1a-111">Тип</span><span class="sxs-lookup"><span data-stu-id="80c1a-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80c1a-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="80c1a-112">Attributes and Elements</span></span>  
 <span data-ttu-id="80c1a-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="80c1a-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80c1a-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="80c1a-114">Attributes</span></span>  
  
|<span data-ttu-id="80c1a-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="80c1a-115">Attribute</span></span>|<span data-ttu-id="80c1a-116">Описание</span><span class="sxs-lookup"><span data-stu-id="80c1a-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="80c1a-117">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="80c1a-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="80c1a-118">Модель управления доступом Windows Communication Foundation (WCF) поддерживает предоставление набора политик авторизации в качестве типов.</span><span class="sxs-lookup"><span data-stu-id="80c1a-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="80c1a-119">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="80c1a-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="80c1a-120">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="80c1a-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80c1a-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="80c1a-121">Child Elements</span></span>  
 <span data-ttu-id="80c1a-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="80c1a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80c1a-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="80c1a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="80c1a-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="80c1a-124">Element</span></span>|<span data-ttu-id="80c1a-125">Описание:</span><span class="sxs-lookup"><span data-stu-id="80c1a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="80c1a-126">\<authorizationPolicies ></span><span class="sxs-lookup"><span data-stu-id="80c1a-126">\<authorizationPolicies></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|<span data-ttu-id="80c1a-127">Задает коллекцию типов политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="80c1a-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80c1a-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="80c1a-128">Remarks</span></span>  
 <span data-ttu-id="80c1a-129">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="80c1a-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="80c1a-130">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="80c1a-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="80c1a-131">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="80c1a-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="80c1a-132">Дополнительные сведения о работе политики авторизации см. в разделе <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [политики авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="80c1a-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c1a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="80c1a-133">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="80c1a-134">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="80c1a-134">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="80c1a-135">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="80c1a-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="80c1a-136">\<add></span><span class="sxs-lookup"><span data-stu-id="80c1a-136">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="80c1a-137">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="80c1a-137">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
