---
title: Пользовательский маркер
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 11b89f6d4f2800f079ba6576801b39c85324f6e0
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "67425070"
---
# <a name="custom-token"></a>Пользовательский маркер
В этом примере демонстрируется добавление пользовательской реализации маркера в приложение Windows Communication Foundation (WCF). В этом примере маркер `CreditCardToken` используется для безопасной передачи информации о кредитных картах клиента в службу. Маркер передается в заголовок сообщения WS-Security, подписывается и шифруется с помощью симметричного элемента привязки безопасности вместе с телом и другими заголовками сообщения. Это полезно в случаях, когда встроенных маркеров недостаточно. В этом образце показано, как предоставить пользовательский маркер безопасности службы вместо того, чтобы использовать встроенные маркеры. Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".

> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

 Итак, этот образец демонстрирует следующее:

- как клиент может передать в службу пользовательские маркеры безопасности;

- как служба может использовать и проверить пользовательский маркер безопасности;

- Как код службы WCF можно получить сведения о полученных маркерах безопасности включая пользовательского маркера безопасности.

- как сертификат X.509 сервера используется для защиты симметричного ключа, служащего для шифрования и подписывания сообщений.

## <a name="client-authentication-using-a-custom-security-token"></a>Проверка подлинности клиента с помощью пользовательского маркера безопасности
 Служба предоставляет одну конечную точку, создаваемую программно с помощью классов `BindingHelper` и `EchoServiceHost`. Конечная точка состоит из адреса, привязки и контракта. Привязка настраивается с пользовательской привязкой с помощью элементов `SymmetricSecurityBindingElement` и `HttpTransportBindingElement`. В этом образце элементу `SymmetricSecurityBindingElement` задается использование сертификата X.509 службы для защиты симметричного ключа во время передачи и для передачи пользовательского маркера `CreditCardToken` в заголовке сообщения WS-Security в виде подписанного и зашифрованного маркера безопасности. Поведение задает учетные данные службы, которые должны использоваться для проверки подлинности клиента, а также информацию о сертификате X.509 службы.

```csharp
public static class BindingHelper
{
    public static Binding CreateCreditCardBinding()
    {
        HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

        // The message security binding element will be configured to require a credit card.
        // The token that is encrypted with the service's certificate.
        SymmetricSecurityBindingElement messageSecurity = new SymmetricSecurityBindingElement();
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;
        return new CustomBinding(messageSecurity, httpTransport);
    }
}
```

 Чтобы реализовать возможность использования в сообщении маркера кредитной карты, в образце используются пользовательские учетные данные службы. Класс учетных данных службы располагается в классе `CreditCardServiceCredentials` и добавляется к коллекциям поведений узла службы в методе `EchoServiceHost.InitializeRuntime`.

```csharp
class EchoServiceHost : ServiceHost
{
    string creditCardFile;

    public EchoServiceHost(parameters Uri[] addresses)
        : base(typeof(EchoService), addresses)
    {
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];
        if (string.IsNullOrEmpty(creditCardFile))
        {
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");
        }

        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);
    }

    override protected void InitializeRuntime()
    {
        // Create a credit card service credentials and add it to the behaviors.
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));
        this.Description.Behaviors.Add(serviceCredentials);

        // Register a credit card binding for the endpoint.
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);

        base.InitializeRuntime();
    }
}
```

 Конечная точка клиента настраивается таким же образом, как и конечная точка службы. Для создания привязки в клиенте используется этот же класс `BindingHelper`. Остальная часть настройки находится в классе `Client`. Клиент в коде настройки также задает сведения, которые должны содержаться в `CreditCardToken`, и сведения о сертификате X.509 службы посредством добавления экземпляра `CreditCardClientCredentials` с соответствующими данными в коллекцию поведений конечной точки клиента. В этом образце в качестве сертификата службы используется сертификат X.509 службы, которому задано значение `CN=localhost`.

```csharp
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
EndpointAddress serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");

// Create a client with given client endpoint configuration
channelFactory = new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);

// configure the credit card credentials on the channel factory
CreditCardClientCredentials credentials =
      new CreditCardClientCredentials(
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));
// configure the service certificate on the credentials
credentials.ServiceCertificate.SetDefaultCertificate(
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);

// replace ClientCredentials with CreditCardClientCredentials
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
channelFactory.Endpoint.Behaviors.Add(credentials);

client = channelFactory.CreateChannel();

Console.WriteLine("Echo service returned: {0}", client.Echo());

((IChannel)client).Close();
channelFactory.Close();
```

