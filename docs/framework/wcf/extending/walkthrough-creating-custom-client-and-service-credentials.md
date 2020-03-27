---
title: Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b5ba5c3-0c6c-48e9-9e46-54acaec443ba
ms.openlocfilehash: ddd9f03e26f7a8345f1070715e4877c533c361fb
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345268"
---
# <a name="walkthrough-creating-custom-client-and-service-credentials"></a>Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы

В этом разделе показано, как реализовать пользовательские учетные данные клиента и службы, и как использовать пользовательские учетные данные из кода приложения.

## <a name="credentials-extensibility-classes"></a>Классы расширяемости учетных данных

<xref:System.ServiceModel.Description.ClientCredentials> Классы <xref:System.ServiceModel.Description.ServiceCredentials> и классы являются основными точками входа в Windows Communication Foundation (WCF) безопасности. Эти классы учетных данных предоставляют интерфейсы API, позволяющие коду приложения задавать учетные данные и преобразовывать типы учетных данных в маркеры безопасности. (*Токены безопасности* — это форма, используемая для передачи информации о учетных данных внутри сообщений SOAP.) Обязанности этих классов учетных данных можно разделить на две области:

- предоставление интерфейсов API, позволяющих приложениям задавать учетные данные;

- выступать в качестве фабрики для реализаций <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

Реализации по умолчанию, представленные в WCF, поддерживают системные типы учетных данных и создают менеджер маркеров безопасности, способный обрабатывать эти типы учетных данных.

## <a name="reasons-to-customize"></a>Причины для настройки учетных данных

Существует причин настраивать классы учетных данных как клиентов, так и служб. В первую очередь это требование об изменении поведения безопасности WCF по умолчанию в отношении обработки системных типов учетных данных, особенно по следующим причинам:

- Изменения, невозможные при использовании других точек расширяемости.

- Добавление новых типов учетных данных.

- Добавление новых пользовательских типов маркеров безопасности.

В этом разделе описывается реализация пользовательских учетных данных клиента и службы и их использование из кода приложения.

## <a name="first-in-a-series"></a>Дальнейшие шаги

Создание класса пользовательских учетных данных является лишь первым шагом, поскольку причина настройки учетных данных заключается в изменении поведения WCF в отношении подготовки учетных данных, сериализации маркеров безопасности или проверки подлинности. В других подразделах этого раздела описывается создание пользовательских сериализаторов и структур проверки подлинности. В этом отношении создание пользовательского класса учетных данных - первый подраздел серии. Следующие действия (создание пользовательских сериализаторов и структур проверки подлинности) можно предпринимать только после создания пользовательских учетных данных. Содержание данного подраздела продолжают следующие подразделы:

- [Практическое руководство. Создание поставщика пользовательских маркеров безопасности](how-to-create-a-custom-security-token-provider.md)

- [Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности](how-to-create-a-custom-security-token-authenticator.md)

- [Как: Создайте пользовательский токен](how-to-create-a-custom-token.md).

## <a name="procedures"></a>Процедуры

#### <a name="to-implement-custom-client-credentials"></a>Реализация пользовательских учетных данных клиента

1. Определите новый класс, производный от класса <xref:System.ServiceModel.Description.ClientCredentials>.

2. Необязательный параметр. Добавьте новые методы или свойства для новых типов учетных данных. Если новые типы учетных данных не добавляются, пропустите этот шаг. В следующем примере добавляется свойство `CreditCardNumber`.

3. Переопределите метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . Этот метод автоматически вызывается инфраструктурой безопасности WCF при использовании пользовательского учетных данных клиента. Он отвечает за создание и возвращение экземпляра реализации класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>.

    > [!IMPORTANT]
    > Важно отметить, что метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> переопределен, чтобы создать пользовательский диспетчер маркеров безопасности. Чтобы создать фактический маркер безопасности, диспетчер маркеров безопасности, производный от <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, должен возвратить пользовательский поставщик маркеров безопасности, производный от <xref:System.IdentityModel.Selectors.SecurityTokenProvider>. Если не следовать этому шаблону при создании маркеров безопасности, приложение может работать неправильно, если объекты <xref:System.ServiceModel.ChannelFactory> кэшируются (кэширование применяется по умолчанию в клиентских прокси WCF). В этом случае также возможна атака с несанкционированным получением прав. Объект пользовательских учетных данных кэшируется в составе <xref:System.ServiceModel.ChannelFactory>. Однако пользовательский объект <xref:System.IdentityModel.Selectors.SecurityTokenManager> создается при каждом вызове, что снижает угрозу безопасности при условии, что в <xref:System.IdentityModel.Selectors.SecurityTokenManager> предусмотрена логика создания маркеров.

