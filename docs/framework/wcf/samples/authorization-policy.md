---
title: Политика авторизации
ms.date: 03/30/2017
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
ms.openlocfilehash: 78ca42abfd2df56edeeb273fcd8ba585aa16f635
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2018
ms.locfileid: "46706558"
---
# <a name="authorization-policy"></a>Политика авторизации

В этом образце показано, как реализовать пользовательскую политику авторизации утверждений и связанный с ней пользовательский диспетчер авторизации службы. Это бывает удобно, если служба осуществляет проверку прав доступа к операциям службы на основании утверждений и предоставляет вызывающей стороне определенные права, прежде чем проверить права доступа. В этом образце показан процесс добавления утверждений, а также процесс проверки прав доступа с использованием готового набора утверждений. Все сообщения приложений, которыми обмениваются служба и клиент, подписываются и шифруются. По умолчанию при использовании привязки `wsHttpBinding` для входа от имени действующей учетной записи Windows NT используются предоставляемые клиентом имя пользователя и пароль. В этом образце показано, как проверять подлинность клиента с помощью пользовательского объекта <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Кроме того, в этом образце показана проверка подлинности клиента на стороне службы с использованием сертификата X.509. Этот образец показывает реализацию объектов <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и <xref:System.ServiceModel.ServiceAuthorizationManager>, которые между собой предоставляют заданным пользователям доступ к определенным методам службы. Этот образец основан на [имя пользователя безопасности сообщения](../../../../docs/framework/wcf/samples/message-security-user-name.md), но показывает, как выполнять преобразование утверждений до <xref:System.ServiceModel.ServiceAuthorizationManager> вызова.

> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.

 Таким образом, в данном образце демонстрируются указанные ниже возможности.

-   Подлинность клиента может проверяться с помощью имени пользователя и пароля.

-   Подлинность клиента может проверяться с помощью сертификата X.509.

-   Сервер проверяет учетные данные клиента с помощью пользовательского проверяющего элемента управления `UsernamePassword`.

-   Сервер проходит проверку подлинности с использованием сертификата X.509 сервера.

-   Сервер может использовать объект <xref:System.ServiceModel.ServiceAuthorizationManager> для управления доступом к определенным методам службы.

-   Реализация политики <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.

