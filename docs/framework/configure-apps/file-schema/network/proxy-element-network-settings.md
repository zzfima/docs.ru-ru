---
title: Элемент <proxy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154794"
---
# <a name="proxy-element-network-settings"></a>\<прокси> элемент (Настройки сети)
Определяет прокси-сервер.  

[**\<конфигурация>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<прокси>**

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
|`autoDetect`|Указывает, обнаруживается ли прокси-сервер автоматически. Значение по умолчанию — `unspecified`.|  
|`bypassonlocal`|Указывает, используется ли прокси-сервер для локальных ресурсов. Местные ресурсы включают`http://localhost` `http://loopback`локальный `http://127.0.0.1`сервер (, или`http://webserver`) и URI без периода (). Значение по умолчанию — `unspecified`.|  
|`proxyaddress`|Определяет прокси URI для использования.|  
|`scriptLocation`|Определяет местоположение сценария конфигурации. Не используйте `bypassonlocal` атрибут с этим атрибутом. |  
|`usesystemdefault`|Определяет, следует ли использовать настройки прокси-серверов Internet Explorer. Если `true`установлено, последующие атрибуты переопределяют настройки прокси-серверов Internet Explorer. Значение по умолчанию — `unspecified`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="text-value"></a>Текстовое значение  
  
## <a name="remarks"></a>Remarks  
 Элемент `proxy` определяет прокси-сервер для приложения. Если этот элемент отсутствует в файле конфигурации, то в рамке .NET будут использоваться настройки прокси в Internet Explorer.  
  
 Значение атрибута `proxyaddress` должно быть хорошо сформированным единым индикатором ресурсов (URI).  
  
 Атрибут `scriptLocation` относится к автоматическому обнаружению скриптов конфигурации прокси. Класс <xref:System.Net.WebProxy> попытается найти сценарий конфигурации (обычно названный Wpad.dat), когда параметр **автоматической конфигурации «Использование»** выбран в Internet Explorer. Если `bypassonlocal` настроен на какое-либо значение, `scriptLocation` игнорируется.
  
 Используйте `usesystemdefault` атрибут для приложений .NET Framework 1.1, которые мигрируют в версию 2.0.  
  
 Исключение брошено, `proxyaddress` если атрибут указывает недействительный прокси по умолчанию. Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере используются по умолчанию из прокси-сервера Internet Explorer, указывается прокси-адрес и обходит прокси для локального доступа.  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема настройки сети](index.md)
