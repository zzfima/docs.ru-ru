---
title: Структура проверки подлинности маркера
ms.date: 03/30/2017
ms.assetid: 84382f2c-f6b1-4c32-82fa-aebc8f6064db
ms.openlocfilehash: 835a158ba668a3aef749602c73fd9157e8d83a40
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425037"
---
# <a name="token-authenticator"></a>Структура проверки подлинности маркера
Данный образец демонстрирует способ реализации пользовательской структуры проверки подлинности маркеров. Средство проверки подлинности маркеров в Windows Communication Foundation (WCF) используется для проверки маркера, используемого с сообщением, проверки его самоединообразия и проверки подлинности удостоверения, связанного с маркером.

 Пользовательские структуры проверки подлинности маркера могут быть полезны в различных случаях, а именно:

- при возникновении необходимости переопределения механизма проверки подлинности по умолчанию, связанного с маркером;

- при построении пользовательского маркера.

 В этом образце демонстрируется следующее:

- как клиент может проходить проверку подлинности с использованием пары "имя пользователя/пароль";

- как сервер может проверить учетные данные клиента с помощью пользовательской структуры проверки подлинности маркера;

- Как код службы WCF связывается с пользовательским средством проверки подлинности маркеров.

- как сервер может проходить проверку подлинности с помощью сертификата X.509 сервера.

 В этом примере также показано, как удостоверение вызывающего объекта доступно из WCF после процесса проверки подлинности пользовательского маркера.

 Служба предоставляет одну конечную точку для взаимодействия со службой, определенной в файле конфигурации App.config. Конечная точка состоит из адреса, привязки и контракта. Привязка настроена со стандартной привязкой `wsHttpBinding`, режимом безопасности, заданным для сообщения - режимом по умолчанию привязки `wsHttpBinding`. В этом образце стандартная привязка `wsHttpBinding` использует проверку подлинности имени пользователя клиента. Кроме того, служба настраивает сертификат службы с помощью поведения `serviceCredentials`. Поведение `securityCredentials` позволяет указать на сертификат службы. Сертификат службы используется клиентом для проверки подлинности службы и обеспечения защиты сообщения. В следующей конфигурации делается ссылка на сертификат localhost, установленный во время установки образца, как описано в инструкциях по установке далее.

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service" />
          </baseAddresses>
        </host>
        <!-- use base address provided by host -->
        <endpoint address=""
                  binding="wsHttpBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
      </service>
    </services>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>

    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceDebug includeExceptionDetailInFaults="False" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
....        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>
```

 Конфигурация конечной точки клиента состоит из имени конфигурации, абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с помощью соответствующих `Mode` и `clientCredentialType`.

```xml
<system.serviceModel>
    <client>
      <endpoint name=""
                address="http://localhost:8000/servicemodelsamples/service"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <binding name="Binding1">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
