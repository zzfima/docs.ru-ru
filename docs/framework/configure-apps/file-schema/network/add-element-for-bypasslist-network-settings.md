---
title: Элемент <add> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 652b8738a201aaa98fa2c5c435fee1a6da91673b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155081"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<добавить элемент> для обвисать (Настройки сети)
Добавляет IP-адрес или имя DNS в список обхода прокси.  
  
[**\<конфигурация>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<по умолчаниюПрокси>**](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<обвахние>**](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add
  address="regular expression"
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Атрибут**|**Описание**|  
|-------------------|---------------------|  
|**address**|Регулярное выражение, описывающее IP-адрес или имя DNS.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[bypasslist](bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающие адреса, которые не используют прокси.|  
  
## <a name="remarks"></a>Remarks  
 Элемент `add` вставляет регулярные выражения, описывающие IP-адреса или имена серверов DNS, в список адресов, которые обходят прокси-сервер.  
  
 Значение `address` атрибута должно быть регулярным выражением, описывая набор IP-адресов или имен узла.  
  
 При указании регулярного выражения для этого элемента следует соблюдать осторожность. Регулярное выражение «a-z»\\.contoso\\.com соответствует любому хозяину в домене contoso.com, но также соответствует любому хозяину в домене contoso.com.cpandl.com. Чтобы соответствовать только хостелу в домене contoso.com, используйте якорь («$»): «А-з.з\\.contoso\\.com$».  
  
 Для получения дополнительной информации о регулярных выражениях см. [.NET Рамки Регулярные выражения](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример добавляет два адреса в список обхода. Первый обходит прокси для всех серверов в домене contoso.com; второй обходит прокси для всех серверов, чей IP-адрес начинается с 192.168.  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема настройки сети](index.md)
