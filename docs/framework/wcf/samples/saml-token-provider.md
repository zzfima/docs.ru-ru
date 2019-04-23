---
title: Поставщик маркеров SAML
ms.date: 03/30/2017
ms.assetid: eb16e5e2-4c8d-4f61-a479-9c965fcec80c
ms.openlocfilehash: e662d9b84bbc43178946fdadc8ddbec6f6b6e042
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59771105"
---
# <a name="saml-token-provider"></a><span data-ttu-id="b78bd-102">Поставщик маркеров SAML</span><span class="sxs-lookup"><span data-stu-id="b78bd-102">SAML Token Provider</span></span>
<span data-ttu-id="b78bd-103">В этом образце демонстрируется, как реализовать пользовательский поставщик маркеров SAML клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-103">This sample demonstrates how to implement a custom client SAML token provider.</span></span> <span data-ttu-id="b78bd-104">Поставщик маркеров в Windows Communication Foundation (WCF) используется для передачи учетных данных в инфраструктуру безопасности.</span><span class="sxs-lookup"><span data-stu-id="b78bd-104">A token provider in Windows Communication Foundation (WCF) is used for supplying credentials to the security infrastructure.</span></span> <span data-ttu-id="b78bd-105">Поставщик токенов осуществляет общую проверку цели и выдает соответствующие учетные данные, чтобы инфраструктура безопасности смогла обеспечить защиту сообщения.</span><span class="sxs-lookup"><span data-stu-id="b78bd-105">The token provider in general examines the target and issues appropriate credentials so that the security infrastructure can secure the message.</span></span> <span data-ttu-id="b78bd-106">WCF поставляется с поставщиком токенов учетных данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b78bd-106">WCF ships with the default Credential Manager Token Provider.</span></span> <span data-ttu-id="b78bd-107">WCF поставляется с [!INCLUDE[infocard](../../../../includes/infocard-md.md)] поставщик маркеров.</span><span class="sxs-lookup"><span data-stu-id="b78bd-107">WCF also ships with an [!INCLUDE[infocard](../../../../includes/infocard-md.md)] token provider.</span></span> <span data-ttu-id="b78bd-108">Пользовательские поставщики маркеров полезны в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="b78bd-108">Custom token providers are useful in the following cases:</span></span>

-   <span data-ttu-id="b78bd-109">если используется хранилище учетных данных с которым эти поставщики не работают;</span><span class="sxs-lookup"><span data-stu-id="b78bd-109">If you have a credential store that these token providers cannot operate with.</span></span>

-   <span data-ttu-id="b78bd-110">Если вы хотите создать собственный пользовательский механизм для преобразования учетных данных из точки, где пользователь предоставляет сведения, которые должны при инфраструктура клиента WCF использует учетные данные.</span><span class="sxs-lookup"><span data-stu-id="b78bd-110">If you want to provide your own custom mechanism for transforming the credentials from the point when the user provides the details to when the WCF client framework uses the credentials.</span></span>

-   <span data-ttu-id="b78bd-111">если строится пользовательский маркер.</span><span class="sxs-lookup"><span data-stu-id="b78bd-111">If you are building a custom token.</span></span>

 <span data-ttu-id="b78bd-112">В этом примере показано, как построить пользовательский поставщик маркеров, который позволяет токена SAML, полученного от за пределами инфраструктура клиента WCF для использования.</span><span class="sxs-lookup"><span data-stu-id="b78bd-112">This sample shows how to build a custom token provider that allows a SAML token obtained from outside of the WCF client framework to be used.</span></span>

 <span data-ttu-id="b78bd-113">Итак, этот образец демонстрирует следующее:</span><span class="sxs-lookup"><span data-stu-id="b78bd-113">To summarize, this sample demonstrates the following:</span></span>

-   <span data-ttu-id="b78bd-114">как настроить клиент с пользовательским поставщиком маркеров;</span><span class="sxs-lookup"><span data-stu-id="b78bd-114">How a client can be configured with a custom token provider.</span></span>

-   <span data-ttu-id="b78bd-115">как передать маркер SAML в пользовательские учетные данные клиента;</span><span class="sxs-lookup"><span data-stu-id="b78bd-115">How a SAML token can be passed to the custom client credentials.</span></span>

