---
title: '&lt;authorizationPolicies&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b367489-54d7-408b-8f56-cb157dd68eaf
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 94bbf10ad093c6b99d586f9aaacb7faffc097cee
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltauthorizationpoliciesgt"></a>&lt;authorizationPolicies&gt;
Этот раздел конфигурации содержит коллекцию типов политик авторизации, которые можно добавить с помощью ключевого слова `add`. Каждая политика авторизации содержит один обязательный атрибут `policyType`, который имеет строковый тип. Данный атрибут определяет политику авторизации, которая позволяет преобразовывать один набор входных требований в другой набор требований. В зависимости от этого может быть предоставлено управление доступом или отказано в предоставлении управления доступом. Дополнительные сведения о работе политику авторизации см. в разделе <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и [политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [Авторизация доступа к операциям службы](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [Как: Создание пользовательского диспетчера авторизации для службы](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [Политика авторизации](../../../../../docs/framework/wcf/samples/authorization-policy.md)
