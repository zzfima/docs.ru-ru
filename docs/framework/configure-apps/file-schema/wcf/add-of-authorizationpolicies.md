---
title: <add> из <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: 65398c5afa9750f215c95899bb6004cae671123a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920277"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="4ebf3-102">\<Добавление > \<> нулевым authorizationpolicies</span><span class="sxs-lookup"><span data-stu-id="4ebf3-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="4ebf3-103">Задает политику авторизации для преобразования требований.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-103">Specifies an authorization policy for claim transformation.</span></span>  
  
 <span data-ttu-id="4ebf3-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="4ebf3-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4ebf3-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4ebf3-105">\<behaviors></span></span>  
<span data-ttu-id="4ebf3-106">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="4ebf3-106">\<behavior></span></span>  
<span data-ttu-id="4ebf3-107">\<serviceAuthorization ></span><span class="sxs-lookup"><span data-stu-id="4ebf3-107">\<serviceAuthorization></span></span>  
<span data-ttu-id="4ebf3-108">\<Нулевым authorizationpolicies ></span><span class="sxs-lookup"><span data-stu-id="4ebf3-108">\<authorizationPolicies></span></span>  
<span data-ttu-id="4ebf3-109">\<add></span><span class="sxs-lookup"><span data-stu-id="4ebf3-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebf3-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ebf3-110">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="4ebf3-111">Тип</span><span class="sxs-lookup"><span data-stu-id="4ebf3-111">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4ebf3-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4ebf3-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4ebf3-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4ebf3-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4ebf3-114">Attributes</span></span>  
  
|<span data-ttu-id="4ebf3-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4ebf3-115">Attribute</span></span>|<span data-ttu-id="4ebf3-116">Описание</span><span class="sxs-lookup"><span data-stu-id="4ebf3-116">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="4ebf3-117">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-117">A required String attribute.</span></span><br /><br /> <span data-ttu-id="4ebf3-118">Модель управления доступом Windows Communication Foundation (WCF) поддерживает подготовку набора политик авторизации в качестве типов.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-118">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="4ebf3-119">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-119">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4ebf3-120">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-120">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4ebf3-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4ebf3-121">Child Elements</span></span>  
 <span data-ttu-id="4ebf3-122">Нет.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4ebf3-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4ebf3-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4ebf3-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="4ebf3-124">Element</span></span>|<span data-ttu-id="4ebf3-125">Описание</span><span class="sxs-lookup"><span data-stu-id="4ebf3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4ebf3-126">\<Нулевым authorizationpolicies ></span><span class="sxs-lookup"><span data-stu-id="4ebf3-126">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="4ebf3-127">Задает коллекцию типов политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-127">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4ebf3-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="4ebf3-128">Remarks</span></span>  
 <span data-ttu-id="4ebf3-129">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-129">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="4ebf3-130">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-130">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="4ebf3-131">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="4ebf3-131">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="4ebf3-132">Дополнительные сведения о принципах работы политики авторизации см. в <xref:System.IdentityModel.Policy.IAuthorizationPolicy> разделе и [Политика авторизации](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4ebf3-132">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebf3-133">См. также</span><span class="sxs-lookup"><span data-stu-id="4ebf3-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="4ebf3-134">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="4ebf3-134">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="4ebf3-135">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="4ebf3-135">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="4ebf3-136">\<add></span><span class="sxs-lookup"><span data-stu-id="4ebf3-136">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="4ebf3-137">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="4ebf3-137">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