-   <span data-ttu-id="b78bd-116">Как маркер SAML предоставляется инфраструктура клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="b78bd-116">How the SAML token is provided to the WCF client framework.</span></span>

-   <span data-ttu-id="b78bd-117">как сервер проходит проверку подлинности на клиенте с использованием сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="b78bd-117">How the server is authenticated by the client using the server's X.509 certificate.</span></span>

 <span data-ttu-id="b78bd-118">Служба предоставляет две конечные точки для взаимодействия со службой, определенной в файле конфигурации App.config. Каждая конечная точка состоит из адреса, привязки и контракта.</span><span class="sxs-lookup"><span data-stu-id="b78bd-118">The service exposes two endpoints for communicating with the service, defined using the configuration file App.config. Each endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="b78bd-119">Привязка настраивается с помощью стандартного элемента `wsFederationHttpBinding`, который использует безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="b78bd-119">The binding is configured with a standard `wsFederationHttpBinding`, which uses Message security.</span></span> <span data-ttu-id="b78bd-120">Одна конечная точка ожидает проверки подлинности клиента с помощью маркера SAML, использующего симметричный ключ проверки, в то время как другая ожидает проверки подлинности клиента с помощью маркера SAML, использующего асимметричный ключ проверки.</span><span class="sxs-lookup"><span data-stu-id="b78bd-120">One endpoint expects the client to authenticate with a SAML token that uses a symmetric proof key while the other expects the client to authenticate with a SAML token that uses an asymmetric proof key.</span></span> <span data-ttu-id="b78bd-121">Кроме того, служба настраивает сертификат службы с помощью поведения `serviceCredentials`.</span><span class="sxs-lookup"><span data-stu-id="b78bd-121">The service also configures the service certificate using `serviceCredentials` behavior.</span></span> <span data-ttu-id="b78bd-122">Поведение `serviceCredentials` позволяет настроить сертификат службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-122">The `serviceCredentials` behavior allows you to configure a service certificate.</span></span> <span data-ttu-id="b78bd-123">Сертификат службы используется клиентом для проверки подлинности службы и обеспечения защиты сообщения.</span><span class="sxs-lookup"><span data-stu-id="b78bd-123">A service certificate is used by a client to authenticate the service and provide message protection.</span></span> <span data-ttu-id="b78bd-124">В следующей конфигурации делается ссылка на сертификат "localhost", установленный во время установки образца, в соответствии с приведенными в конце раздела инструкциями.</span><span class="sxs-lookup"><span data-stu-id="b78bd-124">The following configuration references the "localhost" certificate installed during the sample setup as described in the setup instructions at the end of this topic.</span></span> <span data-ttu-id="b78bd-125">Поведение `serviceCredentials` также позволяет настроить сертификаты для подписи маркеров SAML.</span><span class="sxs-lookup"><span data-stu-id="b78bd-125">The `serviceCredentials` behavior also allows you to configure certificates that are trusted to sign SAML tokens.</span></span> <span data-ttu-id="b78bd-126">Следующая конфигурация ссылается на сертификат "Alice", установленный при выполнении образца.</span><span class="sxs-lookup"><span data-stu-id="b78bd-126">The following configuration references the 'Alice' certificate installed during the sample.</span></span>

