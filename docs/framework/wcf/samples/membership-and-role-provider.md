---
title: "Поставщик членства и ролей"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 34d89d937092f0feed9c103f05bf5db55c4a80e9
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="membership-and-role-provider"></a><span data-ttu-id="cc57c-102">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="cc57c-102">Membership and Role Provider</span></span>
<span data-ttu-id="cc57c-103">В образце поставщиков членства и ролей показано, как создать службу, которая может с помощью поставщиков членства и ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполнять проверку подлинности и авторизацию клиентов.</span><span class="sxs-lookup"><span data-stu-id="cc57c-103">The Membership and Role Provider sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 <span data-ttu-id="cc57c-104">В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="cc57c-104">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc57c-105">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="cc57c-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="cc57c-106">В образце демонстрируются следующие возможности.</span><span class="sxs-lookup"><span data-stu-id="cc57c-106">The sample demonstrates how:</span></span>  
  
-   <span data-ttu-id="cc57c-107">Клиент может проходить проверку подлинности по имени пользователя и паролю.</span><span class="sxs-lookup"><span data-stu-id="cc57c-107">A client can authenticate by using the username-password combination.</span></span>  
  
-   <span data-ttu-id="cc57c-108">Сервер может проверять учетные данные, используя поставщик участия [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc57c-108">The server can validate the client credentials against the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
-   <span data-ttu-id="cc57c-109">Сервер может проходить проверку подлинности с помощью сертификата X.509 сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-109">The server can be authenticated by using the server's X.509 certificate.</span></span>  
  
-   <span data-ttu-id="cc57c-110">Сервер может сопоставить прошедший проверку подлинности клиент с ролью с помощью поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cc57c-110">The server can map the authenticated client to a role by using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider.</span></span>  
  
-   <span data-ttu-id="cc57c-111">Сервер может использовать атрибут `PrincipalPermissionAttribute` для управления доступом к определенным методам, предоставляемым службой.</span><span class="sxs-lookup"><span data-stu-id="cc57c-111">The server can use the `PrincipalPermissionAttribute` to control access to certain methods that are exposed by the service.</span></span>  
  
 <span data-ttu-id="cc57c-112">Поставщики членства и ролей настраиваются на использование хранилища на базе SQL Server.</span><span class="sxs-lookup"><span data-stu-id="cc57c-112">The membership and role providers are configured to use a store backed by SQL Server.</span></span> <span data-ttu-id="cc57c-113">Строка подключения и другие параметры задаются в файле конфигурации службы.</span><span class="sxs-lookup"><span data-stu-id="cc57c-113">A connection string and various options are specified in the service configuration file.</span></span> <span data-ttu-id="cc57c-114">Поставщик участия получает имя `SqlMembershipProvider`, а поставщик ролей - имя `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="cc57c-114">The membership provider is given the name `SqlMembershipProvider` while the role provider is given the name `SqlRoleProvider`.</span></span>  
  
```xml  
<!-- Set the connection string for SQL Server -->  
<connectionStrings>  
  <add name="SqlConn"   
       connectionString="Data Source=localhost;Integrated Security=SSPI;Initial Catalog=aspnetdb;" />  
</connectionStrings>  
  
<system.web>  
  <!-- Configure the Sql Membership Provider -->  
  <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">  
    <providers>  
      <clear />  
      <add   
        name="SqlMembershipProvider"   
        type="System.Web.Security.SqlMembershipProvider"   
        connectionStringName="SqlConn"  
        applicationName="MembershipAndRoleProviderSample"  
        enablePasswordRetrieval="false"  
        enablePasswordReset="false"  
        requiresQuestionAndAnswer="false"  
        requiresUniqueEmail="true"  
        passwordFormat="Hashed" />  
    </providers>  
  </membership>  
  
  <!-- Configure the Sql Role Provider -->  
  <roleManager enabled ="true"   
               defaultProvider ="SqlRoleProvider" >  
    <providers>  
      <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
    </providers>  
  </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="cc57c-115">Служба предоставляет одну конечную точку для взаимодействия с ней. Эта точка задается в файле конфигурации Web.config.</span><span class="sxs-lookup"><span data-stu-id="cc57c-115">The service exposes a single endpoint for communicating with the service, which is defined by using the Web.config configuration file.</span></span> <span data-ttu-id="cc57c-116">Конечная точка состоит из адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="cc57c-116">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="cc57c-117">Привязка настраивается с помощью стандартного элемента `wsHttpBinding`, который по умолчанию использует проверку подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="cc57c-117">The binding is configured with a standard `wsHttpBinding`, which defaults to using Windows authentication.</span></span> <span data-ttu-id="cc57c-118">В этом образце стандартная привязка `wsHttpBinding` использует проверку подлинности имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="cc57c-118">This sample sets the standard `wsHttpBinding` to use username authentication.</span></span> <span data-ttu-id="cc57c-119">Поведение определяет, что для проверки подлинности службы должен использоваться сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-119">The behavior specifies that the server certificate is to be used for service authentication.</span></span> <span data-ttu-id="cc57c-120">Сертификат сервера должен содержать то же значение для `SubjectName` как `findValue` атрибута в [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) элемента конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc57c-120">The server certificate must contain the same value for the `SubjectName` as the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) configuration element.</span></span> <span data-ttu-id="cc57c-121">Кроме того, поведение определяет, что проверка подлинности пар "имя пользователя-пароль" выполняется поставщиком членства [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], а сопоставление ролей выполняется поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], для чего в поведении заданы имена двух поставщиков.</span><span class="sxs-lookup"><span data-stu-id="cc57c-121">In addition the behavior specifies that authentication of username-password pairs is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider and role mapping is performed by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider by specifying the names defined for the two providers.</span></span>  
  
