---
title: '&lt;issuer&gt; для &lt;issuedTokenParameters&gt;'
ms.date: 03/30/2017
ms.assetid: d6a95f32-d58c-40fc-8658-dd92564d3c90
ms.openlocfilehash: aa647f448bad74e25ffce4a5622c7489274996c7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151141"
---
# <a name="ltissuergt-of-ltissuedtokenparametersgt"></a>&lt;issuer&gt; для &lt;issuedTokenParameters&gt;
Задает службу маркеров безопасности, выдающую маркеры безопасности.  
  
 \<system.serviceModel >  
\<привязки >  
\<customBinding >  
\<Привязка >  
\<Безопасность >  
\<issuedTokenParameters >  
\<издатель >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<issuer address="Uri" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описываются атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|address|Обязательная строка. URL-адрес для службы маркеров безопасности.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<заголовки >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адресов для конечных точек, которые может создать конструктор.|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|При использовании выданного маркера задает параметры, позволяющие клиенту проверить подлинность сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Определяет текущий выданный маркер.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.AdditionalRequestParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Идентификация и проверка подлинности службы](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Возможности безопасности при использовании пользовательских привязок](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Федерация и выданные маркеры](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Безопасность пользовательской привязки](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