## <a name="custom-security-token-implementation"></a>Реализация пользовательского маркера безопасности
 Чтобы включить пользовательский маркер безопасности в WCF, создайте представление объекта пользовательского маркера безопасности. В этом образце представление находится в классе `CreditCardToken`. Представление объекта отвечает за хранение всех данных, относящихся к маркеру безопасности, и предоставление списка ключей безопасности, содержащихся в маркере безопасности. В этом случае маркер безопасности кредитной карты не содержит ключ безопасности.

 В следующем разделе описывается, что необходимо предпринять, чтобы включить пользовательский маркер, передаваемых по сети и использовать конечную точку WCF.

```csharp
class CreditCardToken : SecurityToken
{
    CreditCardInfo cardInfo;
    DateTime effectiveTime = DateTime.UtcNow;
    string id;
    ReadOnlyCollection<SecurityKey> securityKeys;

    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }

    public CreditCardToken(CreditCardInfo cardInfo, string id)
    {
        if (cardInfo == null)
            throw new ArgumentNullException("cardInfo");

        if (id == null)
            throw new ArgumentNullException("id");

        this.cardInfo = cardInfo;
        this.id = id;

        // The credit card token is not capable of any cryptography.
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());
    }

    public CreditCardInfo CardInfo { get { return this.cardInfo; } }

    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }

    public override DateTime ValidFrom { get { return this.effectiveTime; } }
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }
    public override string Id { get { return this.id; } }
}
```

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a>Возвращение пользовательского маркера кредитной карты в сообщение и из сообщения
 Сериализаторы маркеров безопасности в WCF отвечают за создание объектное представление маркера безопасности из XML в сообщении и создание XML-форм маркеров безопасности. Они также выполняют другие действия, такие как чтение и запись идентификаторов ключей, указывающих на маркеры безопасности, но в этом примере используются только функции, связанные с маркерами безопасности. Чтобы включить пользовательский маркер необходимо реализовать собственный сериализатор маркеров безопасности. В этом образце для этой цели используется класс `CreditCardSecurityTokenSerializer`.

 На стороне службы пользовательский сериализатор считывает XML-форму пользовательского маркера и создает из нее представление объекта пользовательского маркера.

 На стороне клиента класс `CreditCardSecurityTokenSerializer` записывает данные, содержащиеся в представлении объекта маркера безопасности, в средство записи XML.

```csharp
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer
{
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }

    protected override bool CanReadTokenCore(XmlReader reader)
    {
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);

        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
            return true;

        return base.CanReadTokenCore(reader);
    }

    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)
    {
        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
        {
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);

            reader.ReadStartElement();

            // Read the credit card number.
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);

            // Read the expiration date.
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);

            // Read the issuer of the credit card.
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);
            reader.ReadEndElement();

            CreditCardInfo cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);

            return new CreditCardToken(cardInfo, id);
        }
        else
        {
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);
        }
    }

    protected override bool CanWriteTokenCore(SecurityToken token)
    {
        if (token is CreditCardToken)
            return true;

        else
            return base.CanWriteTokenCore(token);
    }

    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)
    {
        if (writer == null) { throw new ArgumentNullException("writer"); }
        if (token == null) { throw new ArgumentNullException("token"); }

        CreditCardToken c = token as CreditCardToken;
        if (c != null)
        {
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);
            writer.WriteEndElement();
            writer.Flush();
        }
        else
        {
            base.WriteTokenCore(writer, token);
        }
    }
}
```

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a>Создание поставщика маркеров и классов структуры проверки подлинности маркеров
 Учетные данные клиента и службы отвечают за предоставление экземпляра диспетчера маркера безопасности. Экземпляр диспетчера маркера безопасности используется для возвращения поставщиков, структур проверки подлинности и сериализаторов маркеров.

 Поставщик маркеров создает представление объекта маркера на основании сведений учетных данных клиента или службы. Затем представление объекта маркера записывается в сообщение с помощью сериализатора маркеров (об этом говорится в предыдущем разделе).

 Структура проверки подлинности маркеров проверяет маркеры, получаемые в сообщении. Сериализатор маркера создает представление объекта входящего маркера. Это представление объекта затем передается в структуру проверки подлинности маркеров для проверки. После успешной проверки маркера структура проверки подлинности возвращает коллекцию объектов `IAuthorizationPolicy`, представляющих сведения, содержащиеся в маркере. Эти сведения затем используются при обработке сообщения для принятия решений об авторизации и предоставления утверждений для приложения. В этом примере с этой целью структура проверки подлинности маркера кредитной карты использует `CreditCardTokenAuthorizationPolicy`.

 Сериализатор маркеров отвечает за возвращение представления объекта маркера в сеть и из сети. Об этом говорилось в предыдущем разделе.

 В этом образце поставщик маркеров используется только на стороне клиента, а структура проверки подлинности только на стороне службы, поскольку маркер кредитной карты требуется передать только в направлении от клиента к службе.

 Функции на стороне клиента находятся в классах `CreditCardClientCredentials`, `CreditCardClientCredentialsSecurityTokenManager` и `CreditCardTokenProvider`.

 Функции на стороне службы находятся в классах `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` и `CreditCardTokenAuthorizationPolicy`.

