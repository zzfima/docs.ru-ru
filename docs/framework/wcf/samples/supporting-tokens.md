---
title: "Вспомогательные маркеры | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 65a8905d-92cc-4ab0-b6ed-1f710e40784e
caps.latest.revision: 29
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 29
---
# Вспомогательные маркеры
Образец вспомогательных маркеров демонстрирует, как добавить дополнительные маркеры в сообщение, использующее WS\-Security.  Пример добавляет двоичный маркер безопасности X.509 в дополнение к маркеру безопасности имени пользователя.  Этот маркер передается в заголовке сообщения WS\-Security из клиента в службу, и часть сообщения подписывается закрытым ключом, связанным с маркером безопасности X.509, чтобы подтвердить получателю наличие сертификата X.509.  Это полезно в случае, когда для проверки подлинности или авторизации отправителя требуются несколько утверждений, связанных с сообщением.  Служба реализует контракт, определяющий шаблон взаимодействия "запрос\-ответ".  
  
## Демонстрации  
 Образец демонстрирует следующие приемы.  
  
-   Как клиент может передать в службу дополнительные маркеры безопасности.  
  
-   Как сервер может получить доступ к утверждениям, связанным с дополнительными маркерами безопасности.  
  
-   как сертификат X.509 сервера используется для защиты симметричного ключа, служащего для шифрования и подписывания сообщений.  
  
> [!NOTE]
>  Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
## Клиент производит проверку подлинности с помощью маркера имени пользователя и вспомогательного маркера безопасности X.509  
 Служба предоставляет одну конечную точку для взаимодействия, создаваемую программно с помощью классов `BindingHelper` и `EchoServiceHost`.  Конечная точка состоит из адреса, привязки и контракта.  Привязка настраивается с пользовательской привязкой с помощью элементов `SymmetricSecurityBindingElement` и `HttpTransportBindingElement`.  В этом образце в элементе `SymmetricSecurityBindingElement` задается использование сертификата X.509 службы для защиты симметричного ключа во время передачи и для передачи маркера `UserNameToken` вместе со вспомогательным маркером `X509SecurityToken` в заголовке сообщения WS\-Security.  Симметричный ключ используется для шифрования тела сообщения и маркера безопасности с именем пользователя.  Вспомогательный маркер передается как дополнительный двоичный маркер безопасности в заголовке сообщения WS\-Security.  Подлинность вспомогательного маркера подтверждается подписыванием части сообщения закрытым ключом, связанным со вспомогательным маркером безопасности X.509.  
  
```  
public static Binding CreateMultiFactorAuthenticationBinding()  
{  
    HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
  
    // the message security binding element will be configured to require 2 tokens:  
    // 1) A username-password encrypted with the service token  
    // 2) A client certificate used to sign the message  
  
    // Instantiate a binding element that will require the username/password token in the message (encrypted with the server cert)  
    SymmetricSecurityBindingElement messageSecurity = SecurityBindingElement.CreateUserNameForCertificateBindingElement();  
  
    // Create supporting token parameters for the client X509 certificate.  
    X509SecurityTokenParameters clientX509SupportingTokenParameters = new X509SecurityTokenParameters();  
    // Specify that the supporting token is passed in message send by the client to the service  
    clientX509SupportingTokenParameters.InclusionMode = SecurityTokenInclusionMode.AlwaysToRecipient;  
    // Turn off derived keys  
    clientX509SupportingTokenParameters.RequireDerivedKeys = false;  
    // Augment the binding element to require the client's X509 certificate as an endorsing token in the message  
    messageSecurity.EndpointSupportingTokenParameters.Endorsing.Add(clientX509SupportingTokenParameters);  
  
    // Create a CustomBinding based on the constructed security binding element.  
    return new CustomBinding(messageSecurity, httpTransport);  
}  
  
```  
  
 Поведение задает учетные данные службы, которые должны использоваться для проверки подлинности клиента, а также информацию о сертификате X.509 службы.  В этом образце в качестве имени субъекта в сертификате X.509 службы используется `CN=localhost`.  
  
```  
override protected void InitializeRuntime()  
{  
    // Extract the ServiceCredentials behavior or create one.  
    ServiceCredentials serviceCredentials =   
        this.Description.Behaviors.Find<ServiceCredentials>();  
    if (serviceCredentials == null)  
    {  
        serviceCredentials = new ServiceCredentials();  
        this.Description.Behaviors.Add(serviceCredentials);  
    }  
  
    // Set the service certificate  
    serviceCredentials.ServiceCertificate.SetCertificate(  
                                       "CN=localhost");  
  
/*  
Setting the CertificateValidationMode to PeerOrChainTrust means that if the certificate is in the Trusted People store, then it will be trusted without performing a validation of the certificate's issuer chain. This setting is used here for convenience so that the sample can be run without having to have certificates issued by a certification authority (CA).  
This setting is less secure than the default, ChainTrust. The security implications of this setting should be carefully considered before using PeerOrChainTrust in production code.  
*/  
    serviceCredentials.ClientCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
  
    // Create the custom binding and add an endpoint to the service.  
    Binding multipleTokensBinding =  
         BindingHelper.CreateMultiFactorAuthenticationBinding();  
    this.AddServiceEndpoint(typeof(IEchoService),   
                          multipleTokensBinding, string.Empty);  
    base.InitializeRuntime();  
}  
```  
  
 Код службы:  
  
