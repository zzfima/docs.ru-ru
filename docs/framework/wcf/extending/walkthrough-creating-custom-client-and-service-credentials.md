---
title: "Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы
В этом разделе показано, как реализовать пользовательские учетные данные клиента и службы, и как использовать пользовательские учетные данные из кода приложения.  
  
## Классы расширяемости учетных данных  
 Классы <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> являются основными точками входа для расширяемости безопасности [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Эти классы учетных данных предоставляют интерфейсы API, позволяющие коду приложения задавать учетные данные и преобразовывать типы учетных данных в токены безопасности.\(*Токены безопасности* представляют собой форму передачи учетных данных в сообщениях SOAP.\) Обязанности этих классов учетных данных можно разделить на две области:  
  
-   предоставление интерфейсов API, позволяющих приложениям задавать учетные данные;  
  
-   выступать в качестве фабрики для реализаций <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
 И класс <xref:System.ServiceModel.Description.ClientCredentials>, и класс <xref:System.ServiceModel.Description.ServiceCredentials> наследуют от абстрактного класса <xref:System.ServiceModel.Security.SecurityCredentialsManager>, определяющего контракт для возвращения <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] о классах учетных данных и их месте в архитектуре безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] см. в разделе [Security Architecture](http://msdn.microsoft.com/ru-ru/16593476-d36a-408d-808c-ae6fd483e28f).  
  
 Реализации, предусмотренные по умолчанию в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], поддерживают предоставляемые системой типы учетных данных и создают диспетчер учетных данных, способный обрабатывать эти типы учетных данных.  
  
## Причины для настройки учетных данных  
 Существует несколько причин настраивать классы учетных данных как клиентов, так и служб.Прежде всего это необходимость изменить по умолчанию правила безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в части обработки предоставляемых системой типов учетных данных, особенно по следующим причинам.  
  
-   Изменения, невозможные при использовании других точек расширяемости.  
  
-   Добавление новых типов учетных данных.  
  
-   Добавление новых пользовательских типов токенов безопасности.  
  
 В этом разделе описывается реализация пользовательских учетных данных клиента и службы и их использование из кода приложения.  
  
## Дальнейшие шаги  
 Создание пользовательского класса учетных данных — только первый шаг, поскольку причиной настройки учетных данных является изменение поведения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в части выдачи учетных данных, сериализации токенов безопасности или проверки подлинности.В других подразделах этого раздела описывается создание пользовательских сериализаторов и структур проверки подлинности.В этом отношении создание пользовательского класса учетных данных — первый подраздел серии.Следующие действия \(создание пользовательских сериализаторов и структур проверки подлинности\) можно предпринимать только после создания пользовательских учетных данных.Содержание данного подраздела продолжают следующие подразделы:  
  
