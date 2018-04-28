---
title: Практическое руководство. Задание значений учетных данных клиента
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 82293d7f-471a-4549-8f19-0be890e7b074
caps.latest.revision: 28
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 35244032a36af8d3d23fd9d88006ea032a99b44b
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-specify-client-credential-values"></a><span data-ttu-id="6136e-102">Практическое руководство. Задание значений учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-102">How to: Specify Client Credential Values</span></span>
<span data-ttu-id="6136e-103">Используя [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], служба может указать способ проверки подлинности клиента в службе.</span><span class="sxs-lookup"><span data-stu-id="6136e-103">Using [!INCLUDE[indigo1](../../../includes/indigo1-md.md)], the service can specify how a client is authenticated to the service.</span></span> <span data-ttu-id="6136e-104">Например, в службе можно указать, что клиент проходит проверку подлинности с помощью сертификата.</span><span class="sxs-lookup"><span data-stu-id="6136e-104">For example, a service can stipulate that the client be authenticated with a certificate.</span></span>  
  
### <a name="to-determine-the-client-credential-type"></a><span data-ttu-id="6136e-105">Определение типа учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-105">To determine the client credential type</span></span>  
  
1.  <span data-ttu-id="6136e-106">Получите метаданные из конечной точки метаданных службы.</span><span class="sxs-lookup"><span data-stu-id="6136e-106">Retrieve metadata from the service's metadata endpoint.</span></span> <span data-ttu-id="6136e-107">Метаданные обычно состоят из двух файлов: код клиента на выбранном языке программирования (по умолчанию - Visual C#) и XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6136e-107">The metadata typically consists of two files: the client code in the programming language of your choice (the default is Visual C#), and an XML configuration file.</span></span> <span data-ttu-id="6136e-108">Одним из способов получения метаданных является использование программы Svcutil.exe для возвращения кода клиента и конфигурации клиента.</span><span class="sxs-lookup"><span data-stu-id="6136e-108">One way to retrieve metadata is to use the Svcutil.exe tool to return the client code and client configuration.</span></span> <span data-ttu-id="6136e-109">Дополнительные сведения см. в разделе [получение метаданных](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) и [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="6136e-109">For more information, see [Retrieving Metadata](../../../docs/framework/wcf/feature-details/retrieving-metadata.md) and [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
2.  <span data-ttu-id="6136e-110">Откройте XML-файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6136e-110">Open the XML configuration file.</span></span> <span data-ttu-id="6136e-111">Если используется программа Svcutil.exe, то по умолчанию файл имеет имя Output.config.</span><span class="sxs-lookup"><span data-stu-id="6136e-111">If you use the Svcutil.exe tool, the default name of the file is Output.config.</span></span>  
  