```

 Реализация клиента задает используемые имя пользователя и пароль.

```csharp
static void Main()
{
     ...
     client.ClientCredentials.UserNamePassword.UserName = username;
     client.ClientCredentials.UserNamePassword.Password = password;
     ...
}
```

## <a name="custom-token-authenticator"></a>Пользовательская структура проверки подлинности маркера
 Для создания структуры проверки подлинности пользовательского маркера выполните следующие действия.

1. Запишите структуру проверки подлинности пользовательского маркера.

     Образец реализует структуру проверки подлинности пользовательского маркера, которая проверяет, что имя пользователя имеет действительный формат адреса электронной почты. Она наследуется от <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator>. Наиболее важным методом в данном классе является <xref:System.IdentityModel.Selectors.UserNameSecurityTokenAuthenticator.ValidateUserNamePasswordCore%28System.String%2CSystem.String%29>. В данном методе структура проверки подлинности проверяет формат имени пользователя, а также имя узла на предмет законности домена. Если оба условия удовлетворены, то возвращается доступная только для чтения коллекция экземпляров <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, которая затем используется для предоставления утверждений, представляющих информацию, хранящуюся внутри маркера имени пользователя.

    ```csharp
    protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateUserNamePasswordCore(string userName, string password)
    {
        if (!ValidateUserNameFormat(userName))
            throw new SecurityTokenValidationException("Incorrect UserName format");

        ClaimSet claimSet = new DefaultClaimSet(ClaimSet.System, new Claim(ClaimTypes.Name, userName, Rights.PossessProperty));
        List<IIdentity> identities = new List<IIdentity>(1);
        identities.Add(new GenericIdentity(userName));
        List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
        policies.Add(new UnconditionalPolicy(ClaimSet.System, claimSet, DateTime.MaxValue.ToUniversalTime(), identities));
        return policies.AsReadOnly();
    }
    ```

2. Предоставьте политику авторизации, возвращаемую пользовательской структурой проверки подлинности маркера.

     В этом образце приводится собственная реализация политики <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, называемой `UnconditionalPolicy`, которая возвращает набор утверждений и удостоверений, которые были переданы ей в ее конструкторе.

    ```csharp
    class UnconditionalPolicy : IAuthorizationPolicy
    {
        String id = Guid.NewGuid().ToString();
        ClaimSet issuer;
        ClaimSet issuance;
        DateTime expirationTime;
        IList<IIdentity> identities;

        public UnconditionalPolicy(ClaimSet issuer, ClaimSet issuance, DateTime expirationTime, IList<IIdentity> identities)
        {
            if (issuer == null)
                throw new ArgumentNullException("issuer");
            if (issuance == null)
                throw new ArgumentNullException("issuance");

            this.issuer = issuer;
            this.issuance = issuance;
            this.identities = identities;
            this.expirationTime = expirationTime;
        }

        public string Id
        {
            get { return this.id; }
        }

        public ClaimSet Issuer
        {
            get { return this.issuer; }
        }

        public DateTime ExpirationTime
        {
            get { return this.expirationTime; }
        }

        public bool Evaluate(EvaluationContext evaluationContext, ref object state)
        {
            evaluationContext.AddToTarget(this, this.issuance);

            if (this.identities != null)
            {
                object value;
                IList<IIdentity> contextIdentities;
                if (!evaluationContext.Properties.TryGetValue("Identities", out value))
                {
                    contextIdentities = new List<IIdentity>(this.identities.Count);
                    evaluationContext.Properties.Add("Identities", contextIdentities);
                }
                else
                {
                    contextIdentities = value as IList<IIdentity>;
                }
                foreach (IIdentity identity in this.identities)
                {
                    contextIdentities.Add(identity);
                }
            }

            evaluationContext.RecordExpirationTime(this.expirationTime);
            return true;
        }
    }
    ```

3. Запишите пользовательский диспетчер маркеров безопасности.

     Класс <xref:System.IdentityModel.Selectors.SecurityTokenManager> используется для создания объекта <xref:System.IdentityModel.Selectors.SecurityTokenAuthenticator> для конкретных объектов <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, которые передаются в него в методе `CreateSecurityTokenAuthenticator`. Диспетчер маркеров безопасности также используется для создания поставщиков маркеров и сериализаторов маркеров. В этом образце они не представлены. В данном образце пользовательский диспетчер маркеров безопасности наследуется от класса <xref:System.ServiceModel.Security.ServiceCredentialsSecurityTokenManager> и переопределяет метод `CreateSecurityTokenAuthenticator`, возвращающий пользовательскую структуру проверки подлинности маркера имени пользователя, когда переданные требования маркера указывают на запрос структуры проверки подлинности имени пользователя.

    ```csharp
    public class MySecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        MyUserNameCredential myUserNameCredential;

        public MySecurityTokenManager(MyUserNameCredential myUserNameCredential)
            : base(myUserNameCredential)
        {
            this.myUserNameCredential = myUserNameCredential;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType ==  SecurityTokenTypes.UserName)
            {
                outOfBandTokenResolver = null;
                return new MyTokenAuthenticator();
            }
            else
            {
                return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
            }
        }
    }
    ```

4. Запишите пользовательские учетные данные службы.

     Класс учетных данных службы используется для представления учетных данных, которые сконфигурированы для службы, и создает диспетчер маркеров безопасности, который используется для получения структур проверки подлинности маркеров, поставщиков маркеров и сериализаторов маркеров.

    ```csharp
    public class MyUserNameCredential : ServiceCredentials
    {

        public MyUserNameCredential()
            : base()
        {
        }

        protected override ServiceCredentials CloneCore()
        {
            return new MyUserNameCredential();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new MySecurityTokenManager(this);
        }

    }
    ```

5. Настройте службу для использования пользовательских учетных данных службы.

     Для того чтобы служба использовала пользовательские учетные данные службы, нужно удалить класс учетных данных службы по умолчанию после перехвата сертификата службы, который уже предварительно настроен в учетных данных службы по умолчанию. Затем необходимо настроить новый экземпляр учетных данных для использования предварительно настроенных сертификатов службы и добавить этот новый экземпляр учетных данных службы в поведения службы.

    ```csharp
    ServiceCredentials sc = serviceHost.Credentials;
    X509Certificate2 cert = sc.ServiceCertificate.Certificate;
    MyUserNameCredential serviceCredential = new MyUserNameCredential();
    serviceCredential.ServiceCertificate.Certificate = cert;
    serviceHost.Description.Behaviors.Remove((typeof(ServiceCredentials)));
    serviceHost.Description.Behaviors.Add(serviceCredential);
    ```

 Для вывода информации об абоненте можно использовать свойство <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>, как показано в следующем коде. Свойство <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> содержит информацию об утверждениях о текущем вызывающем модуле.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
            ServiceSecurityContext.Current.PrimaryIdentity.Name);
     return;
}
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

## <a name="setup-batch-file"></a>Пакетный файл Setup
 Входящий в состав образца пакетный файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера. Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.

 Ниже представлен краткий обзор различных разделов пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.

- Создание сертификата сервера.

     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера. Переменная `%SERVER_NAME%`задает имя сервера. Измените эту переменную, чтобы задать собственное имя сервера. По умолчанию в этом пакетном файле используется имя localhost.

    ```console
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

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

    > [!NOTE]
    > Пакетный файл Setup предназначен для запуска из командной строки Windows SDK. Требуется, чтобы переменная среды MSSDK указывала на каталог, в котором установлен пакет SDK. Эта переменная среды автоматически устанавливается в командной строке Windows SDK.