Служба предоставляет две конечные точки для взаимодействия со службой, определенной в файле конфигурации App.config. Каждая конечная точка состоит из адреса, привязки и контракта. Одна привязка настраивается с помощью стандартной привязки `wsHttpBinding`, использующей протокол WS-Security и проверку подлинности имени пользователя клиента. Вторая привязка настраивается с помощью стандартной привязки `wsHttpBinding`, использующей протокол WS-Security и проверку подлинности сертификата клиента. [ \<Поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) указывает, что учетные данные пользователя будут использоваться для проверки подлинности службы. Сертификат сервера должен содержать то же значение для `SubjectName` свойство как `findValue` атрибут в [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <!-- configure base address provided by host -->
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service"/>
        </baseAddresses>
      </host>
      <!-- use base address provided by host, provide two endpoints -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <endpoint address="certificate"
                binding="wsHttpBinding"
                bindingConfiguration="Binding2"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
    <message clientCredentialType="UserName" />
        </security>
      </binding>
      <!-- X509 certificate binding -->
      <binding name="Binding2">
        <security mode="Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior" >
        <serviceDebug includeExceptionDetailInFaults ="true" />
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to specify authentication constraints on client certificates.
          -->
          <clientCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
          <!--
          The serviceCredentials behavior allows one to define a service certificate.
          A service certificate is used by a client to authenticate the service and provide message protection.
          This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
        <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
          <!--
          The serviceAuthorization behavior allows one to specify custom authorization policies.
          -->
          <authorizationPolicies>
            <add policyType="Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary" />
          </authorizationPolicies>
        </serviceAuthorization>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

Конфигурация каждой из конечных точек клиента состоит из имени конфигурации, абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с режимом безопасности, как указано в этом случае в [ \<безопасности >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) и `clientCredentialType` как указано в [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
            address="http://localhost:8001/servicemodelsamples/service/username"
    binding="wsHttpBinding"
    bindingConfiguration="Binding1"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator" >
      </endpoint>
      <!-- X509 certificate based endpoint -->
      <endpoint name="Certificate"
                        address="http://localhost:8001/servicemodelsamples/service/certificate"
                binding="wsHttpBinding"
            bindingConfiguration="Binding2"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
      <binding name="Binding1">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
        <!-- X509 certificate binding -->
        <binding name="Binding2">
          <security mode="Message">
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
    </wsHttpBinding>
    </bindings>

    <behaviors>
      <behavior name="ClientCertificateBehavior">
        <clientCredentials>
          <serviceCertificate>
            <!--
            Setting the certificateValidationMode to PeerOrChainTrust
            means that if the certificate
            is in the user's Trusted People store, then it will be
            trusted without performing a
            validation of the certificate's issuer chain. This setting
            is used here for convenience so that the
            sample can be run without having to have certificates
            issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust.
            The security implications of this
            setting should be carefully considered before using
            PeerOrChainTrust in production code.
            -->
            <authentication certificateValidationMode = "PeerOrChainTrust" />
          </serviceCertificate>
        </clientCredentials>
      </behavior>
    </behaviors>

  </system.serviceModel>
```

Для конечной точки, выполняющей проверку подлинности имени пользователя, реализация клиента задает имя пользователя и пароль, которые следует использовать.

```csharp
// Create a client with Username endpoint configuration
CalculatorClient client1 = new CalculatorClient("Username");

client1.ClientCredentials.UserName.UserName = "test1";
client1.ClientCredentials.UserName.Password = "1tset";

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client1.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client1.Close();
```

Для конечной точки, выполняющей проверку подлинности сертификата, реализация клиента задает сертификат клиента, который следует использовать.

```csharp
// Create a client with Certificate endpoint configuration
CalculatorClient client2 = new CalculatorClient("Certificate");

client2.ClientCredentials.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "test1");

try
{
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = client2.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
    ...
}
catch (Exception e)
{
    Console.WriteLine("Call failed : {0}", e.Message);
}

client2.Close();
```

В этом образце для проверки имен пользователей и паролей применяется пользовательский объект <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. В этом образце реализуется класс `MyCustomUserNamePasswordValidator`, наследуемый от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Дополнительные сведения см. в документации по классу <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. В целях демонстрации интеграции с <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> в этом образце пользовательского проверяющего элемента управления реализуется метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, который принимает пары "имя пользователя-пароль", где имя пользователя соответствует паролю, как показано в следующем примере кода.

```csharp
public class MyCustomUserNamePasswordValidator : UserNamePasswordValidator
{
  // This method validates users. It allows in two users,
  // test1 and test2 with passwords 1tset and 2tset respectively.
  // This code is for illustration purposes only and
  // MUST NOT be used in a production environment because it
  // is NOT secure.
  public override void Validate(string userName, string password)
  {
    if (null == userName || null == password)
    {
      throw new ArgumentNullException();
    }

    if (!(userName == "test1" && password == "1tset") && !(userName == "test2" && password == "2tset"))
    {
      throw new SecurityTokenException("Unknown Username or Password");
    }
  }
}
```

После реализации в коде службы проверяющего элемента управления необходимо проинформировать узел службы о проверяющем элементе управления, который следует использовать. Это делается следующим образом:

```csharp
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();
```

Или это можно сделать то же самое в конфигурации:

```xml
<behavior ...>
    <serviceCredentials>
      <!--
      The serviceCredentials behavior allows one to specify a custom validator for username/password combinations.
      -->
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.MyCustomUserNameValidator, service" />
    ...
    </serviceCredentials>
</behavior>
```

Windows Communication Foundation (WCF) предоставляет расширенную модель на основе утверждений для проверки прав доступа. Для контроля прав доступа и проверки, удовлетворяют ли связанные с клиентом удостоверения требованиям, необходимым для доступа к методу службы, используется объект <xref:System.ServiceModel.ServiceAuthorizationManager>.

В целях демонстрации в этом образце показана реализация <xref:System.ServiceModel.ServiceAuthorizationManager> , реализующий <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A> метод, чтобы разрешить доступ пользователей к методам на основе утверждений типа http://example.com/claims/allowedoperation , значение которого представляет собой URI действия операции разрешено вызывать.

```csharp
public class MyServiceAuthorizationManager : ServiceAuthorizationManager
{
  protected override bool CheckAccessCore(OperationContext operationContext)
  {
    string action = operationContext.RequestContext.RequestMessage.Headers.Action;
    Console.WriteLine("action: {0}", action);
    foreach(ClaimSet cs in operationContext.ServiceSecurityContext.AuthorizationContext.ClaimSets)
    {
      if ( cs.Issuer == ClaimSet.System )
      {
        foreach (Claim c in cs.FindClaims("http://example.com/claims/allowedoperation", Rights.PossessProperty))
        {
          Console.WriteLine("resource: {0}", c.Resource.ToString());
          if (action == c.Resource.ToString())
            return true;
        }
      }
    }
    return false;
  }
}
```

После реализации пользовательского объекта <xref:System.ServiceModel.ServiceAuthorizationManager> необходимо проинформировать узел службы об объекте<xref:System.ServiceModel.ServiceAuthorizationManager>, который следует использовать. Это можно сделать с помощью следующего фрагмента кода.

```xml
<behavior ...>
    ...
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">
        ...
    </serviceAuthorization>
</behavior>
```

Основным реализуемым методом <xref:System.IdentityModel.Policy.IAuthorizationPolicy> является метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.

```csharp
public class MyAuthorizationPolicy : IAuthorizationPolicy
{
    string id;

    public MyAuthorizationPolicy()
    {
    id =  Guid.NewGuid().ToString();
    }

    public bool Evaluate(EvaluationContext evaluationContext,
                                            ref object state)
    {
        bool bRet = false;
        CustomAuthState customstate = null;

        if (state == null)
        {
            customstate = new CustomAuthState();
            state = customstate;
        }
        else
            customstate = (CustomAuthState)state;
        Console.WriteLine("In Evaluate");
        if (!customstate.ClaimsAdded)
        {
           IList<Claim> claims = new List<Claim>();

           foreach (ClaimSet cs in evaluationContext.ClaimSets)
              foreach (Claim c in cs.FindClaims(ClaimTypes.Name,
                                         Rights.PossessProperty))
                  foreach (string s in
                        GetAllowedOpList(c.Resource.ToString()))
                  {
                       claims.Add(new
               Claim("http://example.com/claims/allowedoperation",
                                    s, Rights.PossessProperty));
                            Console.WriteLine("Claim added {0}", s);
                      }
                   evaluationContext.AddClaimSet(this,
                           new DefaultClaimSet(this.Issuer,claims));
                   customstate.ClaimsAdded = true;
                   bRet = true;
                }
         else
         {
              bRet = true;
         }
         return bRet;
     }
...
}
```

В приведенном выше примере кода показано, каким образом метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> проверяет, что не было добавлено новых утверждений, которые влияют на обработку, и добавляет нужные утверждения. Разрешенные утверждения получаются из метода `GetAllowedOpList`, реализация которого возвращает заданный список операций, которые разрешено выполнять пользователю. Политика авторизации добавляет утверждения для доступа к определенной операции. Впоследствии эта политика используется объектом <xref:System.ServiceModel.ServiceAuthorizationManager> для принятия решений о предоставлении доступа.

После реализации интерфейса <xref:System.IdentityModel.Policy.IAuthorizationPolicy> необходимо проинформировать узел службы о политиках авторизации, которые следует использовать.

```xml
<serviceAuthorization ...>
       <authorizationPolicies>
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />
       </authorizationPolicies>
</serviceAuthorization>
```

При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Клиент успешно вызывает методы Add, Subtract и Multiple и получает сообщение "Access is denied" при попытке вызывать метод Divide. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

## <a name="setup-batch-file"></a>Пакетный файл Setup

Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.

Ниже представлен краткие общие сведения о различных разделах пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.

-   Создание сертификата сервера.

     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера. Переменная %SERVER_NAME% задает имя сервера. Измените эту переменную, чтобы задать собственное имя сервера. Значением по умолчанию является localhost.

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   Установка сертификата сервера в хранилище доверенных сертификатов клиента.

     Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента. Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы. Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

-   Создание сертификата клиента.

     Следующие строки из файла Setup.bat создают сертификат клиента, который будет использоваться. Переменная %USER_NAME% задает имя сервера. Эта переменная имеет значение "test1", поскольку политика `IAuthorizationPolicy` ищет именно это имя. Если изменить значение переменной %USER_NAME%, необходимо изменить и соответствующее значение в методе `IAuthorizationPolicy.Evaluate`.

     Сертификат хранится в хранилище "My store" (Личном хранилище) в расположении CurrentUser.

    ```
    echo ************
    echo making client cert
    echo ************
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe
    ```

-   Установка сертификата клиента в хранилище доверенных сертификатов сервера.

     Следующие строки из файла Setup.bat копируют сертификат клиента в хранилище доверенных лиц. Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны серверной системы. Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата клиента в хранилище сертификатов сервера не требуется.

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople
    ```

### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца

1. Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

2. Чтобы запустить образец на одном или нескольких компьютерах, следуйте приведенным далее инструкциям.

> [!NOTE]
> Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.

### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере

1. Откройте командную строку разработчика для Visual Studio с правами администратора и запустите *Setup.bat* из папки установки образца. При этом устанавливаются все сертификаты, необходимые для выполнения образца.

    > [!NOTE]
    > Пакетный файл Setup.bat предназначен для запуска из командной строки разработчика для Visual Studio. Переменной среды PATH, задайте в командную строку разработчика для Visual Studio указывает на каталог, содержащий исполняемые файлы, необходимые *Setup.bat* скрипта.

1. Запустите Service.exe из *service\bin*.

1. Запустите Client.exe из *\client\bin*. Действия клиента отображаются в консольном приложении клиента.

  Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).

### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах

1. Создайте каталог на компьютере службы.

2. Скопируйте файлы служебной программы из *\service\bin* в каталог на компьютере службы. Кроме того, скопируйте на компьютер службы файлы Setup.bat, Cleanup.bat, GetComputerName.vbs и ImportClientCert.bat.

3. Создайте на клиентском компьютере каталог для двоичных файлов клиента.

4. Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента. Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.

5. На сервере, запустите `setup.bat service` в командную строку разработчика для Visual Studio, открытой с правами администратора.

   Под управлением `setup.bat` с `service` аргумента создается сертификат службы с полное доменное имя компьютера и экспортируется в файл с именем *Service.cer*.

6. Изменить *Service.exe.config* в соответствии с новым именем сертификата (в `findValue` атрибут в [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)) которого совпадает со значением полное доменное имя на компьютере. Кроме того, изменить **computername** в \<службы > /\<baseAddresses > элемент с localhost на полное доменное имя компьютера службы.

7. Копировать *Service.cer* файла из каталога службы в клиентский каталог на клиентском компьютере.

8. На стороне клиента, выполните `setup.bat client` в командную строку разработчика для Visual Studio, открытой с правами администратора.

   Под управлением `setup.bat` с `client` аргумент создается сертификат клиента с именем **test1** и сертификат клиента будет экспортирован в файл с именем *Client.cer*.

9. В *Client.exe.config* файл на клиентском компьютере, измените значение адреса конечной точки, чтобы соответствовало новому адресу службы. Это можно сделать путем замены **localhost** с полное доменное имя сервера.

10. Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.

11. На стороне клиента, выполните *файл ImportServiceCert.bat* в командную строку разработчика для Visual Studio, открытой с правами администратора.

   Он импортирует сертификат службы из файла Service.cer в **CurrentUser - TrustedPeople** хранения.

12. На сервере, запустите *ImportClientCert.bat* в командную строку разработчика для Visual Studio, открытой с правами администратора.

   Он импортирует сертификат клиента из файла Client.cer в **LocalMachine - TrustedPeople** хранения.

13. На сервере запустите из окна командной строки программу Service.exe.

14. На клиентском компьютере из окна командной строки запустите программу Client.exe.

   Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).

### <a name="clean-up-after-the-sample"></a>Очистка после образца

Очистка после примера, запустите *Cleanup.bat* в папку «samples» после завершения выполнения образца. Он удалит из хранилища сертификатов сертификаты сервера и клиента.

> [!NOTE]
> Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах. Если вы запустили примеры WCF, которые используют сертификаты на компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище CurrentUser - TrustedPeople хранения. Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.