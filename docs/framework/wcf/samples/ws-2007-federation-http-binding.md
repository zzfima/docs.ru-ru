---
title: Привязка HTTP для федерации WS 2007
ms.date: 03/30/2017
ms.assetid: 91c1b477-a96e-4bf5-9330-5e9312113371
ms.openlocfilehash: bf61e64733859d96adf42fbacf08266eca1f5b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183184"
---
# <a name="ws-2007-federation-http-binding"></a><span data-ttu-id="3826e-102">Привязка HTTP для федерации WS 2007</span><span class="sxs-lookup"><span data-stu-id="3826e-102">WS 2007 Federation HTTP Binding</span></span>

<span data-ttu-id="3826e-103">В этом примере показано, как использовать <xref:System.ServiceModel.WS2007FederationHttpBinding> — стандартную привязку для создания федеративных сценариев, поддерживающих версию 1.3 спецификации WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="3826e-103">This sample demonstrates the use of <xref:System.ServiceModel.WS2007FederationHttpBinding>, a standard binding that you can use to build federated scenarios that support version 1.3 of the WS-Trust specification.</span></span>

> [!NOTE]
> <span data-ttu-id="3826e-104">Процедура настройки и инструкции по построению для данного образца приведены в конце этого раздела.</span><span class="sxs-lookup"><span data-stu-id="3826e-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="3826e-105">Образец состоит из клиентской программы на базе консолей *(Client.exe),* программы обслуживания токенов безопасности на основе консоли *(Securitytokenservice.exe)* и программы обслуживания на основе консолей *(Service.exe*).</span><span class="sxs-lookup"><span data-stu-id="3826e-105">The sample consists of a console-based client program (*Client.exe*), a console-based security token service program (*Securitytokenservice.exe*), and a console-based service program (*Service.exe*).</span></span> <span data-ttu-id="3826e-106">Служба реализует контракт, определяющий шаблон взаимодействия "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="3826e-106">The service implements a contract that defines a request/reply communication pattern.</span></span> <span data-ttu-id="3826e-107">Контракт определяется интерфейсом `ICalculator`, который предоставляет математические операции (`Add`, `Subtract`, `Multiply` и `Divide`).</span><span class="sxs-lookup"><span data-stu-id="3826e-107">The contract is defined by the `ICalculator` interface, which exposes math operations (`Add`, `Subtract`, `Multiply`, and `Divide`).</span></span> <span data-ttu-id="3826e-108">Клиент получает маркер безопасности от службы маркеров безопасности (STS) и осуществляет синхронные вызовы службы для заданной математической операции.</span><span class="sxs-lookup"><span data-stu-id="3826e-108">The client obtains a security token from the Security Token Service (STS) and makes synchronous requests to the service for a given math operation.</span></span> <span data-ttu-id="3826e-109">Служба отправляет в ответ результат.</span><span class="sxs-lookup"><span data-stu-id="3826e-109">The service then replies with the result.</span></span> <span data-ttu-id="3826e-110">Действия клиента отображаются в окне консоли.</span><span class="sxs-lookup"><span data-stu-id="3826e-110">Client activity is visible in the console window.</span></span>