#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере

1. Запустите setup. bat из папки образца установки в командной строке Visual Studio 2012, открытой с правами администратора. При этом устанавливаются все сертификаты, необходимые для выполнения образца.

    > [!NOTE]
    > Пакетный файл Setup. bat предназначен для запуска из командной строки Visual Studio 2012. Переменная среды PATH, заданная в командной строке Visual Studio 2012, указывает на каталог, содержащий исполняемые файлы, необходимые для сценария Setup. bat.  
  
2. Запустите программу Service.exe из каталога \service\bin.  
  
3. Запустите программу Client.exe из \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
4. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Создайте на компьютере службы каталог для двоичных файлов службы.  
  
2. Скопируйте файлы служебной программы в каталог службы на компьютере службы. Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
3. Необходимо иметь сертификат сервера с именем субъекта, содержащим полное имя домена компьютера. Для отображения этого нового имени сертификата необходимо обновить файл службы App.config. Можно создать его с помощью файла Setup.bat, если переменной `%SERVER_NAME%` присвоено полное имя узла компьютера, на котором будет работать служба. Обратите внимание, что файл Setup. bat необходимо запускать из Командная строка разработчика для Visual Studio, открытой с правами администратора.  
  
4. Скопируйте сертификат сервера в хранилище CurrentUser-TrustedPeople клиента. Это нужно делать только тогда, когда сертификат сервера выдан центром выдачи, которому доверяет клиент.  
  
5. В файле App.config компьютера службы измените значение базового адреса для указания полного имени компьютера вместо localhost.  
  
6. На компьютере службы запустите из командной строки программу service.exe.  
  
7. Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
8. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиентском компьютере из командной строки запустите программу Client.exe.  
  
10. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
1. После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
