---
title: Безопасность сообщений с возможностью анонимного доступа
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c321cbf9-8c05-4cce-b5a5-4bf7b230ee03
ms.openlocfilehash: 0665ce331492a5322fdfde9e91fc1dae5b8e7ea8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424113"
---
# <a name="message-security-anonymous"></a><span data-ttu-id="aa1e6-102">Безопасность сообщений с возможностью анонимного доступа</span><span class="sxs-lookup"><span data-stu-id="aa1e6-102">Message Security Anonymous</span></span>
<span data-ttu-id="aa1e6-103">В примере анонимной безопасности сообщений показано, как реализовать приложение Windows Communication Foundation (WCF), использующее безопасность на уровне сообщений без проверки подлинности клиента, но требующее проверки подлинности сервера с помощью X. 509 сервера. Certificate.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-103">The Message Security Anonymous sample demonstrates how to implement a Windows Communication Foundation (WCF) application that uses message-level security with no client authentication but that requires server authentication using the server's X.509 certificate.</span></span> <span data-ttu-id="aa1e6-104">Все сообщения приложений, которыми обмениваются служба и клиент, подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="aa1e6-105">Этот пример основан на образце [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="aa1e6-105">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span> <span data-ttu-id="aa1e6-106">Этот образец содержит консольную программу клиента (EXE) и библиотеку службы (DLL), размещаемую в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-106">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="aa1e6-107">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="aa1e6-107">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
> <span data-ttu-id="aa1e6-108">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="aa1e6-109">В этом образце в интерфейс калькулятора добавлена новая операция, возвращающая значение `True`, если клиент прошел проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-109">This sample adds a new operation to the calculator interface that returns `True` if the client was not authenticated.</span></span>

```csharp
public class CalculatorService : ICalculator
{
    public bool IsCallerAnonymous()
    {
        // ServiceSecurityContext.IsAnonymous returns true if the caller is not authenticated.
        return ServiceSecurityContext.Current.IsAnonymous;
    }
    ...
}
```

 <span data-ttu-id="aa1e6-110">Служба предоставляет одну конечную точку для взаимодействия с ней; конечная точка определяется в файле конфигурации (Web.config).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-110">The service exposes a single endpoint for communicating with the service, defined using a configuration file (Web.config).</span></span> <span data-ttu-id="aa1e6-111">Конечная точка состоит из адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-111">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="aa1e6-112">Привязка сконфигурирована с использованием привязки `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-112">The binding is configured with a `wsHttpBinding` binding.</span></span> <span data-ttu-id="aa1e6-113">Режимом безопасности по умолчанию для привязки `wsHttpBinding` является `Message`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-113">The default security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="aa1e6-114">Для атрибута `clientCredentialType` устанавливается значение `None`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-114">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>

  <protocolMapping>
    <add scheme="http" binding="wsHttpBinding" />
  </protocolMapping>

  <bindings>
    <wsHttpBinding>
     <!-- This configuration defines the security mode as Message and -->
     <!-- the clientCredentialType as None. This mode provides -->
     <!-- server authentication only using the service certificate. -->

     <binding>
       <security mode="Message">
         <message clientCredentialType="None" />
       </security>
     </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="aa1e6-115">Учетные данные, используемые для проверки подлинности служб, указываются в [>ном поведении\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-115">The credentials to be used for service authentication are specified in the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md).</span></span> <span data-ttu-id="aa1e6-116">Значение параметра `SubjectName`, содержащееся в сертификате сервера, должно совпадать со значением атрибута `findValue`, указанным следующем образце кода.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-116">The server certificate must contain the same value for the `SubjectName` as the value specified for the `findValue` attribute as shown in the following sample code.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior>
      <!--
    The serviceCredentials behavior allows you to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
      <serviceCredentials>
        <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />
      </serviceCredentials>
      <serviceMetadata httpGetEnabled="True"/>
      <serviceDebug includeExceptionDetailInFaults="False" />
    </behavior>
  </serviceBehaviors>
</behaviors>
```

 <span data-ttu-id="aa1e6-117">Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-117">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="aa1e6-118">Режимом безопасности клиента для привязки `wsHttpBinding` является `Message`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-118">The client security mode for the `wsHttpBinding` binding is `Message`.</span></span> <span data-ttu-id="aa1e6-119">Для атрибута `clientCredentialType` устанавливается значение `None`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-119">The `clientCredentialType` attribute is set to `None`.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint name=""
             address="http://localhost/servicemodelsamples/service.svc"
             binding="wsHttpBinding"
             behaviorConfiguration="ClientCredentialsBehavior"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </client>

  <bindings>
    <wsHttpBinding>
      <!--This configuration defines the security mode as -->
      <!--Message and the clientCredentialType as None. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="None"/>
        </security>
      </binding>
    </wsHttpBinding>
  </bindings>
  ...
