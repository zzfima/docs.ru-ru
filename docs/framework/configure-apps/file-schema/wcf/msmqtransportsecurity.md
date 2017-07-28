---
title: "&lt;msmqTransportSecurity&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 092e911b-ab1b-4069-a26e-6134c3299e06
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# &lt;msmqTransportSecurity&gt;
Задает параметры безопасности транспорта MSMQ для пользовательской привязки.  
  
## Синтаксис  
  
```  
  
<msmqTransportSecurity>  
   msmqAuthenticationMode="None/Windows/Certificate"  
   msmqEncryptionAlgorithm="RC4Stream/AES"  
   msmqProtectionLevel="None/Sign/EncryptAndSign"  
   msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</msmqTransportSecurity>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ.  Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимы следующие значения:<br /><br /> -   None: проверка подлинности не используется.<br />-   Windows: механизм проверки подлинности использует Active Directory для получения сертификата X.509 для SID, связанного с сообщением.  Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />-   Certificate: канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию \- Windows.  Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.  Допустимы следующие значения:<br /><br /> -   RC4Stream<br />-   AES<br /><br /> Значение по умолчанию \- RC4Stream.  Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ.  Шифрование обеспечивает целостность сообщения, а EncryptAndSign \- целостность и неотрекаемость сообщения; то есть гарантируется, что сообщение на самом деле поступает от отправителя, и отправитель действительно является тем, кем называет себя.  Допустимы следующие значения:<br /><br /> -   None: не защищено.<br />-   Sign: сообщения подписываются.<br />-   EncryptAndSign: сообщения шифруются и подписываются.<br /><br /> Значение по умолчанию \- Sign.  Это атрибут типа <xref:System.Net.Security.ProtectionLevel>.|  
|`msmqSecureHashAlgorithm`|Задает алгоритм, который должен использоваться при вычислении дайджеста как части сигнатур.  Допустимы следующие значения:<br /><br /> -   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Значение по умолчанию \- SHA1.  Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<msmqIntegration\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegration.md)|Задает параметры, необходимые для взаимодействия с отправителем или получателем очереди сообщений \(MSMQ\).|  
|[\<msmqTransport\>](../../../../../docs/framework/configure-apps/file-schema/wcf/msmqtransport.md)|Задает свойства обмена данными в очереди для службы Windows Communication Foundation \(WCF\), использующей собственный протокол MSMQ.|  
  
## Заметки  
 Дополнительные сведения о безопасности транспорта см. в разделе [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md).  
  
## См. также  
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>   
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Транспорты](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Выбор транспортов](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Безопасность транспорта](../../../../../docs/framework/wcf/feature-details/transport-security.md)