-   [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
  
-   [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
  
-   [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
## Процедуры  
  
#### Реализация пользовательских учетных данных клиента  
  
1.  Определите новый класс, производный от класса <xref:System.ServiceModel.Description.ClientCredentials>.  
  
2.  Необязательно.Добавьте новые методы или свойства для новых типов учетных данных.Если новые типы учетных данных не добавляются, пропустите этот шаг.В следующем примере добавляется свойство `CreditCardNumber`.  
  
3.  Переопределите метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A>.Этот метод автоматически вызывается инфраструктурой безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании пользовательских учетных данных клиента.Он отвечает за создание и возвращение экземпляра реализации класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>.  
  
    > [!IMPORTANT]
    >  Важно отметить, что метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> переопределен, чтобы создать пользовательский диспетчер токенов безопасности.Чтобы создать фактический токен безопасности, диспетчер токенов безопасности, производный от <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, должен возвратить пользовательский поставщик токенов безопасности, производный от <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.Если не следовать этому шаблону при создании токенов безопасности, приложение может работать неправильно, если объекты <xref:System.ServiceModel.ChannelFactory> кэшируются \(кэширование применяется по умолчанию в клиентских прокси WCF\). В этом случае также возможна атака с несанкционированным получением прав.Объект пользовательских учетных данных кэшируется в составе <xref:System.ServiceModel.ChannelFactory>.Однако пользовательский объект <xref:System.IdentityModel.Selectors.SecurityTokenManager> создается при каждом вызове, что снижает угрозу безопасности при условии, что в <xref:System.IdentityModel.Selectors.SecurityTokenManager> предусмотрена логика создания токенов.  
  
4.  Переопределите метод <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A>.  
  
     [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
     [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]  
  
#### Реализация пользовательского клиентского диспетчера токенов безопасности  
  
1.  Определите новый класс, производный от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.  
  
2.  Необязательно.Переопределите метод<xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, если <xref:System.IdentityModel.Selectors.SecurityTokenProvider> требуется создать пользовательскую реализацию класса.[!INCLUDE[crabout](../../../../includes/crabout-md.md)]о пользовательских поставщиках токенов безопасности см. в разделе [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
3.  Необязательно.Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29>, если <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> требуется создать пользовательскую реализацию класса.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] структурах проверки пользовательского токена безопасности см. в разделе [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md).  
  
4.  Необязательно.Переопределите метод<xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A>, если требуется создать пользовательскую реализацию класса <xref:System.IdentityModel.Selectors.SecurityTokenSerializer>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)]о пользовательских токенах безопасности и сериализаторах пользовательских токенов безопасности см. в разделе [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
     [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]  
  
#### Использование пользовательских учетных данных клиента из кода приложения  
  
1.  Создайте экземпляр сформированного клиента, представляющий интерфейс службы, или создайте экземпляр <xref:System.ServiceModel.ChannelFactory>, указывающий на службу, с которой требуется обмениваться данными.  
  
2.  Удалите предоставляемое системой поведение учетных данных клиента из коллекции <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, обратиться к которой можно через свойство <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.  
  
3.  Создайте новый экземпляр пользовательского класса учетных данных клиента и добавьте его в коллекцию <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, обратиться к которой можно через свойство <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.  
  
     [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
     [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]  
  
 В приведенной выше процедуре было показано, как использовать учетные данные клиента из кода приложения.Учетные данные [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] также можно настроить с помощью файла конфигурации приложения.Использование конфигурации приложения зачастую предпочтительнее, чем жесткое программирование, поскольку так можно изменять параметры приложения без внесения изменений в исходный код, повторной компиляции и повторного развертывания.  
  
 В следующей процедуре показано, как обеспечить поддержку конфигурации пользовательских учетных данных.  
  
#### Создание обработчика конфигурации для пользовательских учетных данных клиента  
  
1.  Определите новый производный класс от класса <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.  
  
2.  Необязательно.Добавьте свойства для всех дополнительных параметров конфигурации, к которым требуется предоставить доступ через конфигурацию приложения.В приведенном ниже примере добавляется одно свойство с именем `CreditCardNumber`.  
  
3.  Переопределите свойство <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> так, чтобы оно возвращало тип пользовательского класса учетных данных клиента, создаваемый элементом конфигурации.  
  
4.  Переопределите метод <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A>.Этот метод отвечает за создание и возвращение экземпляра пользовательского класса учетных данных на основании параметров, загруженных и файла конфигурации.Вызовите из этого метода базовый метод <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29>, чтобы извлечь предоставляемые системой параметры учетных данных, загруженные в экземпляр пользовательских учетных данных клиента.  
  
5.  Необязательно.Если вы добавляли дополнительные свойства на шаге 2, необходимо переопределить свойство <xref:System.Configuration.ConfigurationElement.Properties%2A> для регистрации дополнительных параметров конфигурации, чтобы они распознавались инфраструктурой конфигураций.Объедините добавленные свойства со свойствами базового класса, чтобы разрешить настройку предоставляемых системой параметров посредством данного элемента конфигурации пользовательских учетных данных клиента.  
  
     [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
     [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]  
  
 После создания класса обработчика конфигурации его можно интегрировать в инфраструктуру конфигураций [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Это позволяет использовать пользовательские учетные данные клиента в элементах поведения конечной точки клиента, как показано в следующей процедуре.  
  
#### Регистрация и использование обработчика конфигурации для пользовательских учетных данных клиента в конфигурации приложения  
  
1.  Добавьте элемент \<`extensions`\> и элемент \<`behaviorExtensions`\> в файл конфигурации.  
  
2.  Добавьте элемент \<`add`\> в элемент \<`behaviorExtensions`\> и присвойте соответствующее значение атрибуту `name`.  
  
3.  Присвойте атрибуту `type` полное имя типа.Включите также имя сборки и другие атрибуты сборки.  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
      </extensions>  
    <system.serviceModel>  
    ```  
  
4.  После регистрации обработчика конфигурации элемент пользовательских учетных данных можно использовать внутри того же файла конфигурации вместо предоставляемого системой элемента \<`clientCredentials`\>.Можно использовать как предоставляемые системой свойства, так и любые новые свойства, добавленные в реализацию обработчика конфигурации.В следующем примере с помощью атрибута `creditCardNumber` задается значение пользовательского свойства.  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="myClientCredentialsBehavior">  
          <myClientCredentials creditCardNumber="123-123-123"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
#### Реализация пользовательских учетных данных службы  
  
1.  Определите новый класс, производный от класса <xref:System.ServiceModel.Description.ServiceCredentials>.  
  
2.  Необязательно.Добавьте новые свойства, чтобы предоставить интерфейсы API для добавляемых новых значений учетных данных.Если новые значения учетных данных не добавляются, пропустите этот шаг.В следующем примере добавляется свойство `AdditionalCertificate`.  
  
3.  Переопределите метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A>.Этот метод автоматически вызывается инфраструктурой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] при использовании пользовательских учетных данных клиента.Он отвечает за создание и возвращение экземпляра реализации класса <xref:System.IdentityModel.Selectors.SecurityTokenManager> \(рассматривается в следующей процедуре\).  
  
4.  Необязательно.Переопределите метод <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A>.Это необходимо только при добавлении новых свойств или внутренних полей в реализацию пользовательских учетных данных клиента.  
  
     [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
     [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]  
  
#### Реализация пользовательского диспетчера токенов безопасности службы  
  
1.  Определите новый класс, производный от класса <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>.  
  
2.  Необязательно.Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A>, если требуется создать пользовательскую реализацию <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)]о пользовательских поставщиках токенов безопасности см. в разделе [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md).  
  
3.  Необязательно.Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>, если требуется создать пользовательскую реализацию <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о структурах проверки пользовательского токена безопасности см. в разделе [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)в разделе.  
  
4.  Необязательно.Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29>, если требуется создать пользовательскую реализацию класса <xref:System.IdentityModel.Selectors.SecurityTokenSerializer>.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] о пользовательских токенах безопасности и их сериализаторах см. в разделе [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md).  
  
     [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
     [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]  
  
#### Использование пользовательских учетных данных службы из кода приложения  
  
1.  Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.  
  
2.  Удалите предоставляемое системой поведение учетных данных службы из коллекции <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.  
  
3.  Создайте новый экземпляр пользовательского класса учетных данных службы и добавьте его в коллекцию <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.  
  
     [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
     [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]  
  
 Добавьте поддержку конфигурации, выполнив действия, описанные ранее в процедурах «`To create a configuration handler for custom client credentials`» и «`To register and use a custom client credentials configuration handler in the application configuration`». Единственное отличие состоит в использовании в качестве базового класса для обработчика конфигурации класса <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> вместо класса <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.После этого элемент пользовательских учетных данных службы можно использовать везде, где используется предоставляемый системой элемент `<serviceCredentials>`.  
  
## См. также  
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ServiceCredentials>   
 <xref:System.ServiceModel.Security.SecurityCredentialsManager>   
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>   
 [Практическое руководство. Создание пользовательского поставщика маркеров безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)   
 [Как создавать пользовательскую структуру проверки подлинности маркера безопасности](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)   
 [Как создавать пользовательский маркер](../../../../docs/framework/wcf/extending/how-to-create-a-custom-token.md)