---
title: "Как задать режим безопасности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "свойство Mode"
  - "WCF, безопасность"
  - "WCF, режим безопасности"
ms.assetid: 6e01dd9f-b5dd-4474-b24c-06e124de4ff7
caps.latest.revision: 22
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 22
---
# Как задать режим безопасности
В механизме безопасности [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] предусмотрено три наиболее распространенных режима безопасности, которые используются в большинстве предварительно определенных привязок: транспорт, сообщение, и "транспорт с учетными данными сообщения". Два дополнительных режима характерны для двух привязок: режим "Только учетные данные транспорта", используемый в <xref:System.ServiceModel.BasicHttpBinding>, режим "Оба", используемый в <xref:System.ServiceModel.NetMsmqBinding>.Однако в этом разделе основное внимание уделяется трем наиболее распространенным режимам безопасности: <xref:System.ServiceModel.SecurityMode>, <xref:System.ServiceModel.SecurityMode> и <xref:System.ServiceModel.SecurityMode>.  
  
 Обратите внимание, что не все предварительно определенные привязки поддерживают все указанные режимы.В этом разделе режим задается с помощью классов <xref:System.ServiceModel.WSHttpBinding> и <xref:System.ServiceModel.NetTcpBinding>; также в этом разделе показан порядок задания режима как программно, так и с помощью конфигурации.  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)] [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] о безопасности см. в разделах [Общие сведения о безопасности](../../../docs/framework/wcf/feature-details/security-overview.md)[Защита служб](../../../docs/framework/wcf/securing-services.md) и [Защита служб и клиентов](../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).[!INCLUDE[crabout](../../../includes/crabout-md.md)] режиме транспорта и сообщений см. в разделах [Безопасность транспорта](../../../docs/framework/wcf/feature-details/transport-security.md) и [Безопасность обмена сообщениями](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md).  
  
### Задание режима безопасности в коде  
  
1.  Создайте экземпляр используемого класса привязки.Список предварительно определенных привязок см. в разделе [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md).В данном примере создается экземпляр класса <xref:System.ServiceModel.WSHttpBinding>.  
  
2.  Задайте свойство `Mode` объекта, возвращаемого свойством `Security`.  
  
     [!code-csharp[c_SettingSecurityMode#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#1)]
     [!code-vb[c_SettingSecurityMode#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#1)]  
  
     Или задайте режим "сообщение", как показано в следующем примере кода.  
  
     [!code-csharp[c_SettingSecurityMode#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#2)]
     [!code-vb[c_SettingSecurityMode#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#2)]  
  
     Или задайте режим "транспорт с учетными данными сообщения", как показано в следующем примере кода.  
  
     [!code-csharp[c_SettingSecurityMode#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#3)]
     [!code-vb[c_SettingSecurityMode#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#3)]  
  
3.  Также можно задать режим в конструкторе привязки, как показано в следующем примере кода.  
  
     [!code-csharp[c_SettingSecurityMode#4](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#4)]
     [!code-vb[c_SettingSecurityMode#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#4)]  
  
## Задание свойства ClientCredentialType  
 Задание одного из трех значений режима определяет способ задания свойства `ClientCredentialType`.Например, при использовании класса <xref:System.ServiceModel.WSHttpBinding> задание режима `Transport` означает, что необходимо присвоить свойству <xref:System.ServiceModel.HttpTransportSecurity.ClientCredentialType%2A> класса <xref:System.ServiceModel.HttpTransportSecurity> соответствующее значение.  
  
#### Задание свойства ClientCredentialType для режима Transport  
  
1.  Создайте экземпляр привязки.  
  
2.  Задайте для свойства `Mode` значение `Transport`.  
  
3.  Присвойте свойству `ClientCredential` соответствующее значение.В следующем примере кода показано, как присвоить свойству значение `Windows`.  
  
     [!code-csharp[c_SettingSecurityMode#5](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#5)]
     [!code-vb[c_SettingSecurityMode#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#5)]  
  
#### Задание свойства ClientCredentialType для режима Message  
  
1.  Создайте экземпляр привязки.  
  
2.  Задайте для свойства `Mode` значение `Message`.  
  
3.  Присвойте свойству `ClientCredential` соответствующее значение.В следующем примере кода показано, как присвоить свойству значение `Certificate`.  
  
     [!code-csharp[c_SettingSecurityMode#6](../../../samples/snippets/csharp/VS_Snippets_CFX/c_settingsecuritymode/cs/source.cs#6)]
     [!code-vb[c_SettingSecurityMode#6](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_settingsecuritymode/vb/source.vb#6)]  
  
#### Задание режима и свойства ClientCredentialType в конфигурации  
  
1.  Добавьте соответствующий элемент привязки в элемент [\<привязки\>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) файла конфигурации.В следующем примере добавляется элемент [\<wsHttpBinding\>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).  
  
2.  Добавьте элемент `<binding>` и присвойте его атрибуту `name` соответствующее значение.  
  
3.  Добавьте элемент `<security>` и присвойте атрибуту `mode` значение `Message`, `Transport` или `TransportWithMessageCredential`.  
  
4.  Если задан режим `Transport`, добавьте элемент `<transport>` и присвойте атрибуту `clientCredential` соответствующее значение.  
  
     В следующем примере задается режим "`Transport"`, а затем атрибуту `clientCredentialType` элемента `<transport>` присваивается значение "`Windows"`.  
  
    ```  
    <wsHttpBinding>  
    <binding name="TransportSecurity">  
        <security mode="Transport" />  
           <transport clientCredentialType = "Windows" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     Можно также задать для атрибута `security mode` значение "`Message"`, а затем указать элемент `<"message">`.В этом примере атрибуту `clientCredentialType` присваивается значение "`Certificate"`.  
  
    ```  
    <wsHttpBinding>  
    <binding name="MessageSecurity">  
        <security mode="Message" />  
           <message clientCredentialType = "Certificate" />  
        </security>  
    </binding>  
    </wsHttpBinding >  
    ```  
  
     Значение <xref:System.ServiceModel.BasicHttpSecurityMode> используется в особых случаях; подробнее см. ниже.  
  
### Использование режима TransportWithMessageCredential  
 При задании режима безопасности`TransportWithMessageCredential` транспорт определяет фактический механизм, обеспечивающий безопасность на транспортном уровне.Например, протокол HTTP использует SSL по HTTP \(HTTPS\).Поэтому задание свойства `ClientCredentialType` любого объекта безопасности транспорта \(такого как <xref:System.ServiceModel.HttpTransportSecurity>\) игнорируется.Другими словами, вы можете задать только свойство `ClientCredentialType` объекта безопасности сообщения \(для привязки `WSHttpBinding` это объект <xref:System.ServiceModel.NonDualMessageSecurityOverHttp>\).  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)] [Как использовать средства обеспечения безопасности транспорта и учетные данные сообщения](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md).  
  
## См. также  
 [Практическое руководство. Настройка порта с использованием SSL\-сертификата](../../../docs/framework/wcf/feature-details/how-to-configure-a-port-with-an-ssl-certificate.md)   
 [Как использовать средства обеспечения безопасности транспорта и учетные данные сообщения](../../../docs/framework/wcf/feature-details/how-to-use-transport-security-and-message-credentials.md)   
 [Безопасность транспорта](../../../docs/framework/wcf/feature-details/transport-security.md)   
 [Безопасность обмена сообщениями](../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)   
 [Общие сведения о безопасности](../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Привязки, предоставляемые системой](../../../docs/framework/wcf/system-provided-bindings.md)   
 [\<безопасность\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)   
 [\<безопасность\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)   
 [\<безопасность\>](../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)