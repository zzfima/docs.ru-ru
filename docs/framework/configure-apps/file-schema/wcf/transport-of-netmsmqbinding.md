---
title: "&lt;transport&gt; для &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 72e1b338-39f0-4af1-a5d9-7a2fb79f6a0b
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;transport&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности транспорта.  
  
## Синтаксис  
  
```  
  
<netMsmqBinding>  
    <binding>  
    <security>  
         <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
            msmqEncryptionAlgorithm="RC4Stream/AES"  
            msmqProtectionLevel="None/Sign/EncryptAndSign"  
            msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
    </security>  
   </binding>  
</netMsmqBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|msmqAuthenticationMode|Задает способ проверки подлинности сообщения транспортом MSMQ.  Допустимы следующие значения:<br /><br /> -   None: проверка подлинности не используется.<br />-   WindowsDomain: механизм проверки подлинности использует Active Directory с целью получить сертификат X.509 для идентификатора безопасности, связанного с сообщением.  Затем он используется для проверки списка управления доступом для очереди с целью удостовериться, что пользователь имеет разрешение на запись в очередь.<br />-   Certificate: канал извлекает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию — `WindowsDomain`.<br /><br /> Если данный атрибут имеет значение `None`, то атрибут `msmqProtectionLevel` также должен иметь значение `None`.  Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|msmqEncryptionAlgorithm|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.  Допустимы следующие значения:<br /><br /> -   RC4Stream<br />-   AES<br />-   Значение по умолчанию — `RC4Stream`.  Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|msmqprotectionLevel|Задает способ обеспечения безопасности сообщений на уровне транспорта MSMQ.  Шифрование обеспечивает целостность сообщения, тогда как подпись и шифрование обеспечивают как целостность сообщения, так и неподдельность.  Это гарантирует, что сообщение действительно поступило от отправителя, и отправитель действительно является тем, за кого он себя выдает.  Допустимы следующие значения:<br /><br /> -   None: не защищено.<br />-   Sign: сообщения подписываются.<br />-   EncryptAndSign: сообщения шифруются и подписываются.<br />-   Значение по умолчанию — `Sign`.|  
|msmqSecureHashAlgorithm|Указывает алгоритм хэширования, который будет использоваться при вычислении дайджеста сообщения.  Допустимы следующие значения:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Значение по умолчанию — `SHA1`.  Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Определяет параметры безопасности для поставленного в очередь транспорта.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Transport%2A>   
 <xref:System.ServiceModel.MsmqTransportSecurity>   
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)