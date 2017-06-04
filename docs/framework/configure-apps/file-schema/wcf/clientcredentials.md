---
title: "&lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1e6eef0d-a34e-4d74-b0f7-f65d2181858d
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;clientCredentials&gt;
Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.  
  
## Синтаксис  
  
```  
  
<clientCredentials type="String"  
      supportInteractive="Boolean" >  
   <clientCertificate>  
   </clientCertificate>  
   <digest>  
   </digest>  
   <isuedToken>  
   </isuedToken>  
   <peer>  
   </peer>  
   <serviceCertificate>  
   </serviceCertificate>  
   <windowsAuthentication>  
   </windowsAuthentication>  
</clientCredentials>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`supportInteractive`|Логическое значение, которое указывает, может ли текущий пользователь принимать участие в выборе учетных данных клиента во время выполнения.  Значение по умолчанию — `true`.|  
|`type`|Строка, задающая тип данного элемента конфигурации.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)|Задает сертификат, используемый для проверки подлинности клиента при подключении к службе.  Это элемент типа <xref:System.ServiceModel.Configuration.X509InitiatorCertificateClientElement>.|  
|[\<httpDigest\>](../../../../../docs/framework/configure-apps/file-schema/wcf/httpdigest-element.md)|Задает хэш, используемый для проверки подлинности клиента при подключении к службе.  Это элемент типа <xref:System.ServiceModel.Configuration.HttpDigestClientElement>.|  
|[\<issuedToken\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtoken.md)|Задает тип пользовательского маркера, используемого для проверки подлинности клиента при подключении к службе маркеров безопасности \(STS\).  Это элемент типа <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>.|  
|[\<peer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/peer-of-clientcredentials-element.md)|Задает учетные данные текущего однорангового узла.  Это элемент типа <xref:System.ServiceModel.Configuration.PeerCredentialElement>.|  
|[\<serviceCertificate\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md)|Задает сертификат, используемый при проверки подлинности службы для клиента, и предоставляет структуру для настройки параметров сертификата.  Данный сертификат должен быть предоставлен вне диапазона службой клиенту.  Это элемент типа <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>.|  
|[\<окна\>](../../../../../docs/framework/configure-apps/file-schema/wcf/windows-of-clientcredentials-element.md)|Задает учетные данные Windows.  Значением по умолчанию являются учетные данные текущего потока.  Это элемент типа <xref:System.ServiceModel.Configuration.WindowsClientElement>.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## Заметки  
 Учетные данные клиента используются для проверки подлинности клиента при подключении к службам в случаях, когда требуется взаимная проверка подлинности.  Данный раздел конфигурации также можно использовать для задания сертификатов служб для сценариев, где клиент должен обеспечить защиту сообщений, передаваемых службе, с помощью сертификатов службы.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)