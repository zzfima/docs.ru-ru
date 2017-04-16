---
title: "Сертификат безопасности сообщений | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WS-Security"
ms.assetid: 909333b3-35ec-48f0-baff-9a50161896f6
caps.latest.revision: 51
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 51
---
# Сертификат безопасности сообщений
В этом образце показано, как реализовать приложение, использующее протокол WS\-Security и проверку подлинности с использованием сертификата X.509 v3 для клиента и требующее проверки подлинности сервера с использованием сертификата X.509 v3 сервера.В этом образце используются параметры по умолчанию, обеспечивающие подписывание и шифрование всех сообщений приложения, которыми обмениваются клиент и сервер.Этот образец основан в примере [WSHttpBinding](../../../../docs/framework/wcf/samples/wshttpbinding.md) и содержит консольную программу клиента и библиотеку службы, размещаемую в службах IIS.Служба реализует контракт, определяющий шаблон взаимодействия "запрос\-ответ".  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 В этом образце демонстрируется управление проверкой подлинности с помощью файла конфигурации, а также получение удостоверения вызывающего объекта из контекста безопасности, как показано в следующем образце кода.  
  
```  
public class CalculatorService : ICalculator  
{  
    public string GetCallerIdentity()  
    {  
        // The client certificate is not mapped to a Windows identity by default.  
        // ServiceSecurityContext.PrimaryIdentity is populated based on the information  
        // in the certificate that the client used to authenticate itself to the service.  
        return ServiceSecurityContext.Current.PrimaryIdentity.Name;  
    }  
    ...  
}  
```  
  
 Служба предоставляет одну конечную точку для взаимодействия со службой и одну конечную точку для предоставления документа WSDL службы с использованием протокола WS\-MetadataExchange, определенного с помощью файла конфигурации \(Web.config\).Конечная точка состоит из адреса, привязки и контракта.Привязка настраивается с помощью стандартного элемента [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), который по умолчанию использует безопасность сообщений.В этом образце атрибуту `clientCredentialType` присваивается значение Certificate для запроса проверки подлинности клиента.  
  
```  
<system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="wsHttpBinding"/>  
    </protocolMapping>  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding>  
          <security mode ="Message">  
            <message clientCredentialType="Certificate" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
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
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
  
```  
  
 Поведение задает учетные данные службы, используемые при проверке подлинности службы клиентом.Имя субъекта сертификата сервера задается в атрибуте `findValue` элемента [\<serviceCredentials\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).  
  
```  
<!--For debugging purposes, set the includeExceptionDetailInFaults attribute to true.-->  
<behaviors>  
      <serviceBehaviors>  
        <behavior>  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--   
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by the service to authenticate itself to its clients and to provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
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
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
```  
  
 Конфигурация конечной точки клиента состоит из абсолютного адреса конечной точки службы, привязки и контракта.Привязка клиента настраивается с помощью соответствующих режимов безопасности и проверки подлинности.Если сценарий выполняется на нескольких компьютерах, убедитесь, что адрес конечной точки службы изменен соответствующим образом.  
  
```  
<system.serviceModel>  
    <client>  
      <!-- Use a behavior to configure the client certificate to present to the service. -->  
      <endpoint address="http://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" behaviorConfiguration="ClientCertificateBehavior" contract="Microsoft.Samples.Certificate.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!--   
        This configuration defines the security mode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
...  
</system.serviceModel>  
  
```  
  
 Реализация клиента позволяет задать сертификат для использования посредством файла конфигурации или кода.В следующем образце показано, как задать сертификат для использования в файле конфигурации.  
  
```  
<system.serviceModel>  
  ...  
  
<behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCertificateBehavior">  
          <!--   
        The clientCredentials behavior allows one to define a certificate to present to a service.  
        A certificate is used by a client to authenticate itself to the service and provide message integrity.  
        This configuration references the "client.com" certificate installed during the setup instructions.  
        -->  
          <clientCredentials>  
            <clientCertificate findValue="client.com" storeLocation="CurrentUser" storeName="My" x509FindType="FindBySubjectName"/>  
            <serviceCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certificate authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust"/>  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
  
</system.serviceModel>  
  
```  
  
 В следующем образце показано, как вызвать службу в программе.  
  
```  
// Create a client.  
CalculatorClient client = new CalculatorClient();  
  
// Call the GetCallerIdentity service operation.  
Console.WriteLine(client.GetCallerIdentity());  
...  
//Closing the client gracefully closes the connection and cleans up resources.  
client.Close();  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
```  
CN=client.com  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
Press <ENTER> to terminate client.  
```  
  
 Пакетный файл Setup.bat, входящий в состав образцов реализации безопасности сообщений, позволяет настроить для клиента и сервера соответствующие сертификаты, необходимые для выполнения размещенного приложения, для которого требуется обеспечение безопасности на основе сертификата.Пакетный файл можно выполнять в трех режимах.Чтобы выполнить пакетный файл в режиме одного компьютера, в командной строке среды Visual Studio введите **setup.bat**, для выполнения в режиме службы введите **setup.bat service**, в режиме клиента введите **setup.bat client**.Режимы клиента и сервера используются для выполнения образца на нескольких компьютерах.Подробные сведения см. в описании процедуры настройки в конце этого раздела.Ниже представлен краткий обзор различных разделов пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.  
  
-   Создание сертификата клиента.  
  
     Следующая строка пакетного файла создает сертификат клиента.В качестве имени субъекта создаваемого сертификата используется указанное имя клиента.Сертификат сохраняется в хранилище `My` в расположении `CurrentUser`.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
    ```  
  