```xml
<system.serviceModel>
 <services>
  <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
   <host>
    <baseAddresses>
     <!-- configure base address provided by host -->
     <add
  baseAddress="http://localhost:8000/servicemodelsamples/service/" />
    </baseAddresses>
   </host>
   <!-- use base address provided by host -->
   <!-- Endpoint that expect SAML tokens with Symmetric proof keys -->
   <endpoint address="calc/symm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding1"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
   <!-- Endpoint that expect SAML tokens with Asymmetric proof keys -->
   <endpoint address="calc/asymm"
             binding="wsFederationHttpBinding"
             bindingConfiguration="Binding2"
             contract="Microsoft.ServiceModel.Samples.ICalculator" />
  </service>
 </services>

 <bindings>
  <wsFederationHttpBinding>
   <!-- Binding that expect SAML tokens with Symmetric proof keys -->
   <binding name="Binding1">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="SymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
   <!-- Binding that expect SAML tokens with Asymmetric proof keys -->
   <binding name="Binding2">
    <security mode="Message">
     <message negotiateServiceCredential ="false"
              issuedKeyType="AsymmetricKey"
              issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1"  />
    </security>
   </binding>
  </wsFederationHttpBinding>
 </bindings>

 <behaviors>
  <serviceBehaviors>
   <behavior name="CalculatorServiceBehavior">
    <!--
    The serviceCredentials behavior allows one to define a service certificate.
    A service certificate is used by a client to authenticate the service and provide message protection.
    This configuration references the "localhost" certificate installed during the setup instructions.
    -->
    <serviceCredentials>
     <!-- Set allowUntrustedRsaIssuers to true to allow self-signed, asymmetric key based SAML tokens -->
     <issuedTokenAuthentication allowUntrustedRsaIssuers ="true" >
      <!-- Add Alice to the list of certs trusted to issue SAML tokens -->
      <knownCertificates>
       <add storeLocation="LocalMachine"
            storeName="TrustedPeople"
            x509FindType="FindBySubjectName"
            findValue="Alice"/>
      </knownCertificates>
     </issuedTokenAuthentication>
     <serviceCertificate storeLocation="LocalMachine"
                         storeName="My"
                         x509FindType="FindBySubjectName"
                         findValue="localhost"  />
    </serviceCredentials>
   </behavior>
  </serviceBehaviors>
 </behaviors>

</system.serviceModel>
```

 <span data-ttu-id="b78bd-127">Ниже показано, как разработать пользовательский поставщик маркеров SAML и интегрировать его с WCF: платформа безопасности:</span><span class="sxs-lookup"><span data-stu-id="b78bd-127">The following steps show how to develop a custom SAML token provider and integrate it with WCF: security framework:</span></span>

1. <span data-ttu-id="b78bd-128">Создание пользовательского поставщика маркеров SAML.</span><span class="sxs-lookup"><span data-stu-id="b78bd-128">Write a custom SAML token provider.</span></span>

     <span data-ttu-id="b78bd-129">В этом образце реализуется пользовательский поставщик маркеров SAML, возвращающий маркер безопасности на основании утверждения SAML, предоставляемого во время создания.</span><span class="sxs-lookup"><span data-stu-id="b78bd-129">The sample implements a custom SAML token provider that returns a security token based on a SAML assertion that is provided at construction time.</span></span>

     <span data-ttu-id="b78bd-130">Для выполнения этой задачи пользовательский поставщик маркеров наследуется от класса <xref:System.IdentityModel.Selectors.SecurityTokenProvider> и переопределяет метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A>.</span><span class="sxs-lookup"><span data-stu-id="b78bd-130">To perform this task, the custom token provider is derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%2A> method.</span></span> <span data-ttu-id="b78bd-131">Этот метод создает и возвращает новый маркер `SecurityToken`.</span><span class="sxs-lookup"><span data-stu-id="b78bd-131">This method creates and returns a new `SecurityToken`.</span></span>

    ```
    protected override SecurityToken GetTokenCore(TimeSpan timeout)
    {
     // Create a SamlSecurityToken from the provided assertion
     SamlSecurityToken samlToken = new SamlSecurityToken(assertion);

     // Create a SecurityTokenSerializer that will be used to
     // serialize the SamlSecurityToken
     WSSecurityTokenSerializer ser = new WSSecurityTokenSerializer();
     // Create a memory stream to write the serialized token into
     // Use an initial size of 64Kb
     MemoryStream s = new MemoryStream(UInt16.MaxValue);

     // Create an XmlWriter over the stream
     XmlWriter xw = XmlWriter.Create(s);

     // Write the SamlSecurityToken into the stream
     ser.WriteToken(xw, samlToken);

     // Seek back to the beginning of the stream
     s.Seek(0, SeekOrigin.Begin);

     // Load the serialized token into a DOM
     XmlDocument dom = new XmlDocument();
     dom.Load(s);

     // Create a KeyIdentifierClause for the SamlSecurityToken
     SamlAssertionKeyIdentifierClause samlKeyIdentifierClause = samlToken.CreateKeyIdentifierClause<SamlAssertionKeyIdentifierClause>();

    // Return a GenericXmlToken from the XML for the
    // SamlSecurityToken, the proof token, the valid from and valid
    // until times from the assertion and the key identifier clause
    // created above
    return new GenericXmlSecurityToken(dom.DocumentElement, proofToken, assertion.Conditions.NotBefore, assertion.Conditions.NotOnOrAfter, samlKeyIdentifierClause, samlKeyIdentifierClause, null);
    }
    ```

