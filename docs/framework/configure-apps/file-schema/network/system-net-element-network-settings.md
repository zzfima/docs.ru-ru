---
title: '&lt;system.Net&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f9098ce379cbaf12f589270729018da399f282b0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltsystemnetgt-element-network-settings"></a>&lt;system.Net&gt; элемент (параметры сети)
Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.  
  
 \<configuration>  
\<System.NET >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.net>   
</system.net>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[authenticationModules](../../../../../docs/framework/configure-apps/file-schema/network/authenticationmodules-element-network-settings.md)|Задает модули, используемые для проверки подлинности Интернет-запросов.|  
|[connectionManagement](../../../../../docs/framework/configure-apps/file-schema/network/connectionmanagement-element-network-settings.md)|Указывает максимальное число подключений к Интернет-узла.|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
|[mailSettings](../../../../../docs/framework/configure-apps/file-schema/network/mailsettings-element-network-settings.md)|Настраивает параметры отправки сообщений транспортного протокола SMTP (Simple Mail).|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|Определяет механизм кэширования для сетевых запросов.|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанные с ним дочерние пространства имен.|  
|[webRequestModules](../../../../../docs/framework/configure-apps/file-schema/network/webrequestmodules-element-network-settings.md)|Задает модули, используемые для запроса данных от Интернет-узлов.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Конфигурации](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|Содержит параметры для всех пространств имен.|  
  
## <a name="remarks"></a>Примечания  
 [ \<System.net >](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md) элемент содержит параметры для классов в <xref:System.Net> и связанные с ним дочерние пространства имен. Параметры настройки модулей проверки подлинности, управление соединениями, параметры электронной почты, прокси-сервера и модулей Интернет-запросов при получении данных от Интернет-узлов.  
  
## <a name="example"></a>Пример  
 В следующем примере показано стандартной конфигурации, используемые <xref:System.Net> классы.  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
