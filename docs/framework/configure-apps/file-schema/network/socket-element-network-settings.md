---
title: Элемент <socket> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket
- http://schemas.microsoft.com/.NetConfiguration/v2.0#socket
helpviewer_keywords:
- <socket> element
- socket element
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
ms.openlocfilehash: 0e2b369eccfbc658a790ef61a961315a88361669
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089090"
---
# <a name="socket-element-network-settings"></a>Элемент > \<сокета (параметры сети)
Указывает, используют ли операции сокета порты завершения.  

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. net >** ](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](settings-element-network-settings.md) >\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**сокет >**

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
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|`alwaysUseCompletionPortsForAccept`|Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Accept. Значение по умолчанию — `false`.|  
|`alwaysUseCompletionPortsForConnect`|Указывает, должен ли сокет всегда использовать порты завершения для вызовов метода Connect. Значение по умолчанию — `false`.|  
|`ipProtectionLevel`|Указывает <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> по умолчанию, используемый для сокета. Значение по умолчанию зависит от версии Windows.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[Параметры](settings-element-network-settings.md)|Настраивает основные параметры сети для пространства имен <xref:System.Net>.|  
  
## <a name="remarks"></a>Заметки  
 Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в отношении использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=nameWithType>. Порты завершения рекомендуются для высокопроизводительных серверных приложений.  
  
 По умолчанию для атрибутов `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` задано значение **false**.  
  
 <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> можно использовать для получения текущего значения атрибута `alwaysUseCompletionPortsForAccept` из применимых файлов конфигурации. <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> можно использовать для получения текущего значения атрибута `alwaysUseCompletionPortsForConnect` из применимых файлов конфигурации.  
  
 Атрибут `ipProtectionLevel` указывает <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> по умолчанию, используемый для сокета. Свойство <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> позволяет настроить ограничение сокета IPv6 на указанную область, например адреса с одинаковой локальной ссылкой или локальным префиксом сайта. Этот параметр позволяет приложениям размещать ограничения доступа к сокетам IPv6. Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак. Этот параметр расширяет или ограничивает область действия прослушивающего сокета, обеспечивая неограниченный доступ от общедоступных и частных пользователей при необходимости или ограничивающий доступ только для того же сайта, если это необходимо.  
  
 Этот `ipProtectionLevel` атрибут влияет только на начальный входящий трафик:  
  
- TCP-сервер, прослушивающий входящие подключения на сокете.  
  
- Приложение UDP, получающее пакет на сокете.  
  
 Этот параметр конфигурации не влияет на уже установленные TCP-подключения (трафик в обоих направлениях не ограничен) и не влияет на приложение, отправляющее пакеты UDP.  
  
 Возможные значения параметра `ipProtectionLevel` атрибута соответствуют определенным уровням защиты, указанным в перечислении <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> следующим образом:  
  
|**Значение атрибута**|**Описание**|  
|-|-|  
|еджерестриктед|Уровень защиты IP ограничен границей. Это значение будет использоваться приложениями, предназначенными для взаимодействия через Интернет. Этот параметр не разрешает обход преобразования сетевых адресов (NAT) с помощью реализации Windows Teredo. Эти приложения могут обходить брандмауэры IPv4, поэтому приложения должны быть защищены от Интернет-атак, направленных на открытый порт. В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP на сокете ограничено границей.|  
|Ограничено|Уровень защиты IP-адресов ограничен. Это значение будет использоваться приложениями интрасети, которые не реализуют сценарии Интернета. Обычно эти приложения не тестируются и не защищаются от атак в стиле Интернета. Этот параметр ограничит полученный трафик только локальным каналом.|  
|Без ограничений|Уровень защиты IP-адресов не ограничен. Это значение будет использоваться приложениями, предназначенными для работы через Интернет, включая приложения, использующие возможности просмотра NAT IPv6, встроенные в Windows (например, Teredo). Эти приложения могут обходить брандмауэры IPv4, поэтому приложения должны быть защищены от Интернет-атак, направленных на открытый порт. В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP-адресов на сокете не ограничено.|  
|Не указан|Уровень защиты IP-адресов не указан. В Windows 7 и Windows Server 2008 R2 значение по умолчанию для уровня защиты IP-адресов на сокете не указано.|  
  
 Значение по умолчанию для атрибута `ipProtectionLevel` не **указано**.  
  
 Свойство <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> можно использовать для получения текущего значения атрибута `ipProtectionLevel` из применимых файлов конфигурации.  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как указать, что порты завершения должны использоваться, а <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=nameWithType> по умолчанию должны быть неограниченными.  
  
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
- [Схема параметров сети](index.md)
