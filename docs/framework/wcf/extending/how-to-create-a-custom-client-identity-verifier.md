---
title: "Практическое руководство. Создание пользовательского средства проверки идентификации клиентов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Практическое руководство. Создание пользовательского средства проверки идентификации клиентов
Функция *удостоверения* в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] позволяет клиенту заранее указывать ожидаемое удостоверение службы.  Всякий раз, когда сервер доказывает свою подлинность клиенту, удостоверение проверяется на соответствие ожидаемому удостоверению.  \(Описание удостоверения и принципов его работы см. в разделе [Идентификация и проверка подлинности службы](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).\)  
  
 При необходимости процедуру проверки можно настроить, используя пользовательское средство проверки удостоверения.  Например, можно выполнять дополнительные процедуры проверки удостоверения службы.  В данном примере пользовательское средство проверки удостоверения проверяет дополнительные утверждения в сертификате X.509, возвращенном от сервера.  Пример приложения см. в разделе [Образец идентификации службы](../../../../docs/framework/wcf/samples/service-identity-sample.md).  
  
### Расширение класса EndpointIdentity  
  
1.  Определите новый класс, наследуемый от класса <xref:System.ServiceModel.EndpointIdentity>.  В этом примере расширению присвоено имя `OrgEndpointIdentity`.  
  
2.  Добавьте закрытые члены со свойствами, которые будут использоваться расширенным классом <xref:System.ServiceModel.Security.IdentityVerifier> для проверки удостоверения на соответствие утверждениям в маркере безопасности, возвращенном от службы.  В этом примере определено одно свойство: свойство `OrganizationClaim`.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### Расширение класса IdentityVerifier  
  
1.  Определите новый класс, наследуемый от <xref:System.ServiceModel.Security.IdentityVerifier>.  В этом примере расширению присвоено имя `CustomIdentityVerifier`.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2.  Переопределите метод <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A>.  Этот метод определяет, успешно ли пройдена проверка удостоверения.  
  
3.  Метод `CheckAccess` имеет два параметра.  Первый представляет собой экземпляр класса <xref:System.ServiceModel.EndpointIdentity>.  Второй является экземпляром класса <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
     В реализации метода необходимо проанализировать коллекцию утверждений, возвращенную свойством <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> класса <xref:System.IdentityModel.Policy.AuthorizationContext>, и выполнить требуемые процедуры проверки подлинности.  В этом примере сначала выполняется поиск утверждения типа "различающееся имя" \(DistinguishedName\), после чего имя сравнивается с расширением класса <xref:System.ServiceModel.EndpointIdentity> \(`OrgEndpointIdentity`\).  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### Реализация метода TryGetIdentity  
  
1.  Реализуйте метод <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A>, который определяет, может ли клиентом быть возвращен экземпляр класса <xref:System.ServiceModel.EndpointIdentity>.  Инфраструктура [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] сначала вызывает реализацию метода `TryGetIdentity` для извлечения из сообщения удостоверения службы.  Затем инфраструктура вызывает реализацию метода `CheckAccess` с возвращенными объектами `EndpointIdentity` и <xref:System.IdentityModel.Policy.AuthorizationContext>.  
  
2.  Поместите в метод `TryGetIdentity` следующий код:  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### Реализация пользовательской привязки и задание пользовательского IdentityVerifier  
  
1.  Создайте метод, который возвращает объект <xref:System.ServiceModel.Channels.Binding>.  В этом примере сначала создается экземпляр класса <xref:System.ServiceModel.WSHttpBinding>, после чего для него задается режим безопасности <xref:System.ServiceModel.SecurityMode>, а для его свойства <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> \- значение <xref:System.ServiceModel.MessageCredentialType>.  
  
2.  Создайте коллекцию <xref:System.ServiceModel.Channels.BindingElementCollection> с помощью метода <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A>.  
  
3.  Возвратите из коллекции объект <xref:System.ServiceModel.Channels.SecurityBindingElement> и приведите его к переменной <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.  
  
4.  Присвойте свойству <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> класса <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> в качестве значения новый экземпляр ранее созданного класса `CustomIdentityVerifier`.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5.  Возвращаемая пользовательская привязка используется для создания экземпляра клиента и класса.  Клиент затем может выполнить пользовательскую проверку удостоверения службы, как показано в следующем коде.  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## Пример  
 В следующем примере показана полная реализация класса <xref:System.ServiceModel.Security.IdentityVerifier>.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## Пример  
 В следующем примере показана полная реализация класса <xref:System.ServiceModel.EndpointIdentity>.  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## См. также  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 <xref:System.ServiceModel.EndpointIdentity>   
 <xref:System.ServiceModel.Security.IdentityVerifier>   
 [Образец идентификации службы](../../../../docs/framework/wcf/samples/service-identity-sample.md)   
 [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md)   
 [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md)