---
title: '&lt;defaultProxy&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 1e9548c6d43824ea5017b73a132eb49444ed6c77
ms.sourcegitcommit: 736ec4d3e2c74895b47a0d36126657b95da383c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2018
ms.locfileid: "37140194"
---
# <a name="ltdefaultproxygt-element-network-settings"></a>&lt;defaultProxy&gt; элемент (параметры сети)
Настраивает прокси-сервер протокола передачи гипертекста (HTTP).  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
      <defaultProxy  
        enabled="true|false"  
        useDefaultCredentials="true|false">  
           <bypasslist> … </bypasslist>  
           <proxy> … </proxy>  
           <module> … </module>  
      </defaultProxy>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|`enabled`|Указывает, используется ли веб-прокси. Значение по умолчанию — `true`.|  
|`useDefaultCredentials`|Указывает, используются ли учетные данные по умолчанию для этого узла для доступа к веб-прокси. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.|  
|[Модуль](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|Добавляет в приложение новый модуль прокси-сервера.|  
|[прокси-сервера](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|Определяет прокси-сервер.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[System.NET](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="remarks"></a>Примечания  
 Если элемент defaultProxy пуст, будут использоваться параметры прокси-сервера из Internet Explorer. Это поведение отличается от поведения в .NET Framework версии 1.1.  
  
 Исключение возникает, если [модуль](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) элемент задает тип закрытым, тип не является производным от <xref:System.Net.IWebProxy> класса, произошло исключение в конструкторе по умолчанию для этого объекта или возникло исключение во время Получение прокси-сервера по умолчанию, заданного в системе. Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о корневой причине ошибки.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример использует значения по умолчанию из прокси-сервера обозревателя Internet Explorer, указывает адрес прокси-сервера и обходит прокси-сервер для локальных адресов и домена contoso.com.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
