---
title: "Элемент &lt;socket&gt; (параметры сети) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings/socket"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#socket"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<socket> - элемент"
  - "socket - элемент"
ms.assetid: 366c634c-7d16-478f-aedf-053eda94a1a0
caps.latest.revision: 21
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 21
---
# Элемент &lt;socket&gt; (параметры сети)
Указывает, используют ли операции сокета порты завершения.  
  
## Синтаксис  
  
```  
  
      <socket  
  alwaysUseCompletionPortsForConnect="true|false"  
  alwaysUseCompletionPortsForAccept="true|false"  
  ipProtectionLevel ="EdgeRestricted|Restricted|Unrestricted|Unspecified"  
/socket>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|**Атрибут**|**Описание**|  
|-----------------|------------------|  
|`alwaysUseCompletionPortsForAccept`|Показывает, всегда ли сокет использует порты завершения для вызовов метода Accept.  Значение по умолчанию — `false`.|  
|`alwaysUseCompletionPortsForConnect`|Показывает, всегда ли сокет использует порты завершения для вызовов метода Connect.  Значение по умолчанию — `false`.|  
|`ipProtectionLevel`|Задает значение по умолчанию <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>, которое будет использоваться для сокета  Значение по умолчанию зависит от версии Windows.|  
  
### Дочерние элементы  
 Нет.  
  
### Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|------------------|  
|[settings](../../../../../docs/framework/configure-apps/file-schema/network/settings-element-network-settings.md)|Настраивает основные сетевые параметры для пространства имен <xref:System.Net>.|  
  
## Заметки  
 Атрибуты `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` используются для задания поведения по умолчанию в зависимости от использования портов завершения классами в пространстве имен <xref:System.Net.Sockets?displayProperty=fullName>.  Порты завершения рекомендуется использовать для высокопроизводительных серверных приложений.  
  
 Значением по умолчанию для атрибутов `alwaysUseCompletionPortsForAccept` и `alwaysUseCompletionPortsForConnect` является **false**.  
  
 Свойство <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForAccept%2A> может использоваться для получения текущего значения атрибута `alwaysUseCompletionPortsForAccept` из применимых файлов конфигурации.  Свойство <xref:System.Net.Configuration.SocketElement.AlwaysUseCompletionPortsForConnect%2A> может использоваться для получения текущего значения атрибута `alwaysUseCompletionPortsForConnect` из применимых файлов конфигурации.  
  
 Атрибут `ipProtectionLevel` задает значение <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> по умолчанию, которое будет использоваться для сокета.  Свойство <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> включает конфигурацию ограничения для сокета IPv6 указанной области, например адресам с одинаковой локальной ссылкой или локальным префиксом сайта.  Этот параметр позволяет приложениям устанавливать ограничения доступа к IPv6\-сокетам.  Такие ограничения позволяют приложению, работающему в частной локальной сети, просто и надежно защититься от внешних атак.  Этот параметр расширяет или сужает диапазон прослушивающего сокета, обеспечивая при необходимости неограниченный доступ со стороны открытых и закрытых пользователей или ограничивая доступ только тем же сайтом.  
  
 Этот атрибут `ipProtectionLevel` влияет только на начальный входящий трафик:  
  
-   Сервер TCP, прослушивающий входящие подключения на сокете.  
  
-   Приложение UDP, получающее пакет на сокете.  
  
 Этот параметр конфигурации не влияет на уже установленные подключения по протоколу TCP \(трафик не ограничен в обоих направлениях\) и не влияет на приложения, отправляющие пакеты по протоколу UDP.  
  
 Возможные значения для атрибута `ipProtectionLevel`, соответствующие заданным уровням защиты, задаются в перечислении <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> следующим образом:  
  
|||  
|-|-|  
|**Значение атрибута**|**Описание**|  
|EdgeRestricted|Уровень защиты IP — предельно ограничено.  Это значение используется приложениями, разработанными для работы в Интернете.  Этот параметр не позволяет обойти механизм преобразования сетевых адресов \(NAT\) с помощью реализации Windows Teredo.  Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от атак из Интернета, направленных на открытый порт.  В Windows Server 2003 и Windows XP значение по умолчанию для уровня защиты IP сокета — предельно ограничено.|  
|Ограничено|Уровень защиты IP — ограничено.  Это значение используется приложениями интрасети, не работающих в Интернете.  Эти приложения обычно не тестируются и не защищаются против атак из Интернета.  Этот параметр ограничивает получаемый трафик локальным.|  
|Unrestricted|Уровень защиты IP — неограниченно.  Это значение используется приложениями, разработанными для работы в Интернете, включая приложения, использующие возможности обхода IPv6 NAT, включенные в Windows \(например, Teredo\).  Эти приложения могут обходить брандмауэры протокола IPv4, поэтому они должны быть защищены от атак из Интернета, направленных на открытый порт.  В Windows Server 2008 R2 и Windows Vista значение по умолчанию для уровня защиты IP сокета — неограниченно.|  
|Не указано|Уровень защиты IP — не указано.  В Windows 7 и Windows Server 2008 R2 и значение по умолчанию для уровня защиты IP сокета — не указано.|  
  
 По умолчанию атрибут `ipProtectionLevel` имеет значение **Unspecified**.  
  
 Свойство <xref:System.Net.Configuration.SocketElement.IPProtectionLevel%2A> может использоваться для получения текущего значения атрибута `ipProtectionLevel` из применимых файлов конфигурации.  
  
## Файлы конфигурации  
 Этот элемент может быть использован в файле конфигурации приложения или в файле конфигурации компьютера \(Machine.config\).  
  
## Пример  
 В следующем примере кода показан способ указания, что должны использоваться порты завершения и что значение <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName> по умолчанию должно быть не ограничено.  
  
```  
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
  
## См. также  
 <xref:System.Net?displayProperty=fullName>   
 <xref:System.Net.Configuration.SocketElement?displayProperty=fullName>   
 <xref:System.Net.Sockets?displayProperty=fullName>   
 <xref:System.Net.Sockets.IPProtectionLevel?displayProperty=fullName>   
 <xref:System.Net.Sockets.SocketOptionName?displayProperty=fullName>   
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)