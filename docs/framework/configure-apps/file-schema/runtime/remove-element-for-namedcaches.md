---
title: '&lt;Удалить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6ffaea24910a6b8f4a120d6b72219bff592fab17
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a>&lt;Удалить&gt; элемент для &lt;namedCaches&gt;
Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.  
  
 \<System.Runtime.Caching >  
\<memoryCache >  
\<namedCaches >  
\<Удалите >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>Тип  
 `None`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 `None`  
  
### <a name="child-elements"></a>Дочерние элементы  
 `None`  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|Содержит коллекцию параметров конфигурации для именованного <xref:System.Runtime.Caching.MemoryCache> экземпляров.|  
  
## <a name="remarks"></a>Примечания  
 `remove` Элемент удаляет `namedCache` записи из коллекции именованных кэшей для кэша памяти.  
  
## <a name="see-also"></a>См. также  
 [\<namedCaches > элемент (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
