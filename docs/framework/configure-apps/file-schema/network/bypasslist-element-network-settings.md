---
title: '&lt;bypasslist&gt; элемент (параметры сети)'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2d2076ee5e95ab722fe828ee625392671a6281c1
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32743905"
---
# <a name="ltbypasslistgt-element-network-settings"></a>&lt;bypasslist&gt; элемент (параметры сети)
Предоставляет набор регулярных выражений, описывающих адреса, которые не используют прокси-сервер.  
  
 \<configuration>  
\<System.NET >  
\<defaultProxy >  
\<bypasslist >  
  
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
|[clear](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|Очищает список обхода.|  
|[remove](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|Удаляет IP-адрес или DNS-имя из списка обхода прокси-сервера.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|**Элемент**|**Описание**|  
|-----------------|---------------------|  
|[defaultProxy](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|Настраивает прокси-сервер протокола передачи гипертекста (HTTP).|  
  
## <a name="remarks"></a>Примечания  
 Список пропускаемых содержит регулярных выражений, описывающих URI, <xref:System.Net.WebRequest> экземпляры доступ напрямую вместо того, через прокси-сервер.  
  
 Следует проявлять осторожность при вводе регулярного выражения для данного элемента. Регулярное выражение «[a-z] +\\.contoso\\.com» совпадает с любого узла в домене contoso.com, но он также соответствует любому узлу в contoso.com.cpandl.com домена. Чтобы соответствовать только одному узлу в домене contoso.com, используйте элемент привязки («$»): «[a-z] +\\.contoso\\.com$».  
  
 Дополнительные сведения о регулярных выражениях см. в разделе. [Регулярные выражения .NET framework](../../../../../docs/standard/base-types/regular-expressions.md).  
  
## <a name="configuration-files"></a>Файлы конфигурации  
 Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).  
  
## <a name="example"></a>Пример  
 Список пропускаемых в следующем примере добавляются два адреса. Первый обход прокси-сервера для всех серверов в домене contoso.com. второй обход прокси-сервера для всех серверов, IP-адреса которых начинаются с 192.168.  
  
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
 <xref:System.Net.WebProxy?displayProperty=nameWithType>  
 [Схема параметров сети](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
