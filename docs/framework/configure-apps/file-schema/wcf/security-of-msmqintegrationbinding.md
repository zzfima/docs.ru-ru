---
title: "&lt;security&gt; для &lt;msmqIntegrationBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# &lt;security&gt; для &lt;msmqIntegrationBinding&gt;
Определяет параметры безопасности транспорта для канала интеграции очереди сообщений \(MSMQ\).  
  
## Синтаксис  
  
```  
  
<msmqIntegrationBinding>  
   <binding>   
       <security mode="None/Transport">  
         <transport msmqAuthenticationMode="None/Windows/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
          <message  algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"  
                        clientCredentialType="None/Windows/UserName/Certificate/CardSpace"  
            defaultProtectionLevel="None/Sign/EncryptAndSign" />  
       </security>  
   </binding>  
</msmqIntegrationBinding>   
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|Задает тип системы безопасности, отвечающей за целостность, конфиденциальность и проверку подлинности при использовании канала интеграции очереди сообщений.  Допустимы следующие значения:<br /><br /> -   None: режим безопасности отключен.<br />-   Transport: защита и проверка подлинности обеспечиваются транспортом.  Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.  Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.  Существующие Msmq\-приложения функционально равноценны такому режиму безопасности.<br /><br /> Значение по умолчанию — `Transport`.  Это атрибут типа <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-msmqintegrationbinding.md)|Определяет параметры безопасности для транспорта интеграции очереди сообщений.  Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Элемент привязки [\<msmqIntegrationBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)   
 [\<msmqIntegrationBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)