---
title: "Политика авторизации | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1db325ec-85be-47d0-8b6e-3ba2fdf3dda0
caps.latest.revision: 38
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 38
---
# Политика авторизации
В этом образце показано, как реализовать пользовательскую политику авторизации утверждений и связанный с ней пользовательский диспетчер авторизации службы.Это бывает удобно, если служба осуществляет проверку прав доступа к операциям службы на основании утверждений и предоставляет вызывающей стороне определенные права, прежде чем проверить права доступа.В этом образце показан процесс добавления утверждений, а также процесс проверки прав доступа с использованием готового набора утверждений.Все сообщения приложений, которыми обмениваются служба и клиент, подписываются и шифруются.По умолчанию при использовании привязки `wsHttpBinding` для входа от имени действующей учетной записи Windows NT используются предоставляемые клиентом имя пользователя и пароль.В этом образце показано, как проверять подлинность клиента с помощью пользовательского объекта <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>.Кроме того, в этом образце показана проверка подлинности клиента на стороне службы с использованием сертификата X.509.Этот образец показывает реализацию объектов <xref:System.IdentityModel.Policy.IAuthorizationPolicy> и <xref:System.ServiceModel.ServiceAuthorizationManager>, которые между собой предоставляют заданным пользователям доступ к определенным методам службы.Этот образец основан на примере [Безопасность сообщений с использованием имени пользователя](../../../../docs/framework/wcf/samples/message-security-user-name.md), но показывает, как выполнять преобразование утверждений до вызова <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
> [!NOTE]
>  Процедура установки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Таким образом, в данном образце демонстрируются указанные ниже возможности.  
  
-   Подлинность клиента может проверяться с помощью имени пользователя и пароля.  
  
-   Подлинность клиента может проверяться с помощью сертификата X.509.  
  
-   Сервер проверяет учетные данные клиента с помощью пользовательского проверяющего элемента управления `UsernamePassword`.  
  
-   Сервер проходит проверку подлинности с использованием сертификата X.509 сервера.  
  
-   Сервер может использовать объект <xref:System.ServiceModel.ServiceAuthorizationManager> для управления доступом к определенным методам службы.  
  
-   Реализация политики <xref:System.IdentityModel.Policy.IAuthorizationPolicy>.  
  
 Служба предоставляет две конечные точки для взаимодействия со службой, определенной в файле конфигурации App.config.Каждая конечная точка состоит из адреса, привязки и контракта.Одна привязка настраивается с помощью стандартной привязки `wsHttpBinding`, использующей протокол WS\-Security и проверку подлинности имени пользователя клиента.Вторая привязка настраивается с помощью стандартной привязки `wsHttpBinding`, использующей протокол WS\-Security и проверку подлинности сертификата клиента.Элемент [\<поведение\>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) указывает, что для проверки подлинности службы следует использовать учетные данные пользователя.Свойство `SubjectName` сертификата сервера должно совпадать со значением атрибута `findValue` в элементе конфигурации [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md).  
  
```  
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
  
 Конфигурация каждой из конечных точек клиента состоит из имени конфигурации, абсолютного адреса конечной точки службы, привязки и контракта.Для привязки клиента настраивается соответствующий режим безопасности, как указано в данном случае в [\<безопасность\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md), и `clientCredentialType`, как указано в [\<сообщение\>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md).  
  
```  
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
  
```  
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
  
```  
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
  
 В этом образце для проверки имен пользователей и паролей применяется пользовательский объект <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>.В этом образце реализуется класс `MyCustomUserNamePasswordValidator`, наследуемый от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.Дополнительные сведения см. в документации по классу <xref:System.IdentityModel.Selectors.UsernamePasswordValidator>.В целях демонстрации интеграции с <xref:System.IdentityModel.Selectors.UsernamePasswordValidator> в этом образце пользовательского проверяющего элемента управления реализуется метод <xref:System.IdentityModel.Selectors.UsernamePasswordValidator.Validate%2A>, который принимает пары "имя пользователя\-пароль", где имя пользователя соответствует паролю, как показано в следующем примере кода.  
  
