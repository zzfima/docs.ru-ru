---
title: "&lt;security&gt; для &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# &lt;security&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности для привязки MSMQ.  Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.  
  
## Синтаксис  
  
```  
  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|режим|Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.  Допустимы следующие значения:<br /><br /> -   None: режим безопасности отключен.<br />-   Transport: защита и проверка подлинности обеспечиваются транспортом.  Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.  Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.  Существующие Msmq\-приложения функционально равноценны такому режиму безопасности.<br />-   Message: задает параметры сквозной безопасности приложения.  Безопасность на транспортном уровне не предоставляется.  Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.<br />-   Both: безопасность предоставляется на уровне транспорта и обмена сообщениями SOAP.  На обоих уровнях требуются одни и те же учетные данные.<br /><br /> Значение по умолчанию \- Transport.  Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<сообщение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|Определяет параметры безопасности сообщений SOAP.  Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<транспорт\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|Определяет параметры безопасности для транспорта MSMQ.  Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|привязка|Элемент привязки [\<netMsmqBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md).|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>   
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>   
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)   
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)