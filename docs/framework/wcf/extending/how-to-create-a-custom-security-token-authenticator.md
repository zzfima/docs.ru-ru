---
title: "Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF, authentication
ms.assetid: 10e245f7-d31e-42e7-82a2-d5780325d372
caps.latest.revision: "12"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 4415edbe9f04cb56cefadcb3ae521994fac28ffb
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-custom-security-token-authenticator"></a>Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности
В этом разделе показано, как создать пользовательскую структуру проверки подлинности маркеров безопасности и интегрировать ее с пользовательским диспетчером маркеров безопасности. Структура проверки подлинности маркеров безопасности проверяет содержимое маркера безопасности, которым снабжается входящее сообщение. В случае успешной проверки структура проверки подлинности возвращает коллекцию экземпляров <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, которая при вычислении возвращает набор утверждений.  
  
 Чтобы использовать пользовательскую структуру проверки подлинности маркеров безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], необходимо предварительно создать пользовательские реализации учетных данных и диспетчера маркеров безопасности. Дополнительные сведения о создании пользовательских учетных данных и обеспечения безопасности диспетчер маркеров см. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md). Дополнительные сведения об учетных данных, диспетчер маркеров безопасности и классы поставщика и структуры проверки подлинности см. в разделе [архитектуры безопасности](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).  
  
## <a name="procedures"></a>Процедуры  
  
#### <a name="to-create-a-custom-security-token-authenticator"></a>Создание пользовательской структуры проверки подлинности маркера безопасности  
  
1.  Определите новый класс, производный от класса <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>.  
  
2.  Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateTokenCore%2A>. Метод возвращает значение `true` или `false` в зависимости от того, может ли пользовательская структура проверки подлинности проверить входящий маркер.  
  
3.  Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.ValidateTokenCore%2A>. Этот метод должен соответствующим образом проверить содержимое маркера. Если маркер проходит этап проверки, метод возвращает коллекцию экземпляров <xref:System.IdentityModel.Policy.IAuthorizationPolicy>. В приведенном ниже примере используется пользовательская реализация политики авторизации, которая будет создана в следующей процедуре.  
  
     [!code-csharp[C_CustomTokenAuthenticator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#1)]
     [!code-vb[C_CustomTokenAuthenticator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#1)]  
  
 Приведенный выше образец кода возвращает коллекцию политик авторизации в методе <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator.CanValidateToken%28System.IdentityModel.Tokens.SecurityToken%29>. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не предусматривает открытую реализацию этого интерфейса. В следующей процедуре показано, как сделать это для пользовательских требований.  
  
#### <a name="to-create-a-custom-authorization-policy"></a>Создание пользовательской политики авторизации  
  
1.  Определите новый класс, реализующий интерфейс <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2.  Реализуйте свойство <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A>, доступное только для чтения. Один из способов реализации этого свойства предполагает создание глобального уникального идентификатора (GUID) в конструкторе класса и его возврат при каждом запросе данного свойства.  
  
3.  Реализуйте свойство <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A>, доступное только для чтения. Это свойство должно возвращать издатель наборов утверждений, которые извлекаются из маркера. Этот издатель должен соответствовать издателю маркера или объекту, который отвечает за проверку содержимого маркера. В следующем примере используется утверждение издателя, которое передается данному классу из пользовательской структуры проверки подлинности маркеров безопасности, созданной в приведенной выше процедуре. Пользовательская структура проверки подлинности маркеров безопасности использует предоставляемый системой набор утверждений (возвращаемый свойством <xref:System.IdentityModel.Claims.ClaimSet.System%2A>) для представления издателя маркера имени пользователя.  
  
4.  Выполните метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A>. Этот метод записывает в экземпляр класса <xref:System.IdentityModel.Policy.EvaluationContext> (передаваемый в качестве аргумента) утверждения, основанные на содержимом входящего маркера безопасности. Метод возвращает значение `true` после завершения вычисления. Если реализация зависит от наличия других политик авторизации, которые предоставляют дополнительные сведения для контекста вычисления, этот метод может возвращать значение `false`, если необходимые сведения пока отсутствуют в контексте вычисления. В последнем случае среда [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] снова вызовет данный метод после вычисления всех остальных политик авторизации, созданных для входящего сообщения, если хотя бы одна из этих политик авторизации изменила контекст вычисления.  
  
     [!code-csharp[c_CustomTokenAuthenticator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#2)]
     [!code-vb[c_CustomTokenAuthenticator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#2)]  
  
 [Пошаговое руководство: Создание пользовательского клиента и учетные данные службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md) описывается создание пользовательских учетных данных и пользовательские параметры безопасности диспетчера маркеров. Для использования созданной здесь пользовательской структуры проверки подлинности маркеров безопасности реализация диспетчера маркеров безопасности изменяется таким образом, чтобы возвращать из метода <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> пользовательскую структуру проверки подлинности. Метод возвращает структуру проверки подлинности, когда ему передается соответствующее требование маркера безопасности.  
  
#### <a name="to-integrate-a-custom-security-token-authenticator-with-a-custom-security-token-manager"></a>Интеграция пользовательской структуры проверки подлинности маркеров безопасности с пользовательским диспетчером маркеров безопасности  
  
1.  Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A> в реализации пользовательского диспетчера маркеров безопасности.  
  
2.  Добавьте в метод соответствующие инструкции, чтобы он мог возвращать пользовательскую структуру проверки подлинности маркеров безопасности на основании параметра <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>. Следующий пример возвращает пользовательскую структуру проверки подлинности маркеров безопасности, если типом маркера требований является имя пользователя (представляется свойством <xref:System.IdentityModel.Tokens.SecurityTokenTypes.UserName%2A>), а направлением сообщения, для которого запрашивается структура проверки подлинности маркеров безопасности, являются входящие сообщения (представляется полем <xref:System.ServiceModel.Description.MessageDirection.Input>).  
  
     [!code-csharp[c_CustomTokenAuthenticator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenauthenticator/cs/source.cs#3)]
     [!code-vb[c_CustomTokenAuthenticator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenauthenticator/vb/source.vb#3)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.UserNameSecurityToken>  
 [Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 [Архитектура безопасности](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
