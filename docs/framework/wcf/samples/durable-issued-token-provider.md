---
title: Пользовательский поставщик маркеров
ms.date: 03/30/2017
ms.assetid: 76fb27f5-8787-4b6a-bf4c-99b4be1d2e8b
ms.openlocfilehash: 62e4cca50e9a2fbbf319d66fbe85cec6cdb73b23
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716456"
---
# <a name="durable-issued-token-provider"></a><span data-ttu-id="04a8c-102">Пользовательский поставщик маркеров</span><span class="sxs-lookup"><span data-stu-id="04a8c-102">Durable Issued Token Provider</span></span>
<span data-ttu-id="04a8c-103">Этот пример демонстрирует, как реализовать пользовательский поставщик маркеров, выдаваемых клиенту.</span><span class="sxs-lookup"><span data-stu-id="04a8c-103">This sample demonstrates how to implement a custom client issued token provider.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="04a8c-104">Обсуждение</span><span class="sxs-lookup"><span data-stu-id="04a8c-104">Discussion</span></span>  
 <span data-ttu-id="04a8c-105">Поставщик маркеров в Windows Communication Foundation (WCF) используется для предоставления учетных данных инфраструктуре безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-105">A token provider in Windows Communication Foundation (WCF) is used to supply credentials to the security infrastructure.</span></span> <span data-ttu-id="04a8c-106">Поставщик токенов осуществляет общую проверку цели и выдает соответствующие учетные данные, чтобы инфраструктура безопасности смогла обеспечить защиту сообщения.</span><span class="sxs-lookup"><span data-stu-id="04a8c-106">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="04a8c-107">WCF поставляется с поставщиком токена CardSpace.</span><span class="sxs-lookup"><span data-stu-id="04a8c-107">WCF ships with a CardSpace token provider.</span></span> <span data-ttu-id="04a8c-108">Пользовательские поставщики маркеров полезны в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="04a8c-108">Custom token providers are useful in the following cases:</span></span>  
  
- <span data-ttu-id="04a8c-109">если используется хранилище учетных данных с которым не работает встроенный поставщик маркеров;</span><span class="sxs-lookup"><span data-stu-id="04a8c-109">If you have a credential store that the built-in token provider cannot operate with.</span></span>  
  
- <span data-ttu-id="04a8c-110">Если вы хотите предоставить собственный настраиваемый механизм для преобразования учетных данных с момента предоставления пользователю сведений о том, когда клиент WCF использует учетные данные.</span><span class="sxs-lookup"><span data-stu-id="04a8c-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client uses the credentials.</span></span>  
  
- <span data-ttu-id="04a8c-111">если строится пользовательский маркер.</span><span class="sxs-lookup"><span data-stu-id="04a8c-111">If you are building a custom token.</span></span>  
  
 <span data-ttu-id="04a8c-112">Этот пример показывает, как построить пользовательский поставщик маркеров, который кэширует маркеры, выданные службой маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="04a8c-112">This sample shows how to build a custom token provider that caches tokens issued by a Security Token Service (STS).</span></span>  
  
 <span data-ttu-id="04a8c-113">Итак, этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="04a8c-113">To summarize, this sample demonstrates the following:</span></span>  
  
- <span data-ttu-id="04a8c-114">как настроить клиент с пользовательским поставщиком маркеров;</span><span class="sxs-lookup"><span data-stu-id="04a8c-114">How a client can be configured with a custom token provider.</span></span>  
  
- <span data-ttu-id="04a8c-115">Как выданные маркеры могут быть кэшированы и предоставлены клиенту WCF.</span><span class="sxs-lookup"><span data-stu-id="04a8c-115">How issued tokens can be cached and provided to the WCF client.</span></span>  
  
