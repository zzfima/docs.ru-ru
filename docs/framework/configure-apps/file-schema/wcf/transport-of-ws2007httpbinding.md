---
title: "&lt;transport&gt; для &lt;ws2007HttpBinding&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 31c5404b29f025af5193386eccafdbeab95cb2cf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltws2007httpbindinggt"></a>&lt;transport&gt; для &lt;ws2007HttpBinding&gt;
Определяет параметры проверки подлинности для HTTP-транспорта.  
  
 \<system.serviceModel >  
\<привязки >  
\<ws2007HttpBinding >  
\<Привязка >  
\<Безопасность >  
\<Транспорт >  
  
## <a name="syntax"></a>Синтаксис  
  
```  
transport clientCredentialType =   
       "Basic/Certificate/Digest/None/Ntlm/Windows"  
       proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
       realm="string"   
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Безопасность >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-ws2007httpbinding.md)|Представляет функциональные возможности безопасности [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) элемента.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>  
 [Защита служб и клиентов](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Привязки](../../../../../docs/framework/wcf/bindings.md)  
 [Настройка привязок, предоставляемых системой](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Использование привязок для настройки служб Windows Communication Foundation и клиентов](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Привязка >](../../../../../docs/framework/misc/binding.md)
