---
title: <authorizationPolicies>
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 38d123a53b344ff1e4d781115093d0d1de5ae679
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926464"
---
# <a name="authorizationpolicies"></a><span data-ttu-id="f9ae8-101">\<Нулевым authorizationpolicies ></span><span class="sxs-lookup"><span data-stu-id="f9ae8-101">\<authorizationPolicies></span></span>
<span data-ttu-id="f9ae8-102">Этот раздел конфигурации содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="f9ae8-102">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="f9ae8-103">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="f9ae8-103">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="f9ae8-104">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="f9ae8-104">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="f9ae8-105">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="f9ae8-105">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="f9ae8-106">Дополнительные сведения о принципах работы политики авторизации см. в <xref:System.IdentityModel.Policy.IAuthorizationPolicy> разделе и [Политика авторизации](../../../wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="f9ae8-106">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9ae8-107">См. также</span><span class="sxs-lookup"><span data-stu-id="f9ae8-107">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>
- <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>
- <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>
- <xref:System.IdentityModel.Policy.IAuthorizationPolicy>
- [<span data-ttu-id="f9ae8-108">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="f9ae8-108">Authorizing Access to Service Operations</span></span>](../../../wcf/samples/authorizing-access-to-service-operations.md)
- [<span data-ttu-id="f9ae8-109">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="f9ae8-109">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)
- [<span data-ttu-id="f9ae8-110">\<add></span><span class="sxs-lookup"><span data-stu-id="f9ae8-110">\<add></span></span>](add-of-authorizationpolicies.md)
- [<span data-ttu-id="f9ae8-111">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="f9ae8-111">Authorization Policy</span></span>](../../../wcf/samples/authorization-policy.md)