```  
[ServiceBehavior(IncludeExceptionDetailInFaults = true)]  
public class EchoService : IEchoService  
{  
    public string Echo()  
    {  
        string userName;  
        string certificateSubjectName;  
        GetCallerIdentities(  
            OperationContext.Current.ServiceSecurityContext,   
            out userName,   
            out certificateSubjectName);  
            return String.Format("Hello {0}, {1}",   
                    userName, certificateSubjectName);  
    }  
  
    public void Dispose()  
    {  
    }  
  
    bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet,   
            string claimType, out TClaimResource resourceValue)  
            where TClaimResource : class  
    {  
        resourceValue = default(TClaimResource);  
        IEnumerable<Claim> matchingClaims =   
            claimSet.FindClaims(claimType, Rights.PossessProperty);  
        if(matchingClaims == null)  
            return false;  
        IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();  
        if (enumerator.MoveNext())  
        {  
            resourceValue =   
              (enumerator.Current.Resource == null) ? null :   
              (enumerator.Current.Resource as TClaimResource);  
            return true;  
        }  
        else  
        {  
            return false;  
        }  
    }  
  
    // Returns the username and certificate subject name provided by   
    //the client  
    void GetCallerIdentities(ServiceSecurityContext   
        callerSecurityContext,   
        out string userName, out string certificateSubjectName)  
    {  
        userName = null;  
        certificateSubjectName = null;  
  
       // Look in all the claimsets in the authorization context  
       foreach (ClaimSet claimSet in   
               callerSecurityContext.AuthorizationContext.ClaimSets)  
       {  
            if (claimSet is WindowsClaimSet)  
            {  
                // Try to find a Name claim. This will have been   
                // generated from the windows username.  
                string tmpName;  
                if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,   
                                                      out tmpName))  
                {  
                    userName = tmpName;  
                }  
            }  
            else if (claimSet is X509CertificateClaimSet)  
            {  
                // Try to find an X500DisinguishedName claim. This will   
                // have been generated from the client certificate.  
                X500DistinguishedName tmpDistinguishedName;  
                if (TryGetClaimValue<X500DistinguishedName>(claimSet,   
                               ClaimTypes.X500DistinguishedName,   
                               out tmpDistinguishedName))  
                {  
                    certificateSubjectName = tmpDistinguishedName.Name;  
                }  
            }  
        }  
    }  
}   
```  
  
 Конечная точка клиента настраивается таким же образом, как и конечная точка службы.  Для создания привязки в клиенте используется этот же класс `BindingHelper`.  Остальная часть настройки находится в классе `Client`.  Клиент в коде настройки задает сведения о маркере безопасности имени пользователя, вспомогательном маркере безопасности X.509 и о сертификате X.509 службы в коллекции поведений конечной точки клиента.  
  
