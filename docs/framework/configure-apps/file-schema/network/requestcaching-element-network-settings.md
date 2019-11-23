---
title: Элемент <requestCaching> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
ms.openlocfilehash: f0979d2e0caeb0b22b90572aef0ad53235020f1d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697824"
---
# <a name="requestcaching-element-network-settings"></a>Элемент \<requestCaching> (сетевые параметры)
Управляет механизмом кэширования для сетевых запросов.  
  
[ **\<configuration>** ](../configuration-element.md)  
&nbsp;&nbsp;[ **\<System. NET >** ](system-net-element-network-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp; **\<элемент requestcaching >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<requestCaching  
  isPrivateCache ="true|false"  
  disableAllCaching="true|false"  
  defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
  unspecifiedMaximumAge= "d.hh.mm.ss">  
    <defaultHttpCachePolicy>...</defaultHttpCachePolicy>  
    <defaultFtpCachePolicy>...</defaultFtpCachePolicy>  
</requestCaching>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 Следующие разделы описывают атрибуты, дочерние элементы и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`isPrivateCache`|Указывает, обеспечивает ли кэш изоляцию между данными разных пользователей. Значение по умолчанию — `true`. Это значение должно быть `false` для приложений среднего уровня.|  
|`disableAllCaching`|Указывает, что кэширование отключено для всех веб-ответов и не может быть переопределено программным способом.|  
|`defaultPolicyLevel`|Одно из значений в перечислении <xref:System.Net.Cache.RequestCacheLevel>. Значение по умолчанию — `BypassCache`.|  
|`unspecifiedMaximumAge`|Задает время по умолчанию, по истечении которого содержимое помечается как просроченное.|  
  
## <a name="policylevel-attribute"></a>Атрибут Полицилевел  
  
|Значение|Описание|  
|-----------|-----------------|  
|`Default`|Возвращает кэшированный ресурс, если ресурс является актуальным, длина содержимого является точной, а атрибуты срока действия, изменения и длины содержимого существуют.|  
|`BypassCache`|Возвращает ресурс с сервера.|  
|`CacheOnly`|Возвращает кэшированный ресурс, если длина содержимого имеется и соответствует размеру записи.|  
|`CacheIfAvailable`|Возвращает кэшированный ресурс, если длина содержимого указана и соответствует размеру записи. в противном случае ресурс загружается с сервера и возвращается вызывающему объекту.|  
|`Revalidate`|Возвращает кэшированный ресурс, если метка времени кэшированного ресурса совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, хранится в кэше, и возвращается вызывающему объекту.|  
|`Reload`|Скачивает ресурс с сервера, сохраняет его в кэше и возвращает ресурс вызывающему объекту.|  
|`NoCacheNoStore`|Если кэшированный ресурс существует, он удаляется. Ресурс загружается с сервера и возвращается вызывающему.|  
|`Revalidate`|Удовлетворяет запросу, используя кэшированную копию ресурса, если отметка времени совпадает с меткой времени ресурса на сервере. в противном случае ресурс загружается с сервера, представленного вызывающему объекту, и хранится в кэше.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](defaulthttpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает, активно ли кэширование HTTP и описывает политику кэширования по умолчанию.|  
|[Элемент \<Дефаултфтпкачеполици > (параметры сети)](defaultftpcachepolicy-element-network-settings.md)|Необязательный элемент.<br /><br /> Описывает, активно ли кэширование FTP и описывает политику кэширования по умолчанию.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[system.net](system-net-element-network-settings.md)|Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.|  
  
## <a name="example"></a>Пример  
 В следующем примере показано, как отключить все кэширование.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Net.Cache?displayProperty=nameWithType>
- [Схема параметров сети](index.md)
