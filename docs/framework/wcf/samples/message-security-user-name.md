---
title: Безопасность сообщений с использованием имени пользователя
ms.date: 03/30/2017
helpviewer_keywords:
- WS Security
ms.assetid: c63cfc87-6b20-4949-93b3-bcd4b732b0a2
ms.openlocfilehash: 62b6f24bab1c655038ad3295f5af3dee0fa198fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183501"
---
# <a name="message-security-user-name"></a><span data-ttu-id="07144-102">Безопасность сообщений с использованием имени пользователя</span><span class="sxs-lookup"><span data-stu-id="07144-102">Message Security User Name</span></span>
<span data-ttu-id="07144-103">В этом образце показано, как реализовать приложение, использующее протокол WS-Security и проверку подлинности имен пользователя для клиента и требующее проверки подлинности сервера с использованием сертификата X.509v3 сервера.</span><span class="sxs-lookup"><span data-stu-id="07144-103">This sample demonstrates how to implement an application that uses WS-Security with username authentication for the client and requires server authentication using the server's X.509v3 certificate.</span></span> <span data-ttu-id="07144-104">Все сообщения приложений, которыми обмениваются служба и клиент, подписываются и шифруются.</span><span class="sxs-lookup"><span data-stu-id="07144-104">All application messages between the client and server are signed and encrypted.</span></span> <span data-ttu-id="07144-105">По умолчанию для входа от имени действующей учетной записи Windows используются предоставляемые клиентом имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="07144-105">By default, the username and password supplied by the client are used to logon to a valid Windows account.</span></span> <span data-ttu-id="07144-106">Этот образец основан на [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="07144-106">This sample is based on the [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md).</span></span> <span data-ttu-id="07144-107">Этот образец содержит консольную программу клиента (Client.exe) и библиотеку службы (Service.dll), размещаемую в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="07144-107">This sample consists of a client console program (Client.exe) and a service library (Service.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="07144-108">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="07144-108">The service implements a contract that defines a request-reply communication pattern.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07144-109">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="07144-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="07144-110">В этом образце также демонстрируется следующее.</span><span class="sxs-lookup"><span data-stu-id="07144-110">This sample also demonstrates:</span></span>  
  
- <span data-ttu-id="07144-111">Сопоставление учетных записей по умолчанию для обеспечения дополнительной авторизации.</span><span class="sxs-lookup"><span data-stu-id="07144-111">The default mapping to Windows accounts so that additional authorization can be performed.</span></span>  
  
