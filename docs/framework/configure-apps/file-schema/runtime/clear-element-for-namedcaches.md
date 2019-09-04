---
title: Элемент <clear> для <namedCaches>
ms.date: 03/30/2017
helpviewer_keywords:
- <clear> element for <namedCaches>
- clear element for <namedCaches>
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
ms.openlocfilehash: bcc0e23f0c47ad3a98430e36da31d39612caa3c9
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252761"
---
# <a name="clear-element-for-namedcaches"></a>\<Очистка элемента > для \<намедкачес >
Очищает все `namedCache` записи `namedCaches` в коллекции для кэша памяти.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Runtime. Caching >** ](system-runtime-caching-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<memoryCache >** ](memorycache-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Намедкачес >** ](namedcaches-element-cache-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<очистить >**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
    <clear name="Default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 `None`  
  
### <a name="child-elements"></a>Дочерние элементы  
 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<namedCaches>](namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованных <xref:System.Runtime.Caching.MemoryCache> экземпляров.|  
  
## <a name="remarks"></a>Примечания  
 Элемент очищает все `namedCache` записи в именованной коллекции кэша для кэша памяти. `clear` `clear` Элемент можно использовать перед тем, как `add` использовать элемент для добавления новой именованной записи кэша, чтобы быть уверенным в том, что в коллекции нет других именованных кэшей.  
  
## <a name="see-also"></a>См. также

- [\<Элемент > Намедкачес (параметры кэша)](namedcaches-element-cache-settings.md)
