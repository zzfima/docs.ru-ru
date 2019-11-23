---
title: Практическое руководство. Задание значений учетных данных клиента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
ms.openlocfilehash: 2417c2dd16224d6cbf00d3f1f4a8958420830b6c
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319859"
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="4e555-102">Практическое руководство. Задание значений учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-102">How to: Specify Client Credential Values</span></span>

<span data-ttu-id="4e555-103">С помощью Windows Communication Foundation (WCF) служба может указать, как клиент проходит проверку подлинности в службе.</span><span class="sxs-lookup"><span data-stu-id="4e555-103">Using Windows Communication Foundation (WCF), the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="4e555-104">Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="4e555-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>

## <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="4e555-105">Определение типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-105">To determine the client credential type</span></span>

1. <span data-ttu-id="4e555-106">Получите метаданные из конечной точки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="4e555-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="4e555-107">Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования (по умолчанию - Visual C#) и XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e555-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="4e555-108">Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="4e555-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="4e555-109">Дополнительные сведения см. в разделе [Получение метаданных](./feature-details/retrieving-metadata.md) и [средства служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="4e555-109">For more information, see [Retrieving Metadata](./feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>

2. <span data-ttu-id="4e555-110">Откройте XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e555-110">Open the XML configuration file.</span></span> <span data-ttu-id="4e555-111">Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.</span><span class="sxs-lookup"><span data-stu-id="4e555-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>

3. <span data-ttu-id="4e555-112">Найдите элемент **> безопасности\<** с атрибутом **mode** ( **\<режим безопасности =** `MessageOrTransport` **>** , где `MessageOrTransport` установлен в один из режимов безопасности.</span><span class="sxs-lookup"><span data-stu-id="4e555-112">Find the **\<security>** element with the **mode** attribute (**\<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>

4. <span data-ttu-id="4e555-113">Найдите дочерний элемент, соответствующий значению режима.</span><span class="sxs-lookup"><span data-stu-id="4e555-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="4e555-114">Например, если для режима задано значение **Message**, найдите элемент **> сообщение\<** , содержащийся в элементе **\<> безопасности** .</span><span class="sxs-lookup"><span data-stu-id="4e555-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>

5. <span data-ttu-id="4e555-115">Запишите значение, присвоенное атрибуту **ClientCredentialType** .</span><span class="sxs-lookup"><span data-stu-id="4e555-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="4e555-116">Фактическое значение зависит от используемого режима - транспорт или сообщение.</span><span class="sxs-lookup"><span data-stu-id="4e555-116">The actual value depends on which mode is used, transport or message.</span></span>

<span data-ttu-id="4e555-117">Следующий XML-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="4e555-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>

```xml
<security mode="Message">
    <transport clientCredentialType="Windows" proxyCredentialType="None"
        realm="" />
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"
    algorithmSuite="Default" establishSecurityContext="true" />
</security>
```

## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="4e555-118">Пример: транспортный режим TCP с сертификатом в качестве учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>

<span data-ttu-id="4e555-119">В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента - сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="4e555-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="4e555-120">В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4e555-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="4e555-121">Предполагается, что вы использовали [средство служебной программы метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для возврата метаданных (кода и конфигурации) из службы.</span><span class="sxs-lookup"><span data-stu-id="4e555-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="4e555-122">Дополнительные сведения см. [в разделе инструкции. Создание клиента](how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="4e555-122">For more information, see [How to: Create a Client](how-to-create-a-wcf-client.md).</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="4e555-123">Указание значения учетных данных клиента в коде клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-123">To specify the client credential value on the client in code</span></span>

1. <span data-ttu-id="4e555-124">Используйте [средство служебной программы для метаданных ServiceModel (Svcutil. exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.</span><span class="sxs-lookup"><span data-stu-id="4e555-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>

2. <span data-ttu-id="4e555-125">Создайте экземпляр клиента WCF с помощью созданного кода.</span><span class="sxs-lookup"><span data-stu-id="4e555-125">Create an instance of the WCF client using the generated code.</span></span>

3. <span data-ttu-id="4e555-126">В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>.</span><span class="sxs-lookup"><span data-stu-id="4e555-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="4e555-127">В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="4e555-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>

     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]

     <span data-ttu-id="4e555-128">Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="4e555-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="4e555-129">В случае, если сертификат изменен (в связи с истечением срока действия) используется имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="4e555-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="4e555-130">Использование имени субъекта позволяет инфраструктуре снова найти сертификат.</span><span class="sxs-lookup"><span data-stu-id="4e555-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>

### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="4e555-131">Указание значения учетных данных клиента в конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-131">To specify the client credential value on the client in configuration</span></span>

1. <span data-ttu-id="4e555-132">Добавьте элемент [\<behavior >](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) в элемент [\<Behaviors >](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="4e555-132">Add a [\<behavior>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

2. <span data-ttu-id="4e555-133">Добавьте элемент [\<clientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) в элемент [\<поведения >](../configure-apps/file-schema/wcf/behaviors.md) .</span><span class="sxs-lookup"><span data-stu-id="4e555-133">Add a [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="4e555-134">Необходимо присвоить обязательному атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="4e555-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="4e555-135">Добавьте элемент [\<clientCertificate >](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) в элемент [\<ClientCredentials >](../configure-apps/file-schema/wcf/clientcredentials.md) .</span><span class="sxs-lookup"><span data-stu-id="4e555-135">Add a [\<clientCertificate>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>

4. <span data-ttu-id="4e555-136">Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4e555-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> <span data-ttu-id="4e555-137">Дополнительные сведения см. в разделе [Работа с сертификатами](./feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="4e555-137">For more information about certificates, see [Working with Certificates](./feature-details/working-with-certificates.md).</span></span>

    ```xml
    <behaviors>
       <endpointBehaviors>
          <behavior name="endpointCredentialBehavior">
            <clientCredentials>
              <clientCertificate findValue="Contoso.com"
                                 storeLocation="LocalMachine"
                                 storeName="TrustedPeople"
                                 x509FindType="FindBySubjectName" />
            </clientCredentials>
          </behavior>
       </endpointBehaviors>
    </behaviors>
    ```

5. <span data-ttu-id="4e555-138">При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4e555-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="4e555-139">Элемент конечной точки является дочерним по отношению к элементу [\<клиентского >](../configure-apps/file-schema/wcf/client.md) .</span><span class="sxs-lookup"><span data-stu-id="4e555-139">The endpoint element is a child of the [\<client>](../configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="4e555-140">Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="4e555-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="4e555-141">Если используется созданный файл конфигурации, имя привязки создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="4e555-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="4e555-142">В данном примере это имя `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="4e555-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>

    ```xml
    <client>
      <endpoint name =""
                address="net.tcp://contoso.com:8036/aloha"
                binding="netTcpBinding"
                bindingConfiguration="tcpBindingWithCredential"
                behaviorConfiguration="endpointCredentialBehavior" />
    </client>
    ```

## <a name="see-also"></a><span data-ttu-id="4e555-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="4e555-143">See also</span></span>

- <xref:System.ServiceModel.NetTcpBinding>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>
- <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>
- <xref:System.ServiceModel.ClientBase%601>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>
- [<span data-ttu-id="4e555-144">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="4e555-144">Programming WCF Security</span></span>](./feature-details/programming-wcf-security.md)
- [<span data-ttu-id="4e555-145">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="4e555-145">Selecting a Credential Type</span></span>](./feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4e555-146">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="4e555-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="4e555-147">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="4e555-147">Working with Certificates</span></span>](./feature-details/working-with-certificates.md)
- [<span data-ttu-id="4e555-148">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="4e555-148">How to: Create a Client</span></span>](how-to-create-a-wcf-client.md)
- [<span data-ttu-id="4e555-149">\<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="4e555-149">\<netTcpBinding></span></span>](../configure-apps/file-schema/wcf/nettcpbinding.md)
- [<span data-ttu-id="4e555-150">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="4e555-150">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
- [<span data-ttu-id="4e555-151">сообщение \<></span><span class="sxs-lookup"><span data-stu-id="4e555-151">\<message></span></span>](../configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)
- [<span data-ttu-id="4e555-152">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="4e555-152">\<behavior></span></span>](../configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)
- [<span data-ttu-id="4e555-153">\<поведений ></span><span class="sxs-lookup"><span data-stu-id="4e555-153">\<behaviors></span></span>](../configure-apps/file-schema/wcf/behaviors.md)
- [<span data-ttu-id="4e555-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="4e555-154">\<clientCertificate></span></span>](../configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)
- [<span data-ttu-id="4e555-155">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="4e555-155">\<clientCredentials></span></span>](../configure-apps/file-schema/wcf/clientcredentials.md)
