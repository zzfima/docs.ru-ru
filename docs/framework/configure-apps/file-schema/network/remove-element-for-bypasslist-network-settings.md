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
ms.openlocfilehash: 99c18bd5b779845d52831b4a9591eaf4d5e5530b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920959"
---
# <a name="remove-element-for-bypasslist-network-settings"></a>\<Удаление элемента > для бипасслист (параметры сети)

Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.

\<> конфигурации \
\<System. NET > \
\<defaultProxy > \
\<бипасслист > \
\<Удалить >

## <a name="syntax"></a>Синтаксис

```xml
<remove
  address="regular expression"
/>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы

В следующих разделах описаны атрибуты, дочерние и родительские элементы.

### <a name="attributes"></a>Атрибуты

|**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))|**Описание**|
|-------------------|---------------------|
|`address`|Регулярное выражение, описывающее IP-адрес или DNS-имя.|

### <a name="child-elements"></a>Дочерние элементы

Нет.

### <a name="parent-elements"></a>Родительские элементы

|**Элемент**|**Описание**|
|-----------------|---------------------|
|[бипасслист](bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.|

## <a name="remarks"></a>Примечания

`remove` Элемент удаляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, из списка адресов, которые обходят прокси-сервер. Адреса были определены ранее в файле конфигурации или на более высоком уровне иерархии конфигурации.

Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.

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

## <a name="see-also"></a>См. также

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