```csharp
    public class CreditCardClientCredentials : ClientCredentials
    {
        CreditCardInfo creditCardInfo;

        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)
            : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException("creditCardInfo");

            this.creditCardInfo = creditCardInfo;
        }

        public CreditCardInfo CreditCardInfo
        {
            get { return this.creditCardInfo; }
        }

        protected override ClientCredentials CloneCore()
        {
            return new CreditCardClientCredentials(this.creditCardInfo);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardClientCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        CreditCardClientCredentials creditCardClientCredentials;

        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)
            : base (creditCardClientCredentials)
        {
            this.creditCardClientCredentials = creditCardClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // handle this token for Custom
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);
            // return server cert
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)
            {
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)
                {
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);
                }
            }

            return base.CreateSecurityTokenProvider(tokenRequirement);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {

            return new CreditCardSecurityTokenSerializer(version);
        }

    }

    class CreditCardTokenProvider : SecurityTokenProvider
    {
        CreditCardInfo creditCardInfo;

        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()
        {
            if (creditCardInfo == null)
            {
                throw new ArgumentNullException("creditCardInfo");
            }
            this.creditCardInfo = creditCardInfo;
        }

        protected override SecurityToken GetTokenCore(TimeSpan timeout)
        {
            SecurityToken result = new CreditCardToken(this.creditCardInfo);
            return result;
        }
    }

    public class CreditCardServiceCredentials : ServiceCredentials
    {
        string creditCardFile;

        public CreditCardServiceCredentials(string creditCardFile)
            : base()
        {
            if (creditCardFile == null)
                throw new ArgumentNullException("creditCardFile");

            this.creditCardFile = creditCardFile;
        }

        public string CreditCardDataFile
        {
            get { return this.creditCardFile; }
        }

        protected override ServiceCredentials CloneCore()
        {
            return new CreditCardServiceCredentials(this.creditCardFile);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardServiceCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        CreditCardServiceCredentials creditCardServiceCredentials;

        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)
            : base(creditCardServiceCredentials)
        {
            this.creditCardServiceCredentials = creditCardServiceCredentials;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
            {
                outOfBandTokenResolver = null;
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);
            }

            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {
            return new CreditCardSecurityTokenSerializer(version);
        }
    }

    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator
    {
        string creditCardsFile;
        public CreditCardTokenAuthenticator(string creditCardsFile)
        {
            this.creditCardsFile = creditCardsFile;
        }

        protected override bool CanValidateTokenCore(SecurityToken token)
        {
            return (token is CreditCardToken);
        }

        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)
        {
            CreditCardToken creditCardToken = token as CreditCardToken;

            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)
                throw new SecurityTokenValidationException("The credit card has expired");
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))
                throw new SecurityTokenValidationException("Unknown or invalid credit card");

            // the credit card token has only 1 claim - the card number. The issuer for the claim is the
            // credit card issuer

            DefaultClaimSet cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));
            DefaultClaimSet cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));
            List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));
            return policies.AsReadOnly();
        }

        /// <summary>
        /// Helper method to check if a given credit card entry is present in the User DB
        /// </summary>
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)
        {
            try
            {
                using (StreamReader myStreamReader = new StreamReader(this.creditCardsFile))
                {
                    string line = "";
                    while ((line = myStreamReader.ReadLine()) != null)
                    {
                        string[] splitEntry = line.Split('#');
                        if (splitEntry[0] == cardInfo.CardNumber)
                        {
                            string expirationDateString = splitEntry[1].Trim();
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);
                            if (cardInfo.ExpirationDate == expirationDateOnFile)
                            {
                                string issuer = splitEntry[2];
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);
                            }
                            else
                            {
                                return false;
                            }
                        }
                    }
                    return false;
                }
            }
            catch (Exception e)
            {
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());
            }
        }
    }

    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy
    {
        string id;
        ClaimSet issuer;
        IEnumerable<ClaimSet> issuedClaimSets;

        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)
        {
            if (issuedClaims == null)
                throw new ArgumentNullException("issuedClaims");
            this.issuer = issuedClaims.Issuer;
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };
            this.id = Guid.NewGuid().ToString();
        }

        public ClaimSet Issuer { get { return this.issuer; } }

        public string Id { get { return this.id; } }

        public bool Evaluate(EvaluationContext context, ref object state)
        {
            foreach (ClaimSet issuance in this.issuedClaimSets)
            {
                context.AddClaimSet(this, issuance);
            }

            return true;
        }
    }
```

## <a name="displaying-the-callers-information"></a>Отображение информации об абоненте
 Для вывода информации об абоненте можно использовать свойство `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets`, как показано в следующем коде. Свойство `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` содержит утверждения авторизации, связанные с текущим абонентом. Утверждения предоставляются классом `CreditCardToken` в его коллекции `AuthorizationPolicies`.

