---
title: <serviceCertificate> элемента <clientCredentials>
ms.date: 03/30/2017
ms.assetid: e50c0ac5-f0df-4c90-b54b-fc602c1f84ea
ms.openlocfilehash: 4fe196ef8737c7abde939e36c2bb7afd5a0d86b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61670304"
---
# <a name="servicecertificate-of-clientcredentials-element"></a>\<serviceCertificate > элемента \<clientCredentials > элемент
Задает сертификат для использования при проверке подлинности службы для клиента.  
  
 \<system.ServiceModel>  
\<варианты поведения >  
\<endpointBehaviors>  
\<поведение >  
\<clientCredentials>  
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
|[\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-servicecertificate-element.md)|Задает поведение проверки подлинности для сертификатов служб, используемых клиентом.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<clientCredentials>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Задает учетные данные, используемые клиентом для подтверждения своей подлинности при подключении к службе.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент конфигурации содержит параметры, используемые клиентом для проверки сертификата, представленного службой с помощью проверки подлинности SSL. Он также содержит сертификат для службы, который явно задан в клиенте для шифрования сообщений для службы с помощью безопасности сообщений.  
  
 Атрибуты `serviceCertificate` идентичны атрибуты [ \<clientCertificate >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.ServiceCertificate%2A>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Description.ClientCredentials.ServiceCertificate%2A>
- <xref:System.ServiceModel.Configuration.X509RecipientCertificateClientElement>
- <xref:System.ServiceModel.Security.X509CertificateRecipientClientCredential>
- [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)
- [Защита клиентов](../../../../../docs/framework/wcf/securing-clients.md)
- [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
