---
title: "&lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# &lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt;
Задает параметры службы безопасного обмена данными.  
  
## Синтаксис  
  
```  
  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`securityStateEncoderType`|Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<serviceCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## Заметки  
 Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности \(SCT\), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.  Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>   
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>   
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>