<span data-ttu-id="3826e-111">В этом образце контракт `ICalculator` делается доступным с помощью элемента `ws2007FederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="3826e-111">The sample makes the `ICalculator` contract available using the `ws2007FederationHttpBinding` element.</span></span> <span data-ttu-id="3826e-112">Конфигурация этой привязки к клиенту отображается в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3826e-112">The configuration of this binding on the client is shown in the following code:</span></span>

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Endpoint address and binding for Security Token Service -->
          <issuer address ="http://localhost:8000/sts/windows"
                  binding ="ws2007HttpBinding" />
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

<span data-ttu-id="3826e-113">На [ \<>безопасности ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` значение определяет, какой режим безопасности следует использовать.</span><span class="sxs-lookup"><span data-stu-id="3826e-113">On the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="3826e-114">В этом `message` примере используется безопасность, поэтому [ \<>сообщения](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) указана внутри [ \<>безопасности. ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3826e-114">In this sample, `message` security is used, which is why the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="3826e-115">Эмитент [ \<>](../../configure-apps/file-schema/wcf/issuer.md) элемент внутри [ \<сообщения>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) определяет адрес и привязку для STS, который выдает маркер безопасности клиенту, чтобы клиент мог проверить подлинность службы. `ICalculator`</span><span class="sxs-lookup"><span data-stu-id="3826e-115">The [\<issuer>](../../configure-apps/file-schema/wcf/issuer.md) element inside the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and binding for the STS that issues a security token to the client so that the client can authenticate to the `ICalculator` service.</span></span>
  
<span data-ttu-id="3826e-116">Конфигурация этой привязки к службе отображается в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3826e-116">The configuration of this binding on the service is shown in the following code:</span></span>

```xml
<bindings>
  <ws2007FederationHttpBinding>
    <binding name="ServiceFed" >
      <security mode ="Message">
        <message issuedKeyType ="SymmetricKey"
                 issuedTokenType ="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1" >
          <!-- Metadata address for Security Token Service -->
          <issuerMetadata address ="http://localhost:8000/sts/mex" >
            <identity>
              <certificateReference storeLocation ="CurrentUser"
                                    storeName="TrustedPeople"
                                    x509FindType ="FindBySubjectDistinguishedName"
                                    findValue ="CN=STS" />
            </identity>
          </issuerMetadata>
        </message>
      </security>
    </binding>
  </ws2007FederationHttpBinding>
</bindings>
```

<span data-ttu-id="3826e-117">На [ \<>безопасности ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md) `security` значение определяет, какой режим безопасности следует использовать.</span><span class="sxs-lookup"><span data-stu-id="3826e-117">On the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md), the `security` value specifies which security mode should be used.</span></span> <span data-ttu-id="3826e-118">В этом `message` примере используется безопасность, поэтому [ \<>сообщения](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) указана внутри [ \<>безопасности. ](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="3826e-118">In this sample, `message` security is used, which is why the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) is specified inside the [\<security>](../../configure-apps/file-schema/wcf/security-element-of-ws2007federationhttpbinding.md).</span></span> <span data-ttu-id="3826e-119">[ \<элемент>в](../../configure-apps/file-schema/wcf/issuermetadata.md) [ \<сообщении,](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md)>`ws2007FederationHttpBinding` определяет адрес и идентификацию для конечной точки, которая может быть использована для получения метаданных для STS.</span><span class="sxs-lookup"><span data-stu-id="3826e-119">The [\<issuerMetadata>](../../configure-apps/file-schema/wcf/issuermetadata.md) element of `ws2007FederationHttpBinding` inside the [\<message>](../../configure-apps/file-schema/wcf/message-element-of-ws2007federationhttpbinding.md) specifies the address and identity for an endpoint that can be used to retrieve metadata for the STS.</span></span>

<span data-ttu-id="3826e-120">Поведение службы отображается в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="3826e-120">The behavior for the service is shown in the following code:</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name ="ServiceBehaviour" >
      <serviceDebug includeExceptionDetailInFaults ="true"/>
      <serviceMetadata httpGetEnabled ="true"/>
      <serviceCredentials>
        <issuedTokenAuthentication>
          <knownCertificates>
            <add storeLocation ="LocalMachine"
                 storeName="TrustedPeople"
                 x509FindType="FindBySubjectDistinguishedName"
                 findValue="CN=STS" />
          </knownCertificates>
        </issuedTokenAuthentication>
        <serviceCertificate storeLocation ="LocalMachine"
                            storeName ="My"
                            x509FindType ="FindBySubjectDistinguishedName"
                            findValue ="CN=localhost"/>
      </serviceCredentials>
    </behavior>
  </serviceBehaviors>
