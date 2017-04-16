---
title: "Как создать пользовательскую политику авторизации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 05b0549b-882d-4660-b6f0-5678543e5475
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Как создать пользовательскую политику авторизации
Инфраструктура модели удостоверения в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает модель авторизации, основанную на утверждениях.Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>, который позже может проверяться для принятия решений по авторизации.Пользовательская политика может использоваться для преобразования утверждений из входящих маркеров в утверждения, ожидаемые приложением.Таким образом, прикладной уровень может быть изолирован от сведений различных утверждений, обслуживаемых разными типами маркеров, которые поддерживаются системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].В данном разделе показываются реализация пользовательской политики авторизации и добавление этой политики в коллекцию политик, используемых службой.  
  
### Реализация пользовательской политики авторизации  
  
1.  Определите новый класс, наследуемый от <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2.  Реализуйте предназначенное только для чтения свойство <xref:System.IdentityModel.Policy.IAuthorizationComponent.Id%2A> посредством создания уникальной строки в конструкторе для данного класса и возврата этой строки при каждом доступе к данному свойству.  
  
3.  Реализуйте предназначенное только для чтения свойство <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Issuer%2A> посредством возврата набора <xref:System.IdentityModel.Claims.ClaimSet>, представляющего поставщика политики.Это может быть набор `ClaimSet`, который представляет приложение, или встроенный набор `ClaimSet` \(например, набор `ClaimSet`, возвращаемый статическим свойством <xref:System.IdentityModel.Claims.ClaimSet.System%2A>\).  
  
4.  Реализуйте метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> согласно описанию в следующей процедуре.  
  
### Реализация метода Evaluate  
  
1.  В этот метод передаются два параметра: экземпляр класса <xref:System.IdentityModel.Policy.EvaluationContext> и ссылка на объект.  
  
2.  Если пользовательская политика авторизации добавляет экземпляры <xref:System.IdentityModel.Claims.ClaimSet> независимо от текущего содержимого класса <xref:System.IdentityModel.Policy.EvaluationContext>, добавьте каждый набор `ClaimSet`, вызвав метод <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29>, и верните значение `true` из метода <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%2A>.Возврат значения `true` указывает инфраструктуре авторизации, что политика авторизации выполнила свою работу и снова ее вызывать не требуется.  
  
3.  Если пользовательская политика авторизации добавляет наборы утверждений только в случае наличия определенных утверждений в классе `EvaluationContext`, выполните поиск этих утверждений, проверив экземпляры `ClaimSet`, возвращенные свойством <xref:System.IdentityModel.Policy.EvaluationContext.ClaimSets%2A>.Если утверждения присутствуют, добавьте новые наборы утверждений, вызвав метод <xref:System.IdentityModel.Policy.EvaluationContext.AddClaimSet%28System.IdentityModel.Policy.IAuthorizationPolicy%2CSystem.IdentityModel.Claims.ClaimSet%29>, и в случае отсутствия необходимости добавления дополнительных наборов утверждений верните значение `true`, указывающее инфраструктуре авторизации, что политика авторизации завершила свою работу.Если утверждения отсутствуют, верните значение `false`, указывающее, что в случае добавления дополнительных наборов утверждений в класс `EvaluationContext` другими политиками авторизации политика авторизации должна быть вызвана снова.  
  
4.  В более сложных сценариях обработки второй параметр метода <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> используется для хранения переменной состояния, которую инфраструктура авторизации будет передавать назад в течение каждого последующего вызова метода <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> для конкретной оценки.  
  
### Задание пользовательской политики авторизации с помощью конфигурации  
  
1.  Задайте тип пользовательской политики авторизации с помощью атрибута `policyType` в элементе `add` элемента `authorizationPolicies` в элементе `serviceAuthorization`.  
  
    ```  
    <configuration>  
     <system.serviceModel>  
      <behaviors>  
        <serviceAuthorization serviceAuthorizationManagerType=  
                  "Samples.MyServiceAuthorizationManager" >  
          <authorizationPolicies>         
            <add policyType="Samples.MyAuthorizationPolicy"  
          </authorizationPolicies>  
        </serviceAuthorization>  
      </behaviors>  
     </system.serviceModel>  
    </configuration>  
    ```  
  
### Задание пользовательской политики авторизации с помощью кода  
  
1.  Создайте список <xref:System.Collections.Generic.List%601> политики <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
2.  Создайте экземпляр пользовательской политики авторизации.  
  
3.  Добавьте экземпляр политики авторизации в список.  
  
4.  Повторите шаги 2 и 3 для каждой пользовательской политики авторизации.  
  
5.  Присвойте предназначенную только для чтения версию списка свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>.  
  
     [!code-csharp[c_CustomAuthPol#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#8)]
     [!code-vb[c_CustomAuthPol#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#8)]  
  
## Пример  
 В следующем примере показана полная реализация <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
 [!code-csharp[c_CustomAuthPol#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthpol/cs/c_customauthpol.cs#5)]
 [!code-vb[c_CustomAuthPol#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthpol/vb/source.vb#5)]  
  
## См. также  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 [Как сравнивать утверждения](../../../../docs/framework/wcf/extending/how-to-compare-claims.md)   
 [Как создавать пользовательский диспетчер авторизации для службы](../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)   
 [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md)