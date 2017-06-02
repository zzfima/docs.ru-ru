---
title: "Элемент &lt;httpDigest&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Элемент &lt;httpDigest&gt;
Задает учетные данные, используемые для дайджест\-проверки подлинности клиента при подключении к службе.  
  
## Синтаксис  
  
```  
  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`impersonationLevel`|Задает параметры олицетворения, сообщаемые клиентом серверу.  Режим олицетворения, выбираемый клиентом, не задается принудительно для сервера.  Допустимы следующие значения:<br /><br /> -   Identification: сервер может получать удостоверение и привилегии клиента, но не может олицетворять клиент.<br />-   Impersonation: сервер может олицетворять контекст безопасности клиента в локальной системе.<br />-   Delegation: сервер может олицетворять контекст безопасности клиента в удаленных системах.<br />-   Anonymous: сервер не может олицетворять или идентифицировать клиента.<br />-   None: уровень олицетворения не назначается.<br /><br /> Значение по умолчанию \- Identification.  Это атрибут типа <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.|  
  
## Заметки  
 Дайджест \- это хэш, определяемый с помощью алгоритма и набора входных данных.  Структура проверки подлинности и проверяемый объект согласуют алгоритм и обмениваются данными, используемыми в качестве входных.  Клиент может вычислить хэш и отправить его службе.  Служба также вычисляет хэш и сравнивает значения.  Совпадение значений подтверждает подлинность клиента.  
  
 Эта функция должна быть включена с помощью Active Directory в Windows и службах IIS.  [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Дайджест\-проверка подлинности в IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>   
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>   
 <xref:System.ServiceModel.Description.ClientCredentials>   
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>   
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>   
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Обеспечение безопасности клиентов](../../../../../docs/framework/wcf/securing-clients.md)   
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)   
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)