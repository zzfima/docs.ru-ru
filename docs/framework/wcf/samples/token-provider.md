---
title: Поставщик маркеров
ms.date: 03/30/2017
ms.assetid: 947986cf-9946-4987-84e5-a14678d96edb
ms.openlocfilehash: 6971a70e633f7768c165ee6171fd83f0eefc4183
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425121"
---
# <a name="token-provider"></a>Поставщик маркеров
В этом образце показано, как реализовать пользовательский поставщик маркеров. Поставщик маркеров в Windows Communication Foundation (WCF) используется для предоставления учетных данных инфраструктуре безопасности. Поставщик токенов осуществляет общую проверку цели и выдает соответствующие учетные данные, чтобы инфраструктура безопасности смогла обеспечить защиту сообщения. WCF поставляется с поставщиком маркеров диспетчера учетных данных по умолчанию. WCF также поставляется с поставщиком токена CardSpace. Пользовательские поставщики маркеров полезны в следующих случаях:

- если используется хранилище учетных данных с которым эти поставщики не работают;

- Если вы хотите предоставить собственный настраиваемый механизм для преобразования учетных данных с точки, когда пользователь предоставляет сведения о том, когда клиентская платформа WCF использует учетные данные.

- если строится пользовательский маркер.

 В этом образце показано, как построить поставщик пользовательских маркеров, преобразующий входные данные пользователя в другой формат.

 Итак, этот образец демонстрирует следующее:

- как клиент может проходить проверку подлинности с использованием пары "имя пользователя/пароль";

- как настроить клиент с пользовательским поставщиком маркеров;

- как сервер может проверить учетные данные клиента с помощью пользовательского объекта <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, проверяющего соответствие имени пользователя и пароля;

- как сервер проходит проверку подлинности на клиенте с использованием сертификата X.509.

 В данном образце также показано, как можно получить доступ к удостоверению вызывающего модуля после процесса проверки подлинности пользовательского маркера.

 Служба предоставляет одну конечную точку для взаимодействия со службой, определенной в файле конфигурации App.config. Конечная точка состоит из адреса, привязки и контракта. Привязка настраивается с помощью стандартного элемента `wsHttpBinding`, который по умолчанию использует безопасность сообщений. В этом образце стандартная привязка `wsHttpBinding` использует проверку подлинности имени пользователя клиента. Кроме того, служба настраивает сертификат службы с помощью поведения serviceCredentials. Поведение serviceCredentials позволяет настроить сертификат службы. Сертификат службы используется клиентом для проверки подлинности службы и обеспечения защиты сообщения. В следующей конфигурации делается ссылка на сертификат localhost, установленный во время установки образца, как описано в инструкциях по установке далее.

```xml
<system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <host>
          <baseAddresses>
            <!-- configure base address provided by host -->
            <add baseAddress ="http://localhost:8000/servicemodelsamples/service"/>
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
        -->
          <serviceCredentials>
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
```

 Конфигурация конечной точки клиента состоит из имени конфигурации, абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с помощью соответствующего режима (`Mode`) и типа (`clientCredentialType`) сообщения.

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

 В следующих шагах показано, как разработать пользовательский поставщик маркеров и интегрировать его с платформой безопасности WCF:

1. Создание пользовательского поставщика маркеров.

     В образце реализуется пользовательский поставщик маркеров, получающий имя пользователя и пароль. Пароль должен соответствовать данному имени пользователя. Этот пользовательский поставщик маркеров приводится исключительно с целью демонстрации; его не рекомендуется использовать в реальном развертывании.

     Для выполнения этой задачи пользовательский поставщик маркеров наследует класс <xref:System.IdentityModel.Selectors.SecurityTokenProvider> и переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>. Этот метод создает и возвращает новый маркер `UserNameSecurityToken`.

    ```csharp
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
        // obtain username and password from the user using console window
        string username = GetUserName();
        string password = GetPassword();
        Console.WriteLine("username: {0}", username);

        // return new UserNameSecurityToken containing information obtained from user
        return new UserNameSecurityToken(username, password);
    }
    ```

2. Создание пользовательского диспетчера маркеров безопасности.

     Класс <xref:System.IdentityModel.Selectors.SecurityTokenManager> используется для создания объекта <xref:System.IdentityModel.Selectors.SecurityTokenProvider> для конкретного конструктора <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, который передается в него в методе `CreateSecurityTokenProvider`. Диспетчер маркеров безопасности также используется для создания структур проверки подлинности маркеров и сериализатора маркеров. В этом образце они не представлены. В данном образце пользовательский диспетчер маркеров безопасности наследуется от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> и переопределяет метод `CreateSecurityTokenProvider`, возвращающий пользовательский поставщик маркеров, когда переданные требования маркера указывают на запрос пользовательского поставщика.

    ```csharp
    public class MyUserNameSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        MyUserNameClientCredentials myUserNameClientCredentials;

        public MyUserNameSecurityTokenManager(MyUserNameClientCredentials myUserNameClientCredentials)
            : base(myUserNameClientCredentials)
        {
            this.myUserNameClientCredentials = myUserNameClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // if token requirement matches username token return custom username token provider
            // otherwise use base implementation
            if (tokenRequirement.TokenType == SecurityTokenTypes.UserName)
            {
                return new MyUserNameTokenProvider();
            }
            else
            {
                return base.CreateSecurityTokenProvider(tokenRequirement);
            }
        }
    }
    ```

