---
title: Проверяющий элемент управления для имен пользователей и паролей
ms.date: 03/30/2017
ms.assetid: 42f03841-286b-42d8-ba58-18c75422bc8e
ms.openlocfilehash: 553ccd69a02e057c5131128378611a19502e713d
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424159"
---
# <a name="user-name-password-validator"></a>Проверяющий элемент управления для имен пользователей и паролей
В этом образце показано, как реализовать пользовательский проверяющий элемент управления UserNamePassword. Это бывает полезно в случаях, когда ни один из встроенных режимов проверки имени пользователя и пароля не соответствует требования приложениям, например, когда пары "имя пользователя-пароль" хранятся во внешнем хранилище, например в базе данных. В этом образце показана служба, имеющая пользовательский проверяющий элемент управления, который проверяет две конкретных пары "имя пользователя-пароль". Клиент использует такие пары "имя пользователя-пароль" для проверки подлинности у службы.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\UserNamePasswordValidator`  
  
> [!NOTE]
> Поскольку учетные данные имени пользователя, использующие пары "имя пользователя-пароль", принимаемые пользовательским проверяющим элементом управления, могут создаваться кем угодно, такая служба является менее безопасной по сравнению с поведением по умолчанию, которое предоставляется стандартным проверяющим элементом управления UserNamePassword. Стандартный проверяющий элемент управления UserNamePassword предпринимает попытку сопоставить заданную пару "имя пользователя-пароль" с учетной записью Windows, и если выполнить такое сопоставление не удается, проверка подлинности завершается неудачно. Пользовательский проверяющий элемент управления UserNamePassword в этом образце НЕ ДОЛЖЕН использоваться в рабочей среде; он предназначен только для иллюстрации.

 Таким образом, в этом образце демонстрируются указанные ниже возможности.

- Подлинность клиента может проверяться с помощью маркера имени пользователя.

- Сервер проверяет учетные данные клиента с помощью проверяющего элемента управления, а пользовательские ошибки из логики проверки имени пользователя и пароля распространяются на клиент.

- Сервер проходит проверку подлинности с использованием сертификата X.509 сервера.

 Служба предоставляет одну конечную точку для взаимодействия с нею; она определена в файле конфигурации App.config. Конечная точка состоит из адреса, привязки и контракта. Привязка настраивается с помощью стандартного `wsHttpBinding`, который по умолчанию использует WS-Security и проверку подлинности имени пользователя. В поведении службы задается режим `Custom` проверки пар "имя пользователя-пароль" клиента, а также тип класса проверяющего элемента управления. Коме того, поведение с помощью элемента `serviceCertificate` задает сертификат сервера. Сертификат сервера должен содержать то же значение для `SubjectName`, что и `findValue` в [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <!-- use host/baseAddresses to configure base address provided by host -->
      <host>
        <baseAddresses>
          <add baseAddress ="http://localhost:8001/servicemodelsamples/service" />
        </baseAddresses>
      </host>
      <!-- use base address specified above, provide one endpoint -->
      <endpoint address="username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>

  <bindings>
    <wsHttpBinding>
      <!-- username binding -->
      <binding name="Binding">
        <security mode="Message">
          <message clientCredentialType="UserName" />
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>

  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceDebug includeExceptionDetailInFaults ="true"/>
        <serviceCredentials>
          <!--
          The serviceCredentials behavior allows one to
          specify a custom validator for username/password
          combinations.
          -->
          <userNameAuthentication userNamePasswordValidationMode="Custom"
                                  customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+MyCustomUserNameValidator, service" />
          <!--
          The serviceCredentials behavior allows one to define a service certificate. A service certificate is used by a client to authenticate the service and provide message protection. You must specify a server certificate when passing username/passwords to encrypt the information as it is sent on the wire. Otherwise the username and password information would be sent as clear text. This configuration references the "localhost" certificate installed during the setup instructions.
          -->
          <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>

</system.serviceModel>
```

 Конфигурация конечной точки клиента состоит из имени конфигурации, абсолютного адреса конечной точки службы, привязки и контракта. Привязка клиента настраивается с помощью соответствующего режима и `clientCredentialType` сообщения.

```xml
<system.serviceModel>

    <client>
      <!-- Username based endpoint -->
      <endpoint name="Username"
address="http://localhost:8001/servicemodelsamples/service/username"
                binding="wsHttpBinding"
                bindingConfiguration="Binding"
                behaviorConfiguration="ClientCertificateBehavior"
                contract="Microsoft.ServiceModel.Samples.ICalculator">
      </endpoint>
    </client>

    <bindings>
      <wsHttpBinding>
        <!-- Username binding -->
        <binding name="Binding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <behaviors>
      <endpointBehaviors>
        <behavior name="ClientCertificateBehavior">
          <clientCredentials>
            <serviceCertificate>
              <!--
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
            is in the user's Trusted People store, then it will be trusted without performing a
            validation of the certificate's issuer chain. This setting is used here for convenience so that the
            sample can be run without having to have certificates issued by a certification authority (CA).
            This setting is less secure than the default, ChainTrust. The security implications of this
            setting should be carefully considered before using PeerOrChainTrust in production code.
            -->
              <authentication certificateValidationMode="PeerOrChainTrust" />
            </serviceCertificate>
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>

  </system.serviceModel>
```

 Реализация клиента запрашивает у пользователя имя пользователя и пароль.