```xml  
<system.serviceModel>  
  
  <protocolMapping>  
    <add scheme="http" binding="wsHttpBinding" />  
  </protocolMapping>  
  
  <bindings>  
    <wsHttpBinding>  
      <!-- Set up a binding that uses Username as the client credential type -->  
      <binding>  
        <security mode ="Message">  
          <message clientCredentialType ="UserName"/>  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
  
  <behaviors>  
    <serviceBehaviors>  
      <behavior>  
        <!-- Configure role based authorization to use the Role Provider -->  
        <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                              roleProviderName ="SqlRoleProvider" />  
        <serviceCredentials>  
          <!-- Configure user name authentication to use the Membership Provider -->  
          <userNameAuthentication userNamePasswordValidationMode ="MembershipProvider"   
                                  membershipProviderName ="SqlMembershipProvider"/>  
          <!-- Configure the service certificate -->  
          <serviceCertificate storeLocation ="LocalMachine"   
                              storeName ="My"   
                              x509FindType ="FindBySubjectName"  
                              findValue ="localhost" />  
        </serviceCredentials>  
        <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
        <serviceDebug includeExceptionDetailInFaults="false" />  
        <serviceMetadata httpGetEnabled="true"/>  
      </behavior>  
    </serviceBehaviors>  
  </behaviors>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="cc57c-122">При запуске этого образца клиент вызывает различные операции службы от имени различных учетных записей пользователей: Alice, Bob и Charlie.</span><span class="sxs-lookup"><span data-stu-id="cc57c-122">When you run the sample, the client calls the various service operations under three different user accounts: Alice, Bob, and Charlie.</span></span> <span data-ttu-id="cc57c-123">Запросы и ответы операций появляются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-123">The operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="cc57c-124">Все четыре вызова от имени пользователя Alice должны завершиться успешно.</span><span class="sxs-lookup"><span data-stu-id="cc57c-124">All four calls made as user "Alice" should succeed.</span></span> <span data-ttu-id="cc57c-125">Пользователь Bob должен получить отказ в доступе при попытке вызвать метод Divide.</span><span class="sxs-lookup"><span data-stu-id="cc57c-125">User "Bob" should get an access denied error when trying to call the Divide method.</span></span> <span data-ttu-id="cc57c-126">Пользователь Charlie должен получить отказ в доступе при попытке вызвать метод Multiply.</span><span class="sxs-lookup"><span data-stu-id="cc57c-126">User "Charlie" should get an access denied error when trying to call the Multiply method.</span></span> <span data-ttu-id="cc57c-127">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-127">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cc57c-128">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="cc57c-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cc57c-129">Для сборки выпуска C# .NET или Visual Basic этого решения, следуйте инструкциям в [выполнение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cc57c-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="cc57c-130">Убедитесь, что вы настроили [базы данных служб приложения ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94997).</span><span class="sxs-lookup"><span data-stu-id="cc57c-130">Ensure that you have configured the [ASP.NET Application Services Database](http://go.microsoft.com/fwlink/?LinkId=94997).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc57c-131">Если используется выпуск SQL Server Express Edition, то сервер имеет имя .\SQLEXPRESS.</span><span class="sxs-lookup"><span data-stu-id="cc57c-131">If you are running SQL Server Express Edition, your server name is .\SQLEXPRESS.</span></span> <span data-ttu-id="cc57c-132">Это имя сервера следует использовать при настройке базы данных служб приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], а также в строке подключения в файле Web.config.</span><span class="sxs-lookup"><span data-stu-id="cc57c-132">This server should be used when configuring the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Application Services Database as well as in the Web.config connection string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc57c-133">У учетной записи рабочего процесса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] должны быть разрешения на доступ к созданной на этом этапе базе данных.</span><span class="sxs-lookup"><span data-stu-id="cc57c-133">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] worker process account must have permissions on the database that is created in this step.</span></span> <span data-ttu-id="cc57c-134">Для этого воспользуйтесь служебной программой sqlcmd или средой SQL Server Management Studio.</span><span class="sxs-lookup"><span data-stu-id="cc57c-134">Use the sqlcmd utility or SQL Server Management Studio to do this.</span></span>  
  
3.  <span data-ttu-id="cc57c-135">Чтобы запустить образец на одном или нескольких компьютерах, следуйте приведенным далее инструкциям.</span><span class="sxs-lookup"><span data-stu-id="cc57c-135">To run the sample in a single- or cross-computer configuration, use the following instructions.</span></span>  
  
### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="cc57c-136">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="cc57c-136">To run the sample on the same computer</span></span>  
  
1.  <span data-ttu-id="cc57c-137">Убедитесь, что путь включает папку, в которой хранится файл Makecert.exe.</span><span class="sxs-lookup"><span data-stu-id="cc57c-137">Make sure that the path includes the folder where Makecert.exe is located.</span></span>  
  
2.  <span data-ttu-id="cc57c-138">Из командной строки Visual Studio, запущенной с правами администратора, запустите файл Setup.bat из папки установки образца.</span><span class="sxs-lookup"><span data-stu-id="cc57c-138">Run Setup.bat from the sample install folder in a Visual Studio command prompt run with administrator privileges.</span></span> <span data-ttu-id="cc57c-139">Он устанавливает сертификаты службы, необходимые для запуска образца.</span><span class="sxs-lookup"><span data-stu-id="cc57c-139">This installs the service certificates required for running the sample.</span></span>  
  
3.  <span data-ttu-id="cc57c-140">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="cc57c-140">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="cc57c-141">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-141">Client activity is displayed on the client console application.</span></span>  
  
4.  <span data-ttu-id="cc57c-142">Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="cc57c-142">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="cc57c-143">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="cc57c-143">To run the sample across computers</span></span>  
  
1.  <span data-ttu-id="cc57c-144">Создайте каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="cc57c-144">Create a directory on the service computer.</span></span> <span data-ttu-id="cc57c-145">Создайте для этого каталога виртуальное приложение servicemodelsamples, с помощью средства управления службами IIS.</span><span class="sxs-lookup"><span data-stu-id="cc57c-145">Create a virtual application named servicemodelsamples for this directory by using the Internet Information Services (IIS) management tool.</span></span>  
  
2.  <span data-ttu-id="cc57c-146">Скопируйте файлы служебной программы из каталога «\inetpub\wwwroot\servicemodelsamples» в виртуальный каталог на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="cc57c-146">Copy the service program files from \inetpub\wwwroot\servicemodelsamples to the virtual directory on the service computer.</span></span> <span data-ttu-id="cc57c-147">Убедитесь, что скопированы все файлы из подкаталога \bin.</span><span class="sxs-lookup"><span data-stu-id="cc57c-147">Ensure that you copy the files in the \bin subdirectory.</span></span> <span data-ttu-id="cc57c-148">Кроме того, скопируйте на компьютер службы файлы Setup.bat, GetComputerName.vbs и Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="cc57c-148">Also copy the Setup.bat, GetComputerName.vbs, and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="cc57c-149">Создайте на клиентском компьютере каталог для двоичных файлов клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-149">Create a directory on the client computer for the client binaries.</span></span>  
  
4.  <span data-ttu-id="cc57c-150">Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-150">Copy the client program files to the client directory on the client computer.</span></span> <span data-ttu-id="cc57c-151">Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="cc57c-151">Also copy the Setup.bat, Cleanup.bat, and ImportServiceCert.bat files to the client.</span></span>  
  
5.  <span data-ttu-id="cc57c-152">Откройте на сервере командную строку Visual Studio с правами администратора и запустите `setup.bat service`.</span><span class="sxs-lookup"><span data-stu-id="cc57c-152">On the server, open a Visual Studio command prompt with administrative privileges and run `setup.bat service`.</span></span> <span data-ttu-id="cc57c-153">Под управлением `setup.bat` с `service` аргумент создается сертификат службы с полным доменным именем компьютера и экспортируется в файл с именем Service.cer.</span><span class="sxs-lookup"><span data-stu-id="cc57c-153">Running `setup.bat` with the `service` argument creates a service certificate with the fully-qualified domain name of the computer and exports the service certificate to a file named Service.cer.</span></span>  
  
6.  <span data-ttu-id="cc57c-154">Изменить файл Web.config, чтобы отразить новое имя сертификата (в `findValue` атрибута в [ \<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), который одинаков как полное доменное имя компьютера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-154">Edit Web.config to reflect the new certificate name (in the `findValue` attribute in the [\<serviceCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), which is the same as the fully-qualified domain name of the computer.</span></span>  
  
7.  <span data-ttu-id="cc57c-155">Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="cc57c-155">Copy the Service.cer file from the service directory to the client directory on the client computer.</span></span>  
  
8.  <span data-ttu-id="cc57c-156">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="cc57c-156">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="cc57c-157">На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.</span><span class="sxs-lookup"><span data-stu-id="cc57c-157">On the client, open a Visual Studio command prompt with administrative privileges and run ImportServiceCert.bat.</span></span> <span data-ttu-id="cc57c-158">Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="cc57c-158">This imports the service certificate from the Service.cer file into the CurrentUser - TrustedPeople store.</span></span>  
  
10. <span data-ttu-id="cc57c-159">На клиентском компьютере из командной строки запустите программу Client.exe.</span><span class="sxs-lookup"><span data-stu-id="cc57c-159">On the client computer, launch Client.exe from a command prompt.</span></span> <span data-ttu-id="cc57c-160">Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span><span class="sxs-lookup"><span data-stu-id="cc57c-160">If the client and service are not able to communicate, see [Troubleshooting Tips](http://msdn.microsoft.com/en-us/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="cc57c-161">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="cc57c-161">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="cc57c-162">После завершения работы образца запустите в папке образцов файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="cc57c-162">Run Cleanup.bat in the samples folder after you have finished running the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc57c-163">Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.</span><span class="sxs-lookup"><span data-stu-id="cc57c-163">This script does not remove service certificates on a client when running this sample across computers.</span></span> <span data-ttu-id="cc57c-164">Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser - TrustedPeople».</span><span class="sxs-lookup"><span data-stu-id="cc57c-164">If you have run [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] samples that use certificates across computers, be sure to clear the service certificates that have been installed in the CurrentUser - TrustedPeople store.</span></span> <span data-ttu-id="cc57c-165">Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span><span class="sxs-lookup"><span data-stu-id="cc57c-165">To do this, use the following command: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>` For example: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.</span></span>  
  