3.  <span data-ttu-id="6136e-112">Найти  **\<безопасности >** элемент с **режим** атрибут (**< режим безопасности =** `MessageOrTransport` **>** где `MessageOrTransport` задан один из режимов безопасности.</span><span class="sxs-lookup"><span data-stu-id="6136e-112">Find the **\<security>** element with the **mode** attribute (**<security mode =**`MessageOrTransport`**>** where `MessageOrTransport` is set to one of the security modes.</span></span>  
  
4.  <span data-ttu-id="6136e-113">Найдите дочерний элемент, соответствующий значению режима.</span><span class="sxs-lookup"><span data-stu-id="6136e-113">Find the child element that matches the mode value.</span></span> <span data-ttu-id="6136e-114">Например, если включен режим **сообщение**, найти  **\<сообщения >** элемента, содержащегося в  **\<безопасности >** элемента.</span><span class="sxs-lookup"><span data-stu-id="6136e-114">For example, if the mode is set to **Message**, find the **\<message>** element contained in the **\<security>** element.</span></span>  
  
5.  <span data-ttu-id="6136e-115">Обратите внимание, значение, присваиваемое **clientCredentialType** атрибута.</span><span class="sxs-lookup"><span data-stu-id="6136e-115">Note the value assigned to the **clientCredentialType** attribute.</span></span> <span data-ttu-id="6136e-116">Фактическое значение зависит от используемого режима - транспорт или сообщение.</span><span class="sxs-lookup"><span data-stu-id="6136e-116">The actual value depends on which mode is used, transport or message.</span></span>  
  
 <span data-ttu-id="6136e-117">Следующий XML-код представляет конфигурацию для клиента, использующего безопасность сообщений. Для проверки подлинности клиента требуется сертификат.</span><span class="sxs-lookup"><span data-stu-id="6136e-117">The following XML code shows configuration for a client using message security and requiring a certificate to authenticate the client.</span></span>  
  
```xml  
<security mode="Message">  
    <transport clientCredentialType="Windows" proxyCredentialType="None"  
        realm="" />  
     <message clientCredentialType="Certificate" negotiateServiceCredential="true"  
    algorithmSuite="Default" establishSecurityContext="true" />  
</security>  
```  
  
## <a name="example-tcp-transport-mode-with-certificate-as-client-credential"></a><span data-ttu-id="6136e-118">Пример: транспортный режим TCP с сертификатом в качестве учетных данных клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-118">Example: TCP Transport Mode with Certificate as Client Credential</span></span>  
 <span data-ttu-id="6136e-119">В этом примере в качестве режима безопасности задается Transport, а в качестве значения учетных данных клиента - сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="6136e-119">This example sets the security mode to Transport mode and sets the client credential value to an X.509 certificate.</span></span> <span data-ttu-id="6136e-120">В следующих процедурах показано, как задать значение учетных данных клиента в коде клиента и в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6136e-120">The following procedures demonstrate how to set the client credential value on the client in code and configuration.</span></span> <span data-ttu-id="6136e-121">Предполагается, что используется [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для возврата метаданных (код и конфигурация) из службы.</span><span class="sxs-lookup"><span data-stu-id="6136e-121">This assumes that you have used the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to return the metadata (code and configuration) from the service.</span></span> <span data-ttu-id="6136e-122">Дополнительные сведения см. в разделе [как: создание клиента](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="6136e-122">For more information, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-code"></a><span data-ttu-id="6136e-123">Указание значения учетных данных клиента в коде клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-123">To specify the client credential value on the client in code</span></span>  
  
1.  <span data-ttu-id="6136e-124">Используйте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) для создания кода и конфигурации из службы.</span><span class="sxs-lookup"><span data-stu-id="6136e-124">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate code and configuration from the service.</span></span>  
  
2.  <span data-ttu-id="6136e-125">Создайте экземпляр клиента [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] с помощью созданного кода.</span><span class="sxs-lookup"><span data-stu-id="6136e-125">Create an instance of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client using the generated code.</span></span>  
  
3.  <span data-ttu-id="6136e-126">В классе клиента задайте соответствующее значение для свойства <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> класса <xref:System.ServiceModel.ClientBase%601>.</span><span class="sxs-lookup"><span data-stu-id="6136e-126">On the client class, set the <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> property of the <xref:System.ServiceModel.ClientBase%601> class to an appropriate value.</span></span> <span data-ttu-id="6136e-127">В этом примере в качестве значения свойства задается сертификат X.509 с помощью метода <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>.</span><span class="sxs-lookup"><span data-stu-id="6136e-127">This example sets the property to an X.509 certificate using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential> class.</span></span>  
  
     [!code-csharp[c_TcpService#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_tcpservice/cs/source.cs#4)]
     [!code-vb[c_TcpService#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_tcpservice/vb/source.vb#4)]  
  
     <span data-ttu-id="6136e-128">Можно использовать любое перечисление класса <xref:System.Security.Cryptography.X509Certificates.X509FindType>.</span><span class="sxs-lookup"><span data-stu-id="6136e-128">You can use any of the enumerations of the <xref:System.Security.Cryptography.X509Certificates.X509FindType> class.</span></span> <span data-ttu-id="6136e-129">В случае, если сертификат изменен (в связи с истечением срока действия) используется имя субъекта.</span><span class="sxs-lookup"><span data-stu-id="6136e-129">The subject name is used here in case the certificate is changed (due to an expiration date).</span></span> <span data-ttu-id="6136e-130">Использование имени субъекта позволяет инфраструктуре снова найти сертификат.</span><span class="sxs-lookup"><span data-stu-id="6136e-130">Using the subject name enables the infrastructure to find the certificate again.</span></span>  
  
#### <a name="to-specify-the-client-credential-value-on-the-client-in-configuration"></a><span data-ttu-id="6136e-131">Указание значения учетных данных клиента в конфигурации клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-131">To specify the client credential value on the client in configuration</span></span>  
  
1.  <span data-ttu-id="6136e-132">Добавить [ \<поведение >](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) элемент [ \<поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6136e-132">Add a [\<behavior>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>  
  
2.  <span data-ttu-id="6136e-133">Добавить [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемент [ \<поведения >](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6136e-133">Add a [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element to the [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span> <span data-ttu-id="6136e-134">Необходимо присвоить обязательному атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="6136e-134">Be sure to set the required `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="6136e-135">Добавить [ \<clientCertificate >](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) элемент [ \<clientCredentials >](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6136e-135">Add a [\<clientCertificate>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md) element to the [\<clientCredentials>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) element.</span></span>  
  
4.  <span data-ttu-id="6136e-136">Присвойте соответствующие значения следующим атрибутам: `storeLocation`, `storeName`, `x509FindType` и `findValue`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6136e-136">Set the following attributes to appropriate values: `storeLocation`, `storeName`, `x509FindType`, and `findValue`, as shown in the following code.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="6136e-137"> сертификаты, в разделе [работа с сертификатами](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="6136e-137"> certificates, see [Working with Certificates](../../../docs/framework/wcf/feature-details/working-with-certificates.md).</span></span>  
  
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
  
5.  <span data-ttu-id="6136e-138">При настройке клиента укажите поведение, задав атрибут `behaviorConfiguration` элемента `<endpoint>`, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="6136e-138">When configuring the client, specify the behavior by setting the `behaviorConfiguration` attribute of the `<endpoint>` element, as shown in the following code.</span></span> <span data-ttu-id="6136e-139">Элемент конечной точки является дочерним элементом [ \<клиента >](../../../docs/framework/configure-apps/file-schema/wcf/client.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="6136e-139">The endpoint element is a child of the [\<client>](../../../docs/framework/configure-apps/file-schema/wcf/client.md) element.</span></span> <span data-ttu-id="6136e-140">Также укажите имя конфигурации привязки, установив привязку для клиента в атрибуте `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="6136e-140">Also, specify the name of the binding configuration by setting the `bindingConfiguration` attribute to the binding for the client.</span></span> <span data-ttu-id="6136e-141">Если используется созданный файл конфигурации, имя привязки создается автоматически.</span><span class="sxs-lookup"><span data-stu-id="6136e-141">If you are using a generated configuration file, the binding's name is automatically generated.</span></span> <span data-ttu-id="6136e-142">В данном примере это имя `"tcpBindingWithCredential"`.</span><span class="sxs-lookup"><span data-stu-id="6136e-142">In this example, the name is `"tcpBindingWithCredential"`.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name =""  
                address="net.tcp://contoso.com:8036/aloha"  
                binding="netTcpBinding"  
                bindingConfiguration="tcpBindingWithCredential"  
                behaviorConfiguration="endpointCredentialBehavior" />  
    </client>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="6136e-143">См. также</span><span class="sxs-lookup"><span data-stu-id="6136e-143">See Also</span></span>  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>  
 <xref:System.ServiceModel.ClientBase%601>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential>  
 [<span data-ttu-id="6136e-144">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="6136e-144">Programming WCF Security</span></span>](../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 [<span data-ttu-id="6136e-145">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="6136e-145">Selecting a Credential Type</span></span>](../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="6136e-146">Служебная программа для метаданных ServiceModel (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="6136e-146">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="6136e-147">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="6136e-147">Working with Certificates</span></span>](../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [<span data-ttu-id="6136e-148">Практическое руководство. Создание клиента</span><span class="sxs-lookup"><span data-stu-id="6136e-148">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="6136e-149">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="6136e-149">\<netTcpBinding></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)  
 [<span data-ttu-id="6136e-150">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="6136e-150">\<security></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)  
 [<span data-ttu-id="6136e-151">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="6136e-151">\<message></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/message-element-of-nettcpbinding.md)  
 [<span data-ttu-id="6136e-152">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6136e-152">\<behavior></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)  
 [<span data-ttu-id="6136e-153">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="6136e-153">\<behaviors></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)  
 [<span data-ttu-id="6136e-154">\<clientCertificate ></span><span class="sxs-lookup"><span data-stu-id="6136e-154">\<clientCertificate></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-servicecredentials.md)  
 [<span data-ttu-id="6136e-155">\<clientCredentials ></span><span class="sxs-lookup"><span data-stu-id="6136e-155">\<clientCredentials></span></span>](../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)