```csharp
// Get the username and password
Console.WriteLine("Username authentication required.");
Console.WriteLine("Provide a username.");
Console.WriteLine("   Enter username: (test1)");
string username = Console.ReadLine();
Console.WriteLine("   Enter password:");
string password = "";
ConsoleKeyInfo info = Console.ReadKey(true);
while (info.Key != ConsoleKey.Enter)
{
    if (info.Key != ConsoleKey.Backspace)
    {
        if (info.KeyChar != '\0')
        {
            password += info.KeyChar;
        }
        info = Console.ReadKey(true);
    }
    else if (info.Key == ConsoleKey.Backspace)
    {
        if (password != "")
        {
            password = password.Substring(0, password.Length - 1);
        }
        info = Console.ReadKey(true);
    }
}
for (int i = 0; i < password.Length; i++)
{
    Console.Write("*");
}
Console.WriteLine();
// Create a proxy with Certificate endpoint configuration
CalculatorProxy proxy = new CalculatorProxy("Username")
try
{
  proxy.ClientCredentials.Username.Username = username;
  proxy.ClientCredentials.Username.Password = password;
    // Call the Add service operation.
    double value1 = 100.00D;
    double value2 = 15.99D;
    double result = proxy.Add(value1, value2);
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
  }
  catch (Exception e)
  {
      Console.WriteLine("Call failed:");
      while (e != null)
      {
          Console.WriteLine("\t{0}", e.Message);
          e = e.InnerException;
      }
      proxy.Abort();
  }
}
```

 В этом образце для проверки пар "имя пользователя-пароль" используется пользовательский элемент UserNamePasswordValidator. В этом образце реализуется класс `CustomUserNamePasswordValidator`, наследуемый от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. Дополнительные сведения см. в разделе, посвященном <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>. В данном образце пользовательского элемента управления реализуется метод `Validate`, принимающий две конкретные пары "имя пользователя-пароль", как показано в следующем фрагменте кода.

```csharp
public class CustomUserNameValidator : UserNamePasswordValidator
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
   throw new FaultException("Unknown Username or Incorrect Password");
   }
  }
 }
```

 После реализации в коде службы проверяющего элемента управления необходимо проинформировать узел службы о проверяющем элементе управления, который следует использовать. Для этого можно воспользоваться следующим фрагментом кода.

```csharp
serviceHost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;
serviceHost.Credentials. UserNameAuthentication.CustomUserNamePasswordValidator = new CustomUserNamePasswordValidator();
```

 Либо можно решить эту же задачу с помощью файла конфигурации, как показано ниже.

```xml
<behaviors>
 <serviceBehaviors>
  <behavior name="CalculatorServiceBehavior">
  ...
   <serviceCredentials>
    <!--
    The serviceCredentials behavior allows one to specify authentication constraints on username / password combinations.
    -->
    <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService+CustomUserNameValidator, service" />
   ...
  </behavior>
 </serviceBehaviors>
</behaviors>
```

 При выполнении примера запросы и ответы операций отображаются в окне консоли клиента. Клиент должен успешно вызывать все методы. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.

## <a name="setup-batch-file"></a>Пакетный файл Setup
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера. Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без резидентного размещения приложения.

 Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.

- Создание сертификата сервера.

     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера. Переменная %SERVER_NAME% задает имя сервера. Измените эту переменную, чтобы задать собственное имя сервера. Значением по умолчанию является localhost.

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

#### <a name="to-set-up-and-build-the-sample"></a>Настройка и сборка образца

1. Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).

2. Чтобы выполнить образец на одном или нескольких компьютерах, выполните следующие инструкции.

#### <a name="to-run-the-sample-on-the-same-machine"></a>Запуск образца на том же компьютере

1. Запустите setup. bat из папки образцов установки в командной строке Visual Studio 2012. При этом устанавливаются все сертификаты, необходимые для выполнения образца.

    > [!NOTE]
    > Пакетный файл Setup. bat предназначен для запуска из командной строки Visual Studio 2012. Переменная среды PATH, заданная в командной строке Visual Studio 2012, указывает на каталог, содержащий исполняемые файлы, необходимые для сценария Setup. bat.  
  
2. Запустите программу Service.exe из папки service\bin.  
  
3. Запустите программу Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
4. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-run-the-sample-across-machines"></a>Выполнение примера на нескольких компьютерах  
  
1. Создайте на компьютере службы каталог для двоичных файлов службы.  
  
2. Скопируйте файлы служебной программы из каталога службы на компьютер службы. Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.  
  
3. Необходимо иметь сертификат сервера с именем субъекта, содержащим полное доменное имя компьютера. Необходимо обновить файл конфигурации сервера, чтобы в нем отражалось это новое имя сертификата.  
  
4. Скопируйте сертификат сервера в хранилище CurrentUser-TrustedPeople клиента. Это нужно делать только в том случае, если сертификат сервера не выдан центром выдачи, которому доверяет клиент.  
  
5. В файле App.config компьютера службы также измените значение базового адреса для указания полного доменного имени компьютера вместо localhost.  
  
6. На компьютере службы из окна командной строки запустите программу Service.exe.  
  
7. Скопируйте на клиентский компьютер файлы программы клиента из папки \client\bin\ в языковой папке.  
  
8. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиентском компьютере из окна командной строки запустите программу Client.exe.  
  
10. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
#### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
1. После завершения работы примера запустите в папке примеров файл Cleanup.bat. Он удалит из хранилища сертификатов сертификат сервера.  
