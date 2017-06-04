---
title: "Практическое руководство. Создание сеанса безопасности | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "безопасность [WCF], создание сеанса"
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# Практическое руководство. Создание сеанса безопасности
В [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] все предоставляемые системой привязки, за исключением привязки [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), автоматически используют безопасные сеансы при включенной безопасности сообщений.  
  
 По умолчанию безопасные сеансы не сохраняются на перезапускаемом веб\-сервере.  После установления безопасного сеанса клиент и служба кэшируют ключ, связанный с безопасным сеансом.  При обмене сообщениями происходит только обмен идентификатором кэшированного ключа.  При перезапуске веб\-сервера кэш также перезапускается, следовательно, веб\-сервер не может извлечь кэшированный ключ для идентификатора.  В этом случае исключение передается назад клиенту.  Безопасные сеансы, использующие токен контекста безопасности с отслеживанием состояния \(SCT\), сохраняются при перезапуске веб\-сервера.  [!INCLUDE[crabout](../../../../includes/crabout-md.md)] использовании токенов SCT с отслеживанием состояния в безопасном сеансе см. в разделе [Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).  
  
### Задание использования службой безопасных сеансов с помощью одной из предоставляемых системой привязок  
  
-   Настройте службу на использование предоставляемой системой привязки, поддерживающей безопасность сообщений.  
  
     Если предоставляемые системой привязки настроены на использование безопасности сообщений \(за исключением привязки [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)\), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] автоматически использует безопасные сеансы.  В следующей таблице перечислены предоставляемые системой привязки, поддерживающие безопасность сообщений, и указано, является ли безопасность сообщений механизмом безопасности по умолчанию для данной привязки.  
  
    |Предоставляемая системой привязка|Элемент конфигурации|Безопасность сообщений включена по умолчанию|  
    |---------------------------------------|--------------------------|--------------------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Нет|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Да|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Да|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Да|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Нет|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Нет|  
  
     В следующем примере кода с помощью конфигурации задается привязка с именем `wsHttpBinding_Calculator`, использующая элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), безопасность сообщений и безопасные сеансы.  
  
    ```  
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
  
     В следующем примере кода задается, что для обеспечения безопасности службы `secureCalculator` используются элемент [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), безопасность сообщений и безопасные сеансы.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  Безопасные сеансы для элемента [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) можно отключить, задав атрибуту `establishSecurityContext` значение `false`.  Безопасные сеансы для других предоставляемых системой привязок можно отключить, только создав пользовательскую привязку.  
  
### Задание использования службой безопасных сеансов с помощью пользовательской привязки  
  
-   Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] создании пользовательской привязки см. в разделе [Практическое руководство. Изменение привязки, предоставляемой системой](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).  
  
     В следующем примере кода с помощью конфигурации задается пользовательская привязка для обмена сообщениями с использованием безопасного сеанса.  
  
    ```  
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
  
     В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode> для начальной загрузки безопасного сеанса.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## См. также  
 [Общие сведения о привязках WCF](../../../../docs/framework/wcf/bindings-overview.md)