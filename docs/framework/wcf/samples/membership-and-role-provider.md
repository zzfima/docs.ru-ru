---
title: Поставщик членства и ролей
ms.date: 03/30/2017
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
ms.openlocfilehash: 7fba608d6d0ed3b7caab62ff16926d7b03516ed1
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424672"
---
# <a name="membership-and-role-provider"></a>Поставщик членства и ролей
В образце поставщика членства и роли показано, как служба может использовать поставщиков членства и ролей ASP.NET для проверки подлинности и авторизации клиентов.  
  
 В этом образце клиентом является консольное приложение (EXE), а служба размещается в службах IIS.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В образце демонстрируются следующие возможности.  
  
- Клиент может проходить проверку подлинности по имени пользователя и паролю.  
  
- Сервер может проверить учетные данные клиента по отношению к поставщику членства ASP.NET.  
  
- Сервер может проходить проверку подлинности с помощью сертификата X.509 сервера.  
  
- Сервер может сопоставлять прошедший проверку подлинности клиент с ролью с помощью поставщика роли ASP.NET.  
  
- Сервер может использовать атрибут `PrincipalPermissionAttribute` для управления доступом к определенным методам, предоставляемым службой.  
  
 Поставщики членства и ролей настраиваются на использование хранилища на базе SQL Server. Строка подключения и другие параметры задаются в файле конфигурации службы. Поставщик участия получает имя `SqlMembershipProvider`, а поставщик ролей - имя `SqlRoleProvider`.  
  
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
  
 Служба предоставляет одну конечную точку для взаимодействия с ней. Эта точка задается в файле конфигурации Web.config. Конечная точка состоит из адреса, привязки и контракта. Привязка настраивается с помощью стандартного элемента `wsHttpBinding`, который по умолчанию использует проверку подлинности Windows. В этом образце стандартная привязка `wsHttpBinding` использует проверку подлинности имени пользователя. Поведение определяет, что для проверки подлинности службы должен использоваться сертификат сервера. Сертификат сервера должен содержать то же значение для `SubjectName`, что и атрибут `findValue` в элементе [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md) Configuration. Кроме того, поведение указывает, что проверка подлинности пар "имя пользователя-пароль" выполняется поставщиком членства ASP.NET, а сопоставление ролей выполняется поставщиком роли ASP.NET путем указания имен, определенных для двух поставщиков.  
  
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
  
 При запуске этого образца клиент вызывает различные операции службы от имени различных учетных записей пользователей: Alice, Bob и Charlie. Запросы и ответы операций появляются в окне консоли клиента. Все четыре вызова от имени пользователя Alice должны завершиться успешно. Пользователь Bob должен получить отказ в доступе при попытке вызвать метод Divide. Пользователь Charlie должен получить отказ в доступе при попытке вызвать метод Multiply. Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Чтобы создать C# или Visual Basic выпуск .NET решения, следуйте инструкциям в разделе [выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
2. Убедитесь, что вы настроили [базу данных Службы приложений ASP.NET](https://go.microsoft.com/fwlink/?LinkId=94997).  
  
    > [!NOTE]
    > Если используется выпуск SQL Server Express Edition, то сервер имеет имя .\SQLEXPRESS. Этот сервер следует использовать при настройке базы данных ASP.NET Службы приложений, а также в строке подключения Web. config.  
  
    > [!NOTE]
    > Учетная запись рабочего процесса ASP.NET должна иметь разрешения на базу данных, созданную на этом шаге. Для этого воспользуйтесь служебной программой sqlcmd или средой SQL Server Management Studio.  
  
3. Чтобы запустить образец на одном или нескольких компьютерах, следуйте приведенным далее инструкциям.  
  
### <a name="to-run-the-sample-on-the-same-computer"></a>Запуск образца на одном компьютере  
  
1. Убедитесь, что путь включает папку, в которой хранится файл Makecert.exe.  
  
2. Запустите программу Setup. bat из образца папки установки в Командная строка разработчика для запуска Visual Studio с правами администратора. Он устанавливает сертификаты службы, необходимые для запуска образца.  
  
3. Запустите программу Client.exe из каталога \client\bin. Действия клиента отображаются в консольном приложении клиента.  
  
4. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-run-the-sample-across-computers"></a>Запуск образца на нескольких компьютерах  
  
1. Создайте каталог на компьютере службы. Создайте для этого каталога виртуальное приложение servicemodelsamples, с помощью средства управления службами IIS.  
  
2. Скопируйте файлы служебной программы из каталога «\inetpub\wwwroot\servicemodelsamples» в виртуальный каталог на компьютере службы. Убедитесь, что скопированы все файлы из подкаталога \bin. Кроме того, скопируйте на компьютер службы файлы Setup.bat, GetComputerName.vbs и Cleanup.bat.  
  
3. Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4. Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента. Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5. На сервере откройте Командная строка разработчика для Visual Studio с правами администратора и запустите `setup.bat service`. При запуске `setup.bat` с аргументом `service` создается сертификат службы с полным доменным именем компьютера и экспортируется сертификат службы в файл с именем Service. cer.  
  
6. Измените файл Web. config в соответствии с новым именем сертификата (в атрибуте `findValue` в [\<serviceCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)), который совпадает с полным доменным именем компьютера.  
  
7. Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиенте откройте Командная строка разработчика для Visual Studio с правами администратора и запустите Импортсервицецерт. bat. Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser - TrustedPeople.  
  
10. На клиентском компьютере из командной строки запустите программу Client.exe. Если клиент и служба не могут обмениваться данными, см. раздел [Советы по устранению неполадок для примеров WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).  
  
### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
- После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
> [!NOTE]
> Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах. Если вы выполнили примеры Windows Communication Foundation (WCF), использующие сертификаты на нескольких компьютерах, обязательно очистите сертификаты службы, установленные в хранилище CurrentUser-TrustedPeople. Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## <a name="the-setup-batch-file"></a>Файл Setup.bat  
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера. Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.  
  
 Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.  
  
- Создание сертификата сервера.  
  
     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера. Переменная %SERVER_NAME% задает имя сервера. Измените эту переменную, чтобы задать собственное имя сервера. По умолчанию в этом пакетном файле используется имя localhost.  
  
     Сертификат хранится в хранилище «My store (Личном хранилище)» в расположении LocalMachine.  
  
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
  
    ```bat  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
