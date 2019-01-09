---
title: '&lt;clientCertificate&gt; для &lt;serviceCredentials&gt;'
ms.date: 03/30/2017
ms.assetid: 90ad03aa-2317-43dd-8a72-6d24cdcad15c
ms.openlocfilehash: 7f777fd0e09a1bb9491f346a8e9806627aa63441
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145501"
---
# <a name="ltclientcertificategt-of-ltservicecredentialsgt"></a>&lt;clientCertificate&gt; для &lt;serviceCredentials&gt;
Задает файл сертификата X.509, используемый для подписания и шифрования сообщений к клиенту от службы при дуплексном обмене данными.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<serviceBehaviors >  
\<serviceBehaviors >  
\<поведение >  
\<serviceCredentials >  
\<clientCertificate >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clientCertificate>
  <certificate />
  <authentication />
</clientCertificate>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<authentication>](../../../../../docs/framework/configure-apps/file-schema/wcf/authentication-of-clientcertificate-element.md)|Задает параметры проверки подлинности для сертификата клиента.|  
|[\<сертификат >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-of-clientcertificate-element.md)|Задает тип сертификата для использования.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<serviceCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.|  
  
## <a name="remarks"></a>Примечания  
 Этот элемент используется в случаях, когда служба должна получить клиентский сертификат заранее для безопасного обмена данными с клиентом. Это характерно для дуплексного обмена данными. В более распространенном варианте «запрос/отклик» клиент включает сертификат в запрос, который используется службой для шифрования и подписания отклика. Тем не менее при дуплексном обмене данными служба не получает запроса от клиента, и ей, таким образом, необходим сертификат клиента заранее, чтобы обеспечить защиту сообщения, отправляемого клиенту. Следовательно, необходимо получить сертификат клиента при согласовании вне диапазона и указать сертификат с помощью этого элемента. Дополнительные сведения о дуплексных службах см. в разделе [как: Создание дуплексного контракта](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md).  
  
 Заданный в этом элементе сертификат используется для шифрования сообщений к клиенту только для привязок, которые настроены с использованием режима проверки подлинности `MutualCertificateDuplex`.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.ClientCertificate%2A>  
 <xref:System.ServiceModel.Configuration.X509InitiatorCertificateServiceElement>  
 <xref:System.ServiceModel.Description.ServiceCredentials.ClientCertificate%2A>  
 <xref:System.ServiceModel.Security.X509CertificateInitiatorServiceCredential>  
 [Практическое руководство. Создание дуплексного контракта](../../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)
