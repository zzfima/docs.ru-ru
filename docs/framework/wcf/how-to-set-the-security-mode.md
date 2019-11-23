---
title: Практическое руководство. Задание режима безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Mode property
- WCF, security mode
- WCF, security
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
ms.openlocfilehash: 9b9e25cbafb6387b4584a21fd642d80bc41cd8dc
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320898"
---
# <a name="how-to-set-the-security-mode"></a><span data-ttu-id="e9bd8-102">Практическое руководство. Задание режима безопасности</span><span class="sxs-lookup"><span data-stu-id="e9bd8-102">How to: Set the Security Mode</span></span>

<span data-ttu-id="e9bd8-103">В системе безопасности Windows Communication Foundation (WCF) есть три стандартных режима безопасности, которые находятся на большинстве предопределенных привязок: транспорт, сообщение и "Транспорт с учетными данными сообщений".</span><span class="sxs-lookup"><span data-stu-id="e9bd8-103">Windows Communication Foundation (WCF) security has three common security modes that are found on most predefined bindings: transport, message, and "transport with message credential."</span></span> <span data-ttu-id="e9bd8-104">Два дополнительных режима характерны для двух привязок: режим "Только учетные данные транспорта", используемый в <xref:System.ServiceModel.BasicHttpBinding>, режим "Оба", используемый в <xref:System.ServiceModel.NetMsmqBinding>.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-104">Two additional modes are specific to two bindings: the "transport-credential only" mode found on the <xref:System.ServiceModel.BasicHttpBinding>, and the "Both" mode, found on the <xref:System.ServiceModel.NetMsmqBinding>.</span></span> <span data-ttu-id="e9bd8-105">Однако в этом разделе основное внимание уделяется трем наиболее распространенным режимам безопасности: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> и <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-105">However, this topic concentrates on the three common security modes: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message>, and <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.</span></span>

<span data-ttu-id="e9bd8-106">Обратите внимание, что не все предварительно определенные привязки поддерживают все указанные режимы.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-106">Note that not every predefined binding supports all of these modes.</span></span> <span data-ttu-id="e9bd8-107">В этом разделе режим задается с помощью классов <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.NetTcpBinding>; также в этом разделе показан порядок задания режима как программно, так и с помощью конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-107">This topic sets the mode with the <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.NetTcpBinding> classes and demonstrates how to set the mode both programmatically and through configuration.</span></span>

