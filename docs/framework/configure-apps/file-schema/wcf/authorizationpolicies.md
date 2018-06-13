---
title: '&lt;authorizationPolicies&gt;'
ms.date: 03/30/2017
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
ms.openlocfilehash: 8e1bc702db899c4b0b3ee539fdc89cdda6c4cf10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752901"
---
# <a name="ltauthorizationpoliciesgt"></a><span data-ttu-id="89001-102">&lt;authorizationPolicies&gt;</span><span class="sxs-lookup"><span data-stu-id="89001-102">&lt;authorizationPolicies&gt;</span></span>
<span data-ttu-id="89001-103">Этот раздел конфигурации содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="89001-103">This configuration section contains a collection of authorization policy types, which can be added using the `add` keyword.</span></span> <span data-ttu-id="89001-104">Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип.</span><span class="sxs-lookup"><span data-stu-id="89001-104">Each authorization policy contains a single required `policyType` attribute that is a string.</span></span> <span data-ttu-id="89001-105">Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований.</span><span class="sxs-lookup"><span data-stu-id="89001-105">The attribute specifies an authorization policy, which enables transformation of one set of input claims into another set of claims.</span></span> <span data-ttu-id="89001-106">В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом.</span><span class="sxs-lookup"><span data-stu-id="89001-106">Access control can be granted or denied based on that.</span></span> <span data-ttu-id="89001-107">Дополнительные сведения о работе политику авторизации см. в разделе <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span><span class="sxs-lookup"><span data-stu-id="89001-107">For more information on how an authorization policy works, see <xref:System.IdentityModel.Policy.IAuthorizationPolicy> and [Authorization Policy](../../../../../docs/framework/wcf/samples/authorization-policy.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89001-108">См. также</span><span class="sxs-lookup"><span data-stu-id="89001-108">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [<span data-ttu-id="89001-109">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="89001-109">Authorizing Access to Service Operations</span></span>](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [<span data-ttu-id="89001-110">Практическое руководство. Создание пользовательского диспетчера авторизации для службы</span><span class="sxs-lookup"><span data-stu-id="89001-110">How to: Create a Custom Authorization Manager for a Service</span></span>](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [<span data-ttu-id="89001-111">\<add></span><span class="sxs-lookup"><span data-stu-id="89001-111">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [<span data-ttu-id="89001-112">Политика авторизации</span><span class="sxs-lookup"><span data-stu-id="89001-112">Authorization Policy</span></span>](../../../../../docs/framework/wcf/samples/authorization-policy.md)
