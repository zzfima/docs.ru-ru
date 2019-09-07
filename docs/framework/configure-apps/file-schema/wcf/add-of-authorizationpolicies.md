---
title: <add> из <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
ms.openlocfilehash: e2597bc51e788c919bfe3ce3422ae2911cc6b33b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400701"
---
# <a name="add-of-authorizationpolicies"></a><span data-ttu-id="2ce4b-102">\<Добавление > \<> нулевым authorizationpolicies</span><span class="sxs-lookup"><span data-stu-id="2ce4b-102">\<add> of \<authorizationPolicies></span></span>
<span data-ttu-id="2ce4b-103">Задает политику авторизации для преобразования требований.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-103">Specifies an authorization policy for claim transformation.</span></span>  
  
<span data-ttu-id="2ce4b-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2ce4b-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2ce4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="2ce4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="2ce4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="2ce4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceAuthorization >** ](serviceauthorization-element.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceAuthorization>**](serviceauthorization-element.md)</span></span>\
<span data-ttu-id="2ce4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Нулевым authorizationpolicies >** ](authorizationpolicies.md)</span><span class="sxs-lookup"><span data-stu-id="2ce4b-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<authorizationPolicies>**](authorizationpolicies.md)</span></span>\
<span data-ttu-id="2ce4b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Добавить >**</span><span class="sxs-lookup"><span data-stu-id="2ce4b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ce4b-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2ce4b-112">Syntax</span></span>  
  
```xml  
<authorizationPolicies>
  <add policyType="String" />
</authorizationPolicies>
```  
  
## <a name="type"></a><span data-ttu-id="2ce4b-113">Тип</span><span class="sxs-lookup"><span data-stu-id="2ce4b-113">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2ce4b-114">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2ce4b-114">Attributes and Elements</span></span>  
 <span data-ttu-id="2ce4b-115">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-115">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2ce4b-116">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2ce4b-116">Attributes</span></span>  
  
|<span data-ttu-id="2ce4b-117">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2ce4b-117">Attribute</span></span>|<span data-ttu-id="2ce4b-118">Описание</span><span class="sxs-lookup"><span data-stu-id="2ce4b-118">Description</span></span>|  
|---------------|-----------------|  
|`policyType`|<span data-ttu-id="2ce4b-119">Обязательный строковый атрибут.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-119">A required String attribute.</span></span><br /><br /> <span data-ttu-id="2ce4b-120">Модель управления доступом Windows Communication Foundation (WCF) поддерживает подготовку набора политик авторизации в качестве типов.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-120">The Windows Communication Foundation (WCF) access control model supports provisioning a set of authorization policies as types.</span></span> <span data-ttu-id="2ce4b-121">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-121">This attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2ce4b-122">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-122">Access control can be granted or denied based on that.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2ce4b-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2ce4b-123">Child Elements</span></span>  
 <span data-ttu-id="2ce4b-124">Нет.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2ce4b-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2ce4b-125">Parent Elements</span></span>  
  
|<span data-ttu-id="2ce4b-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="2ce4b-126">Element</span></span>|<span data-ttu-id="2ce4b-127">Описание</span><span class="sxs-lookup"><span data-stu-id="2ce4b-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2ce4b-128">\<Нулевым authorizationpolicies ></span><span class="sxs-lookup"><span data-stu-id="2ce4b-128">\<authorizationPolicies></span></span>](authorizationpolicies.md)|<span data-ttu-id="2ce4b-129">Задает коллекцию типов политики авторизации.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-129">Specifies a collection of authorization policy types.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2ce4b-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="2ce4b-130">Remarks</span></span>  
 <span data-ttu-id="2ce4b-131">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-131">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="2ce4b-132">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-132">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="2ce4b-133">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="2ce4b-133">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="2ce4b-134">Дополнительные сведения о принципах работы политики авторизации см. в <xref:System.IdentityModel.Policy.IAuthorizationPolicy> разделе и [Политика авторизации](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="2ce4b-134">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ce4b-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ce4b-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="2ce4b-136">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="2ce4b-136">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="2ce4b-137">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="2ce4b-137">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="2ce4b-138">\<add></span><span class="sxs-lookup"><span data-stu-id="2ce4b-138">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="2ce4b-139">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="2ce4b-139">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
