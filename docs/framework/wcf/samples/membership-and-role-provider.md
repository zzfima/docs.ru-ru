---
title: "Поставщик членства и ролей | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d11a31c-e75f-4fcf-9cf4-b7f26e056bcd
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Поставщик членства и ролей
В образце поставщиков членства и ролей показано, как создать службу, которая может с помощью поставщиков членства и ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполнять проверку подлинности и авторизацию клиентов.  
  
 В этом образце клиентом является консольное приложение \(EXE\), а служба размещается в службах IIS.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца расположены в конце этого раздела.  
  
 В образце демонстрируются следующие возможности.  
  
-   Клиент может проходить проверку подлинности по имени пользователя и паролю.  
  
-   Сервер может проверять учетные данные, используя поставщик участия [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
-   Сервер может проходить проверку подлинности с помощью сертификата X.509 сервера.  
  
-   Сервер может сопоставить прошедший проверку подлинности клиент с ролью с помощью поставщика ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
-   Сервер может использовать атрибут `PrincipalPermissionAttribute` для управления доступом к определенным методам, предоставляемым службой.  
  
 Поставщики членства и ролей настраиваются на использование хранилища на базе SQL Server.Строка подключения и другие параметры задаются в файле конфигурации службы.Поставщик участия получает имя `SqlMembershipProvider`, а поставщик ролей — имя `SqlRoleProvider`.  
  
```  
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
  
 Служба предоставляет одну конечную точку для взаимодействия с ней. Эта точка задается в файле конфигурации Web.config.Конечная точка состоит из адреса, привязки и контракта.Привязка настраивается с помощью стандартного элемента `wsHttpBinding`, который по умолчанию использует проверку подлинности Windows.В этом образце стандартная привязка `wsHttpBinding` использует проверку подлинности имени пользователя.Поведение определяет, что для проверки подлинности службы должен использоваться сертификат сервера.Значение `SubjectName` сертификата сервера должно совпадать со значением атрибута `findValue` в элементе конфигурации [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).Кроме того, поведение определяет, что проверка подлинности пар "имя пользователя\-пароль" выполняется поставщиком членства [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], а сопоставление ролей выполняется поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], для чего в поведении заданы имена двух поставщиков.  
  
```  
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
  
 При запуске этого образца клиент вызывает различные операции службы от имени различных учетных записей пользователей: Alice, Bob и Charlie.Запросы и ответы операций появляются в окне консоли клиента.Все четыре вызова от имени пользователя Alice должны завершиться успешно.Пользователь Bob должен получить отказ в доступе при попытке вызвать метод Divide.Пользователь Charlie должен получить отказ в доступе при попытке вызвать метод Multiply.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
### Настройка, построение и выполнение образца  
  
1.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Выполнение примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
2.  Убедитесь, что настроена [база данных служб приложения ASP.NET](http://go.microsoft.com/fwlink/?LinkId=94997).  
  
    > [!NOTE]
    >  Если используется выпуск SQL Server Express Edition, то сервер имеет имя.SQLEXPRESSЭто имя сервера следует использовать при настройке базы данных служб приложения [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], а также в строке подключения в файле Web.config.  
  
    > [!NOTE]
    >  У учетной записи рабочего процесса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] должны быть разрешения на доступ к созданной на этом этапе базе данных.Для этого воспользуйтесь служебной программой sqlcmd или средой SQL Server Management Studio.  
  
3.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте приведенным далее инструкциям.  
  
### Запуск образца на одном компьютере  
  
1.  Убедитесь, что путь включает папку, в которой хранится файл Makecert.exe.  
  
2.  Из командной строки Visual Studio, запущенной с правами администратора, запустите файл Setup.bat из папки установки образца.Он устанавливает сертификаты службы, необходимые для запуска образца.  
  
3.  Запустите программу Client.exe из каталога \\client\\bin.Действия клиента отображаются в консольном приложении клиента.  
  
4.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Запуск образца на нескольких компьютерах  
  
1.  Создайте каталог на компьютере службы.Создайте для этого каталога виртуальное приложение servicemodelsamples, с помощью средства управления службами IIS.  
  
2.  Скопируйте файлы служебной программы из каталога «\\inetpub\\wwwroot\\servicemodelsamples» в виртуальный каталог на компьютере службы.Убедитесь, что скопированы все файлы из подкаталога \\bin.Кроме того, скопируйте на компьютер службы файлы Setup.bat, GetComputerName.vbs и Cleanup.bat.  
  
3.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5.  Откройте на сервере командную строку Visual Studio с правами администратора и запустите `setup.bat service`.При запуске команды `setup.bat` с аргументом `service` создается сертификат службы с полным именем домена компьютера и экспортируется в файл с именем Service.cer.  
  
6.  Внесите в файл Web.config изменения в соответствии с новым именем сертификата \(в атрибуте `findValue` в [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\), которое совпадает с полным именем домена компьютера.  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  
  
9. На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
10. На клиентском компьютере из командной строки запустите программу Client.exe.Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Очистка после образца  
  
-   После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
> [!NOTE]
>  Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser — TrustedPeople».Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## Файл Setup.bat  
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.  
  
 Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.  
  
-   Создание сертификата сервера.  
  
     Следующие строки из файла Setup.bat создают сертификат сервера, который будет использоваться.Переменная %SERVER\_NAME% задает имя сервера.Измените эту переменную, чтобы задать собственное имя сервера.По умолчанию в этом пакетном файле используется имя localhost.  
  
     Сертификат хранится в хранилище «My store \(Личном хранилище\)» в расположении LocalMachine.  
  
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
  
     Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента.Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
## См. также