<span data-ttu-id="e9bd8-108">Дополнительные сведения см. в статьях безопасность WCF, см. раздел [Общие сведения о безопасности](./feature-details/security-overview.md), безопасность [служб](securing-services.md)и [Безопасность служб и клиентов](./feature-details/securing-services-and-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-108">For more information, see WCF security, see [Security Overview](./feature-details/security-overview.md), [Securing Services](securing-services.md), and [Securing Services and Clients](./feature-details/securing-services-and-clients.md).</span></span> <span data-ttu-id="e9bd8-109">Дополнительные сведения о транспортном режиме и сообщении см. в разделе [Безопасность транспорта](./feature-details/transport-security.md) и [безопасность сообщений](./feature-details/message-security-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-109">For more information about transport mode and message, see [Transport Security](./feature-details/transport-security.md) and [Message Security](./feature-details/message-security-in-wcf.md).</span></span>

## <a name="to-set-the-security-mode-in-code"></a><span data-ttu-id="e9bd8-110">Задание режима безопасности в коде</span><span class="sxs-lookup"><span data-stu-id="e9bd8-110">To set the security mode in code</span></span>

1. <span data-ttu-id="e9bd8-111">Создайте экземпляр используемого класса привязки.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-111">Create an instance of the binding class that you are using.</span></span> <span data-ttu-id="e9bd8-112">Список предварительно определенных привязок см. в разделе [привязки, предоставляемые системой](system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-112">For a list of predefined bindings, see [System-Provided Bindings](system-provided-bindings.md).</span></span> <span data-ttu-id="e9bd8-113">В данном примере создается экземпляр класса <xref:System.ServiceModel.WSHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-113">This example creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class.</span></span>

2. <span data-ttu-id="e9bd8-114">Задайте свойство `Mode` объекта, возвращаемого свойством `Security`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-114">Set the `Mode` property of the object returned by the `Security` property.</span></span>

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     <span data-ttu-id="e9bd8-115">Или задайте режим "сообщение", как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-115">Alternatively, set the mode to message, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     <span data-ttu-id="e9bd8-116">Или задайте режим "транспорт с учетными данными сообщения", как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-116">Or set the mode to transport with message credentials, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. <span data-ttu-id="e9bd8-117">Также можно задать режим в конструкторе привязки, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-117">You can also set the mode in the constructor of the binding, as shown in the following code.</span></span>

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a><span data-ttu-id="e9bd8-118">Задание свойства ClientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e9bd8-118">Setting the ClientCredentialType Property</span></span>

<span data-ttu-id="e9bd8-119">Задание одного из трех значений режима определяет способ задания свойства `ClientCredentialType`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-119">Setting the mode to one of the three values determines how you set the `ClientCredentialType` property.</span></span> <span data-ttu-id="e9bd8-120">Например, при использовании класса <xref:System.ServiceModel.WSHttpBinding> задание режима `Transport` означает, что необходимо присвоить свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.HttpTransportSecurity> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-120">For example, using the <xref:System.ServiceModel.WSHttpBinding> class, setting the mode to `Transport` means you must set the <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> property of the <xref:System.ServiceModel.HttpTransportSecurity> class to an appropriate value.</span></span>

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a><span data-ttu-id="e9bd8-121">Задание свойства ClientCredentialType для режима Transport</span><span class="sxs-lookup"><span data-stu-id="e9bd8-121">To set the ClientCredentialType property for Transport mode</span></span>

1. <span data-ttu-id="e9bd8-122">Создайте экземпляр привязки.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-122">Create an instance of the binding.</span></span>

2. <span data-ttu-id="e9bd8-123">Задайте для свойства `Mode` значение `Transport`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-123">Set the `Mode` property to `Transport`.</span></span>

3. <span data-ttu-id="e9bd8-124">Присвойте свойству `ClientCredential` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-124">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="e9bd8-125">В следующем примере кода показано, как присвоить свойству значение `Windows`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-125">The following code sets the property to `Windows`.</span></span>

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a><span data-ttu-id="e9bd8-126">Задание свойства ClientCredentialType для режима Message</span><span class="sxs-lookup"><span data-stu-id="e9bd8-126">To set the ClientCredentialType property for Message mode</span></span>

1. <span data-ttu-id="e9bd8-127">Создайте экземпляр привязки.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-127">Create an instance of the binding.</span></span>

2. <span data-ttu-id="e9bd8-128">Задайте для свойства `Mode` значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-128">Set the `Mode` property to `Message`.</span></span>

3. <span data-ttu-id="e9bd8-129">Присвойте свойству `ClientCredential` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-129">Set the `ClientCredential` property to an appropriate value.</span></span> <span data-ttu-id="e9bd8-130">В следующем примере кода показано, как присвоить свойству значение `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-130">The following code sets the property to `Certificate`.</span></span>

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a><span data-ttu-id="e9bd8-131">Задание режима и свойства ClientCredentialType в конфигурации</span><span class="sxs-lookup"><span data-stu-id="e9bd8-131">To set the Mode and ClientCredentialType property in configuration</span></span>

1. <span data-ttu-id="e9bd8-132">Добавьте соответствующий элемент привязки в [\<привязки >](../configure-apps/file-schema/wcf/bindings.md) элемента файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-132">Add an appropriate binding element to the [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element of the configuration file.</span></span> <span data-ttu-id="e9bd8-133">В следующем примере добавляется элемент [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e9bd8-133">The following example adds a [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>

2. <span data-ttu-id="e9bd8-134">Добавьте элемент `<binding>` и задайте для его атрибута `name` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-134">Add a `<binding>` element and set its `name` attribute to an appropriate value.</span></span>

3. <span data-ttu-id="e9bd8-135">Добавьте элемент `<security>` и присвойте атрибуту `mode` значение `Message`, `Transport` или `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-135">Add a `<security>` element and set the `mode` attribute to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

4. <span data-ttu-id="e9bd8-136">Если задан режим `Transport`, добавьте элемент `<transport>` и присвойте атрибуту `clientCredential` соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-136">If the mode is set to `Transport`, add a `<transport>` element and set the `clientCredential` attribute to an appropriate value.</span></span>

     <span data-ttu-id="e9bd8-137">В следующем примере задается режим "`Transport"`, а затем атрибуту `clientCredentialType` элемента `<transport>` присваивается значение "`Windows"`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-137">The following example sets the mode to "`Transport"`, and then sets the `clientCredentialType` attribute of the `<transport>` element to "`Windows"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="e9bd8-138">Можно также задать для атрибута `security mode` значение "`Message"`, а затем указать элемент `<"message">`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-138">Alternatively, set the `security mode` to "`Message"`, followed by a `<"message">` element.</span></span> <span data-ttu-id="e9bd8-139">В этом примере атрибуту `clientCredentialType` присваивается значение "`Certificate"`.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-139">This example sets the `clientCredentialType` to "`Certificate"`.</span></span>

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     <span data-ttu-id="e9bd8-140">Значение <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> используется в особых случаях; подробнее см. ниже.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-140">Using the <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> value is a special case, and is explained below.</span></span>

### <a name="using-transportwithmessagecredential"></a><span data-ttu-id="e9bd8-141">Использование режима TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e9bd8-141">Using TransportWithMessageCredential</span></span>

<span data-ttu-id="e9bd8-142">При задании режима безопасности`TransportWithMessageCredential` транспорт определяет фактический механизм, обеспечивающий безопасность на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-142">When setting the security mode to `TransportWithMessageCredential`, the transport determines the actual mechanism that provides the transport-level security.</span></span> <span data-ttu-id="e9bd8-143">Например, протокол HTTP использует SSL по HTTP (HTTPS).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-143">For example, the HTTP protocol uses Secure Sockets Layer (SSL) over HTTP (HTTPS).</span></span> <span data-ttu-id="e9bd8-144">Поэтому задание свойства `ClientCredentialType` любого объекта безопасности транспорта (такого как <xref:System.ServiceModel.HttpTransportSecurity>) игнорируется.</span><span class="sxs-lookup"><span data-stu-id="e9bd8-144">Therefore, setting the `ClientCredentialType` property of any transport security object (such as <xref:System.ServiceModel.HttpTransportSecurity>) is ignored.</span></span>  <span data-ttu-id="e9bd8-145">Другими словами, можно задать только свойство `ClientCredentialType` объекта безопасности сообщения (для привязки `WSHttpBinding` это объект <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-145">In other words, you can only set the `ClientCredentialType` of the message security object (for the `WSHttpBinding` binding, the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp> object).</span></span>

<span data-ttu-id="e9bd8-146">Дополнительные сведения см. [в разделе как использовать безопасность транспорта и учетные данные сообщений](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="e9bd8-146">For more information, see [How to: Use Transport Security and Message Credentials](./feature-details/how-to-use-transport-security-and-message-credentials.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9bd8-147">См. также:</span><span class="sxs-lookup"><span data-stu-id="e9bd8-147">See also</span></span>

- [<span data-ttu-id="e9bd8-148">Практическое руководство. Настройка порта с использованием SSL-сертификата</span><span class="sxs-lookup"><span data-stu-id="e9bd8-148">How to: Configure a Port with an SSL Certificate</span></span>](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="e9bd8-149">Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения</span><span class="sxs-lookup"><span data-stu-id="e9bd8-149">How to: Use Transport Security and Message Credentials</span></span>](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [<span data-ttu-id="e9bd8-150">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="e9bd8-150">Transport Security</span></span>](./feature-details/transport-security.md)
- [<span data-ttu-id="e9bd8-151">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="e9bd8-151">Message Security</span></span>](./feature-details/message-security-in-wcf.md)
- [<span data-ttu-id="e9bd8-152">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="e9bd8-152">Security Overview</span></span>](./feature-details/security-overview.md)
- [<span data-ttu-id="e9bd8-153">Привязки, предоставляемые системой</span><span class="sxs-lookup"><span data-stu-id="e9bd8-153">System-Provided Bindings</span></span>](system-provided-bindings.md)
- [<span data-ttu-id="e9bd8-154">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="e9bd8-154">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [<span data-ttu-id="e9bd8-155">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="e9bd8-155">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [<span data-ttu-id="e9bd8-156">\<> безопасности</span><span class="sxs-lookup"><span data-stu-id="e9bd8-156">\<security></span></span>](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