2. <span data-ttu-id="b78bd-132">Создание пользовательского диспетчера маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="b78bd-132">Write custom security token manager.</span></span>

     <span data-ttu-id="b78bd-133">Класс <xref:System.IdentityModel.Selectors.SecurityTokenManager> используется для создания объекта <xref:System.IdentityModel.Selectors.SecurityTokenProvider> для конкретного конструктора <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, который передается в него в методе `CreateSecurityTokenProvider`.</span><span class="sxs-lookup"><span data-stu-id="b78bd-133">The <xref:System.IdentityModel.Selectors.SecurityTokenManager> class is used to create <xref:System.IdentityModel.Selectors.SecurityTokenProvider> for specific <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> that is passed to it in `CreateSecurityTokenProvider` method.</span></span> <span data-ttu-id="b78bd-134">Диспетчер маркеров безопасности также используется для создания структур проверки подлинности маркеров и сериализатора маркеров. В этом образце они не представлены.</span><span class="sxs-lookup"><span data-stu-id="b78bd-134">A security token manager is also used to create token authenticators and token serializer, but those are not covered by this sample.</span></span> <span data-ttu-id="b78bd-135">В этом образце пользовательский диспетчер маркеров безопасности наследует от класса <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> и переопределяет метод `CreateSecurityTokenProvider`, возвращающий пользовательский поставщик маркеров SAML, когда переданные требования маркера указывают на запрос маркера SAML.</span><span class="sxs-lookup"><span data-stu-id="b78bd-135">In this sample the custom security token manager inherits from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class and overrides the `CreateSecurityTokenProvider` method to return the custom SAML token provider when the passed token requirements indicate that the SAML token is requested.</span></span> <span data-ttu-id="b78bd-136">Если класс учетных данных клиента (см. шаг 3) не указал утверждение, диспетчер маркеров безопасности создает соответствующий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b78bd-136">If the client credentials class (see step 3) has not specified an assertion, the security token manager creates an appropriate instance.</span></span>

    ```
    public class SamlSecurityTokenManager :
     ClientCredentialsSecurityTokenManager
    {
     SamlClientCredentials samlClientCredentials;

     public SamlSecurityTokenManager ( SamlClientCredentials samlClientCredentials)
      : base(samlClientCredentials)
     {
      // Store the creating client credentials
      this.samlClientCredentials = samlClientCredentials;
     }

     public override SecurityTokenProvider CreateSecurityTokenProvider ( SecurityTokenRequirement tokenRequirement )
     {
      // If token requirement matches SAML token return the
      // custom SAML token provider
      if (tokenRequirement.TokenType == SecurityTokenTypes.Saml ||
          tokenRequirement.TokenType == "http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1")
      {
       // Retrieve the SAML assertion and proof token from the
       // client credentials
       SamlAssertion assertion = this.samlClientCredentials.Assertion;
       SecurityToken prooftoken = this.samlClientCredentials.ProofToken;

       // If either the assertion of proof token is null...
       if (assertion == null || prooftoken == null)
       {
        // ...get the SecurityBindingElement and then the
        // specified algorithm suite
        SecurityBindingElement sbe = null;
        SecurityAlgorithmSuite sas = null;

        if ( tokenRequirement.TryGetProperty<SecurityBindingElement> ( "http://schemas.microsoft.com/ws/2006/05/servicemodel/securitytokenrequirement/SecurityBindingElement", out sbe))
        {
         sas = sbe.DefaultAlgorithmSuite;
        }

        // If the token requirement is for a SymmetricKey based token..
        if (tokenRequirement.KeyType == SecurityKeyType.SymmetricKey)
        {
         // Create a symmetric proof token
         prooftoken = SamlUtilities.CreateSymmetricProofToken ( tokenRequirement.KeySize );
         // and a corresponding assertion based on the claims specified in the client credentials
         assertion = SamlUtilities.CreateSymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, new X509SecurityToken ( samlClientCredentials.ClientCertificate.Certificate ), new X509SecurityToken ( samlClientCredentials.ServiceCertificate.DefaultCertificate ), (BinarySecretSecurityToken)prooftoken, sas);
        }
        // otherwise...
        else
        {
         // Create an asymmetric proof token
         prooftoken = SamlUtilities.CreateAsymmetricProofToken();
         // and a corresponding assertion based on the claims
         // specified in the client credentials
         assertion = SamlUtilities.CreateAsymmetricKeyBasedAssertion ( this.samlClientCredentials.Claims, prooftoken, sas );
        }
       }

       // Create a SamlSecurityTokenProvider based on the assertion and proof token
       return new SamlSecurityTokenProvider(assertion, prooftoken);
      }
      // otherwise use base implementation
      else
      {
       return base.CreateSecurityTokenProvider(tokenRequirement);
      }
    }
    ```

