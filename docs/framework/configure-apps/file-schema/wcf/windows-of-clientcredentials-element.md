---
title: "&lt;windows&gt; элемента &lt;clientCredentials&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 793e41c2-31ea-4159-abbc-2123bf097233
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# &lt;windows&gt; элемента &lt;clientCredentials&gt;
Определяет параметры учетных данных Windows, которые используются для представления клиента.  
  
## Синтаксис  
  
```  
  
<windows   
    allowedImpersonationLevel="Identification/Impersonation/Delegation/Anonymous/None"  
        allowNtlm="Boolean"  
/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`allowedImpersonationLevel`|Задает параметры олицетворения, сообщаемые клиентом серверу.  Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.  Допустимы следующие значения:<br /><br /> -   Identification: сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиент.<br />-   Impersonation: сервер может олицетворять контекст безопасности клиента в локальной системе.<br />-   Delegation: сервер может олицетворять контекст безопасности клиента в удаленных системах.<br />-   Anonymous: сервер не может олицетворять или идентифицировать клиента.<br />-   None: уровень олицетворения не назначается.<br /><br /> Значение по умолчанию \- Identification.  Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.|  
|`allowNtlm`|Если установить для данного свойства значение `true`, то проверка подлинности может понижаться до NTLM в том случае, если проверка Kerberos недоступна.<br /><br /> Если установить для данного свойства значение `false`, это приведет к тому, что [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] будет принимать все возможные усилия для вызова исключения в том случае, если используется NTLM.  Обратите внимание, что установка для данного свойства значения `false` не предотвращает отправки учетных данных NTLM по сети.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WindowsClientElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Windows%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.Windows%2A>   
 <xref:System.ServiceModel.Security.WindowsClientCredential>   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)