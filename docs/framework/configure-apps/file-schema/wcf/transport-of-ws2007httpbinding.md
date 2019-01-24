---
title: '&lt;transport&gt; для &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 6f09a71a7ec7dbfae5eb6f1896f1fba68456973f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54642598"
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a>&lt;transport&gt; для &lt;ws2007HttpBinding&gt;
Определяет параметры проверки подлинности для HTTP-транспорта.  
  
 \<system.serviceModel>  
\<привязки >  
\<ws2007HttpBinding >  
\<Привязка >  
\<Безопасность >  
\<Транспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a>Тип  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`clientCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе. Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена. Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности. Значение по умолчанию - пустая строка.<br /><br /> Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности. Она также может указывать коллекцию пользователей, которым разрешен доступ. Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.|  
  
## <a name="clientcredentialtype-attribute"></a>Атрибут clientCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Режим безопасности отключен.|  
|Basic|Используется обычная проверка подлинности.|  
|Digest|Используется дайджест-проверка подлинности.|  
|Ntlm|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|Windows|Используется встроенная проверка подлинности Windows.|  
|Сертификат|Для проверки подлинности клиента используются сертификаты X.509.|  
  
## <a name="proxycredentialtype-attribute"></a>Атрибут proxyCredentialType  
  
|Значение|Описание|  
|-----------|-----------------|  
|Нет|Режим безопасности отключен.|  
|Basic|Используется обычная проверка подлинности.|  
|Digest|Используется дайджест-проверка подлинности.|  
|Ntlm|Используется проверка подлинности NTLM в качестве резервной в домене Windows.|  
|Windows|Используется встроенная проверка подлинности Windows.|  
|Сертификат|Для проверки подлинности клиента используются сертификаты X.509.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Представляет возможности безопасности [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемент.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Привязки](../../../../../docs/framework/wcf/bindings.md)
- [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [Использование привязок для настройки служб и клиентов](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [\<Привязка >](../../../../../docs/framework/misc/binding.md)
