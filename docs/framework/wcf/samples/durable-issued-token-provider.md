---
title: Пользовательский поставщик маркеров
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: 08c6837f45ba1c422cdc3df2c884aa81b50a7f2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144751"
---
# <a name="durable-issued-token-provider"></a>Пользовательский поставщик маркеров
Этот пример демонстрирует, как реализовать пользовательский поставщик маркеров, выдаваемых клиенту.  
  
## <a name="discussion"></a>Обсуждение  
 Поставщик токенов в Windows Communication Foundation (WCF) используется для предоставления учетных данных в инфраструктуру безопасности. Поставщик токенов осуществляет общую проверку цели и выдает соответствующие учетные данные, чтобы инфраструктура безопасности смогла обеспечить защиту сообщения. WCF поставляется с поставщиком токенов CardSpace. Пользовательские поставщики маркеров полезны в следующих случаях:  
  
- если используется хранилище учетных данных с которым не работает встроенный поставщик маркеров;  
  
- Если вы хотите предоставить свой собственный пользовательский механизм для преобразования учетных данных с момента, когда пользователь предоставляет подробную информацию, когда клиент WCF использует учетные данные.  
  
- если строится пользовательский маркер.  
  
 Этот пример показывает, как построить пользовательский поставщик маркеров, который кэширует маркеры, выданные службой маркеров безопасности (STS).  
  
 Итак, этот образец демонстрирует следующее:  
  
- как настроить клиент с пользовательским поставщиком маркеров;  
  
- Как выданные токены могут быть кэшированы и предоставлены клиенту WCF.  
  
- как сервер проходит проверку подлинности на клиенте с использованием сертификата X.509.  
  
 Образец содержит консольную программу клиента (Client.exe), консольную программу службы маркеров безопасности (Securitytokenservice.exe) и консольную программу службы (Service.exe). Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ". Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление). Клиент получает маркер безопасности от службы маркеров безопасности (STS) и осуществляет синхронные вызовы службы для заданной математической операции, а служба в ответ отправляет результат. Действия клиента отображаются в окне консоли.  
  
> [!NOTE]
> Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.  
  
 Этот образец предоставляет контракт ICalculator с использованием [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md). В следующем коде показана конфигурация этой привязки на клиенте.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuer address="http://localhost:8000/sts/windows"
                  binding="wsHttpBinding" />
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 В элементе `security` привязки `wsFederationHttpBinding` значение `mode` задает используемый режим безопасности. В этом образце используется безопасность сообщений, и поэтому элемент `message` привязки `wsFederationHttpBinding` указывается внутри элемента `security` привязки `wsFederationHttpBinding`. Элемент `issuer` привязки `wsFederationHttpBinding` в элементе `message` привязки `wsFederationHttpBinding` задает адрес и привязку для службы маркеров безопасности, которая выдает маркер безопасности клиенту, чтобы клиент мог проверить подлинность службы калькулятора.  
  
 В следующем коде показана конфигурация этой привязки на службе.  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="ServiceFed">
      <security mode="Message">
        <message issuedKeyType="SymmetricKey"
                 issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">
          <issuerMetadata address="http://localhost:8000/sts/mex">
            <identity>
              <certificateReference storeLocation="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType="FindBySubjectDistinguishedName"
                                    findValue="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>  
```  
  
 В элементе `security` привязки `wsFederationHttpBinding` значение `mode` задает используемый режим безопасности. В этом образце используется безопасность сообщений, и поэтому элемент `message` привязки `wsFederationHttpBinding` указывается внутри элемента `security` привязки `wsFederationHttpBinding`. Элемент `issuerMetadata` привязки `wsFederationHttpBinding` в элементе `message` привязки `wsFederationHttpBinding` задает адрес и удостоверение для конечной точки, которая может использоваться с целью извлечения метаданных для службы маркеров безопасности.  
  
 Поведение для службы показано в следующем коде.  
  
```xml  
<behavior name="ServiceBehavior">
  <serviceDebug includeExceptionDetailInFaults="true" />
  <serviceMetadata httpGetEnabled="true" />
  <serviceCredentials>
    <issuedTokenAuthentication>
      <knownCertificates>
        <add storeLocation="LocalMachine"
              storeName="TrustedPeople"
              x509FindType="FindBySubjectDistinguishedName"
              findValue="CN=STS" />
      </knownCertificates>
    </issuedTokenAuthentication>
    <serviceCertificate storeLocation="LocalMachine"
                        storeName="My"
                        x509FindType="FindBySubjectDistinguishedName"
                        findValue="CN=localhost" />
  </serviceCredentials>
