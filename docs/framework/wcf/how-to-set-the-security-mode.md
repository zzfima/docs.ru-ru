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
# <a name="how-to-set-the-security-mode"></a>Практическое руководство. Задание режима безопасности

В системе безопасности Windows Communication Foundation (WCF) есть три стандартных режима безопасности, которые находятся на большинстве предопределенных привязок: транспорт, сообщение и "Транспорт с учетными данными сообщений". Два дополнительных режима характерны для двух привязок: режим "Только учетные данные транспорта", используемый в <xref:System.ServiceModel.BasicHttpBinding>, режим "Оба", используемый в <xref:System.ServiceModel.NetMsmqBinding>. Однако в этом разделе основное внимание уделяется трем наиболее распространенным режимам безопасности: <xref:System.ServiceModel.SecurityMode.Transport>, <xref:System.ServiceModel.SecurityMode.Message> и <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>.

Обратите внимание, что не все предварительно определенные привязки поддерживают все указанные режимы. В этом разделе режим задается с помощью классов <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.NetTcpBinding>; также в этом разделе показан порядок задания режима как программно, так и с помощью конфигурации.

Дополнительные сведения см. в статьях безопасность WCF, см. раздел [Общие сведения о безопасности](./feature-details/security-overview.md), безопасность [служб](securing-services.md)и [Безопасность служб и клиентов](./feature-details/securing-services-and-clients.md). Дополнительные сведения о транспортном режиме и сообщении см. в разделе [Безопасность транспорта](./feature-details/transport-security.md) и [безопасность сообщений](./feature-details/message-security-in-wcf.md).

## <a name="to-set-the-security-mode-in-code"></a>Задание режима безопасности в коде

1. Создайте экземпляр используемого класса привязки. Список предварительно определенных привязок см. в разделе [привязки, предоставляемые системой](system-provided-bindings.md). В данном примере создается экземпляр класса <xref:System.ServiceModel.WSHttpBinding>.

2. Задайте свойство `Mode` объекта, возвращаемого свойством `Security`.

     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]

     Или задайте режим "сообщение", как показано в следующем примере кода.

     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]

     Или задайте режим "транспорт с учетными данными сообщения", как показано в следующем примере кода.

     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]

3. Также можно задать режим в конструкторе привязки, как показано в следующем примере кода.

     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]

## <a name="setting-the-clientcredentialtype-property"></a>Задание свойства ClientCredentialType

Задание одного из трех значений режима определяет способ задания свойства `ClientCredentialType`. Например, при использовании класса <xref:System.ServiceModel.WSHttpBinding> задание режима `Transport` означает, что необходимо присвоить свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.HttpTransportSecurity> соответствующее значение.

### <a name="to-set-the-clientcredentialtype-property-for-transport-mode"></a>Задание свойства ClientCredentialType для режима Transport

1. Создайте экземпляр привязки.

2. Задайте для свойства `Mode` значение `Transport`.

3. Присвойте свойству `ClientCredential` соответствующее значение. В следующем примере кода показано, как присвоить свойству значение `Windows`.

     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]

### <a name="to-set-the-clientcredentialtype-property-for-message-mode"></a>Задание свойства ClientCredentialType для режима Message

1. Создайте экземпляр привязки.

2. Задайте для свойства `Mode` значение `Message`.

3. Присвойте свойству `ClientCredential` соответствующее значение. В следующем примере кода показано, как присвоить свойству значение `Certificate`.

     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]

### <a name="to-set-the-mode-and-clientcredentialtype-property-in-configuration"></a>Задание режима и свойства ClientCredentialType в конфигурации

1. Добавьте соответствующий элемент привязки в [\<привязки >](../configure-apps/file-schema/wcf/bindings.md) элемента файла конфигурации. В следующем примере добавляется элемент [\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md) .

2. Добавьте элемент `<binding>` и задайте для его атрибута `name` соответствующее значение.

3. Добавьте элемент `<security>` и присвойте атрибуту `mode` значение `Message`, `Transport` или `TransportWithMessageCredential`.

4. Если задан режим `Transport`, добавьте элемент `<transport>` и присвойте атрибуту `clientCredential` соответствующее значение.

     В следующем примере задается режим "`Transport"`, а затем атрибуту `clientCredentialType` элемента `<transport>` присваивается значение "`Windows"`.

    ```xml
    <wsHttpBinding>
    <binding name="TransportSecurity">
        <security mode="Transport" >
           <transport clientCredentialType = "Windows" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     Можно также задать для атрибута `security mode` значение "`Message"`, а затем указать элемент `<"message">`. В этом примере атрибуту `clientCredentialType` присваивается значение "`Certificate"`.

    ```xml
    <wsHttpBinding>
    <binding name="MessageSecurity">
        <security mode="Message" >
           <message clientCredentialType = "Certificate" />
        </security>
    </binding>
    </wsHttpBinding >
    ```

     Значение <xref:System.ServiceModel.BasicHttpSecurityMode.TransportWithMessageCredential> используется в особых случаях; подробнее см. ниже.

### <a name="using-transportwithmessagecredential"></a>Использование режима TransportWithMessageCredential

При задании режима безопасности`TransportWithMessageCredential` транспорт определяет фактический механизм, обеспечивающий безопасность на транспортном уровне. Например, протокол HTTP использует SSL по HTTP (HTTPS). Поэтому задание свойства `ClientCredentialType` любого объекта безопасности транспорта (такого как <xref:System.ServiceModel.HttpTransportSecurity>) игнорируется.  Другими словами, можно задать только свойство `ClientCredentialType` объекта безопасности сообщения (для привязки `WSHttpBinding` это объект <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>).

Дополнительные сведения см. [в разделе как использовать безопасность транспорта и учетные данные сообщений](./feature-details/how-to-use-transport-security-and-message-credentials.md).

## <a name="see-also"></a>См. также:

- [Практическое руководство. Настройка порта с использованием SSL-сертификата](./feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)
- [Практическое руководство. Использование средств обеспечения безопасности транспорта и учетных данных сообщения](./feature-details/how-to-use-transport-security-and-message-credentials.md)
- [Безопасность транспорта](./feature-details/transport-security.md)
- [Безопасность сообщений](./feature-details/message-security-in-wcf.md)
- [Общие сведения о безопасности](./feature-details/security-overview.md)
- [Привязки, предоставляемые системой](system-provided-bindings.md)
- [\<> безопасности](../configure-apps/file-schema/wcf/security-of-wshttpbinding.md)
- [\<> безопасности](../configure-apps/file-schema/wcf/security-of-basichttpbinding.md)
- [\<> безопасности](../configure-apps/file-schema/wcf/security-of-nettcpbinding.md)