3. Создание пользовательских учетных данных клиента.

     Класс учетных данных клиента используется для представления учетных данных, которые сконфигурированы для прокси клиента, и создает диспетчер маркеров безопасности, который используется для получения структур проверки подлинности маркеров, поставщиков маркеров и сериализаторов маркеров.

    ```csharp
    public class MyUserNameClientCredentials : ClientCredentials
    {
        public MyUserNameClientCredentials()
            : base()
        {
        }

        protected override ClientCredentials CloneCore()
        {
            return new MyUserNameClientCredentials();
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            // return custom security token manager
            return new MyUserNameSecurityTokenManager(this);
        }
    }
    ```

4. Настройка клиента для использования пользовательских учетных данных клиента.

     Чтобы клиент мог использовать пользовательские учетные данные клиента, образец удаляет класс учетных данных клиента по умолчанию и предоставляет новый класс учетных данных клиента.

    ```csharp
    static void Main()
    {
        // ...
           // Create a client with given client endpoint configuration
          CalculatorClient client = new CalculatorClient();

          // set new credentials
           client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
         client.ChannelFactory.Endpoint.Behaviors.Add(new MyUserNameClientCredentials());
       // ...
    }
    ```

 На стороне службы для вывода информации о вызывающем модуле можно использовать свойство <xref:System.ServiceModel.ServiceSecurityContext.PrimaryIdentity%2A>, как показано в следующем примере кода. Свойство <xref:System.ServiceModel.ServiceSecurityContext.Current%2A> содержит информацию об утверждениях о текущем вызывающем модуле.

```csharp
static void DisplayIdentityInformation()
{
    Console.WriteLine("\t\tSecurity context identity  :  {0}",
        ServiceSecurityContext.Current.PrimaryIdentity.Name);
}
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

## <a name="setup-batch-file"></a>Пакетный файл Setup
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующий сертификат, необходимый для выполнения резидентного приложения, для которого требуется обеспечение безопасности на основе сертификата сервера. Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.

 Ниже представлен краткие общие сведения о различных разделах пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.

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
> Пакетный файл Setup.bat предназначен для запуска из командной строки Windows SDK. Требуется, чтобы переменная среды MSSDK указывала на каталог, в котором установлен пакет SDK. Эта переменная среды автоматически устанавливается в командной строке Windows SDK.

#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца

1. Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).

2. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

#### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере

1. Запустите setup. bat из папки образца установки в командной строке Visual Studio 2012, открытой с правами администратора. При этом устанавливаются все сертификаты, необходимые для выполнения образца.

    > [!NOTE]
    > Пакетный файл Setup. bat предназначен для запуска из командной строки Visual Studio 2012. Переменная среды PATH, заданная в командной строке Visual Studio 2012, указывает на каталог, содержащий исполняемые файлы, необходимые для сценария Setup. bat.  
  
2. Запустите программу Service.exe из каталога \service\bin.  
  
3. Запустите программу Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
4. При запросе имени пользователя введите имя пользователя.  
  
5. При запросе пароля используйте ту же строку, которая была введена при запросе имени пользователя.  
  
6. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Создайте на компьютере службы каталог для двоичных файлов службы.  
  
2. Скопируйте файлы служебной программы в каталог службы на компьютере службы. Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
3. Необходимо иметь сертификат сервера с именем субъекта, содержащим полное имя домена компьютера. Для отображения этого нового имени сертификата необходимо обновить файл Service.exe.config. Сертификат сервера можно создать путем изменения пакетного файла Setup.bat. Обратите внимание, что файл Setup. bat необходимо запускать из Командная строка разработчика для Visual Studio, открытой с правами администратора. Необходимо присвоить переменной `%SERVER_NAME%` полное имя узла компьютера, используемого для размещения службы.  
  
4. Скопируйте сертификат сервера в хранилище CurrentUser-TrustedPeople клиента. Это нужно делать, когда сертификат сервера выдан издателем, которому доверяет клиент.  
  
5. В файле Service.exe.config компьютера службы измените значение базового адреса для указания полного имени компьютера вместо localhost.  
  
6. На компьютере службы запустите из командной строки программу service.exe.  
  
7. Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.  
  
8. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиентском компьютере из командной строки запустите программу `Client.exe`.  
  
10. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
1. После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