</behavior>  
```  
  
 Элемент `issuedTokenAuthentication` в элементе `serviceCredentials` позволяет службе задавать ограничения на маркерах, которые разрешено предоставлять клиентам при проверке подлинности. Эта конфигурация указывает, что службой принимаются маркеры, подписанные сертификатом с именем субъекта "CN=STS".  
  
 Служба маркеров безопасности предоставляет единственную конечную точку, используя стандартную привязку wsHttpBinding. Служба маркеров безопасности отвечает на запросы выдачи маркеров от клиентов и осуществляет проверку подлинности клиента с использованием учетной записи Windows, выдавая маркер, содержащий имя пользователя клиента в качестве утверждения в выданном маркере. В одной из частей процедуры создания маркера служба маркеров безопасности подписывает маркер с использованием закрытого ключа, связанного с сертификатом CN=STS. Дополнительно она создает симметричный ключ и шифрует его с использованием открытого ключа, связанного с сертификатом CN=localhost. При возврате маркера клиенту служба маркеров безопасности также возвращает симметричный ключ. Клиент представляет выданный маркер службе "Калькулятор" и подтверждает свое знание симметричного ключа, подписывая сообщение этим ключом.  
  
## <a name="custom-client-credentials-and-token-provider"></a>Пользовательские учетные данные клиента и поставщик маркера  
 Следующие шаги показывают, как создать пользовательского поставщика токенов, который кэширует, выдал токены и интегрирует его с WCF: безопасность.  
  
### <a name="to-develop-a-custom-token-provider"></a>Разработка пользовательского поставщика маркеров  
  
1. Создание пользовательского поставщика маркеров.  
  
     В этом примере реализован пользовательский поставщик маркеров, который возвращает маркер безопасности, извлекаемый из кэша.  
  
     Для выполнения этой задачи пользовательский поставщик маркеров наследует класс <xref:System.IdentityModel.Selectors.SecurityTokenProvider> и переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>. Этот метод пытается получить маркер из кэша. Если маркер не может быть найден в кэше, метод получает маркер от базового поставщика и кэширует этот маркер. В обоих случаях метод возвращает `SecurityToken`.  
  
    ```csharp  
    protected override SecurityToken GetTokenCore(TimeSpan timeout)  
    {  
      GenericXmlSecurityToken token;  
      if (!this.cache.TryGetToken(target, issuer, out token))  
      {  
        token = (GenericXmlSecurityToken) this.innerTokenProvider.GetToken(timeout);  
        this.cache.AddToken(token, target, issuer);  
      }  
      return token;  
    }  
    ```  
  
2. Создание пользовательского диспетчера маркеров безопасности.  
  
     Класс <xref:System.IdentityModel.Selectors.SecurityTokenManager> используется для создания объекта <xref:System.IdentityModel.Selectors.SecurityTokenProvider> для конкретного конструктора <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, который передается в него в методе `CreateSecurityTokenProvider`. Диспетчер маркеров безопасности также используется для создания структур проверки подлинности маркеров и сериализаторов маркеров, но в этом образце они не представлены. В данном образце пользовательский диспетчер маркеров безопасности наследуется от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> и переопределяет метод `CreateSecurityTokenProvider`, возвращающий пользовательский поставщик маркеров, когда переданные требования маркера указывают на запрос выданного маркера.  
  
    ```csharp
    class DurableIssuedTokenClientCredentialsTokenManager :  
     ClientCredentialsSecurityTokenManager  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentialsTokenManager ( DurableIssuedTokenClientCredentials creds ): base(creds)  
      {  
        this.cache = creds.IssuedTokenCache;  
      }  
  
      public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )  
      {  
        if (IsIssuedSecurityTokenRequirement(tokenRequirement))  
        {  
          return new DurableIssuedSecurityTokenProvider ((IssuedSecurityTokenProvider)base.CreateSecurityTokenProvider( tokenRequirement), this.cache);  
        }  
        else
        {  
          return base.CreateSecurityTokenProvider(tokenRequirement);  
        }  
      }  
    }  
    ```  
  
3. Создание пользовательских учетных данных клиента.  
  
     Класс учетных данных клиента используется для представления учетных данных, которые сконфигурированы для прокси клиента, и создает диспетчер маркеров безопасности, который используется для получения структур проверки подлинности маркеров, поставщиков маркеров и сериализаторов маркеров.  
  
    ```csharp
    public class DurableIssuedTokenClientCredentials : ClientCredentials  
    {  
      IssuedTokenCache cache;  
  
      public DurableIssuedTokenClientCredentials() : base()  
      {  
      }  
  
      DurableIssuedTokenClientCredentials ( DurableIssuedTokenClientCredentials other) : base(other)  
      {  
        this.cache = other.cache;  
      }  
  
      public IssuedTokenCache IssuedTokenCache  
      {  
        get  
        {  
          return this.cache;  
        }  
        set  
        {  
          this.cache = value;  
        }  
      }  
  
      protected override ClientCredentials CloneCore()  
      {  
        return new DurableIssuedTokenClientCredentials(this);  
      }  
  
      public override SecurityTokenManager CreateSecurityTokenManager()  
      {  
        return new DurableIssuedTokenClientCredentialsTokenManager ((DurableIssuedTokenClientCredentials)this.Clone());  
      }  
    }  
    ```  
  
4. Реализация кэша маркера. Образец реализации использует абстрактный базовый класс, через который потребители данного кэша маркера взаимодействуют с кэшем.  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     Чтобы клиент мог использовать пользовательские учетные данные клиента, образец удаляет класс учетных данных клиента по умолчанию и предоставляет новый класс учетных данных клиента.  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a>Выполнение примера  
 См. приведенные ниже инструкции для запуска этого образца. При выполнении образца запрос маркера безопасности показан в окне консоли службы маркеров безопасности. Запросы и ответы операций отображаются в окнах консоли клиента и службы. Чтобы закрыть приложение, нажмите клавишу ВВОД в любом из окон консоли.  
  
## <a name="the-setupcmd-batch-file"></a>Пакетный файл Setup.cmd  
 Входящий в состав примера пакетный файл Setup.cmd позволяет настроить сервер и службу маркеров безопасности с соответствующими сертификатами, необходимыми для выполнения резидентного приложения. Пакетный файл создает два сертификата, оба в хранилище сертификатов CurrentUser/TrustedPeople. Имя субъекта первого сертификата CN=STS, он используется службой маркеров безопасности, чтобы подписывать маркеры безопасности, выдаваемые клиенту. Имя субъекта второго сертификата CN=localhost, он используется службой маркеров безопасности для шифрования секрета, чтобы служба могла его дешифровать.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Настройка, сборка и выполнение образца  
  
1. Запустите файл Setup.cmd, чтобы создать требуемые сертификаты.  
  
2. Чтобы создать решение, следуйте инструкциям по [созданию образцов Фонда связи Windows.](../../../../docs/framework/wcf/samples/building-the-samples.md) Убедитесь, что все проекты в решении построены (Shared, RSTRSTR, Service, SecurityTokenService и Client).  
  
3. Убедитесь в том, что Service.exe и SecurityTokenService.exe запущены с правами администратора.  
  
4. Запустите Client.exe.  
  
### <a name="to-clean-up-after-the-sample"></a>Очистка после образца  
  
1. После завершения работы примера запустите в папке примеров файл Cleanup.cmd.  
  
> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы. Этот образец расположен в следующем каталоге.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