```  
 static void Main()  
 {  
     // Create the custom binding and an endpoint address for   
     // the service.  
     Binding multipleTokensBinding =   
         BindingHelper.CreateMultiFactorAuthenticationBinding();  
         EndpointAddress serviceAddress = new EndpointAddress(  
         "http://localhost/servicemodelsamples/service.svc");  
       ChannelFactory<IEchoService> channelFactory = null;  
       IEchoService client = null;  
  
       Console.WriteLine("Username authentication required.");  
       Console.WriteLine(  
         "Provide a valid machine or domain account. [domain\\user]");  
       Console.WriteLine("   Enter username:");  
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
                    password =   
                       password.Substring(0, password.Length - 1);  
                }  
                info = Console.ReadKey(true);  
            }  
         }  
         for (int i = 0; i < password.Length; i++)  
            Console.Write("*");  
         Console.WriteLine();  
         try  
         {  
           // Create a proxy with the previously create binding and   
           // endpoint address  
              channelFactory =   
                 new ChannelFactory<IEchoService>(  
                     multipleTokensBinding, serviceAddress);  
           // configure the username credentials, the client   
           // certificate and the server certificate on the channel   
           // factory   
           channelFactory.Credentials.UserName.UserName = username;  
           channelFactory.Credentials.UserName.Password = password;  
           channelFactory.Credentials.ClientCertificate.SetCertificate(  
           "CN=client.com", StoreLocation.CurrentUser, StoreName.My);  
              channelFactory.Credentials.ServiceCertificate.SetDefaultCertificate(  
           "CN=localhost", StoreLocation.LocalMachine, StoreName.My);  
           client = channelFactory.CreateChannel();  
           Console.WriteLine("Echo service returned: {0}",   
                                           client.Echo());  
  
           ((IChannel)client).Close();  
           channelFactory.Close();  
        }  
        catch (CommunicationException e)  
        {  
         Abort((IChannel)client, channelFactory);  
         // if there is a fault then print it out  
         FaultException fe = null;  
         Exception tmp = e;  
         while (tmp != null)  
         {  
            fe = tmp as FaultException;  
            if (fe != null)  
            {  
                break;  
            }  
            tmp = tmp.InnerException;  
        }  
        if (fe != null)  
        {  
           Console.WriteLine("The server sent back a fault: {0}",   
         fe.CreateMessageFault().Reason.GetMatchingTranslation().Text);  
        }  
        else  
        {  
         Console.WriteLine("The request failed with exception: {0}",e);  
        }  
    }  
    catch (TimeoutException)  
    {  
        Abort((IChannel)client, channelFactory);  
        Console.WriteLine("The request timed out");  
    }  
    catch (Exception e)  
    {  
         Abort((IChannel)client, channelFactory);  
          Console.WriteLine(  
          "The request failed with unexpected exception: {0}", e);  
    }  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
## Отображение информации об абоненте  
 Для вывода информации об абоненте можно использовать свойство `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets`, как показано в следующем коде.  Свойство `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` содержит утверждения авторизации, связанные с текущим абонентом.  Эти утверждения автоматически предоставляются [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] для каждого маркера, полученного в сообщении.  
  
```  
bool TryGetClaimValue<TClaimResource>(ClaimSet claimSet, string   
                         claimType, out TClaimResource resourceValue)  
    where TClaimResource : class  
{  
    resourceValue = default(TClaimResource);  
    IEnumerable<Claim> matchingClaims =   
    claimSet.FindClaims(claimType, Rights.PossessProperty);  
    if (matchingClaims == null)  
          return false;  
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();  
    if (enumerator.MoveNext())  
    {  
        resourceValue = (enumerator.Current.Resource == null) ? null : (enumerator.Current.Resource as TClaimResource);  
        return true;  
    }  
    else  
    {  
         return false;  
    }  
}  
  