</behaviors>
```
  
<span data-ttu-id="3826e-121">ВыданноеToTokenAuthentication>> позволяет службе указывать ограничения на токены, которые она позволяет клиентам представить во время проверки подлинности. [ \<](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="3826e-121">The [\<issuedTokenAuthentication>](../../configure-apps/file-schema/wcf/issuedtokenauthentication-of-servicecredentials.md)> allows the service to specify constraints on the tokens it allows clients to present during authentication.</span></span> <span data-ttu-id="3826e-122">Эта конфигурация указывает, что маркеры, подписанные сертификатом, у которых имя субъекта CN=STS, принимаются службой.</span><span class="sxs-lookup"><span data-stu-id="3826e-122">This configuration specifies that tokens signed by a certificate whose subject name is CN=STS are accepted by the service.</span></span>

<span data-ttu-id="3826e-123">Служба маркеров безопасности делает единственную конечную точку доступной с помощью стандартной привязки <xref:System.ServiceModel.WS2007HttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="3826e-123">STS makes a single endpoint available using the standard <xref:System.ServiceModel.WS2007HttpBinding>.</span></span> <span data-ttu-id="3826e-124">Служба отвечает на запросы маркеров от клиентов.</span><span class="sxs-lookup"><span data-stu-id="3826e-124">The service responds to requests from clients for tokens.</span></span> <span data-ttu-id="3826e-125">Если клиент прошел проверку подлинности с использованием учетной записи Windows, служба выдает маркер, содержащий имя пользователя клиента в качестве утверждения.</span><span class="sxs-lookup"><span data-stu-id="3826e-125">If the client is authenticated using a Windows account, the service issues a token that contains the client's user name as a claim.</span></span> <span data-ttu-id="3826e-126">В одной из частей процедуры создания маркера служба маркеров безопасности подписывает маркер с использованием закрытого ключа, связанного с сертификатом CN=STS.</span><span class="sxs-lookup"><span data-stu-id="3826e-126">As part of creating the token, STS signs the token using the private key associated with the CN=STS certificate.</span></span> <span data-ttu-id="3826e-127">Дополнительно она создает симметричный ключ и шифрует его с использованием открытого ключа, связанного с сертификатом CN=localhost.</span><span class="sxs-lookup"><span data-stu-id="3826e-127">In addition, it creates a symmetric key and encrypts it using the public key associated with the CN=localhost certificate.</span></span> <span data-ttu-id="3826e-128">При возврате маркера клиенту служба маркеров безопасности также возвращает симметричный ключ.</span><span class="sxs-lookup"><span data-stu-id="3826e-128">In returning the token to the client, STS also returns the symmetric key.</span></span> <span data-ttu-id="3826e-129">Клиент предъявляет выданный маркер службе `ICalculator` и подтверждает свое знание симметричного ключа, подписывая сообщение этим ключом.</span><span class="sxs-lookup"><span data-stu-id="3826e-129">The client presents the issued token to the `ICalculator` service and proves that it knows the symmetric key by signing the message with that key.</span></span>

<span data-ttu-id="3826e-130">При выполнении примера запрос маркера безопасности показан в окне консоли службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3826e-130">When you run the sample, the request for the security token is shown in the STS console window.</span></span> <span data-ttu-id="3826e-131">Запросы и ответы операций появляются в окнах консоли клиента и службы.</span><span class="sxs-lookup"><span data-stu-id="3826e-131">The operation's requests and responses are displayed in the client and service console windows.</span></span> <span data-ttu-id="3826e-132">Чтобы закрыть приложение, нажмите клавишу ВВОД в любом из окон консоли.</span><span class="sxs-lookup"><span data-stu-id="3826e-132">Press ENTER in any of the console windows to shut down the application.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714
Press <ENTER> to terminate client.
```

