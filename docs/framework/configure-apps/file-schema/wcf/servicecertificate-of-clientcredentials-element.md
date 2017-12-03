---
title: "&lt;serviceCertificate&gt; элемента &lt;clientCredentials&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3fbb3ef0fddd287fa3feb30732b26c651ac0067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltservicecertificategt-of-ltclientcredentialsgt-element"></a>&lt;serviceCertificate&gt; элемента &lt;clientCredentials&gt;
Задает сертификат для использования при проверке подлинности службы для клиента.  
  
 \<система. ServiceModel >  
\<поведения >  
\<endpointBehaviors >  
\<поведение >  
\<clientCredentials >  
\<serviceCertificate >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<serviceCertificate />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<defaultCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)|Задает сертификат X.509 для использования, когда служба или служба маркеров безопасности не предоставляет сертификат посредством протокола согласования.|  
|[\<scopedCertificates >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopedcertificates-element.md)|Представляет коллекцию сертификатов X.509, предоставленную конкретными службами (в области действия) для проверки подлинности. Эта коллекция обычно используется, чтобы задать сертификаты служб для служб маркеров безопасности в федеративной инфраструктуре.|  
|[\<Проверка подлинности >](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL. Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.  
  
 Атрибуты `serviceCertificate` идентичны элемент с атрибутами [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>  
 <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)  
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
