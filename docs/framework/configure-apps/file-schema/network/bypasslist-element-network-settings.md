---
title: Элемент <bypasslist> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: db975d44db96f605767d7320737ff3c162bbc8a5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282962"
---
# <a name="bypasslist-element-network-settings"></a>\<bypasslist > (сетевые параметры)
Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.  
  
 \<configuration>  
\<system.net>  
\<defaultProxy>  
\<bypasslist>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[add](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|Добавляет IP-адрес или DNS-имя в список обхода прокси-сервера.|  
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Очищает список вариантов обхода.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="remarks"></a>Примечания  
 В списке пропускаемых адресов содержит регулярных выражений, описывающих URI, <xref:System.Net.WebRequest> экземпляры доступ напрямую вместо того, через прокси-сервер.  
  
 Будьте внимательны при указании регулярное выражение для этого элемента. Регулярное выражение «[a-z] +\\.contoso\\.com» совпадений, любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена. Чтобы сопоставить только на узле в домене contoso.com, используйте привязку («$»): «[a-z] +\\.contoso\\.com$».  
  
 Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Следующий пример добавляет два адреса в списке пропускаемых адресов. Первый обходит прокси-сервер для всех серверов в домене contoso.com. второй обходит прокси-сервер для всех серверов, IP-адреса начинается с 192.168.  
  
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
