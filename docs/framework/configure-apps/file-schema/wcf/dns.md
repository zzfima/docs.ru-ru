---
title: '&lt;DNS&gt;'
ms.date: 03/30/2017
ms.assetid: 81819dae-4825-43b7-bccd-f16d2d3d2f06
ms.openlocfilehash: 6125bf157d04a1b0298a183465d11a18ac3786f0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltdnsgt"></a>&lt;DNS&gt;
Задает ожидаемое удостоверение сервера. Удостоверение является действительным для режима проверки подлинности сертификата X509, если сертификат сервера содержит DNS с тем же самым значением. Оно также действительно для режима проверки подлинности Windows, если SPN имеет такое же значение.  
  
 Дополнительные сведения о настройке значения элемента см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
 \<удостоверение >  
\<DNS >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<dns value = "String" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|value|Сервер DNS сертификата. Протокол DNS - это отраслевой протокол, используемый для нахождения компьютеров в сетях, использующих протокол IP. Пользователям проще запоминать отображаемые имена [ http://go.microsoft.com/fwlink/?prd=10929 ](http://go.microsoft.com/fwlink/?prd=10929) или [ http://go.microsoft.com/fwlink/?LinkID=96165 ](http://go.microsoft.com/fwlink/?LinkID=96165), проще, чем числовые адреса, например 207.46.131.137.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает удостоверение службы, подлинность которой должна быть проверена клиентом.|  
  
## <a name="example"></a>Пример  
 В следующем коде конфигурации задается значение сервера DNS сертификата X.509, используемого для проверки подлинности сервера.  
  
```xml  
<identity>  
  <dns value = "www.cohowinery.com" />  
</identity>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.DnsEndpointIdentity>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