- <span data-ttu-id="07144-112">Способ доступа к данным идентификации клиента из кода службы.</span><span class="sxs-lookup"><span data-stu-id="07144-112">How to access the caller's identity information from the service code.</span></span>  
  
 <span data-ttu-id="07144-113">Служба предоставляет одну конечную точку для взаимодействия с нею; она определена в файле конфигурации Web.config. Конечная точка состоит из адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="07144-113">The service exposes a single endpoint for communicating with the service, which is defined using the configuration file Web.config. The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="07144-114">Привязка настроена со стандартной [ \<wsHttpBinding>, ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)которая по умолчанию использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="07144-114">The binding is configured with a standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), which defaults to using message security.</span></span> <span data-ttu-id="07144-115">Этот пример устанавливает стандартный [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) использовать проверку подлинности имени пользователя клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-115">This sample sets the standard [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to use client username authentication.</span></span> <span data-ttu-id="07144-116">Поведение указывает, что для проверки подлинности службы следует использовать учетные данные пользователя.</span><span class="sxs-lookup"><span data-stu-id="07144-116">The behavior specifies that the user credentials are to be used for service authentication.</span></span> <span data-ttu-id="07144-117">Сертификат сервера должен содержать то же значение `findValue` для имени объекта, что и атрибут в [ \<>. ](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="07144-117">The server certificate must contain the same value for the subject name as the `findValue` attribute in the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      By default, Username authentication attempts to authenticate the provided  
      username as a Windows computer or domain account.  
      -->  
      <binding>  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!--   
      The serviceCredentials behavior allows one to define a service certificate.  
      A service certificate is used by the service to authenticate itself to the client and to provide message protection.  
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
</system.serviceModel>  
```  
  
 <span data-ttu-id="07144-118">Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="07144-118">The client endpoint configuration consists of an absolute address for the service endpoint, the binding, and the contract.</span></span> <span data-ttu-id="07144-119">Привязка клиента настраивается с помощью соответствующих `securityMode` и `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="07144-119">The client binding is configured with the appropriate `securityMode` and `authenticationMode`.</span></span> <span data-ttu-id="07144-120">Если сценарий выполняется на нескольких компьютерах, необходимо изменить адрес конечной точки службы соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="07144-120">When running in a cross-computer scenario, the service endpoint address must be changed accordingly.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint address="http://localhost/servicemodelsamples/service.svc"
              binding="wsHttpBinding"
              bindingConfiguration="Binding1"
              behaviorConfiguration="ClientCredentialsBehavior"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
      This configuration defines the security mode as Message and   
      the clientCredentialType as Username.  
      -->  
      <binding name="Binding1">  
        <security mode="Message">  
          <message clientCredentialType="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true.-->  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="ClientCredentialsBehavior">  
        <!--   
      Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
      is in the user's Trusted People store, then it is trusted without performing a  
      validation of the certificate's issuer chain. This setting is used here for convenience so that the   
      sample can be run without having to have certificates issued by a certification authority (CA).  
      This setting is less secure than the default, ChainTrust. The security implications of this   
      setting should be carefully considered before using PeerOrChainTrust in production code.   
      -->  
        <clientCredentials>  
          <serviceCertificate>  
            <authentication certificateValidationMode="PeerOrChainTrust" />  
          </serviceCertificate>  
        </clientCredentials>  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="07144-121">Реализация клиента задает используемые имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="07144-121">The client implementation sets the user name and password to use.</span></span>  

```csharp
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Configure client with valid computer or domain account (username,password).  
client.ClientCredentials.UserName.UserName = username;  
client.ClientCredentials.UserName.Password = password.ToString();  
  
// Call GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```

 <span data-ttu-id="07144-122">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="07144-123">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
MyMachine\TestAccount  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="07144-124">Пакетный файл Setup.bat, входящий в состав образца реализации безопасности сообщений с возможностью анонимного доступа, позволяет настроить для сервера соответствующий сертификат, необходимый для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="07144-124">The Setup.bat batch file included with the MessageSecurity samples enables you to configure the server with a relevant certificate to run a hosted application that requires certificate-based security.</span></span> <span data-ttu-id="07144-125">Пакетный файл можно выполнять в двух режимах.</span><span class="sxs-lookup"><span data-stu-id="07144-125">The batch file can be run in two modes.</span></span> <span data-ttu-id="07144-126">Чтобы выполнить пакетный файл в режиме одного компьютера, введите `setup.bat` в командной строке.</span><span class="sxs-lookup"><span data-stu-id="07144-126">To run the batch file in the single-computer mode, type `setup.bat` at the command line.</span></span> <span data-ttu-id="07144-127">Чтобы выполнить его в режиме службы, введите `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="07144-127">To run it in service mode type `setup.bat service`.</span></span> <span data-ttu-id="07144-128">Этот режим используется для выполнения образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="07144-128">You use this mode when running the sample across computers.</span></span> <span data-ttu-id="07144-129">Подробные сведения см. в описании процедуры настройки в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="07144-129">See the setup procedure at the end of this topic for details.</span></span>  
  
 <span data-ttu-id="07144-130">Ниже приводится краткое описание различных разделов пакетного файла.</span><span class="sxs-lookup"><span data-stu-id="07144-130">The following provides a brief overview of the different sections of the batch files.</span></span>  
  
- <span data-ttu-id="07144-131">Создание сертификата сервера</span><span class="sxs-lookup"><span data-stu-id="07144-131">Creating the server certificate</span></span>  
  
     <span data-ttu-id="07144-132">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="07144-132">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span>  
  
    ```bat
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     <span data-ttu-id="07144-133">Переменная %SERVER_NAME% задает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="07144-133">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="07144-134">Сертификат хранится в хранилище LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="07144-134">The certificate is stored in the LocalMachine store.</span></span> <span data-ttu-id="07144-135">Если пакетный файл Setup.bat запускается с аргументом service (например, `setup.bat service`), переменная %SERVER_NAME% содержит полное имя домена компьютера.</span><span class="sxs-lookup"><span data-stu-id="07144-135">If the Setup.bat batch file is run with an argument of service (such as `setup.bat service`) the %SERVER_NAME% contains the fully-qualified domain name of the computer.</span></span>  <span data-ttu-id="07144-136">В противном случае по умолчанию используется значение localhost.</span><span class="sxs-lookup"><span data-stu-id="07144-136">Otherwise it defaults to localhost.</span></span>  
  
