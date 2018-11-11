---
title: '&lt;Добавление&gt; элемент для bypasslist (параметры сети)'
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
ms.openlocfilehash: ca1d33b2077736a9760f65857bffe4e96c4aeab0
ms.sourcegitcommit: 0fbd677fcdc5bf46c4d827f492eaaa970edc07b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2018
ms.locfileid: "50235730"
---
# <a name="ltaddgt-element-for-bypasslist-network-settings"></a>&lt;Добавление&gt; элемент для bypasslist (параметры сети)
Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<bypasslist >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|  
|-------------------|---------------------|  
|**address**|Регулярное выражение, описывающее IP-адрес или DNS-имя.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[bypasslist](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.|  
  
## <a name="remarks"></a>Примечания  
 `add` Элемент вставляет регулярное выражение, описывающее IP-адреса или имена DNS-серверов в список адресов, которые обходят прокси-сервер.  
  
 Значение `address` атрибут должен быть регулярное выражение, которое описывает набор IP-адресов или имен узлов.  
  
 Будьте внимательны при указании регулярное выражение для этого элемента. Регулярное выражение «[a-z] +\\.contoso\\.com» совпадений, любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена. Чтобы сопоставить только на узле в домене contoso.com, используйте привязку («$»): «[a-z] +\\.contoso\\.com$».  
  
 Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример добавляет два адреса в списке пропускаемых адресов. Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адрес начинается с 192.168.  
  
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
  
## <a name="see-also"></a>См. также  
- <xref:System.Net.WebProxy?displayProperty=nameWithType>  
- [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