<span data-ttu-id="3826e-133">Файл *Setup.bat,* включенный в этот пример, позволяет настроить сервер и STS с соответствующими сертификатами для запуска самоходного приложения.</span><span class="sxs-lookup"><span data-stu-id="3826e-133">The *Setup.bat* file included with this sample allows you to configure the server and STS with the relevant certificates to run a self-hosted application.</span></span> <span data-ttu-id="3826e-134">Пакетный файл создает два сертификата в хранилище сертификатов LocalMachine/TrustedPeople.</span><span class="sxs-lookup"><span data-stu-id="3826e-134">The batch file creates two certificates in the LocalMachine/TrustedPeople certificate store.</span></span> <span data-ttu-id="3826e-135">Имя субъекта первого сертификата CN=STS, он используется службой маркеров безопасности, чтобы подписывать маркеры безопасности, выдаваемые клиенту.</span><span class="sxs-lookup"><span data-stu-id="3826e-135">The first certificate has a subject name of CN=STS and is used by STS to sign the security tokens that it issues to the client.</span></span> <span data-ttu-id="3826e-136">Имя субъекта второго сертификата CN=localhost, он используется службой маркеров безопасности для шифрования ключа таким образом, чтобы служба могла его расшифровать.</span><span class="sxs-lookup"><span data-stu-id="3826e-136">The second certificate has a subject name of CN=localhost and is used by STS to encrypt a key in a way that the service can decrypt.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3826e-137">Настройка, сборка и выполнение образца</span><span class="sxs-lookup"><span data-stu-id="3826e-137">To set up, build, and run the sample</span></span>
  
1. <span data-ttu-id="3826e-138">Убедитесь, что вы выполнили [одноразовую процедуру настройки для образцов Фонда связи Windows.](one-time-setup-procedure-for-the-wcf-samples.md)</span><span class="sxs-lookup"><span data-stu-id="3826e-138">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="3826e-139">Откройте командный запрос разработчика для Visual Studio с привилегиями администратора и запустите файл Setup.bat для создания необходимых сертификатов.</span><span class="sxs-lookup"><span data-stu-id="3826e-139">Open a Developer Command Prompt for Visual Studio with administrator privileges and run the Setup.bat file to create the required certificates.</span></span>

 <span data-ttu-id="3826e-140">Этот пакетный файл использует *Certmgr.exe* и Makecert.exe, которые распространяются с Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="3826e-140">This batch file uses *Certmgr.exe* and Makecert.exe, which are distributed with the Windows SDK.</span></span> <span data-ttu-id="3826e-141">Тем не менее, необходимо запустить *Setup.bat* из команды Visual Studio, чтобы позволить скрипту найти эти инструменты.</span><span class="sxs-lookup"><span data-stu-id="3826e-141">However, you must run *Setup.bat* from within a Visual Studio command prompt to enable the script to find these tools.</span></span>

1. <span data-ttu-id="3826e-142">Чтобы создать выпуск решения на языке C# или Visual Basic .NET, следуйте инструкциям в разделе [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3826e-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

2. <span data-ttu-id="3826e-143">Чтобы запустить образец в одно- или кросс-компьютерной конфигурации, следуйте инструкциям в [Запуске образцов Фонда связи Windows.](running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="3826e-143">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="3826e-144">Если вы используете Windows Vista, вы должны запустить *Service.exe*, *Client.exe*, и *SecurityTokenService.exe* с повышенными привилегиями (право нажмите на файлы, а затем нажмите **Run в качестве администратора).**</span><span class="sxs-lookup"><span data-stu-id="3826e-144">If you are using Windows Vista, you must run *Service.exe*, *Client.exe*, and *SecurityTokenService.exe* with elevated privileges (right-click the files and then click **Run as administrator**).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3826e-145">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="3826e-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3826e-146">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="3826e-146">Check for the following (default) directory before continuing:</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="3826e-147">Если этого каталога не существует, перейдите в [Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) Образцы для .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) чтобы загрузить все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] образцы.</span><span class="sxs-lookup"><span data-stu-id="3826e-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3826e-148">Этот образец находится в следующем каталоге:</span><span class="sxs-lookup"><span data-stu-id="3826e-148">This sample is located in the following directory:</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\WS2007FederationHttp`
