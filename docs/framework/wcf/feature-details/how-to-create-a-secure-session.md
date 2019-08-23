---
title: Практическое руководство. Создание сеанса безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: bdb0f89b950d086e04cbb9d6da161bd315fc64b3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934384"
---
# <a name="how-to-create-a-secure-session"></a>Практическое руководство. Создание сеанса безопасности
За исключением [ \<привязки > BasicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , предоставляемые системой привязки в Windows Communication Foundation (WCF) автоматически используют защищенные сеансы при включенной безопасности сообщений.  
  
 По умолчанию безопасные сеансы не сохраняются на перезапускаемом веб-сервере. После установления безопасного сеанса клиент и служба кэшируют ключ, связанный с безопасным сеансом. При обмене сообщениями происходит только обмен идентификатором кэшированного ключа. При перезапуске веб-сервера кэш также перезапускается, следовательно, веб-сервер не может извлечь кэшированный ключ для идентификатора. В этом случае исключение передается назад клиенту. Безопасные сеансы, использующие токен контекста безопасности с отслеживанием состояния (SCT), сохраняются при перезапуске веб-сервера. Дополнительные сведения об использовании SCT с отслеживанием состояния в безопасном сеансе см [. в разделе как Создайте маркер контекста безопасности для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a>Задание использования службой безопасных сеансов с помощью одной из предоставляемых системой привязок  
  
- Настройте службу на использование предоставляемой системой привязки, поддерживающей безопасность сообщений.  
  
     За исключением [ \<привязки > BasicHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) , когда предоставляемые системой привязки настроены для использования безопасности сообщений, WCF автоматически использует защищенные сеансы. В следующей таблице перечислены предоставляемые системой привязки, поддерживающие безопасность сообщений, и указано, является ли безопасность сообщений механизмом безопасности по умолчанию для данной привязки.  
  
    |Предоставляемая системой привязка|Элемент конфигурации|Безопасность сообщений включена по умолчанию|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Нет|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Да|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Да|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Да|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Нет|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Нет|  
  
     В следующем примере кода используется конфигурация для указания привязки с именем `wsHttpBinding_Calculator` , которая [ \<использует > WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), безопасность сообщений и защищенные сеансы.  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     В следующем примере кода указывается, `secureCalculator` что [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)для защиты службы используются > WSHttpBinding, безопасность сообщений и безопасные сеансы.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > Защищенные сеансы можно отключить для [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) , задав `establishSecurityContext` для `false`атрибута значение. Безопасные сеансы для других предоставляемых системой привязок можно отключить, только создав пользовательскую привязку.  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a>Задание использования службой безопасных сеансов с помощью пользовательской привязки  
  
- Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом.  
  
     Дополнительные сведения о создании пользовательской привязки см. в разделе [как Настройка привязки](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md), предоставляемой системой.  
  
     В следующем примере кода с помощью конфигурации задается пользовательская привязка для обмена сообщениями с использованием безопасного сеанса.  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязках WCF](../../../../docs/framework/wcf/bindings-overview.md)
