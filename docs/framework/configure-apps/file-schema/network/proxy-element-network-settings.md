---
title: '&lt;прокси-сервер&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b5ae716994f9b8222a633699367c94480179c97b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltproxygt-element-network-settings"></a>&lt;прокси-сервер&gt; элемент (параметры сети)
Определяет прокси-сервер.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<прокси-сервера >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<proxy
  autoDetect="true|false|unspecified" 
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`autoDetect`|Указывает, обнаруживается ли прокси-сервер автоматически. Значение по умолчанию — `unspecified`.|  
|`bypassonlocal`|Указывает, пропускает ли прокси-сервер для локальных ресурсов. Локальные ресурсы включают локальный сервер (http://localhost, http://loopback, или http://127.0.0.1) и URI без точки (http://webserver). Значение по умолчанию — `unspecified`.|  
|`proxyaddress`|Указывает URI, который используется прокси-сервер.|  
|`scriptLocation`|Указывает расположение скрипта конфигурации.|  
|`usesystemdefault`|Указывает, следует ли использовать параметры прокси-сервера обозревателя Internet Explorer. Если значение `true`, следующие атрибуты переопределят параметры прокси Internet Explorer. Значение по умолчанию — `unspecified`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="text-value"></a>Текстовое значение  
  
## <a name="remarks"></a>Примечания  
 `proxy` Элемент определяет прокси-сервер для приложения. Если этот элемент отсутствует в файле конфигурации, .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.  
  
 Значение для `proxyaddress` атрибут должен иметь правильный формат унифицированного указателя ресурса (URI).  
  
 `scriptLocation` Атрибут ссылается на автоматическое обнаружение сценариев настройки прокси-сервера. <xref:System.Net.WebProxy> Класс попытается обнаружить сценарий конфигурации (обычно именованный Wpad.dat) при **использовать сценарий автоматической настройки** флажок в Internet Explorer.  
  
 Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1.1, выполняется миграция в версии 2.0.  
  
 Исключение возникает, если `proxyaddress` атрибут указывает на недопустимое значение по умолчанию прокси-сервер. Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о корневой причине ошибки.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример использует значения по умолчанию из прокси-сервера обозревателя Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервера для локального доступа.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