- <span data-ttu-id="04a8c-116">как сервер проходит проверку подлинности на клиенте с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="04a8c-116">How the server is authenticated by the client using the server's X.509 certificate.</span></span>  
  
 <span data-ttu-id="04a8c-117">Образец содержит консольную программу клиента (Client.exe), консольную программу службы маркеров безопасности (Securitytokenservice.exe) и консольную программу службы (Service.exe).</span><span class="sxs-lookup"><span data-stu-id="04a8c-117">This sample consists of a client console program (Client.exe), a security token service console program (Securitytokenservice.exe) and a service console program (Service.exe).</span></span> <span data-ttu-id="04a8c-118">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="04a8c-118">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="04a8c-119">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (сложение, вычитание, умножение и деление).</span><span class="sxs-lookup"><span data-stu-id="04a8c-119">The contract is defined by the `ICalculator` interface, which exposes math operations (add, subtract, multiply, and divide).</span></span> <span data-ttu-id="04a8c-120">Клиент получает маркер безопасности от службы маркеров безопасности (STS) и осуществляет синхронные вызовы службы для заданной математической операции, а служба в ответ отправляет результат.</span><span class="sxs-lookup"><span data-stu-id="04a8c-120">The client gets a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation and the service replies with the result.</span></span> <span data-ttu-id="04a8c-121">Действия клиента отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="04a8c-121">Client activity is visible in the console window.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04a8c-122">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="04a8c-122">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="04a8c-123">Этот образец предоставляет контракт ICalculator с помощью [\<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="04a8c-123">This sample exposes the ICalculator contract using the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span> <span data-ttu-id="04a8c-124">В следующем коде показана конфигурация этой привязки на клиенте.</span><span class="sxs-lookup"><span data-stu-id="04a8c-124">The configuration of this binding on the client is shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="04a8c-125">В элементе `security` привязки `wsFederationHttpBinding` значение `mode` задает используемый режим безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-125">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="04a8c-126">В этом образце используется безопасность сообщений, и поэтому элемент `message` привязки `wsFederationHttpBinding` указывается внутри элемента `security` привязки `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="04a8c-126">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="04a8c-127">Элемент `issuer` привязки `wsFederationHttpBinding` в элементе `message` привязки `wsFederationHttpBinding` задает адрес и привязку для службы маркеров безопасности, которая выдает маркер безопасности клиенту, чтобы клиент мог проверить подлинность службы калькулятора.</span><span class="sxs-lookup"><span data-stu-id="04a8c-127">The `issuer` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and binding for the Security Token Service that issues a security token to the client so that the client can authenticate to the Calculator service.</span></span>  
  
 <span data-ttu-id="04a8c-128">В следующем коде показана конфигурация этой привязки на службе.</span><span class="sxs-lookup"><span data-stu-id="04a8c-128">The configuration of this binding on the service is shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="04a8c-129">В элементе `security` привязки `wsFederationHttpBinding` значение `mode` задает используемый режим безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-129">On the `security` element of `wsFederationHttpBinding`, the `mode` value configures which security mode should be used.</span></span> <span data-ttu-id="04a8c-130">В этом образце используется безопасность сообщений, и поэтому элемент `message` привязки `wsFederationHttpBinding` указывается внутри элемента `security` привязки `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="04a8c-130">In this sample, messages security is being used, which is why the `message` element of `wsFederationHttpBinding` is specified inside the `security` element of `wsFederationHttpBinding`.</span></span> <span data-ttu-id="04a8c-131">Элемент `issuerMetadata` привязки `wsFederationHttpBinding` в элементе `message` привязки `wsFederationHttpBinding` задает адрес и удостоверение для конечной точки, которая может использоваться с целью извлечения метаданных для службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-131">The `issuerMetadata` element of `wsFederationHttpBinding` inside the `message` element of `wsFederationHttpBinding` specifies the address and identity for an endpoint that can be used to retrieve metadata for the Security Token Service.</span></span>  
  
 <span data-ttu-id="04a8c-132">Поведение для службы показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="04a8c-132">The behavior for the service is shown in the following code.</span></span>  
  
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
  
 <span data-ttu-id="04a8c-133">Элемент `issuedTokenAuthentication` в элементе `serviceCredentials` позволяет службе задавать ограничения на маркерах, которые разрешено предоставлять клиентам при проверке подлинности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-133">The `issuedTokenAuthentication` element inside the `serviceCredentials` element allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="04a8c-134">Эта конфигурация указывает, что службой принимаются маркеры, подписанные сертификатом с именем субъекта "CN=STS".</span><span class="sxs-lookup"><span data-stu-id="04a8c-134">This configuration specifies that tokens signed by a certificate whose Subject Name is CN=STS are accepted by the service.</span></span>  
  
 <span data-ttu-id="04a8c-135">Служба маркеров безопасности предоставляет единственную конечную точку, используя стандартную привязку wsHttpBinding.</span><span class="sxs-lookup"><span data-stu-id="04a8c-135">The Security Token Service exposes a single endpoint using the standard wsHttpBinding.</span></span> <span data-ttu-id="04a8c-136">Служба маркеров безопасности отвечает на запросы выдачи маркеров от клиентов и осуществляет проверку подлинности клиента с использованием учетной записи Windows, выдавая маркер, содержащий имя пользователя клиента в качестве утверждения в выданном маркере.</span><span class="sxs-lookup"><span data-stu-id="04a8c-136">The Security Token Service responds to request from clients for tokens and, provided the client authenticates using a Windows account, issues a token that contains the client's user name as a claim in the issued token.</span></span> <span data-ttu-id="04a8c-137">В одной из частей процедуры создания маркера служба маркеров безопасности подписывает маркер с использованием закрытого ключа, связанного с сертификатом CN=STS.</span><span class="sxs-lookup"><span data-stu-id="04a8c-137">As part of creating the token, the Security Token Service signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="04a8c-138">Дополнительно она создает симметричный ключ и шифрует его с использованием открытого ключа, связанного с сертификатом CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="04a8c-138">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="04a8c-139">При возврате маркера клиенту служба маркеров безопасности также возвращает симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="04a8c-139">In returning the token to the client, the Security Token Service also returns the symmetric key.</span></span> <span data-ttu-id="04a8c-140">Клиент представляет выданный маркер службе "Калькулятор" и подтверждает свое знание симметричного ключа, подписывая сообщение этим ключом.</span><span class="sxs-lookup"><span data-stu-id="04a8c-140">The client presents the issued token to the Calculator service, and proves that it knows the symmetric key by signing the message with that key.</span></span>  
  