3. <span data-ttu-id="b78bd-137">Создание пользовательских учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-137">Write a custom client credential.</span></span>

     <span data-ttu-id="b78bd-138">Класс учетных данных клиента используется для представления учетных данных, которые сконфигурированы для прокси клиента, и создает диспетчер маркеров безопасности, который используется для получения структур проверки подлинности маркеров, поставщиков маркеров и сериализаторов маркеров.</span><span class="sxs-lookup"><span data-stu-id="b78bd-138">Client credentials class is used to represent the credentials that are configured for the client proxy and creates a security token manager that is used to obtain token authenticators, token providers and token serializer.</span></span>

    ```
    public class SamlClientCredentials : ClientCredentials
    {
     ClaimSet claims;
     SamlAssertion assertion;
     SecurityToken proofToken;

     public SamlClientCredentials() : base()
     {
      // Set SupportInteractive to false to suppress Cardspace UI
      base.SupportInteractive = false;
     }

     protected SamlClientCredentials(SamlClientCredentials other) : base ( other )
     {
      // Just do reference copy given sample nature
      this.assertion = other.assertion;
      this.claims = other.claims;
      this.proofToken = other.proofToken;
     }

     public SamlAssertion Assertion { get { return assertion; } set { assertion = value; } }

     public SecurityToken ProofToken { get { return proofToken; } set { proofToken = value; } }
     public ClaimSet Claims { get { return claims; } set { claims = value; } }

     protected override ClientCredentials CloneCore()
     {
      return new SamlClientCredentials(this);
     }

     public override SecurityTokenManager CreateSecurityTokenManager()
     {
      // return custom security token manager
      return new SamlSecurityTokenManager(this);
     }
    }
    ```

