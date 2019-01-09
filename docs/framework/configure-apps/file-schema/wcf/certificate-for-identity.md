---
title: '&lt;certificate&gt; для &lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 0b65157aea84760f3e52bc294f7559967fc308f1
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146918"
---
# <a name="ltcertificategt-for-ltidentitygt"></a>&lt;certificate&gt; для &lt;identity&gt;
Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.  
  
 Дополнительные сведения о настройке значения элемента см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<удостоверение >  
\<сертификат >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|encodedValue|Кодировка Base64 сертификата.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="example"></a>Пример  
 В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.EndpointIdentity>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
