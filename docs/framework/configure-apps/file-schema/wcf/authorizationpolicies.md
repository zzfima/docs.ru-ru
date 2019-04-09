---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 2910f47b85ee67694cae0c3a725c3c7c7b3803c0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122829"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="d826c-101">\<authorizationPolicies></span><span class="sxs-lookup"><span data-stu-id="d826c-101">\<authorizationPolicies></span></span>
<span data-ttu-id="d826c-102">Этот раздел конфигурации содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="d826c-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="d826c-103">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="d826c-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="d826c-104">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="d826c-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="d826c-105">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="d826c-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="d826c-106">Дополнительные сведения о работе политики авторизации см. в разделе <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [политики авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d826c-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d826c-107">См. также</span><span class="sxs-lookup"><span data-stu-id="d826c-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="d826c-108">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="d826c-108">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="d826c-109">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="d826c-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="d826c-110">\<add></span><span class="sxs-lookup"><span data-stu-id="d826c-110">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)
- [<span data-ttu-id="d826c-111">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="d826c-111">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
