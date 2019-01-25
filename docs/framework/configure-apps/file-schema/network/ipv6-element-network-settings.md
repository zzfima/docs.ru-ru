---
title: '&lt;IPv6&gt; (сетевые параметры)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/ipv6
- http://schemas.microsoft.com/.NetConfiguration/v2.0#ipv6
helpviewer_keywords:
- <ipv6> element
- ipv6 element
ms.assetid: 10b79aef-327b-4718-a892-e11f55e4d169
ms.openlocfilehash: 1ca1bb6a0b1a9c3deab9cb3ba15e9b3b2c29f1f7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531893"
---
# <a name="ltipv6gt-element-network-settings"></a>&lt;IPv6&gt; (сетевые параметры)
Включает протокол IP версии 6 (IPv6) ответы от устаревших членов из <xref:System.Net.Dns> класса.  
  
 \<configuration>  
\<system.net>  
\<Параметры >  
\<ipv6>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<ipv6  
  enabled="true|false"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`enabled`|Указывает ли члены <xref:System.Net.Dns> класса вернуть IP версии 6 (IPv6) адреса. Значение по умолчанию — `false`.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 Этот параметр обеспечивает поддержку IPv6 для устаревших членов <xref:System.Net.Dns> класса: <xref:System.Net.Dns.BeginGetHostByName%2A>, <xref:System.Net.Dns.BeginResolve%2A>, <xref:System.Net.Dns.EndGetHostByName%2A>, <xref:System.Net.Dns.EndResolve%2A>, <xref:System.Net.Dns.GetHostByAddress%2A>, <xref:System.Net.Dns.GetHostByName%2A>, и <xref:System.Net.Dns.Resolve%2A>. Для других членов <xref:System.Net?displayProperty=nameWithType> пространства имен, IPv6-адреса может быть возвращено, если была включена поддержка IPv6 в операционной системе.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как включить поддержку IPv6 для <xref:System.Net.Dns> класса.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <ipv6 enabled="true"/>  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также
- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Dns?displayProperty=nameWithType>
- <xref:System.Net.Sockets.Socket.OSSupportsIPv6%2A?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