```csharp
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)
{
    claimValue = null;
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
        return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    enumerator.MoveNext();
    claimValue = (enumerator.Current.Resource == null) ? null :
        enumerator.Current.Resource.ToString();
    return true;
}

string GetCallerCreditCardNumber()
{
     foreach (ClaimSet claimSet in
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)
     {
         string creditCardNumber = null;
         if (TryGetStringClaimValue(claimSet,
             Constants.CreditCardNumberClaim, out creditCardNumber))
             {
                 string issuer;
                 if (!TryGetStringClaimValue(claimSet.Issuer,
                        ClaimTypes.Name, out issuer))
                 {
                     issuer = "Unknown";
                 }
                 return $"Credit card '{creditCardNumber}' issued by '{issuer}'";
        }
    }
    return "Credit card is not known";
}
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

## <a name="setup-batch-file"></a>Пакетный файл Setup
 Входящий в состав образца пакетный файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения приложения, размещенного в службах IIS, которое требует обеспечения безопасности на основе сертификата сервера. Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.

 Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.

- Создание сертификата сервера.

     Следующие строки из файла `Setup.bat` создают используемый в дальнейшем сертификат сервера. Переменная `%SERVER_NAME%`задает имя сервера. Измените эту переменную, чтобы задать собственное имя сервера. По умолчанию в этом пакетном файле используется имя localhost. При изменении переменной `%SERVER_NAME%` требуется заменить все вхождения "localhost" в файлах Client.cs и Service.cs именем сервера, используемым в скрипте Setup.bat.

     Сертификат хранится в хранилище "My store" (Личном хранилище) в расположении `LocalMachine`. Для служб, размещенных в службах IIS, сертификат хранится в хранилище LocalMachine. Для резидентных служб необходимо изменить пакетный файл, чтобы сертификат клиента хранился в местоположении хранения CurrentUser, заменив строку LocalMachine строкой CurrentUser.

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

- Установка сертификата сервера в хранилище доверенных сертификатов клиента.

     Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента. Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы. Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.

    ```
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- Чтобы разрешить доступ к закрытому ключу сертификата из службы, размещенной в службах IIS, учетной записи пользователя, под которой выполняется процесс, размещенный в службах IIS, должны быть предоставлены соответствующие разрешения для закрытого ключа. Это производится в последних шагах скрипта Setup.bat.

    ```
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
>  Пакетный файл Setup.bat предназначен для запуска из командной строки с 2012 Visual Studio. Набор переменных среды в командной строке Visual Studio 2012 путь указывает на каталог, содержащий исполняемые файлы, необходимые для скрипта Setup.bat.

#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца

1. Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере

1. Откройте окно командной строки Visual Studio 2012 с правами администратора и запустите файл Setup.bat из папки установки образца. При этом устанавливаются все сертификаты, необходимые для выполнения образца. Убедитесь, что папка, в которой находится файл Makecert.exe, входит в путь поиска.

> [!NOTE]
>  После завершения работы с образцом для удаления сертификатов обязательно запустите файл Cleanup.bat. В других образцах обеспечения безопасности используются те же сертификаты.  
  
1. Запустите Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
2. Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок для образцов WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computer"></a>Выполнение образца на нескольких компьютерах  
  
1. Создайте на компьютере службы каталог для двоичных файлов службы.  
  
2. Скопируйте файлы служебной программы в каталог службы на компьютере службы. Не забудьте скопировать файл CreditCardFile.txt; в противном случае структура проверки подлинности кредитной карты не сможет выполнить проверку подлинности данных кредитной карты, отправленных клиентом. Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
3. Необходимо иметь сертификат сервера с именем субъекта, содержащим полное имя домена компьютера. Можно создать его с помощью файла Setup.bat, если заменить имя переменной `%SERVER_NAME%` полным именем компьютера, на котором будет размещаться служба. Обратите внимание на то, что файл Setup.bat нужно запускать в командной строке разработчика для Visual Studio, открытой с правами администратора.  
  
4. Скопируйте сертификат сервера в хранилище CurrentUser-TrustedPeople на стороне клиента. Это необходимо сделать только в том случае, если сертификат сервера не был выдан доверенным издателем.  
  
5. В файле EchoServiceHost.cs измените значение имени субъекта сертификата, чтобы указать полное имя компьютера вместо localhost.  
  
6. Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
7. В файле Client.cs измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
8. В файле Client.cs измените значение имени субъекта сертификата X.509 службы, чтобы оно соответствовало полному имени компьютера удаленного узла вместо localhost.  
  
9. На клиентском компьютере из окна командной строки запустите программу Client.exe.  
  
10. Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок для образцов WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
1. После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
