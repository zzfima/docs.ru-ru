---
title: <proxy> (Сетевые параметры)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 8df9bbf2615776c2e023f03401785da95b2226eb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59204826"
---
# <a name="proxy-element-network-settings"></a>\<прокси-сервер > (сетевые параметры)
Определяет прокси-сервер.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
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
  
|**Атрибут**|**Описание**|  
|-------------------|---------------------|  
|`autoDetect`|Указывает, обнаруживается ли прокси-сервер автоматически. Значение по умолчанию — `unspecified`.|  
|`bypassonlocal`|Указывает, пропускает ли прокси-сервер для локальных ресурсов. Локальные ресурсы включают локальный сервер (`http://localhost`, `http://loopback`, или `http://127.0.0.1`) и URI без точки (`http://webserver`). Значение по умолчанию — `unspecified`.|  
|`proxyaddress`|Указывает URI, используемый прокси-сервер.|  
|`scriptLocation`|Указывает расположение скрипта конфигурации. Не используйте `bypassonlocal` атрибута с этим атрибутом. |  
|`usesystemdefault`|Указывает, следует ли использовать параметры прокси-сервера Internet Explorer. Если значение `true`, следующие атрибуты переопределят параметры прокси-сервера Internet Explorer. Значение по умолчанию — `unspecified`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="text-value"></a>Текстовое значение  
  
## <a name="remarks"></a>Примечания  
 `proxy` Элемент определяет прокси-сервер для приложения. Если этот элемент отсутствует в файле конфигурации, то платформа .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.  
  
 Значение для `proxyaddress` атрибут должен иметь правильный формат универсального кода ресурса (URI).  
  
 `scriptLocation` Атрибут ссылается на автоматическое обнаружение сценариев настройки прокси-сервера. <xref:System.Net.WebProxy> Класс будет пытаться обнаружить сценарий конфигурации (обычно именованный Wpad.dat) при **использовать сценарий автоматической настройки** установлен флажок в Internet Explorer. Если `bypassonlocal` присвоено любое значение `scriptLocation` учитывается.
  
 Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1.1, которые переносят до версии 2.0.  
  
 Исключение возникает в том случае, если `proxyaddress` атрибут указывает на недопустимое значение по умолчанию прокси-сервер. Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере используются значения по умолчанию от прокси-сервера Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервера для локального доступа.  
  
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

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