</system.serviceModel>
```

 <span data-ttu-id="aa1e6-120">В этом образце свойству <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> задается значение <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> для проверки подлинности сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-120">The sample sets the <xref:System.ServiceModel.Security.X509ServiceCertificateAuthentication.CertificateValidationMode%2A> to <xref:System.ServiceModel.Security.X509CertificateValidationMode.PeerOrChainTrust> for authenticating the service's certificate.</span></span> <span data-ttu-id="aa1e6-121">Его можно задать в файле App.config для клиента (в разделе `behaviors`).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-121">This is done in the client's App.config file in the `behaviors` section.</span></span> <span data-ttu-id="aa1e6-122">Это значение параметра обеспечивает, что если сертификат находится в хранилище пользователя "Доверенные лица", он признается доверенным без выполнения проверки цепочки издателей сертификата.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-122">This means that if the certificate is in the user's Trusted People store, then it is trusted without performing a validation of the certificate's issuer chain.</span></span> <span data-ttu-id="aa1e6-123">В данном случает этот параметр используется для удобства, чтобы можно было выполнить образец без затребования сертификатов, выдаваемых центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-123">This setting is used here for convenience so that the sample can be run without requiring certificates issued by a certification authority (CA).</span></span> <span data-ttu-id="aa1e6-124">Этот параметр обеспечивает более низкий уровень безопасности, чем значение по умолчанию (ChainTrust).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-124">This setting is less secure than the default, ChainTrust.</span></span> <span data-ttu-id="aa1e6-125">Прежде чем использовать параметр `PeerOrChainTrust` в рабочей среде, необходимо тщательно изучить связанные с этим проблемы безопасности.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-125">The security implications of this setting should be carefully considered before using `PeerOrChainTrust` in production code.</span></span>

 <span data-ttu-id="aa1e6-126">Реализация клиента добавляет вызов метода `IsCallerAnonymous` и иным образом не отличается от образца [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="aa1e6-126">The client implementation adds a call to the `IsCallerAnonymous` method and otherwise does not differ from the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) sample.</span></span>

```csharp
// Create a client with a client endpoint configuration.
CalculatorClient client = new CalculatorClient();

// Call the GetCallerIdentity operation.
Console.WriteLine("IsCallerAnonymous returned: {0}", client.IsCallerAnonymous());

// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = client.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

...

//Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 <span data-ttu-id="aa1e6-127">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-127">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="aa1e6-128">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-128">Press ENTER in the client window to shut down the client.</span></span>

```console
IsCallerAnonymous returned: True
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

 <span data-ttu-id="aa1e6-129">Пакетный файл Setup.bat, входящий в состав образца реализации безопасности сообщений с возможностью анонимного доступа, позволяет настроить для сервера соответствующий сертификат, необходимый для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-129">The Setup.bat batch file included with the Message Security Anonymous sample enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="aa1e6-130">Пакетный файл можно выполнять в двух режимах.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-130">The batch file can be run in two modes.</span></span> <span data-ttu-id="aa1e6-131">Чтобы выполнить пакетный файл в режиме одного компьютера, введите `setup.bat` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-131">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="aa1e6-132">Чтобы выполнить его в режиме службы, введите `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-132">To run it in service mode, type `setup.bat service`.</span></span> <span data-ttu-id="aa1e6-133">Этот режим используется для выполнения образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-133">Use this mode when running the sample across computers.</span></span> <span data-ttu-id="aa1e6-134">Подробные сведения см. в описании процедуры настройки в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-134">See the setup procedure at the end of this topic for details.</span></span>

 <span data-ttu-id="aa1e6-135">Ниже приводится краткое описание различных разделов пакетного файла.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-135">The following provides a brief overview of the different sections of the batch files:</span></span>