4. Переопределите метод <xref:System.ServiceModel.Description.ClientCredentials.CloneCore%2A> .

    [!code-csharp[c_CustomCredentials#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#1)]
    [!code-vb[c_CustomCredentials#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#1)]

#### <a name="to-implement-a-custom-client-security-token-manager"></a>Реализация пользовательского клиентского диспетчера маркеров безопасности

1. Определите новый производный класс на основе класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>.

2. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, если <xref:System.IdentityModel.Selectors.SecurityTokenProvider> требуется создать пользовательскую реализацию класса. Для получения дополнительной информации о пользовательских поставщиков токенов безопасности [см.](how-to-create-a-custom-security-token-provider.md)

3. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%28System.IdentityModel.Selectors.SecurityTokenRequirement%2CSystem.IdentityModel.Selectors.SecurityTokenResolver%40%29>, если <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> требуется создать пользовательскую реализацию класса. Для получения дополнительной информации о пользовательских маркерных маркеров безопасности, [см.](how-to-create-a-custom-security-token-authenticator.md)

4. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%2A>, если требуется создать пользовательскую реализацию класса <xref:System.IdentityModel.Selectors.SecurityTokenSerializer>. Для получения дополнительной информации о пользовательских маркеров безопасности и пользовательских серийных маркеров безопасности, [см.](how-to-create-a-custom-token.md)

    [!code-csharp[c_CustomCredentials#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#2)]
    [!code-vb[c_CustomCredentials#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#2)]

#### <a name="to-use-a-custom-client-credentials-from-application-code"></a>Использование пользовательских учетных данных клиента из кода приложения

1. Создайте экземпляр сформированного клиента, представляющий интерфейс службы, или создайте экземпляр <xref:System.ServiceModel.ChannelFactory>, указывающий на службу, с которой требуется обмениваться данными.

2. Удалите предоставляемое системой поведение учетных данных клиента из коллекции <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, обратиться к которой можно через свойство <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

3. Создайте новый экземпляр пользовательского класса учетных данных клиента и добавьте его в коллекцию <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>, обратиться к которой можно через свойство <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>.

    [!code-csharp[c_CustomCredentials#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#3)]
    [!code-vb[c_CustomCredentials#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/client/client.vb#3)]

В приведенной выше процедуре было показано, как использовать учетные данные клиента из кода приложения. Учетные данные WCF также могут быть настроены с помощью файла конфигурации приложения. Использование конфигурации приложения зачастую предпочтительнее, чем жесткое программирование, поскольку так можно изменять параметры приложения без внесения изменений в исходный код, повторной компиляции и повторного развертывания.

В следующей процедуре показано, как обеспечить поддержку конфигурации пользовательских учетных данных.

#### <a name="creating-a-configuration-handler-for-custom-client-credentials"></a>Создание обработчика конфигурации для пользовательских учетных данных клиента

1. Определите новый производный класс на основе класса <xref:System.ServiceModel.Configuration.ClientCredentialsElement>.

2. Необязательный параметр. Добавьте свойства для всех дополнительных параметров конфигурации, к которым требуется предоставить доступ через конфигурацию приложения. В приведенном ниже примере добавляется одно свойство с именем `CreditCardNumber`.

3. Переопределите свойство <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.BehaviorType%2A> так, чтобы оно возвращало тип пользовательского класса учетных данных клиента, создаваемый элементом конфигурации.

4. Переопределите метод <xref:System.ServiceModel.Configuration.BehaviorExtensionElement.CreateBehavior%2A> . Этот метод отвечает за создание и возвращение экземпляра пользовательского класса учетных данных на основании параметров, загруженных и файла конфигурации. Вызовите из этого метода базовый метод <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ApplyConfiguration%28System.ServiceModel.Description.ClientCredentials%29>, чтобы извлечь предоставляемые системой параметры учетных данных, загруженные в экземпляр пользовательских учетных данных клиента.

5. Необязательный параметр. Если вы добавляли дополнительные свойства на шаге 2, необходимо переопределить свойство <xref:System.Configuration.ConfigurationElement.Properties%2A> для регистрации дополнительных параметров конфигурации, чтобы они распознавались инфраструктурой конфигураций. Объедините добавленные свойства со свойствами базового класса, чтобы разрешить настройку предоставляемых системой параметров посредством данного элемента конфигурации пользовательских учетных данных клиента.

    [!code-csharp[c_CustomCredentials#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#7)]
    [!code-vb[c_CustomCredentials#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#7)]

Если у вас есть класс обработчика конфигурации, он может быть интегрирован в структуру конфигурации WCF. Это позволяет использовать пользовательские учетные данные клиента в элементах поведения конечной точки клиента, как показано в следующей процедуре.

#### <a name="to-register-and-use-a-custom-client-credentials-configuration-handler-in-the-application-configuration"></a>Регистрация и использование обработчика конфигурации для пользовательских учетных данных клиента в конфигурации приложения

1. Добавьте `extensions` в файл конфигурации элемент <> и элемент <`behaviorExtensions`>.

2. Добавьте `add` элемент <> `behaviorExtensions` элемент <`name`> элемент и установите атрибут в соответствующее значение.

3. Присвойте атрибуту `type` полное имя типа. Включите также имя сборки и другие атрибуты сборки.

    ```xml
    <system.serviceModel>
      <extensions>
        <behaviorExtensions>
          <add name="myClientCredentials" type="Microsoft.ServiceModel.Samples.MyClientCredentialsConfigHandler, CustomCredentials, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
        </behaviorExtensions>
      </extensions>
    </system.serviceModel>
    ```

4. После регистрации обработчика конфигурации элемент пользовательских учетных данных может быть `clientCredentials` использован в одном и том же файле конфигурации вместо системного <> элемента. Можно использовать как предоставляемые системой свойства, так и любые новые свойства, добавленные в реализацию обработчика конфигурации. В следующем примере с помощью атрибута `creditCardNumber` задается значение пользовательского свойства.

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="myClientCredentialsBehavior">
          <myClientCredentials creditCardNumber="123-123-123"/>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

#### <a name="to-implement-custom-service-credentials"></a>Реализация пользовательских учетных данных службы

1. Определите новый производный класс на основе класса <xref:System.ServiceModel.Description.ServiceCredentials>.

2. Необязательный параметр. Добавьте новые свойства, чтобы предоставить интерфейсы API для добавляемых новых значений учетных данных. Если новые значения учетных данных не добавляются, пропустите этот шаг. В следующем примере добавляется свойство `AdditionalCertificate`.

3. Переопределите метод <xref:System.ServiceModel.Security.SecurityCredentialsManager.CreateSecurityTokenManager%2A> . Этот метод автоматически вызывается инфраструктурой WCF при использовании пользовательского учетных данных клиента. Он отвечает за создание и возвращение экземпляра реализации класса <xref:System.IdentityModel.Selectors.SecurityTokenManager> (рассматривается в следующей процедуре).

4. Необязательный параметр. Переопределите метод <xref:System.ServiceModel.Description.ServiceCredentials.CloneCore%2A> . Это необходимо только при добавлении новых свойств или внутренних полей в реализацию пользовательских учетных данных клиента.

    [!code-csharp[c_CustomCredentials#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#4)]
    [!code-vb[c_CustomCredentials#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#4)]

#### <a name="to-implement-a-custom-service-security-token-manager"></a>Реализация пользовательского диспетчера маркеров безопасности службы

1. Определите новый класс, производный от класса <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager>.

2. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%2A>, если <xref:System.IdentityModel.Selectors.SecurityTokenProvider> требуется создать пользовательскую реализацию класса. Для получения дополнительной информации о пользовательских поставщиков токенов безопасности [см.](how-to-create-a-custom-security-token-provider.md)

3. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenAuthenticator%2A>, если <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> требуется создать пользовательскую реализацию класса. Для получения дополнительной информации о пользовательских маркерных маркеров, [см.](how-to-create-a-custom-security-token-authenticator.md)

4. Необязательный параметр. Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenSerializer%28System.IdentityModel.Selectors.SecurityTokenVersion%29>, если требуется создать пользовательскую реализацию класса <xref:System.IdentityModel.Selectors.SecurityTokenSerializer>. Для получения дополнительной информации о пользовательских маркеров безопасности и пользовательских серийных маркеров безопасности, [см.](how-to-create-a-custom-token.md)

    [!code-csharp[c_CustomCredentials#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#5)]
    [!code-vb[c_CustomCredentials#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#5)]

#### <a name="to-use-custom-service-credentials-from-application-code"></a>Использование пользовательских учетных данных службы из кода приложения

1. Создайте экземпляр <xref:System.ServiceModel.ServiceHost>.

2. Удалите предоставляемое системой поведение учетных данных службы из коллекции <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

3. Создайте новый экземпляр пользовательского класса учетных данных службы и добавьте его в коллекцию <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A>.

    [!code-csharp[c_CustomCredentials#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customcredentials/cs/source.cs#6)]
    [!code-vb[c_CustomCredentials#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customcredentials/vb/service/service.vb#6)]

Добавить поддержку конфигурации, используя шаги, описанные ранее в процедурах "`To create a configuration handler for custom client credentials`и "`To register and use a custom client credentials configuration handler in the application configuration` Разница лишь в том, чтобы использовать <xref:System.ServiceModel.Configuration.ServiceCredentialsElement> класс вместо <xref:System.ServiceModel.Configuration.ClientCredentialsElement> класса в качестве базового класса для обработчика конфигурации. После этого элемент пользовательских учетных данных службы можно использовать везде, где используется предоставляемый системой элемент `<serviceCredentials>`.

## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ServiceCredentials>
- <xref:System.ServiceModel.Security.SecurityCredentialsManager>
- <xref:System.IdentityModel.Selectors.SecurityTokenManager>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement>
- [Практическое руководство. Создание поставщика пользовательских маркеров безопасности](how-to-create-a-custom-security-token-provider.md)
- [Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности](how-to-create-a-custom-security-token-authenticator.md)
- [Практическое руководство. Создание пользовательского токена](how-to-create-a-custom-token.md)
