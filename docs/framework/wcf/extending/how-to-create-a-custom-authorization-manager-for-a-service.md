---
title: "Как создавать пользовательский диспетчер авторизации для службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "класс OperationRequirement"
  - "Windows Communication Foundation, расширение"
ms.assetid: 6214afde-44c1-4bf5-ba07-5ad6493620ea
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Как создавать пользовательский диспетчер авторизации для службы
Инфраструктура модели удостоверения в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] поддерживает расширяемую модель авторизации, основанную на утверждениях.Утверждения извлекаются из маркеров, дополнительно обрабатываемых пользовательской политикой авторизации, и затем помещаются в контекст <xref:System.IdentityModel.Policy.AuthorizationContext>.Диспетчер авторизации проверяет утверждения в контексте <xref:System.IdentityModel.Policy.AuthorizationContext> для принятия решений об авторизации.  
  
 По умолчанию решения об авторизации принимаются классом <xref:System.ServiceModel.ServiceAuthorizationManager>; однако эти решения можно переопределить, создав пользовательский диспетчер авторизации.Чтобы создать пользовательский диспетчер авторизации, создайте класс, наследующий от класса <xref:System.ServiceModel.ServiceAuthorizationManager>, и реализуйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.Решения об авторизации принимаются в методе <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, который возвращает `true`, если доступ предоставлен, и `false`, если в доступе отказано.  
  
 Если решение об авторизации зависит от содержимого тела сообщения, используйте метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccess%2A>.  
  
 В связи с вопросами производительности при возможности следует внести изменения в приложение, чтобы решение об авторизации не требовало доступа к телу сообщения.  
  
 Пользовательский диспетчер авторизации для службы можно зарегистрировать в коде или конфигурации.  
  
### Создание пользовательского диспетчера авторизации  
  
1.  Создайте класс, производный от класса <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
     [!code-csharp[c_CustomAuthMgr#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#5)]
     [!code-vb[c_CustomAuthMgr#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#5)]  
  
2.  Переопределите метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.  
  
     Для принятия решения об авторизации используйте метод <xref:System.ServiceModel.OperationContext>, передаваемый в метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%28System.ServiceModel.OperationContext%29>.  
  
     В следующем примере кода метод <xref:System.IdentityModel.Claims.ClaimSet.FindClaims%28System.String%2CSystem.String%29> используется для поиска пользовательского утверждения `http://www.contoso.com/claims/allowedoperation` и принятия решения об авторизации.  
  
     [!code-csharp[c_CustomAuthMgr#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#6)]
     [!code-vb[c_CustomAuthMgr#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#6)]  
  
### Регистрация пользовательского диспетчера авторизации с помощью кода  
  
1.  Создайте экземпляр пользовательского диспетчера авторизации и назначьте его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ServiceAuthorizationManager%2A>.  
  
     Доступ к поведению <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> возможен с помощью свойства <xref:System.ServiceModel.ServiceHostBase.Authorization%2A>.  
  
     В следующем примере кода регистрируется пользовательский диспетчер авторизации `MyServiceAuthorizationManager`.  
  
     [!code-csharp[c_CustomAuthMgr#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#4)]
     [!code-vb[c_CustomAuthMgr#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#4)]  
  
### Регистрация пользовательского диспетчера авторизации с помощью конфигурации  
  
1.  Откройте файл конфигурации службы.  
  
2.  Добавьте элемент [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) в элемент [\<поведения\>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md).  
  
     Добавьте в элемент [\<serviceAuthorization\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) атрибут `serviceAuthorizationManagerType` и установите для него значение типа, представляющего пользовательский диспетчер авторизации.  
  
3.  Добавьте привязку, обеспечивающую безопасность связи между клиентом и службой.  
  
     Привязка, выбранная для этой связи, определяет утверждения, добавляемые в контекст <xref:System.IdentityModel.Policy.AuthorizationContext> и используемые пользовательским диспетчером авторизации для принятия решений об авторизации.Дополнительные сведения о привязках, предоставляемых системой, см. в разделе [Привязки, предоставляемые системой](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
4.  Свяжите поведение с конечной точкой службы, добавив элемент [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) и задав для атрибута `behaviorConfiguration` значение атрибута name элемента [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md).  
  
     Дополнительные сведения о настройке конечной точки службы см. в разделе [Практическое руководство. Создание конечной точки службы в конфигурации](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).  
  
     В следующем примере кода регистрируется пользовательский диспетчер авторизации `Samples.MyServiceAuthorizationManager`.  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.CalculatorService"  
              behaviorConfiguration="CalculatorServiceBehavior">  
            <host>  
              <baseAddresses>  
                <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
              </baseAddresses>  
            </host>  
            <endpoint address=""  
                      binding="wsHttpBinding_Calculator"  
                      contract="Microsoft.ServiceModel.Samples.ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <WSHttpBinding>  
           <binding name = "wsHttpBinding_Calculator">  
             <security mode="Message">  
               <message clientCredentialType="Windows"/>  
             </security>  
            </binding>  
          </WSHttpBinding>  
    </bindings>  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="CalculatorServiceBehavior">  
              <serviceAuthorization serviceAuthorizationManagerType="Samples.MyServiceAuthorizationManager,MyAssembly" />  
             </behavior>  
         </serviceBehaviors>  
       </behaviors>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
    > [!WARNING]
    >  Обратите внимание, что при указании serviceAuthorizationManagerType строка должна содержать полное имя типа.запятую и имя сборки, в которой определен тип.Если опустить имя сборки, WCF попытается загрузить тип из System.ServiceModel.dll.  
  
## Пример  
 В следующем образце кода показана базовая реализация класса <xref:System.ServiceModel.ServiceAuthorizationManager>, которая содержит переопределение метода <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>.В этом примере кода производится проверка <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие пользовательского утверждения и возвращается `true`, если ресурс для этого пользовательского утверждения соответствует значению действия из контекста <xref:System.ServiceModel.OperationContext>.Более полная реализация класса <xref:System.ServiceModel.ServiceAuthorizationManager> содержится в разделе [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
 [!code-csharp[c_CustomAuthMgr#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customauthmgr/cs/c_customauthmgr.cs#2)]
 [!code-vb[c_CustomAuthMgr#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customauthmgr/vb/c_customauthmgr.vb#2)]  
  
## См. также  
 <xref:System.ServiceModel.ServiceAuthorizationManager>   
 [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md)   
 [Политика авторизации](../../../../docs/framework/wcf/samples/authorization-policy.md)