- <span data-ttu-id="07144-137">Установка сертификата сервера в хранилище доверенных сертификатов клиента</span><span class="sxs-lookup"><span data-stu-id="07144-137">Installing the server certificate into the client's trusted certificate store</span></span>  
  
     <span data-ttu-id="07144-138">Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-138">The following line copies the server certificate into the client trusted people store.</span></span> <span data-ttu-id="07144-139">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="07144-139">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="07144-140">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="07144-140">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```console
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
- <span data-ttu-id="07144-141">Предоставление разрешений в закрытом ключе сертификата</span><span class="sxs-lookup"><span data-stu-id="07144-141">Granting permissions on the certificate's private key</span></span>  
  
     <span data-ttu-id="07144-142">Следующие строки в пакетном файле Setup.bat делают серверный сертификат, хранящийся в магазине LocalMachine, доступным для учетной записи процесса ASP.NET работника.</span><span class="sxs-lookup"><span data-stu-id="07144-142">The following lines in the Setup.bat batch file make the server certificate stored in the LocalMachine store accessible to the ASP.NET worker process account.</span></span>  
  
    ```bat
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
    > <span data-ttu-id="07144-143">Если вы используете неамериканское английское издание Windows, вы должны отсеить `NT AUTHORITY\NETWORK SERVICE` файл Setup.bat и заменить имя учетной записи региональным эквивалентом.</span><span class="sxs-lookup"><span data-stu-id="07144-143">If you are using a non-U.S. English edition of Windows you must edit the Setup.bat file and replace the `NT AUTHORITY\NETWORK SERVICE` account name with your regional equivalent.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="07144-144">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="07144-144">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="07144-145">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="07144-145">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="07144-146">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="07144-146">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="07144-147">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="07144-147">To run the sample on the same computer</span></span>  
  
1. <span data-ttu-id="07144-148">Убедитесь, что путь включает папку, в которой хранятся файлы Makecert.exe и FindPrivateKey.exe.</span><span class="sxs-lookup"><span data-stu-id="07144-148">Ensure that the path includes the folder where Makecert.exe and FindPrivateKey.exe are located.</span></span>  
  
2. <span data-ttu-id="07144-149">Выполнить Setup.bat из папки установки образца в команде разработчика Prompt для визуальной студии, открытой с привилегиями администратора.</span><span class="sxs-lookup"><span data-stu-id="07144-149">Run Setup.bat from the sample install folder in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="07144-150">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="07144-150">This installs all the certificates required for running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="07144-151">Пакетный файл Setup.bat предназначен для запуска от команды разработчиков Prompt для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="07144-151">The Setup.bat batch file is designed to be run from a Developer Command Prompt for Visual Studio.</span></span> <span data-ttu-id="07144-152">Необходимо, чтобы переменная среды path указывала на каталог, в котором установлен пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="07144-152">It requires that the path environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="07144-153">Эта переменная среды автоматически устанавливается в командном запросе разработчика для Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="07144-153">This environment variable is automatically set within a Developer Command Prompt for Visual Studio.</span></span>  
  
3. <span data-ttu-id="07144-154">Проверить доступ к службе с помощью браузера, введя адрес. `http://localhost/servicemodelsamples/service.svc`</span><span class="sxs-lookup"><span data-stu-id="07144-154">Verify access to the service using a browser by entering the address `http://localhost/servicemodelsamples/service.svc`.</span></span>
  