## <a name="custom-client-credentials-and-token-provider"></a><span data-ttu-id="04a8c-141">Пользовательские учетные данные клиента и поставщик маркера</span><span class="sxs-lookup"><span data-stu-id="04a8c-141">Custom Client Credentials and Token Provider</span></span>  
 <span data-ttu-id="04a8c-142">Ниже показано, как разработать пользовательский поставщик маркеров, который кэширует выданные маркеры и интегрирует их с WCF: Security.</span><span class="sxs-lookup"><span data-stu-id="04a8c-142">The following steps show how to develop a custom token provider that caches issued tokens and integrate it with WCF: security.</span></span>  
  
### <a name="to-develop-a-custom-token-provider"></a><span data-ttu-id="04a8c-143">Разработка пользовательского поставщика маркеров</span><span class="sxs-lookup"><span data-stu-id="04a8c-143">To develop a custom token provider</span></span>  
  
1. <span data-ttu-id="04a8c-144">Создание пользовательского поставщика маркеров.</span><span class="sxs-lookup"><span data-stu-id="04a8c-144">Write a custom token provider.</span></span>  
  
     <span data-ttu-id="04a8c-145">В этом примере реализован пользовательский поставщик маркеров, который возвращает маркер безопасности, извлекаемый из кэша.</span><span class="sxs-lookup"><span data-stu-id="04a8c-145">The sample implements a custom token provider that returns a security token retrieved from a cache.</span></span>  
  
     <span data-ttu-id="04a8c-146">Для выполнения этой задачи пользовательский поставщик маркеров наследует класс <xref:System.IdentityModel.Selectors.SecurityTokenProvider> и переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="04a8c-146">To perform this task, the custom token provider derives the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="04a8c-147">Этот метод пытается получить маркер из кэша. Если маркер не может быть найден в кэше, метод получает маркер от базового поставщика и кэширует этот маркер.</span><span class="sxs-lookup"><span data-stu-id="04a8c-147">This method tries to get a token from the cache, or if a token cannot be found in the cache, retrieves a token from the underlying provider and then caches that token.</span></span> <span data-ttu-id="04a8c-148">В обоих случаях метод возвращает `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="04a8c-148">In both cases the method returns a `SecurityToken`.</span></span>  
  
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
  
2. <span data-ttu-id="04a8c-149">Создание пользовательского диспетчера маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-149">Write custom security token manager.</span></span>  
  
     <span data-ttu-id="04a8c-150">Класс <xref:System.IdentityModel.Selectors.SecurityTokenManager> используется для создания объекта <xref:System.IdentityModel.Selectors.SecurityTokenProvider> для конкретного конструктора <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, который передается в него в методе `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="04a8c-150">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> is used to create a <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for a specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in the `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="04a8c-151">Диспетчер маркеров безопасности также используется для создания структур проверки подлинности маркеров и сериализаторов маркеров, но в этом образце они не представлены.</span><span class="sxs-lookup"><span data-stu-id="04a8c-151">Security token manager is also used to create token authenticators and token serializers, but those are not covered by this sample.</span></span> <span data-ttu-id="04a8c-152">В данном образце пользовательский диспетчер маркеров безопасности наследуется от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> и переопределяет метод `CreateSecurityTokenProvider`, возвращающий пользовательский поставщик маркеров, когда переданные требования маркера указывают на запрос выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="04a8c-152">In this sample, the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom token provider when the passed token requirements indicate that an issued token is requested.</span></span>  
  
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
  
3. <span data-ttu-id="04a8c-153">Создание пользовательских учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="04a8c-153">Write a custom client credential.</span></span>  
  
     <span data-ttu-id="04a8c-154">Класс учетных данных клиента используется для представления учетных данных, которые сконфигурированы для прокси клиента, и создает диспетчер маркеров безопасности, который используется для получения структур проверки подлинности маркеров, поставщиков маркеров и сериализаторов маркеров.</span><span class="sxs-lookup"><span data-stu-id="04a8c-154">A client credentials class is used to represent the credentials that are configured for the client proxy and creates the security token manager that is used to obtain token authenticators, token providers and token serializers.</span></span>  
  
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
  
4. <span data-ttu-id="04a8c-155">Реализация кэша маркера.</span><span class="sxs-lookup"><span data-stu-id="04a8c-155">Implement the token cache.</span></span> <span data-ttu-id="04a8c-156">Образец реализации использует абстрактный базовый класс, через который потребители данного кэша маркера взаимодействуют с кэшем.</span><span class="sxs-lookup"><span data-stu-id="04a8c-156">The sample implementation uses an abstract base class through which consumers of a given token cache interact with the cache.</span></span>  
  
    ```csharp
    public abstract class IssuedTokenCache  
    {  
      public abstract void AddToken ( GenericXmlSecurityToken token, EndpointAddress target, EndpointAddress issuer);  
      public abstract bool TryGetToken(EndpointAddress target, EndpointAddress issuer, out GenericXmlSecurityToken cachedToken);  
    }  
    // Configure the client to use the custom client credential.  
    ```  
  
     <span data-ttu-id="04a8c-157">Чтобы клиент мог использовать пользовательские учетные данные клиента, образец удаляет класс учетных данных клиента по умолчанию и предоставляет новый класс учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="04a8c-157">For the client to use the custom client credential, the sample deletes the default client credential class and supplies the new client credential class.</span></span>  
  
    ```csharp
    clientFactory.Endpoint.Behaviors.Remove<ClientCredentials>();  
    DurableIssuedTokenClientCredentials durableCreds = new DurableIssuedTokenClientCredentials();  
    durableCreds.IssuedTokenCache = cache;  
    durableCreds.ServiceCertificate.Authentication.CertificateValidationMode = X509CertificateValidationMode.PeerOrChainTrust;  
    clientFactory.Endpoint.Behaviors.Add(durableCreds);  
    ```  
  
## <a name="running-the-sample"></a><span data-ttu-id="04a8c-158">Запуск образца</span><span class="sxs-lookup"><span data-stu-id="04a8c-158">Running the sample</span></span>  
 <span data-ttu-id="04a8c-159">См. приведенные ниже инструкции для запуска этого образца.</span><span class="sxs-lookup"><span data-stu-id="04a8c-159">See the following instructions to run the sample.</span></span> <span data-ttu-id="04a8c-160">При выполнении образца запрос маркера безопасности показан в окне консоли службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="04a8c-160">When you run the sample, the request for the security token is shown in the Security Token Service console window.</span></span> <span data-ttu-id="04a8c-161">Запросы и ответы операций отображаются в окнах консоли клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="04a8c-161">The operation requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="04a8c-162">Чтобы закрыть приложение, нажмите клавишу ВВОД в любом из окон консоли.</span><span class="sxs-lookup"><span data-stu-id="04a8c-162">Press ENTER in any of the console windows to shut down the application.</span></span>  
  
## <a name="the-setupcmd-batch-file"></a><span data-ttu-id="04a8c-163">Пакетный файл Setup.cmd</span><span class="sxs-lookup"><span data-stu-id="04a8c-163">The Setup.cmd Batch File</span></span>  
 <span data-ttu-id="04a8c-164">Входящий в состав примера пакетный файл Setup.cmd позволяет настроить сервер и службу маркеров безопасности с соответствующими сертификатами, необходимыми для выполнения резидентного приложения.</span><span class="sxs-lookup"><span data-stu-id="04a8c-164">The Setup.cmd batch file included with this sample allows you to configure the server and security token service with relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="04a8c-165">Пакетный файл создает два сертификата, оба в хранилище сертификатов CurrentUser/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="04a8c-165">The batch file creates two certificates both in the CurrentUser/TrustedPeople certificate store.</span></span> <span data-ttu-id="04a8c-166">Имя субъекта первого сертификата CN=STS, он используется службой маркеров безопасности, чтобы подписывать маркеры безопасности, выдаваемые клиенту.</span><span class="sxs-lookup"><span data-stu-id="04a8c-166">The first certificate has a subject name of CN=STS and is used by the Security Token Service to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="04a8c-167">Имя субъекта второго сертификата CN=localhost, он используется службой маркеров безопасности для шифрования секрета, чтобы служба могла его дешифровать.</span><span class="sxs-lookup"><span data-stu-id="04a8c-167">The second certificate has a subject name of CN=localhost and is used by the Security Token Service to encrypt a secret so that the service can decrypt it.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="04a8c-168">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="04a8c-168">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="04a8c-169">Запустите файл Setup.cmd, чтобы создать требуемые сертификаты.</span><span class="sxs-lookup"><span data-stu-id="04a8c-169">Run the Setup.cmd file to create the required certificates.</span></span>  
  
2. <span data-ttu-id="04a8c-170">Чтобы выполнить сборку решения, следуйте инструкциям в разделе [Создание примеров Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="04a8c-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="04a8c-171">Убедитесь, что все проекты в решении построены (Shared, RSTRSTR, Service, SecurityTokenService и Client).</span><span class="sxs-lookup"><span data-stu-id="04a8c-171">Ensure that all the projects in the solution are built (Shared, RSTRSTR, Service, SecurityTokenService, and Client).</span></span>  
  
3. <span data-ttu-id="04a8c-172">Убедитесь в том, что Service.exe и SecurityTokenService.exe запущены с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="04a8c-172">Ensure that Service.exe and SecurityTokenService.exe are both running with administrator privileges.</span></span>  
  
4. <span data-ttu-id="04a8c-173">Запустите Client.exe.</span><span class="sxs-lookup"><span data-stu-id="04a8c-173">Run Client.exe.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="04a8c-174">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="04a8c-174">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="04a8c-175">После завершения работы примера запустите в папке примеров файл Cleanup.cmd.</span><span class="sxs-lookup"><span data-stu-id="04a8c-175">Run Cleanup.cmd in the samples folder once you have finished running the sample.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="04a8c-176">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="04a8c-176">The samples may already be installed on your machine.</span></span> <span data-ttu-id="04a8c-177">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="04a8c-177">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="04a8c-178">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="04a8c-178">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="04a8c-179">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="04a8c-179">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Security\DurableIssuedTokenProvider`  