-   Установка сертификата клиента в хранилище доверенных сертификатов сервера.  
  
     Следующая строка пакетного файла копирует сертификат клиента в хранилище TrustedPeople сервера, чтобы сервер мог принимать соответствующие решения о доверии или недоверии.Чтобы установленный в хранилище TrustedPeople сертификат был доверенным для службы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], для режима проверки сертификата клиента должно быть задано значение `PeerOrChainTrust` или `PeerTrust`.Чтобы узнать, как это сделать с помощью файла конфигурации, см. приведенный выше образец конфигурации службы.  
  
    ```  
    echo ************  
    echo copying client cert to server's LocalMachine store  
    echo ************  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople   
    ```  
  
-   Создание сертификата сервера.  
  
     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.  
  
    ```  
    echo ************  
    echo Server cert setup starting  
    echo %SERVER_NAME%  
    echo ************  
    echo making server cert  
    echo ************  
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe  
    ```  
  
     Переменная %SERVER\_NAME% задает имя сервера.Сертификат хранится в хранилище LocalMachine.Если пакетный файл Setup.bat запускается с аргументом service \(например, **setup.bat service**\), переменная %SERVER\_NAME% содержит полное имя домена компьютера.В противном случае по умолчанию используется значение localhost.  
  
-   Установка сертификата сервера в хранилище доверенных сертификатов клиента.  
  
     Следующая строка копирует сертификат сервера в хранилище доверенных лиц клиента.Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.  
  
    ```  
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople  
    ```  
  
-   Предоставление разрешений в отношении закрытого ключа сертификата.  
  
     Следующие строки файла Setup.bat открывают доступ к сертификату сервера, расположенному в хранилище LocalMachine, для учетной записи рабочего процесса [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
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
  
    > [!NOTE]
    >  Если используется в англоязычном\(не американском\) выпуске Windows, необходимо изменить файл Setup.bat и заменить имя учетной записи «NT AUTHORITY\\NETWORK SERVICE» своим региональным эквивалентом.  
  
> [!NOTE]
>  Средства, используемые в этом пакетном файле, расположены в каталоге C:\\Program Files\\Microsoft Visual Studio 8\\Common7\\tools или C:\\Program Files\\Microsoft SDKs\\Windows\\v6.0\\bin.Один из этих каталогов должен быть указан в системном пути.Если установлена среда Visual Studio, самым простым способом получения этого каталога в пути является открытие командной строки Visual Studio.Выберите пункт **Пуск**, а затем пункт **Все программы**, **Visual Studio 2012**, **Инструменты**.В командной строке уже должны быть настроены соответствующие пути.В противном случае необходимо вручную добавить соответствующий каталог в путь.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением работы проверьте наличие следующего \(предусмотренного по умолчанию\) каталога:  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец находится в следующем каталоге:  
>   
>  `<диск_установки>:\WF_WCF_Samples\WCF\Basic\Binding\WS\MessageSecurity`  
  
### Настройка, построение и выполнение образца  
  
1.  Убедитесь, что выполнена процедура, описанная в разделе [Процедура однократной настройки образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Чтобы создать выпуск решения на языке C\# или Visual Basic .NET, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
### Запуск образца на одном компьютере  
  
1.  Откройте командную строку Visual Studio с правами администратора и запустите файл Setup.bat из папки установки образцов.При этом устанавливаются все сертификаты, необходимые для запуска образца.  
  
    > [!NOTE]
    >  Пакетный файл Setup.bat предназначен для запуска из командной строки Visual Studio.Необходимо, чтобы переменная среды path указывала на каталог, в котором установлен пакет SDK.Эта переменная среды автоматически устанавливается в командной строке Visual Studio 2010.  
  
2.  Проверьте доступ к службе с помощью браузера путем ввода адреса `http://localhost/servicemodelsamples/service.svc`.  
  
3.  Запустите программу Client.exe из каталога \\client\\bin.Действия клиента отображаются в консольном приложении клиента.  
  
4.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Запуск образца на нескольких компьютерах  
  
1.  Создайте каталог на компьютере службы.Создайте для этого каталога виртуальное приложение servicemodelsamples, с помощью средства управления службами IIS.  
  
2.  Скопируйте файлы служебной программы из каталога «\\inetpub\\wwwroot\\servicemodelsamples» в виртуальный каталог на компьютере службы.Убедитесь, что скопированы все файлы из подкаталога \\bin.Также скопируйте файлы Setup.bat, Cleanup.bat и ImportClientCert.bat на компьютер службы.  
  
3.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5.  На сервере откройте командную строку Visual Studio с правами администратора и выполните команду **setup.bat service**.При запуске команды **setup.bat** с аргументом **service** создается сертификат службы с полным именем домена компьютера и экспортируется в файл с именем Service.cer.  
  
6.  Внесите в файл Web.config изменения в соответствии с новым именем сертификата \(в атрибуте `findValue` в [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\), которое совпадает с полным именем домена компьютера.  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  На клиентском компьютере выполните команду **setup.bat client** с правами администратора из командной строки Visual Studio.При выполнении команды **setup.bat** с аргументом **client** создается сертификат клиента с именем client.com, который экспортируется в файл с именем Client.cer.  
  
9. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.Для этого замените имя localhost полным доменным именем сервера.  
  
10. Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
11. На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
12. На сервере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.При этом импортируется сертификат клиента из файла Client.cer в хранилище «LocalMachine — TrustedPeople».  
  
13. На клиентском компьютере из окна командной строки запустите программу Client.exe.Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
### Очистка после образца  
  
-   После завершения работы образца запустите в папке образцов файл Cleanup.bat.  
  
    > [!NOTE]
    >  Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.Если образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser — TrustedPeople».Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Пример: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## См. также