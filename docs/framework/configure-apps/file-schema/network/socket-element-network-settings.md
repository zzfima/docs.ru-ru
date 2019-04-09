---
title: <socket> (Сетевые параметры)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 82bfe3b6e3107ff787716657dbf0b31dcadde911
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160164"
---
# <a name="socket-element-network-settings"></a>\<сокет > (сетевые параметры)
Указывает, используют ли операции сокета порты завершения.  
  
 \<configuration>  
\<system.net>  
\<Параметры >  
\<сокет >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Атрибут**|**Описание**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Указывает, всегда ли сокет использует порты завершения для вызовы метода приема. Значение по умолчанию — `false`.|  
|`alwaysUseCompletionPortsForConnect`|Указывает, всегда ли сокет использует порты завершения для вызовов метода Connect. Значение по умолчанию — `false`.|  
|`ipProtectionLevel`|Указывает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> для сокета. Значение по умолчанию зависит от версии Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[параметры](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Примечания  
 Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в отношении использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=nameWithType>. Порты завершения рекомендуется использовать для высокопроизводительных серверных приложений.  
  
 Значение по умолчанию для `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` атрибутов **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> Можно использовать для получения текущего значения `alwaysUseCompletionPortsForAccept` атрибут из применимые файлы конфигурации. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> Можно использовать для получения текущего значения `alwaysUseCompletionPortsForConnect` атрибут из применимые файлы конфигурации.  
  
 `ipProtectionLevel` Атрибут указывает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> для сокета. <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Свойство позволяет настроить ограничение для сокет IPv6 указанным диапазоном, такие как адреса, с тем же связи, локальных или локальным префиксом сайта. Этот параметр позволяет приложениям устанавливать ограничения доступа к сокетам IPv6. Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак. Этот параметр расширяет или сужает диапазон прослушивающего сокета, включение неограниченный доступ со стороны открытых и закрытых пользователей, когда это необходимо, или ограничить доступ только для одного сайта и при необходимости.  
  
 Это `ipProtectionLevel` атрибут влияет только начального входящего трафика:  
  
-   TCP-сервер, прослушивание входящих подключений через сокет.  
  
-   Приложение UDP, получения пакета на сокете.  
  
 Этот параметр конфигурации не влияет на уже установленные TCP-соединения, (трафик не ограничен в обоих направлениях) и не влияет на приложения, отправляющие пакеты UDP.  
  
 Возможные значения `ipProtectionLevel` соответствуют параметры атрибутов с уровнями защиты определенных, указанный в <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> перечисления следующим образом:  
  
|**Значение атрибута**|**Описание**|  
|-|-|  
|EdgeRestricted|Уровень защиты IP — предельно ограничено. Это значение используется приложениями, разработанными для работы в Интернете. Этот параметр не допуская сетевых адресов (NAT) с помощью реализации Windows Teredo. Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от Интернет-атак, направленных на открытый порт. В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP сокета — предельно ограничено.|  
|Ограничено|Уровень защиты IP — ограниченным доступом. Это значение будет использоваться приложениями интрасети, не работающих в Интернете. Эти приложения обычно не протестированы и не защищаются против атак из Интернета. Этот параметр ограничивает получаемый трафик локальным.|  
|Без ограничений|Уровень защиты IP — неограниченно. Это значение будет использоваться приложениями, разработанными для работы в Интернете, включая приложения, использующие возможности обхода IPv6 NAT в Windows (например, Teredo). Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от Интернет-атак, направленных на открытый порт. В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP сокета — неограниченно.|  
|Не указан|Уровень защиты IP не определен. В Windows 7 и Windows Server 2008 R2 значение по умолчанию для уровня защиты IP сокета не определен.|  
  
 Значение по умолчанию для `ipProtectionLevel` атрибут **Unspecified**.  
  
 <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> Свойство может использоваться для получения текущего значения `ipProtectionLevel` атрибут из применимые файлы конфигурации.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что следует использовать порты завершения и, по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> должно быть не ограничено.  
  
```xml  
<configuration>  
  <system.net>  
    <settings>  
      <socket  
        alwaysUseCompletionPortsForAccept="true"  
        alwaysUseCompletionPortsForConnect="true"  
        ipProtectionLevel="Unrestricted"  
       />  
    </settings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Net?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SocketElement?displayProperty=nameWithType>
- <xref:System.Net.Sockets?displayProperty=nameWithType>
- <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType>
- <xref:System.Net.Sockets.SocketOptionName.IPProtectionLevel?displayProperty=nameWithType>
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