- <span data-ttu-id="aa1e6-136">Создание сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-136">Creating the server certificate.</span></span>

     <span data-ttu-id="aa1e6-137">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-137">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>

    ```bat
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

     <span data-ttu-id="aa1e6-138">Переменная %SERVER_NAME% задает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-138">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="aa1e6-139">Сертификат хранится в хранилище LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-139">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="aa1e6-140">Если пакетный файл Setup запускается с аргументом service (например, `setup.bat service`), переменная %SERVER_NAME% содержит полное имя домена компьютера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-140">If the setup batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="aa1e6-141">В противном случае по умолчанию используется значение localhost.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-141">Otherwise it defaults to localhost.</span></span>

- <span data-ttu-id="aa1e6-142">Установка сертификата сервера в хранилище доверенных сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-142">Installing the server certificate into the client's trusted certificate store.</span></span>

     <span data-ttu-id="aa1e6-143">Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-143">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="aa1e6-144">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-144">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="aa1e6-145">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-145">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

- <span data-ttu-id="aa1e6-146">Предоставление разрешений в отношении закрытого ключа сертификата.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-146">Granting permissions on the certificate's private key.</span></span>

     <span data-ttu-id="aa1e6-147">Следующие строки в пакетном файле Setup. bat делают сертификат сервера, хранящийся в хранилище LocalMachine, доступным для учетной записи рабочего процесса ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-147">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>

    ```bat
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%MSSDK%\bin\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr "5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
> <span data-ttu-id="aa1e6-148">Если вы используете версию Windows, отличную от версии на английском языке, необходимо изменить файл Setup. bat и заменить имя учетной записи `NT AUTHORITY\NETWORK SERVICE` своим региональным эквивалентом.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-148">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="aa1e6-149">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="aa1e6-149">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="aa1e6-150">Убедитесь, что вы выполнили [однократную процедуру настройки для Windows Communication Foundation примеров](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-150">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="aa1e6-151">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-151">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="aa1e6-152">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="aa1e6-152">To run the sample on the same computer</span></span>

1. <span data-ttu-id="aa1e6-153">Убедитесь, что путь включает папку, в которой хранятся файлы Makecert.exe и FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-153">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>

2. <span data-ttu-id="aa1e6-154">Запустите программу Setup. bat из образца папки установки в Командная строка разработчика для запуска Visual Studio с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-154">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio run with administrator privileges.</span></span> <span data-ttu-id="aa1e6-155">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-155">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    > <span data-ttu-id="aa1e6-156">Пакетный файл установки предназначен для запуска из Командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-156">The setup batch file is designed to be run from a  Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="aa1e6-157">Необходимо, чтобы переменная среды path указывала на каталог, в котором установлен пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-157">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="aa1e6-158">Эта переменная среды автоматически задается в Командная строка разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-158">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="aa1e6-159">Проверьте доступ к службе с помощью браузера, введя адрес `http://localhost/servicemodelsamples/service.svc`.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-159">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>  
  
4. <span data-ttu-id="aa1e6-160">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-160">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="aa1e6-161">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-161">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="aa1e6-162">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-162">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="aa1e6-163">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="aa1e6-163">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="aa1e6-164">Создайте каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-164">Create a directory on the service computer.</span></span> <span data-ttu-id="aa1e6-165">Создайте для этого каталога виртуальное приложение servicemodelsamples, с помощью средства управления службами IIS.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-165">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2. <span data-ttu-id="aa1e6-166">Скопируйте файлы служебной программы из каталога «\inetpub\wwwroot\servicemodelsamples» в виртуальный каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-166">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="aa1e6-167">Убедитесь, что скопированы все файлы из подкаталога \bin.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-167">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="aa1e6-168">Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-168">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="aa1e6-169">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-169">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="aa1e6-170">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-170">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="aa1e6-171">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-171">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="aa1e6-172">На сервере запустите `setup.bat service` в Командная строка разработчика для Visual Studio, открытой с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-172">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="aa1e6-173">При запуске `setup.bat` с аргументом `service` создается сертификат службы с полным доменным именем компьютера и экспортируется сертификат службы в файл с именем Service. cer.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-173">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="aa1e6-174">Измените файл Web. config в соответствии с новым именем сертификата (в атрибуте `findValue` в [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), который совпадает с полным доменным именем компьютера.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-174">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7. <span data-ttu-id="aa1e6-175">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-175">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="aa1e6-176">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-176">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="aa1e6-177">На клиенте запустите Импортсервицецерт. bat в Командная строка разработчика для Visual Studio, открытой с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-177">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="aa1e6-178">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-178">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="aa1e6-179">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-179">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="aa1e6-180">Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="aa1e6-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="aa1e6-181">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="aa1e6-181">To clean up after the sample</span></span>  
  
- <span data-ttu-id="aa1e6-182">После завершения работы образца запустите в папке образцов файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-182">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aa1e6-183">Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-183">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="aa1e6-184">Если вы выполнили примеры Windows Communication Foundation (WCF), использующие сертификаты на нескольких компьютерах, обязательно очистите сертификаты службы, установленные в хранилище CurrentUser-TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="aa1e6-184">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="aa1e6-185">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Пример: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span><span class="sxs-lookup"><span data-stu-id="aa1e6-185">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com.`</span></span>