## <a name="the-setup-batch-file"></a><span data-ttu-id="cc57c-166">Файл Setup.bat</span><span class="sxs-lookup"><span data-stu-id="cc57c-166">The Setup Batch File</span></span>  
 <span data-ttu-id="cc57c-167">Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-167">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="cc57c-168">Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="cc57c-168">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>  
  
 <span data-ttu-id="cc57c-169">Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="cc57c-169">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>  
  
-   <span data-ttu-id="cc57c-170">Создание сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-170">Creating the server certificate.</span></span>  
  
     <span data-ttu-id="cc57c-171">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-171">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="cc57c-172">Переменная %SERVER_NAME% задает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-172">The %SERVER_NAME% variable specifies the server name.</span></span> <span data-ttu-id="cc57c-173">Измените эту переменную, чтобы задать собственное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="cc57c-173">Change this variable to specify your own server name.</span></span> <span data-ttu-id="cc57c-174">По умолчанию в этом пакетном файле используется имя localhost.</span><span class="sxs-lookup"><span data-stu-id="cc57c-174">This batch file defaults it to localhost.</span></span>  
  
     <span data-ttu-id="cc57c-175">Сертификат хранится в хранилище «My store (Личном хранилище)» в расположении LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="cc57c-175">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
-   <span data-ttu-id="cc57c-176">Установка сертификата сервера в хранилище доверенных сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-176">Installing the server certificate into the client's trusted certificate store.</span></span>  
  
     <span data-ttu-id="cc57c-177">Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="cc57c-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="cc57c-178">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="cc57c-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="cc57c-179">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="cc57c-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="cc57c-180">См. также</span><span class="sxs-lookup"><span data-stu-id="cc57c-180">See Also</span></span>