4. <span data-ttu-id="07144-155">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="07144-155">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="07144-156">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-156">Client activity is displayed on the client console application.</span></span>  
  
5. <span data-ttu-id="07144-157">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="07144-157">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="07144-158">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="07144-158">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="07144-159">Создайте каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="07144-159">Create a directory on the service computer.</span></span> <span data-ttu-id="07144-160">Создайте для этого каталога виртуальное приложение servicemodelsamples, воспользовавшись для этого средством управления службами IIS.</span><span class="sxs-lookup"><span data-stu-id="07144-160">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services management tool.</span></span>  
  
2. <span data-ttu-id="07144-161">Скопируйте файлы служебной программы из каталога «\inetpub\wwwroot\servicemodelsamples» в виртуальный каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="07144-161">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="07144-162">Убедитесь, что скопированы все файлы из подкаталога \bin.</span><span class="sxs-lookup"><span data-stu-id="07144-162">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="07144-163">Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.</span><span class="sxs-lookup"><span data-stu-id="07144-163">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="07144-164">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-164">Create a directory on the client computer for the client binaries.</span></span>  
  
4. <span data-ttu-id="07144-165">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="07144-165">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="07144-166">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="07144-166">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5. <span data-ttu-id="07144-167">На сервере, `setup.bat service` запуск в команде разработчиков Prompt для Visual Studio открыт с администратором привилегий.</span><span class="sxs-lookup"><span data-stu-id="07144-167">On the server, run `setup.bat service` in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="07144-168">Запуск `setup.bat` с `service` аргументом создает сертификат обслуживания с полностью квалифицированным доменным именем компьютера и экспортирует сертификат службы в файл под названием Service.cer.</span><span class="sxs-lookup"><span data-stu-id="07144-168">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6. <span data-ttu-id="07144-169">Внесите в файл Web.config изменения в соответствии с новым именем сертификата (в атрибуте findValue в элементе serviceCertificate), которое совпадает с полным именем домена компьютера`.`</span><span class="sxs-lookup"><span data-stu-id="07144-169">Edit Web.config to reflect the new certificate name (in the findValue attribute in the serviceCertificate element) which is the same as the fully-qualified domain name of the computer`.`</span></span>  
  
7. <span data-ttu-id="07144-170">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="07144-170">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8. <span data-ttu-id="07144-171">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="07144-171">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="07144-172">На клиенте, запустить ImportServiceCert.bat в разработчика команды Prompt для Visual Studio открыл с администратором привилегий.</span><span class="sxs-lookup"><span data-stu-id="07144-172">On the client, run ImportServiceCert.bat in a Developer Command Prompt for Visual Studio opened with administrator privileges.</span></span> <span data-ttu-id="07144-173">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="07144-173">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="07144-174">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="07144-174">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="07144-175">Если клиент и служба не в состоянии общаться, [см.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="07144-175">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="07144-176">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="07144-176">To clean up after the sample</span></span>  
  
- <span data-ttu-id="07144-177">После завершения работы образца запустите в папке образцов файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="07144-177">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="07144-178">Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="07144-178">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="07144-179">Если вы используете образцы Windows Communication Foundation (WCF), которые используют сертификаты на всех компьютерах, обязательно очистите сертификаты службы, установленные в магазине CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="07144-179">If you have run Windows Communication Foundation (WCF) samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="07144-180">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="07144-180">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
