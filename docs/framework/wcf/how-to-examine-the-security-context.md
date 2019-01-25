---
title: Как выполнить Анализ контекста безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ServiceSecurityContext class
- WCF, security
- Claimset class
ms.assetid: 389b5a57-4175-4bc0-ada0-fc750d51149f
ms.openlocfilehash: bcc23097a6778bb537421ba494dd94414b37f4e2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646270"
---
# <a name="how-to-examine-the-security-context"></a>Как выполнить Анализ контекста безопасности
При программировании служб Windows Communication Foundation (WCF), контекст безопасности службы позволяет определять сведения об учетных данных клиента и утверждения, используемый для проверки подлинности в службе. Это осуществляется с помощью свойств класса <xref:System.ServiceModel.ServiceSecurityContext>.  
  
 Например, извлечь удостоверение текущего клиента можно с помощью свойства <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> или <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>. Чтобы определить, является ли клиент анонимным, следует использовать свойство <xref:System.ServiceModel.ServiceSecurityContext.IsAnonymous%2A>.  
  
 Кроме того, перебором коллекции утверждений в свойстве <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A> можно определить, какие утверждения делаются от имени клиента.  
  
### <a name="to-get-the-current-security-context"></a>Получение текущего контекста безопасности  
  
-   Для получения текущего контекста безопасности необходимо получить доступ к статическому свойству <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>. После этого можно проверять любые свойства текущего контекста из ссылки.  
  
### <a name="to-determine-the-identity-of-the-caller"></a>Определение удостоверения вызывающего объекта  
  
1.  Выведите на печать значение свойств <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> и <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A>.  
  
### <a name="to-parse-the-claims-of-a-caller"></a>Анализ утверждений вызывающего объекта  
  
1.  Верните текущий класс <xref:System.IdentityModel.Policy.AuthorizationContext>. Используйте свойство <xref:System.ServiceModel.ServiceSecurityContext.Current%2A>, чтобы вернуть текущий контекст безопасности службы, и верните контекст `AuthorizationContext` с помощью свойства <xref:System.ServiceModel.ServiceSecurityContext.AuthorizationContext%2A>.  
  
2.  Проанализируйте коллекцию объектов <xref:System.IdentityModel.Claims.ClaimSet>, возвращаемую свойством <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> класса <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
## <a name="example"></a>Пример  
 В следующем примере выводятся на печать значения свойств <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> и <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A> текущего контекста безопасности, свойство <xref:System.IdentityModel.Claims.Claim.ClaimType%2A>, значение ресурса утверждения и свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> каждого утверждения текущего контекста безопасности.  
  
 [!code-csharp[c_PrincipalPermissionAttribute#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_principalpermissionattribute/cs/source.cs#4)]
 [!code-vb[c_PrincipalPermissionAttribute#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_principalpermissionattribute/vb/source.vb#4)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 В коде используются следующие пространства имен:  
  
-   <xref:System>  
  
-   <xref:System.ServiceModel>  
  
-   <xref:System.IdentityModel.Policy>  
  
-   <xref:System.IdentityModel.Claims>  
  
## <a name="see-also"></a>См. также
- [Защита служб](../../../docs/framework/wcf/securing-services.md)
- [Идентификация и проверка подлинности службы](../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
