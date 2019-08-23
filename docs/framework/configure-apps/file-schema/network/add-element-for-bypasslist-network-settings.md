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
ms.openlocfilehash: da234402c6ec7e2c1f85e4bd674517b1147f0d18
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927482"
---
# <a name="add-element-for-bypasslist-network-settings"></a>\<Добавление элемента > для бипасслист (параметры сети)
Добавление в список обхода прокси IP-адреса или DNS-имени.  
  
 \<configuration>  
\<> System. NET  
\<defaultProxy >  
\<бипасслист >  
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
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[бипасслист](bypasslist-element-network-settings.md)|Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.|  
  
## <a name="remarks"></a>Примечания  
 `add` Элемент вставляет регулярные выражения, описывающие IP-адреса или имена DNS-серверов, в список адресов, которые обходят прокси-сервер.  
  
 Значение `address` атрибута должно быть регулярным выражением, описывающим набор IP-адресов или имен узлов.  
  
 При указании регулярного выражения для этого элемента следует соблюдать осторожность. Регулярное выражение "[a-z] +\\. contoso\\. com" соответствует любому узлу в домене contoso.com, но также соответствует любому узлу в домене contoso.com.cpandl.com. Чтобы сопоставить только узел в домене contoso.com, используйте привязку ("$"): "[a-z] +\\. contoso\\. com $".  
  
 Дополнительные сведения о регулярных выражениях см. в разделе. [.NET Framework регулярных выражений](../../../../standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 В следующем примере в список обхода добавляется два адреса. Первый обход прокси-сервера для всех серверов в домене contoso.com; во втором пропускается прокси-сервер для всех серверов, IP-адрес которых начинается с 192,168.  
  
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
- [Схема параметров сети](index.md)