// Returns the username and certificate subject name provided by the client  
void GetCallerIdentities(ServiceSecurityContext callerSecurityContext, out string userName, out string certificateSubjectName)  
{  
    userName = null;  
    certificateSubjectName = null;  
  
    // Look in all the claimsets in the authorization context  
    foreach (ClaimSet claimSet in   
      callerSecurityContext.AuthorizationContext.ClaimSets)  
    {  
        if (claimSet is WindowsClaimSet)  
        {  
            // Try to find a Name claim. This will have been generated   
            //from the windows username.  
            string tmpName;  
            if (TryGetClaimValue<string>(claimSet, ClaimTypes.Name,   
                                                     out tmpName))  
            {  
                userName = tmpName;  
            }  
        }  
        else if (claimSet is X509CertificateClaimSet)  
         {  
            //Try to find an X500DisinguishedName claim.   
            //This will have been generated from the client   
            //certificate.  
            X500DistinguishedName tmpDistinguishedName;  
            if (TryGetClaimValue<X500DistinguishedName>(claimSet,   
               ClaimTypes.X500DistinguishedName,   
               out tmpDistinguishedName))  
            {  
                    certificateSubjectName = tmpDistinguishedName.Name;  
            }  
        }  
    }  
}  
```  
  
## Запуск примера  
 При выполнении образца клиент сначала запрашивает имя пользователя и пароль для маркера имени пользователя.  Обязательно предоставьте правильные значения для вашей учетной записи в системе, так как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в службе сопоставляет значения в маркере имени пользователя с идентификацией, предоставленной системой.  После этого клиент отображает ответ от службы.  Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
## Пакетный файл Setup  
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения приложения, размещенного в службах IIS, которое требует обеспечения безопасности на основе сертификата сервера.  Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.  
  
 Ниже представлен краткий обзор различных разделов пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.  
  
### Создание сертификата клиента  
 Следующие строки из файла Setup.bat создают сертификат клиента, который будет использоваться.  Переменная `%CLIENT_NAME%` задает субъект сертификата клиента.  В этом образце в качестве имени субъекта используется "client.com".  
  
 Сертификат хранится в хранилище "My store" \(Личном хранилище\) в расположении `CurrentUser`.  
  
```  
echo ************  
echo making client cert  
echo ************  
makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
```  
  
### Установка сертификата клиента в хранилище доверенных сертификатов сервера  
 Следующая строка из файла Setup.bat копирует сертификат клиента в хранилище доверенных лиц сервера.  Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны серверной системы.  Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.  
  
```  
echo ************  
echo copying client cert to server's CurrentUserstore  
echo ************  
certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
```  
  
### Создание сертификата сервера  
 Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.  Переменная `%SERVER_NAME%` задает имя сервера.  Измените эту переменную, чтобы задать собственное имя сервера.  По умолчанию в этом пакетном файле используется имя localhost.  
  
 Сертификат хранится в хранилище «My store \(Личном хранилище\)» в расположении LocalMachine.  Для служб, размещенных в службах IIS, сертификат хранится в хранилище LocalMachine.  Для резидентных служб необходимо изменить пакетный файл, чтобы сертификат сервера хранился в местоположении хранения CurrentUser, заменив строку LocalMachine строкой CurrentUser.  
  
```  
echo ************  
echo Server cert setup starting  
echo %SERVER_NAME%  
echo ************  
echo making server cert  
echo ************  
makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
```  
  
### Установка сертификата сервера в хранилище доверенных сертификатов клиента  
 Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента.  Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.  Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.  
  
```  
echo ************  
echo copying server cert to client's TrustedPeople store  
echo ************certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
```  
  
### Обеспечение доступа к закрытому ключу сертификата  
 Чтобы разрешить доступ к закрытому ключу сертификата из службы, размещенной в службах IIS, учетной записи пользователя, под которой выполняется процесс, размещенный в службах IIS, должны быть предоставлены соответствующие разрешения для закрытого ключа.  Это производится в последних шагах скрипта Setup.bat.  
  
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
  
##### Настройка, сборка и выполнение образца  
  
1.  Убедитесь, что выполнена [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  При построении решения следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Чтобы выполнить образец на одном или нескольких компьютерах, выполните следующие инструкции.  
  
##### Запуск образца на том же компьютере  
  
1.  Откройте окно командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора и запустите файл Setup.bat из папки установки образца.  При этом устанавливаются все сертификаты, необходимые для выполнения образца.  
  
    > [!NOTE]
    >  Пакетный файл Setup.bat предназначен для запуска из командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  Переменная среды PATH, заданная в командной строке [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], указывает на каталог, содержащий исполняемые файлы, необходимые для скрипта Setup.bat.  После завершения работы с образцом для удаления сертификатов обязательно запустите файл Cleanup.bat.  В других образцах обеспечения безопасности используются те же сертификаты.  
  
2.  Запустите программу Client.exe из каталога \\client\\bin.  Действия клиента отображаются в консольном приложении клиента.  
  
3.  Если клиенту и службе не удается взаимодействовать, см. раздел [Советы по устранению неполадок](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
##### Выполнение примера на нескольких компьютерах  
  
1.  Создайте каталог на компьютере службы.  Создайте для этого каталога виртуальное приложение servicemodelsamples, воспользовавшись для этого средством управления службами IIS.  
  
2.  Скопируйте файлы программы службы из каталога \\inetpub\\wwwroot\\servicemodelsamples в виртуальный каталог на компьютере службы.  Убедитесь, что скопированы все файлы из подкаталога \\bin.  Кроме того, скопируйте файлы Cleanup.bat и ImportClientCert.bat на компьютер службы.  
  
3.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.  Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5.  На сервере откройте командную строку Visual Studio с правами администратора и запустите файл `setup.bat service`.  При запуске команды `setup.bat` ``  с аргументом `service` создается сертификат службы с полным именем домена компьютера, который экспортируется в файл с именем Service.cer.  
  
6.  Внесите в файл Web.config изменения в соответствии с новым именем сертификата \(в атрибуте `findValue` в элементе [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\), которое совпадает с полным доменным именем компьютера.  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл `setup.bat client`.  При выполнении команды `setup.bat` с аргументом `client` создается сертификат клиента с именем Client.com, который экспортируется в файл с именем Client.cer.  
  
9. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.  Для этого замените имя localhost полным доменным именем сервера.  
  
10. Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
11. Запустите на клиенте файл ImportServiceCert.bat.  Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
12. На сервере запустите файл ImportClientCert.bat. Он импортирует сертификат клиента из файла Client.cer в хранилище LocalMachine \- TrustedPeople.  
  
13. На клиентском компьютере из окна командной строки запустите программу Client.exe.  Если клиенту и службе не удается взаимодействовать, см. раздел [Советы по устранению неполадок](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
##### Очистка после образца  
  
-   После завершения работы примера запустите в папке примеров файл Cleanup.bat.  
  
> [!NOTE]
>  Этот скрипт не удаляет сертификаты службы на клиенте при выполнении примера на нескольких компьютерах.  Если примеры [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в которых использовались сертификаты, выполнялись на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище CurrentUser \- TrustedPeople.  Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Например: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## См. также