```  
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
  
 После реализации в коде службы проверяющего элемента управления необходимо проинформировать узел службы о проверяющем элементе управления, который следует использовать.Для этого можно воспользоваться следующим фрагментом кода.  
  
```  
Servicehost.Credentials.UserNameAuthentication.UserNamePasswordValidationMode = UserNamePasswordValidationMode.Custom;  
serviceHost.Credentials.UserNameAuthentication.CustomUserNamePasswordValidator = new MyCustomUserNamePasswordValidatorProvider();  
```  
  
 Либо можно решить эту же задачу с помощью файла конфигурации.  
  
```  
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
  
 В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] реализована функциональная модель проверки прав доступа на основе утверждений.Для контроля прав доступа и проверки, удовлетворяют ли связанные с клиентом удостоверения требованиям, необходимым для доступа к методу службы, используется объект <xref:System.ServiceModel.ServiceAuthorizationManager>.  
  
 В демонстрационных целях в этом образце показана реализация <xref:System.ServiceModel.ServiceAuthorizationManager>, включающая метод <xref:System.ServiceModel.ServiceAuthorizationManager.CheckAccessCore%2A>, который дает возможность пользователю обращаться к методам на основе утверждений типа http:\/\/example.com\/claims\/allowedoperation, значения которых представляют собой коды URI действий разрешенных к вызову операций.  
  
```  
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
  
 После реализации пользовательского объекта <xref:System.ServiceModel.ServiceAuthorizationManager> необходимо проинформировать узел службы об объекте <xref:System.ServiceModel.ServiceAuthorizationManager>, который следует использовать.Это можно сделать с помощью следующего фрагмента кода.  
  
```  
<behavior ...>  
    ...  
    <serviceAuthorization serviceAuthorizationManagerType="Microsoft.ServiceModel.Samples.MyServiceAuthorizationManager, service">  
        ...  
    </serviceAuthorization>  
</behavior>  
  
```  
  
 Основным реализуемым методом <xref:System.IdentityModel.Policy.IAuthorizationPolicy> является метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29>.  
  
```  
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
  
 В приведенном выше примере кода показано, каким образом метод <xref:System.IdentityModel.Policy.IAuthorizationPolicy.Evaluate%28System.IdentityModel.Policy.EvaluationContext%2CSystem.Object%40%29> проверяет, что не было добавлено новых утверждений, которые влияют на обработку, и добавляет нужные утверждения.Разрешенные утверждения получаются из метода `GetAllowedOpList`, реализация которого возвращает заданный список операций, которые разрешено выполнять пользователю.Политика авторизации добавляет утверждения для доступа к определенной операции.Впоследствии эта политика используется объектом <xref:System.ServiceModel.ServiceAuthorizationManager> для принятия решений о предоставлении доступа.  
  
 После реализации интерфейса <xref:System.IdentityModel.Policy.IAuthorizationPolicy> необходимо проинформировать узел службы о политиках авторизации, которые следует использовать.  
  
```  
<serviceAuthorization ...>  
       <authorizationPolicies>   
            <add policyType='Microsoft.ServiceModel.Samples.CustomAuthorizationPolicy.MyAuthorizationPolicy, PolicyLibrary' />  
       </authorizationPolicies>   
</serviceAuthorization>  
  
```  
  
 При выполнении образца запросы и ответы операций отображаются в окне консоли клиента.Клиент успешно вызывает методы Add, Subtract и Multiple и получает сообщение "Access is denied" при попытке вызывать метод Divide.Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.  
  
## Пакетный файл Setup  
 Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующие сертификаты, необходимые для выполнения резидентного приложения, которое требует обеспечения безопасности на основе сертификата сервера.  
  
 Ниже представлен краткие общие сведения различных разделов пакетных файлов, позволяющий изменять их для выполнения в соответствующей конфигурации.  
  
-   Создание сертификата сервера.  
  
     Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.Переменная %SERVER\_NAME% задает имя сервера.Измените эту переменную, чтобы задать собственное имя сервера.Значением по умолчанию является localhost.  
  
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
  
-   Создание сертификата клиента.  
  
     Следующие строки из файла Setup.bat создают сертификат клиента, который будет использоваться.Переменная %USER\_NAME% задает имя сервера.Эта переменная имеет значение "test1", поскольку политика `IAuthorizationPolicy` ищет именно это имя.Если изменить значение переменной %USER\_NAME%, необходимо изменить и соответствующее значение в методе `IAuthorizationPolicy.Evaluate`.  
  
     Сертификат хранится в хранилище "My store" \(Личном хранилище\) в расположении CurrentUser.  
  
    ```  
    echo ************  
    echo making client cert  
    echo ************  
    makecert.exe -sr CurrentUser -ss MY -a sha1 -n CN=%CLIENT_NAME% -sky exchange -pe  
  
    ```  
  
-   Установка сертификата клиента в хранилище доверенных сертификатов сервера.  
  
     Следующие строки из файла Setup.bat копируют сертификат клиента в хранилище доверенных лиц.Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны серверной системы.Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата клиента в хранилище сертификатов сервера не требуется.  
  
    ```  
    certmgr.exe -add -r CurrentUser -s My -c -n %CLIENT_NAME% -r LocalMachine -s TrustedPeople  
    ```  
  