4. <span data-ttu-id="b78bd-139">Настройка клиента для использования пользовательских учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-139">Configure the client to use the custom client credential.</span></span>

     <span data-ttu-id="b78bd-140">В образце удаляется класс учетных данных клиента по умолчанию и предоставляется новый класс учетных данных клиента, чтобы клиент мог использовать пользовательские учетные данные клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-140">The sample deletes the default client credential class and supplies the new client credential class so the client can use the custom client credential.</span></span>

    ```
    // Create new credentials class
    SamlClientCredentials samlCC = new SamlClientCredentials();

    // Set the client certificate. This is the cert that will be used to sign the SAML token in the symmetric proof key case
    samlCC.ClientCertificate.SetCertificate(StoreLocation.CurrentUser, StoreName.My, X509FindType.FindBySubjectName, "Alice");

    // Set the service certificate. This is the cert that will be used to encrypt the proof key in the symmetric proof key case
    samlCC.ServiceCertificate.SetDefaultCertificate(StoreLocation.CurrentUser, StoreName.TrustedPeople, X509FindType.FindBySubjectName, "localhost");

    // Create some claims to put in the SAML assertion
    IList<Claim> claims = new List<Claim>();
    claims.Add(Claim.CreateNameClaim(samlCC.ClientCertificate.Certificate.Subject));
    ClaimSet claimset = new DefaultClaimSet(claims);
    samlCC.Claims = claimset;

    // set new credentials
    client.ChannelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
    client.ChannelFactory.Endpoint.Behaviors.Add(samlCC);
    ```

 <span data-ttu-id="b78bd-141">На стороне службы отображаются утверждения, связанные с вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="b78bd-141">On the service, the claims associated with the caller are displayed.</span></span> <span data-ttu-id="b78bd-142">При выполнении примера запросы и ответы операций отображаются в окне консоли клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-142">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b78bd-143">Чтобы закрыть клиент, нажмите клавишу ВВОД в окне клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-143">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="b78bd-144">Пакетный файл Setup</span><span class="sxs-lookup"><span data-stu-id="b78bd-144">Setup Batch File</span></span>
 <span data-ttu-id="b78bd-145">Входящий в состав образца файл Setup.bat позволяет настроить для сервера соответствующий сертификат, необходимый для выполнения резидентного приложения, для которого требуется обеспечение безопасности на основе сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-145">The Setup.bat batch file included with this sample allows you to configure the server with the relevant certificate to run a self-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="b78bd-146">Этот пакетный файл необходимо изменить, чтобы его можно было использовать на нескольких компьютерах или без размещения приложения.</span><span class="sxs-lookup"><span data-stu-id="b78bd-146">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="b78bd-147">Ниже представлены общие сведения о различных разделах пакетных файлов, позволяющие изменять их для выполнения в соответствующей конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b78bd-147">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

