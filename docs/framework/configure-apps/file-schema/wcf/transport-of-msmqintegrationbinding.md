---
title: "&lt;transport&gt; для &lt;msmqIntegrationBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 054579e3-7fdd-47df-99ca-952706ba5c8e
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# &lt;transport&gt; для &lt;msmqIntegrationBinding&gt;
Определяет параметры безопасности для транспорта интеграции очереди сообщений.  
  
## Синтаксис  
  
```  
  
<security>  
    <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
        msmqEncryptionAlgorithm="RC4Stream/AES"  
        msmqProtectionLevel="None/Sign/EncryptAndSign"  
        msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
</security>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`msmqAuthenticationMode`|Задает способ проверки подлинности сообщения транспортом MSMQ.  Если задано значение `None`, атрибуту `msmqProtectionLevel` также должно быть присвоено значение `None`.<br /><br /> Допустимы следующие значения:<br /><br /> -   None: проверка подлинности не используется.<br />-   WindowsDomain: механизм проверки подлинности использует Active Directory для получения сертификата X.509 для SID, связанного с сообщением.  Затем это используется для проверки ACL очереди, чтобы убедиться в наличии у пользователя разрешений для записи в очередь.<br />-   Certificate: канал получает сертификат из хранилища сертификатов.<br /><br /> Значение по умолчанию \- WindowsDomain.  Это атрибут типа <xref:System.ServiceModel.MsmqAuthenticationMode>.|  
|`msmqEncryptionAlgorithm`|Задает алгоритм, который будет использоваться для шифрования сообщений при их передаче между диспетчерами очередей сообщений.  Допустимы следующие значения:<br /><br /> -   RC4Stream<br />-   AES<br /><br /> Значение по умолчанию \- RC4Stream.  Это атрибут типа <xref:System.ServiceModel.MsmqEncryptionAlgorithm>.|  
|`msmqProtectionLevel`|Задает способ обеспечения безопасности сообщения на уровне транспорта MSMQ.  Шифрование обеспечивает целостность сообщения, а EncryptAndSign \- целостность и неотрекаемость сообщения; то есть гарантируется, что сообщение на самом деле поступает от отправителя, и отправитель действительно является тем, кем называет себя.<br /><br /> -   Допустимы следующие значения:<br />-   None: не защищено.<br />-   Sign: сообщения подписываются.<br />-   EncryptAndSign: сообщения шифруются и подписываются.<br /><br /> Значение по умолчанию \- Sign.  Это атрибут типа ProtectionLevel.|  
|`msmqSecureHashAlgorithm`|-   Задает алгоритм, который должен использоваться при вычислении дайджеста как части сигнатур.  Допустимы следующие значения:<br />-   MD5<br />-   SHA1<br />-   SHA256<br />-   SHA512<br /><br /> Значение по умолчанию \- SHA1.  Это атрибут типа <xref:System.ServiceModel.MsmqSecureHashAlgorithm>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Определяет параметры безопасности для привязки MSMQ.|  
  
## Заметки  
 Данный элемент инкапсулирует параметры безопасности для транспорта интеграции очереди сообщений.  Данные параметры одинаковы для интеграции очереди сообщений и использующих очереди транспортов.  Это позволяет задать режим проверки подлинности, алгоритм шифрования, алгоритм SHA и уровень защиты.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>   
 <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.MsmqTransportSecurity>   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)