#### Настройка и построение образца  
  
1.  Чтобы построить решение, следуйте инструкциям в разделе [Построение образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
2.  Чтобы запустить образец на одном или нескольких компьютерах, следуйте приведенным далее инструкциям.  
  
> [!NOTE]
>  Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.  
  
#### Запуск образца на одном компьютере  
  
1.  Откройте окно командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] с правами администратора и запустите файл Setup.bat из папки установки образца.При этом устанавливаются все сертификаты, необходимые для запуска образца.  
  
    > [!NOTE]
    >  Пакетный файл Setup.bat предназначен для запуска из командной строки [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].Переменная среды PATH, заданная в командной строке [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], указывает на каталог, содержащий исполняемые файлы, необходимые для скрипта Setup.bat.  
  
2.  Из командной строки Visual Studio, открытой с правами администратора, запустите файл Setup.bat из папки установки образца.При этом устанавливаются все сертификаты, необходимые для запуска образца.  
  
3.  Запустите программу Service.exe из каталога service\\bin.  
  
4.  Запустите программу Client.exe из каталога \\client\\bin.Действия клиента отображаются в консольном приложении клиента.  
  
5.  Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### Запуск образца на нескольких компьютерах  
  
1.  Создайте каталог на компьютере службы.  
  
2.  Копируйте файлы служебных программ из каталога \\service\\bin в каталог на компьютере службы.Кроме того, скопируйте на компьютер службы файлы Setup.bat, Cleanup.bat, GetComputerName.vbs и ImportClientCert.bat.  
  
3.  Создайте на клиентском компьютере каталог для двоичных файлов клиента.  
  
4.  Скопируйте в клиентский каталог на клиентском компьютере файлы программы клиента.Кроме того, скопируйте на клиент файлы Setup.bat, Cleanup.bat и ImportServiceCert.bat.  
  
5.  На сервере откройте командную строку Visual Studio с правами администратора и запустите `setup.bat service`.При запуске команды `setup.bat` с аргументом `service` создается сертификат службы с полным именем домена компьютера, который экспортируется в файл с именем Service.cer.  
  
6.  Внесите в файл Service.exe.config изменения в соответствии с новым именем сертификата \(в атрибуте `findValue` в [\<serviceCertificate\>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-servicecredentials.md)\), которое совпадает с полным именем домена компьютера.Кроме того, измените имя компьютера в элементе \<service\>\/\<baseAddresses\> с localhost на полное доменное имя компьютера службы.  
  
7.  Скопируйте файл Service.cer из каталога службы в клиентский каталог на клиентском компьютере.  
  
8.  На клиентском компьютере запустите `setup.bat client` из командной строки Visual Studio, открытой с правами администратора.При запуске `setup.bat` с аргументом `client` будет создан сертификат клиента с именем test1, после чего сертификат клиента будет экспортирован в файл с именем Client.cer.  
  
9. В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.Для этого замените имя localhost полным доменным именем сервера.  
  
10. Скопируйте файл Client.cer из клиентского каталога в каталог службы на сервере.  
  
11. На клиентском компьютере откройте командную строку Visual Studio с правами администратора и запустите файл ImportServiceCert.bat.Он импортирует сертификат службы из файла Service.cer в хранилище CurrentUser \- TrustedPeople.  
  
12. На сервере откройте командную строку Visual Studio с правами администратора и запустите файл ImportClientCert.bat.При этом импортируется сертификат клиента из файла Client.cer в хранилище «LocalMachine — TrustedPeople».  
  
13. На сервере запустите из окна командной строки программу Service.exe.  
  
14. На клиентском компьютере из окна командной строки запустите программу Client.exe.Если клиенту и службе не удается взаимодействовать, см. раздел [Troubleshooting Tips](http://msdn.microsoft.com/ru-ru/8787c877-5e96-42da-8214-fa737a38f10b).  
  
#### Очистка после образца  
  
1.  После завершения работы образца запустите в папке образцов файл Cleanup.bat.Он удалит из хранилища сертификатов сертификаты сервера и клиента.  
  
> [!NOTE]
>  Этот скрипт не удаляет сертификаты службы на клиенте при запуске образца на нескольких компьютерах.Если образцы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], в которых использовались сертификаты, запускались на нескольких компьютерах, обязательно удалите сертификаты службы, которые были установлены в хранилище «CurrentUser — TrustedPeople».Для этого воспользуйтесь следующей командой: `certmgr -del -r CurrentUser -s TrustedPeople -c -n <Fully Qualified Server Machine Name>`. Пример: `certmgr -del -r CurrentUser -s TrustedPeople -c -n server1.contoso.com`.  
  
## См. также