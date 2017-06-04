---
title: "&lt;message&gt; для &lt;netMsmqBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6ebf0240-d7be-4493-b0fe-f00fd5989d77
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;message&gt; для &lt;netMsmqBinding&gt;
Определяет параметры безопасности сообщений SOAP для данной привязки `netMsmqBinding`.  
  
## Синтаксис  
  
```  
  
<netMsmqBinding>  
    <binding>  
      <security>  
         <message   
                      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
            clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />  
    </security>  
</netMsmqBinding>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|algorithmSuite|Задает алгоритмы шифрования сообщений и ключей, которые используются для обеспечения безопасности на уровне сообщений для сообщений, которые отправляются с помощью транспорта MSMQ.<br /><br /> Значение по умолчанию — `Aes256`.  Это атрибут типа <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|clientCredentialType|Задает тип учетных данных, используемых при проверке подлинности клиента для сообщений, которые отправляются с помощью транспорта MSMQ.  Допустимы следующие значения:<br /><br /> -   None: данное значение позволяет службе взаимодействовать с анонимными клиентами.  Как для службы, так и для клиента учетные данные не требуются.<br />-   Windows: данное значение позволяет проводить обмен сообщениями SOAP, если выполнена проверка подлинности с помощью учетных данных Windows.  В этом случае всегда выполняется проверка подлинности на основе Kerberos.<br />-   UserName: данное значение позволяет службе запрашивать проверку подлинности клиента на основе учетных данных UserName.  В этом случае учетные данные должны быть определены с помощью поведения `clientCredentials`. **Caution:**  [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] не поддерживает передачу дайджеста пароля или получение ключей с использованием пароля и использование таких ключей для обеспечения безопасности сообщений.  Таким образом, служба [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] принудительно обеспечивает безопасность обмена при использовании учетных данных UserName.  В данном режиме требуется, чтобы сертификат службы был указан на стороне клиента при помощи поведения `clientCredential` и при помощи `serviceCertificate`. <br /><br /> -   Certificate: данное значение позволяет службе требовать проверки подлинности клиента с помощью сертификата.  В этом случае учетные данные клиента должны быть определены с помощью поведения `clientCredentials`.  Учетные данные службы в данном случае должны быть определены с помощью поведения `clientCredentials`, которому задается значение `serviceCertificate`.<br />-   CardSpace: данное значение позволяет службе требовать проверки подлинности клиента с помощью CardSpace.  Необходимо определить `serviceCertiifcate` в поведении `clientCredential`.<br /><br /> Значение по умолчанию — `Windows`.  Это атрибут типа <xref:System.ServiceModel.MessageCredentialType>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<безопасность\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netmsmqbinding.md)|Определяет параметры безопасности для привязки.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>   
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetMsmqSecurity.Message%2A>   
 <xref:System.ServiceModel.MessageSecurityOverMsmq>   
 [Очереди в WCF](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/ru-ru/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<привязка\>](../../../../../docs/framework/misc/binding.md)