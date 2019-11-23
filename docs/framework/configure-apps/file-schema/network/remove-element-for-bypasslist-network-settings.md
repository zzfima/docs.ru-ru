---
title: Элемент <remove> для bypasslist (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/remove
- http://schemas.microsoft.com/.NetConfiguration/v2.0#remove
helpviewer_keywords:
- <bypasslist>, remove element
- remove element, bypasslist
- bypasslist, remove element
- remove element, bypasslist
ms.assetid: 61dcfb4a-e3d9-4abf-a2cd-7d685fe2f64b
ms.openlocfilehash: 97b49a8a520d6a4f72945366874991d2deb18710
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697896"
---
# <a name="remove-element-for-bypasslist-network-settings"></a>\<удалить элемент > для бипасслист (параметры сети)

Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.

[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. NET >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<defaultProxy >** ](defaultproxy-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<бипасслист >** ](bypasslist-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<удалить >**  

## <a name="syntax"></a>Синтаксис

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.

### <a name="attributes"></a>Атрибуты

|**Атрибут**|**Описание**|
|-------------------|---------------------|
|`address`|Регулярное выражение, описывающее IP-адрес или DNS-имя.|

### <a name="child-elements"></a>Дочерние элементы

Нет

### <a name="parent-elements"></a>Родительские элементы

|**Элемент**|**Описание**|
|-----------------|---------------------|
|[бипасслист](bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.|

## <a name="remarks"></a>Примечания

Элемент `remove` удаляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, из списка адресов, которые обходят прокси-сервер. Адреса были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.

Значение атрибута `address` должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.

Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).

## <a name="configuration-files"></a>Файлы конфигурации

Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).

## <a name="example"></a>Пример

В следующем примере удаляется предыдущее определение для домена adventure-works.com, а затем домен contoso.com добавляется в список обхода.

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <bypasslist>
        <remove address="[a-z]+\.adventure-works\.com$" />
        <add address="[a-z]+\.contoso\.com$" />
      </bypasslist>
    </defaultProxy>
  </system.net>
</configuration>
```

## <a name="see-also"></a>См. также:

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
