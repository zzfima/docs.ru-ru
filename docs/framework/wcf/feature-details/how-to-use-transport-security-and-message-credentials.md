---
title: Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TransportWithMessageCredentials
ms.assetid: 6cc35346-c37a-4859-b82b-946c0ba6e68f
author: BrucePerlerMS
ms.openlocfilehash: 40fe7b1fa6a61b56d5dfdde75a92834f096a8be4
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "47200416"
---
# <a name="how-to-use-transport-security-and-message-credentials"></a><span data-ttu-id="c4c67-102">Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения</span><span class="sxs-lookup"><span data-stu-id="c4c67-102">How to: Use Transport Security and Message Credentials</span></span>
<span data-ttu-id="c4c67-103">Защита службы с помощью учетных данных транспорта и сообщений использует лучшие возможности режимов безопасности транспорта и сообщений в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="c4c67-103">Securing a service with both transport and message credentials uses the best of both Transport and Message security modes in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="c4c67-104">В общих словах, TLS обеспечивает целостность и конфиденциальность, а MLS предоставляет различные учетные данные, которые невозможно использовать в строгих механизмах обеспечения безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="c4c67-104">In sum, transport-layer security provides integrity and confidentiality, while message-layer security provides a variety of credentials that are not possible with strict transport security mechanisms.</span></span> <span data-ttu-id="c4c67-105">В этом разделе приведены основные этапы реализации транспорта с учетными данными сообщения с помощью привязок <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.NetTcpBinding>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-105">This topic shows the basic steps for implementing transport with message credentials using the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> bindings.</span></span> <span data-ttu-id="c4c67-106">Дополнительные сведения о задании режима безопасности см. в разделе [как: Настройка режима безопасности](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c4c67-106">For more information about setting the security mode, see [How to: Set the Security Mode](../../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
 <span data-ttu-id="c4c67-107">При задании режима безопасности`TransportWithMessageCredential` транспорт определяет фактический механизм, обеспечивающий безопасность на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="c4c67-107">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="c4c67-108">В случае HTTP таким механизмом является SSL по HTTP (HTTPS); в случае TCP таким механизмом является SSL по TCP или Windows.</span><span class="sxs-lookup"><span data-stu-id="c4c67-108">For HTTP, the mechanism is Secure Sockets Layer (SSL) over HTTP (HTTPS); for TCP, it is SSL over TCP or Windows.</span></span>  
  
 <span data-ttu-id="c4c67-109">Если транспортом является HTTP (используется <xref:System.ServiceModel.WSHttpBinding>), SSL по HTTP обеспечивает безопасность на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="c4c67-109">If the transport is HTTP (using the <xref:System.ServiceModel.WSHttpBinding>), SSL over HTTP provides the transport-level security.</span></span> <span data-ttu-id="c4c67-110">В этом случае необходимо задать для компьютера, на котором размещена служба, SSL-сертификат, привязанный к порту, как показано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c4c67-110">In that case, you must configure the computer hosting the service with an SSL certificate bound to a port, as shown later in this topic.</span></span>  
  
 <span data-ttu-id="c4c67-111">Если транспортом является TCP (используется <xref:System.ServiceModel.NetTcpBinding>), по умолчанию безопасность на транспортном уровне обеспечивается механизмом безопасности Windows или SSL по TCP.</span><span class="sxs-lookup"><span data-stu-id="c4c67-111">If the transport is TCP (using the <xref:System.ServiceModel.NetTcpBinding>), by default the transport-level security provided is Windows security, or SSL over TCP.</span></span> <span data-ttu-id="c4c67-112">При использовании SSL по TCP необходимо указать сертификат с помощью метода <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A>, как показано далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="c4c67-112">When using SSL over TCP, you must specify the certificate using the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method, as shown later in this topic.</span></span>  
  
### <a name="to-use-the-wshttpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="c4c67-113">Использование привязки WSHttpBinding с сертификатом для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="c4c67-113">To use the WSHttpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="c4c67-114">Воспользуйтесь средством HttpCfg.exe для привязки SSL-сертификата к порту на компьютере.</span><span class="sxs-lookup"><span data-stu-id="c4c67-114">Use the HttpCfg.exe tool to bind an SSL certificate to a port on the machine.</span></span> <span data-ttu-id="c4c67-115">Дополнительные сведения см. в разделе [как: Настройка порта SSL-сертификат](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="c4c67-115">For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md).</span></span>  
  
2.  <span data-ttu-id="c4c67-116">Создайте экземпляр класса <xref:System.ServiceModel.WSHttpBinding> и задайте для свойства <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-116">Create an instance of the <xref:System.ServiceModel.WSHttpBinding> class and set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
3.  <span data-ttu-id="c4c67-117">Присвойте свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-117">Set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="c4c67-118">(Дополнительные сведения см. в разделе [Выбор типа учетных данных](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) В следующем коде используется значение <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-118">(For more information, see [Selecting a Credential Type](../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md).) The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="c4c67-119">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="c4c67-119">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="c4c67-120">Обратите внимание, что адрес должен использовать схему "HTTPS" и содержать фактическое имя компьютера и номер порта, к которому привязан SSL-сертификат.</span><span class="sxs-lookup"><span data-stu-id="c4c67-120">Note that the address must use the "HTTPS" scheme and must contain the actual name of the machine and the port number that the SSL certificate is bound to.</span></span> <span data-ttu-id="c4c67-121">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="c4c67-121">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="c4c67-122">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-122">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
6.  <span data-ttu-id="c4c67-123">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost> и вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c4c67-123">Create the instance of the <xref:System.ServiceModel.ServiceHost> and call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#7)]
     [!code-vb[c_SettingSecurityMode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#7)]  
  
### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security-in-code"></a><span data-ttu-id="c4c67-124">Использование привязки NetTcpBinding с сертификатом для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="c4c67-124">To use the NetTcpBinding with a certificate for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="c4c67-125">Создайте экземпляр класса <xref:System.ServiceModel.NetTcpBinding> и задайте для свойства <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-125">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="c4c67-126">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-126">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="c4c67-127">В следующем коде используется значение <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-127">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
3.  <span data-ttu-id="c4c67-128">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="c4c67-128">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="c4c67-129">Обратите внимание, что адрес должен использовать схему "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="c4c67-129">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="c4c67-130">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="c4c67-130">(Alternatively, you can set the base address in configuration.)</span></span>  
  
4.  <span data-ttu-id="c4c67-131">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-131">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
5.  <span data-ttu-id="c4c67-132">Воспользуйтесь методом <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>, чтобы явно задать сертификат X.509 для службы.</span><span class="sxs-lookup"><span data-stu-id="c4c67-132">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
6.  <span data-ttu-id="c4c67-133">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-133">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
7.  <span data-ttu-id="c4c67-134">Вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c4c67-134">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#8)]
     [!code-vb[c_SettingSecurityMode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#8)]  
  
### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security-in-code"></a><span data-ttu-id="c4c67-135">Использование привязки NetTcpBinding с Windows для обеспечения безопасности транспорта (в коде)</span><span class="sxs-lookup"><span data-stu-id="c4c67-135">To use the NetTcpBinding with Windows for transport security (in code)</span></span>  
  
1.  <span data-ttu-id="c4c67-136">Создайте экземпляр класса <xref:System.ServiceModel.NetTcpBinding> и задайте для свойства <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> значение <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-136">Create an instance of the <xref:System.ServiceModel.NetTcpBinding> class and set the <xref:System.ServiceModel.NetTcpSecurity.Mode%2A> property to <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>  
  
2.  <span data-ttu-id="c4c67-137">Настройте безопасность транспорта на использование Windows, задав для свойства <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> значение <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-137">Set the transport security to use Windows by setting the <xref:System.ServiceModel.TcpTransportSecurity.ClientCredentialType%2A> to <xref:System.ServiceModel.TcpClientCredentialType.Windows>.</span></span> <span data-ttu-id="c4c67-138">(Обратите внимание, что это значение используется по умолчанию.)</span><span class="sxs-lookup"><span data-stu-id="c4c67-138">(Note that this is the default.)</span></span>  
  
3.  <span data-ttu-id="c4c67-139">Присвойте свойству <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-139">Set the <xref:System.ServiceModel.MessageSecurityOverTcp.ClientCredentialType%2A> to an appropriate value.</span></span> <span data-ttu-id="c4c67-140">В следующем коде используется значение <xref:System.ServiceModel.MessageCredentialType.Certificate>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-140">The following code uses the <xref:System.ServiceModel.MessageCredentialType.Certificate> value.</span></span>  
  
4.  <span data-ttu-id="c4c67-141">Создайте экземпляр класса <xref:System.Uri> с соответствующим базовым адресом.</span><span class="sxs-lookup"><span data-stu-id="c4c67-141">Create an instance of the <xref:System.Uri> class with an appropriate base address.</span></span> <span data-ttu-id="c4c67-142">Обратите внимание, что адрес должен использовать схему "net.tcp".</span><span class="sxs-lookup"><span data-stu-id="c4c67-142">Note that the address must use the "net.tcp" scheme.</span></span> <span data-ttu-id="c4c67-143">(Кроме того, базовый адрес можно задать в конфигурации.)</span><span class="sxs-lookup"><span data-stu-id="c4c67-143">(Alternatively, you can set the base address in configuration.)</span></span>  
  
5.  <span data-ttu-id="c4c67-144">Создайте экземпляр класса <xref:System.ServiceModel.ServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-144">Create the instance of the <xref:System.ServiceModel.ServiceHost> class.</span></span>  
  
6.  <span data-ttu-id="c4c67-145">Воспользуйтесь методом <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> класса <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential>, чтобы явно задать сертификат X.509 для службы.</span><span class="sxs-lookup"><span data-stu-id="c4c67-145">Use the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential.SetCertificate%2A> method of the <xref:System.ServiceModel.Security.X509CertificateRecipientServiceCredential> class to explicitly set the X.509 certificate for the service.</span></span>  
  
7.  <span data-ttu-id="c4c67-146">Добавьте конечную точку службы с помощью метода <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A>.</span><span class="sxs-lookup"><span data-stu-id="c4c67-146">Add a service endpoint using the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method.</span></span>  
  
8.  <span data-ttu-id="c4c67-147">Вызовите метод <xref:System.ServiceModel.ICommunicationObject.Open%2A>, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c4c67-147">Call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method, as shown in the following code.</span></span>  
  
     [!code-csharp[c_SettingSecurityMode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#9)]
     [!code-vb[c_SettingSecurityMode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#9)]  
  
## <a name="using-configuration"></a><span data-ttu-id="c4c67-148">Использование конфигурации</span><span class="sxs-lookup"><span data-stu-id="c4c67-148">Using Configuration</span></span>  
  
#### <a name="to-use-the-wshttpbinding"></a><span data-ttu-id="c4c67-149">Использование привязки WSHttpBinding</span><span class="sxs-lookup"><span data-stu-id="c4c67-149">To use the WSHttpBinding</span></span>  
  
1.  <span data-ttu-id="c4c67-150">Задайте для компьютера SSL-сертификат, привязанный к порту.</span><span class="sxs-lookup"><span data-stu-id="c4c67-150">Configure the computer with an SSL certificate bound to a port.</span></span> <span data-ttu-id="c4c67-151">(Дополнительные сведения см. в разделе [как: Настройка порта SSL-сертификат](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span><span class="sxs-lookup"><span data-stu-id="c4c67-151">(For more information, see [How to: Configure a Port with an SSL Certificate](../../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)).</span></span> <span data-ttu-id="c4c67-152">Необходимо задать <`transport`> значение элемента с этой конфигурацией.</span><span class="sxs-lookup"><span data-stu-id="c4c67-152">You do not need to set a <`transport`> element value with this configuration.</span></span>  
  
2.  <span data-ttu-id="c4c67-153">Задайте тип учетных данных клиента для MLS.</span><span class="sxs-lookup"><span data-stu-id="c4c67-153">Specify the client credential type for the message-level security.</span></span> <span data-ttu-id="c4c67-154">В следующем примере задается `clientCredentialType` атрибут <`message`> элемент `UserName`.</span><span class="sxs-lookup"><span data-stu-id="c4c67-154">The following example sets the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span>  
  
    ```xml  
    <wsHttpBinding>  
    <binding name="WsHttpBinding_ICalculator">  
            <security mode="TransportWithMessageCredential" >  
               <message clientCredentialType="UserName" />  
            </security>  
    </binding>  
    </wsHttpBinding>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-a-certificate-for-transport-security"></a><span data-ttu-id="c4c67-155">Использование привязки NetTcpBinding с сертификатом для обеспечения безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="c4c67-155">To use the NetTcpBinding with a certificate for transport security</span></span>  
  
1.  <span data-ttu-id="c4c67-156">В случае SSL по TCP необходимо явно задать сертификат в элементе `<behaviors>`.</span><span class="sxs-lookup"><span data-stu-id="c4c67-156">For SSL over TCP, you must explicitly specify the certificate in the `<behaviors>` element.</span></span> <span data-ttu-id="c4c67-157">В следующем примере сертификат задается своим издателем в хранилище по умолчанию (в хранилище локального компьютера и личном хранилище).</span><span class="sxs-lookup"><span data-stu-id="c4c67-157">The following example specifies a certificate by its issuer in the default store location (local machine and personal stores).</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
       <behavior name="mySvcBehavior">  
           <serviceCredentials>  
             <serviceCertificate findValue="contoso.com"  
                                 x509FindType="FindByIssuerName" />  
           </serviceCredentials>  
       </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="c4c67-158">Добавить [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) в раздел привязок</span><span class="sxs-lookup"><span data-stu-id="c4c67-158">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section</span></span>  
  
3.  <span data-ttu-id="c4c67-159">Добавьте элемент привязки и присвойте атрибуту `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-159">Add a binding element, and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="c4c67-160">Добавьте <`security`> и присвойте `mode` атрибут `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="c4c67-160">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
5.  <span data-ttu-id="c4c67-161">Добавьте <`message>` и присвойте `clientCredentialType` атрибут соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-161">Add a <`message>` element, and set the `clientCredentialType` attribute to an appropriate value.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <message clientCredentialType="Windows" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
#### <a name="to-use-the-nettcpbinding-with-windows-for-transport-security"></a><span data-ttu-id="c4c67-162">Использование привязки NetTcpBinding с Windows для обеспечения безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="c4c67-162">To use the NetTcpBinding with Windows for transport security</span></span>  
  
1.  <span data-ttu-id="c4c67-163">Добавить [ \<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) в раздел привязок</span><span class="sxs-lookup"><span data-stu-id="c4c67-163">Add a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) to the bindings section,</span></span>  
  
2.  <span data-ttu-id="c4c67-164">Добавьте <`binding`> и присвойте `name` атрибут соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-164">Add a <`binding`> element and set the `name` attribute to an appropriate value.</span></span>  
  
3.  <span data-ttu-id="c4c67-165">Добавьте <`security`> и присвойте `mode` атрибут `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="c4c67-165">Add a <`security`> element, and set the `mode` attribute to `TransportWithMessageCredential`.</span></span>  
  
4.  <span data-ttu-id="c4c67-166">Добавьте <`transport`> и присвойте `clientCredentialType` атрибут `Windows`.</span><span class="sxs-lookup"><span data-stu-id="c4c67-166">Add a <`transport`> element and set the `clientCredentialType` attribute to `Windows`.</span></span>  
  
5.  <span data-ttu-id="c4c67-167">Добавьте <`message`> и присвойте `clientCredentialType` атрибут соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="c4c67-167">Add a <`message`> element and set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="c4c67-168">В следующем коде задается значение для сертификата.</span><span class="sxs-lookup"><span data-stu-id="c4c67-168">The following code sets the value to a certificate.</span></span>  
  
    ```xml  
    <bindings>  
    <netTcpBinding>  
      <binding name="myTcpBinding">  
        <security mode="TransportWithMessageCredential" >  
           <transport clientCredentialType="Windows" />  
           <message clientCredentialType="Certificate" />  
        </security>  
      </binding>  
    </netTcpBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c4c67-169">См. также</span><span class="sxs-lookup"><span data-stu-id="c4c67-169">See Also</span></span>  
 [<span data-ttu-id="c4c67-170">Практическое руководство. Задание режима безопасности</span><span class="sxs-lookup"><span data-stu-id="c4c67-170">How to: Set the Security Mode</span></span>](../../../../docs/framework/wcf/how-to-set-the-security-mode.md)  
 [<span data-ttu-id="c4c67-171">Защита служб</span><span class="sxs-lookup"><span data-stu-id="c4c67-171">Securing Services</span></span>](../../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="c4c67-172">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c4c67-172">Securing Services and Clients</span></span>](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