-   <span data-ttu-id="b78bd-148">Создание сертификата сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-148">Creating the server certificate:</span></span>

     <span data-ttu-id="b78bd-149">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-149">The following lines from the Setup.bat batch file create the server certificate to be used.</span></span> <span data-ttu-id="b78bd-150">Переменная `%SERVER_NAME%`задает имя сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-150">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="b78bd-151">Измените эту переменную, чтобы задать собственное имя сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-151">Change this variable to specify your own server name.</span></span> <span data-ttu-id="b78bd-152">По умолчанию в этом пакетном файле используется имя localhost.</span><span class="sxs-lookup"><span data-stu-id="b78bd-152">The default value in this batch file is localhost.</span></span>

     <span data-ttu-id="b78bd-153">Сертификат хранится в хранилище «My store (Личном хранилище)» в расположении LocalMachine.</span><span class="sxs-lookup"><span data-stu-id="b78bd-153">The certificate is stored in My (Personal) store under the LocalMachine store location.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss My -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="b78bd-154">Установка сертификата сервера в хранилище доверенных сертификатов клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-154">Installing the server certificate into the client's trusted certificate store:</span></span>

     <span data-ttu-id="b78bd-155">Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-155">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="b78bd-156">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-156">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="b78bd-157">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов клиента не требуется.</span><span class="sxs-lookup"><span data-stu-id="b78bd-157">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r LocalMachine -s TrustedPeople
    ```

-   <span data-ttu-id="b78bd-158">Создание сертификата издателя.</span><span class="sxs-lookup"><span data-stu-id="b78bd-158">Creating the issuer certificate.</span></span>

     <span data-ttu-id="b78bd-159">Следующие строки из файла Setup.bat создают используемый в дальнейшем сертификат издателя.</span><span class="sxs-lookup"><span data-stu-id="b78bd-159">The following lines from the Setup.bat batch file create the issuer certificate to be used.</span></span> <span data-ttu-id="b78bd-160">Переменная `%USER_NAME%` задает имя издателя.</span><span class="sxs-lookup"><span data-stu-id="b78bd-160">The `%USER_NAME%` variable specifies the issuer name.</span></span> <span data-ttu-id="b78bd-161">Измените эту переменную, чтобы задать собственное имя издателя.</span><span class="sxs-lookup"><span data-stu-id="b78bd-161">Change this variable to specify your own issuer name.</span></span> <span data-ttu-id="b78bd-162">По умолчанию в этом пакетном файле используется имя Alice.</span><span class="sxs-lookup"><span data-stu-id="b78bd-162">The default value in this batch file is Alice.</span></span>

     <span data-ttu-id="b78bd-163">Сертификат хранится в хранилище "My store" в расположении CurrentUser.</span><span class="sxs-lookup"><span data-stu-id="b78bd-163">The certificate is stored in My store under the CurrentUser store location.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr CurrentUser -ss My -a sha1 -n CN=%USER_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="b78bd-164">Установка сертификата издателя в хранилище доверенных сертификатов сервера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-164">Installing the issuer certificate into the server's trusted certificate store.</span></span>

     <span data-ttu-id="b78bd-165">Следующие строки из файла Setup.bat копируют сертификат сервера в хранилище доверенных лиц клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-165">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="b78bd-166">Этот шаг является обязательным, поскольку сертификаты, созданные с помощью программы Makecert.exe, не получают неявного доверия со стороны клиентской системы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-166">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="b78bd-167">Если уже имеется сертификат, имеющий доверенный корневой сертификат клиента, например сертификат, выпущенный корпорацией Майкрософт, выполнять этот шаг по добавлению сертификата сервера в хранилище сертификатов издателя не требуется.</span><span class="sxs-lookup"><span data-stu-id="b78bd-167">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft-issued certificate—this step of populating the server certificate store with the issuer certificate is not required.</span></span>

    ```
    certmgr.exe -add -r CurrentUser -s My -c -n %USER_NAME% -r LocalMachine -s TrustedPeople
    ```

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="b78bd-168">Настройка и сборка образца</span><span class="sxs-lookup"><span data-stu-id="b78bd-168">To set up and build the sample</span></span>

1. <span data-ttu-id="b78bd-169">Убедитесь, что вы выполнили [выполняемая однократно процедура настройки для образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b78bd-169">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="b78bd-170">Чтобы построить решение, следуйте инструкциям в [сборка образцов Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b78bd-170">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

> [!NOTE]
>  <span data-ttu-id="b78bd-171">Если для восстановления конфигурации этого образца используется программа Svcutil.exe, измените имя конечной точки в конфигурации клиента, чтобы оно соответствовало клиентскому коду.</span><span class="sxs-lookup"><span data-stu-id="b78bd-171">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="b78bd-172">Запуск образца на одном компьютере</span><span class="sxs-lookup"><span data-stu-id="b78bd-172">To run the sample on the same computer</span></span>

1. <span data-ttu-id="b78bd-173">Запустите файл Setup.bat из папки установки образца с правами администратора Запустите командную строку Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="b78bd-173">Run Setup.bat from the sample installation folder inside a Visual Studio 2012 command prompt run with administrator privileges.</span></span> <span data-ttu-id="b78bd-174">При этом устанавливаются все сертификаты, необходимые для выполнения образца.</span><span class="sxs-lookup"><span data-stu-id="b78bd-174">This installs all the certificates required for running the sample.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="b78bd-175">Пакетный файл Setup.bat предназначен для запуска из командной строки с 2012 Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b78bd-175">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="b78bd-176">Набор переменных среды в командной строке Visual Studio 2012 путь указывает на каталог, содержащий исполняемые файлы, необходимые для скрипта Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="b78bd-176">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>  
  
2. <span data-ttu-id="b78bd-177">Запустите программу Service.exe из папки service\bin.</span><span class="sxs-lookup"><span data-stu-id="b78bd-177">Launch Service.exe from service\bin.</span></span>  
  
3. <span data-ttu-id="b78bd-178">Запустите программу Client.exe из каталога \client\bin.</span><span class="sxs-lookup"><span data-stu-id="b78bd-178">Launch Client.exe from \client\bin.</span></span> <span data-ttu-id="b78bd-179">Действия клиента отображаются в консольном приложении клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-179">Client activity is displayed on the client console application.</span></span>  
  
4. <span data-ttu-id="b78bd-180">Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок для образцов WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="b78bd-180">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-run-the-sample-across-computers"></a><span data-ttu-id="b78bd-181">Запуск образца на нескольких компьютерах</span><span class="sxs-lookup"><span data-stu-id="b78bd-181">To run the sample across computers</span></span>  
  
1. <span data-ttu-id="b78bd-182">Создайте на компьютере службы каталог для двоичных файлов службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-182">Create a directory on the service computer for the service binaries.</span></span>  
  
2. <span data-ttu-id="b78bd-183">Скопируйте файлы служебной программы в каталог службы на компьютере службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-183">Copy the service program files to the service directory on the service computer.</span></span> <span data-ttu-id="b78bd-184">Кроме того, скопируйте файлы Setup.bat и Cleanup.bat на компьютер службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-184">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3. <span data-ttu-id="b78bd-185">Необходимо иметь сертификат сервера с именем субъекта, содержащим полное имя домена компьютера.</span><span class="sxs-lookup"><span data-stu-id="b78bd-185">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="b78bd-186">Для отображения этого нового имени сертификата необходимо обновить файл Service.exe.config.</span><span class="sxs-lookup"><span data-stu-id="b78bd-186">The Service.exe.config file must be updated to reflect this new certificate name.</span></span> <span data-ttu-id="b78bd-187">Сертификат сервера можно создать путем изменения пакетного файла Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="b78bd-187">You can create server certificate by modifying the Setup.bat batch file.</span></span> <span data-ttu-id="b78bd-188">Обратите внимание на то, что файл setup.bat нужно запускать в командной строке разработчика для окна Visual Studio, открытой с правами администратора.</span><span class="sxs-lookup"><span data-stu-id="b78bd-188">Note that the setup.bat file must be run in a Developer Command Prompt for Visual Studio window opened with administrator privileges.</span></span> <span data-ttu-id="b78bd-189">Необходимо установить переменную `%SERVER_NAME%` равной полному имени узла компьютера, используемого для размещения службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-189">You must set the `%SERVER_NAME%` variable to the fully-qualified host name of the computer that is used to host the service.</span></span>  
  
4. <span data-ttu-id="b78bd-190">Скопируйте сертификат сервера в хранилище CurrentUser-TrustedPeople клиента.</span><span class="sxs-lookup"><span data-stu-id="b78bd-190">Copy the server certificate into the CurrentUser-TrustedPeople store of the client.</span></span> <span data-ttu-id="b78bd-191">Выполнять этот шаг не требуется, когда сертификат сервера выдан издателем, которому доверяет клиент.</span><span class="sxs-lookup"><span data-stu-id="b78bd-191">This step is not necessary when the server certificate is issued by a client trusted issuer.</span></span>  
  
5. <span data-ttu-id="b78bd-192">В файле Service.exe.config компьютера службы измените значение базового адреса для указания полного имени компьютера вместо localhost.</span><span class="sxs-lookup"><span data-stu-id="b78bd-192">In the Service.exe.config file on the service computer, change the value of the base address to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6. <span data-ttu-id="b78bd-193">На компьютере службы запустите из командной строки программу Service.exe.</span><span class="sxs-lookup"><span data-stu-id="b78bd-193">On the service computer, run Service.exe from a command prompt.</span></span>  
  
7. <span data-ttu-id="b78bd-194">Скопируйте на клиентские компьютеры файлы из папки \client\bin\ в папку языка.</span><span class="sxs-lookup"><span data-stu-id="b78bd-194">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
8. <span data-ttu-id="b78bd-195">В файле Client.exe.config на клиентском компьютере измените значение адреса конечной точки, чтобы оно соответствовало новому адресу службы.</span><span class="sxs-lookup"><span data-stu-id="b78bd-195">In the Client.exe.config file on the client computer, change the address value of the endpoint to match the new address of your service.</span></span>  
  
9. <span data-ttu-id="b78bd-196">На клиентском компьютере из командной строки запустите программу `Client.exe`.</span><span class="sxs-lookup"><span data-stu-id="b78bd-196">On the client computer, launch `Client.exe` from a command prompt window.</span></span>  
  
10. <span data-ttu-id="b78bd-197">Если клиент и служба не может взаимодействовать, см. в разделе [советы по устранению неполадок для образцов WCF](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="b78bd-197">If the client and service are not able to communicate, see [Troubleshooting Tips for WCF Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751511(v=vs.90)).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="b78bd-198">Очистка после образца</span><span class="sxs-lookup"><span data-stu-id="b78bd-198">To clean up after the sample</span></span>  
  
1. <span data-ttu-id="b78bd-199">После завершения работы примера запустите в папке примеров файл Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="b78bd-199">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
