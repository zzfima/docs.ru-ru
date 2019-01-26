---
title: '&lt;Удалить&gt; элемент для &lt;namedCaches&gt;'
ms.date: 03/30/2017
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
ms.openlocfilehash: ceeef00cb688c725cc595582fb6845b9e3fa9b92
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083396"
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a>&lt;Удалить&gt; элемент для &lt;namedCaches&gt;
Удаляет элемент именованного кэша из коллекции `namedCaches` для кэша памяти.  
  
 \<system.runtime.caching>  
\<memoryCache>  
\<namedCaches>  
\<Удалить >  
  
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
 `remove` Приводит к удалению `namedCache` запись из коллекции именованных кэшей для кэша памяти.  
  
## <a name="see-also"></a>См. также
- [\<namedCaches > (параметры кэша)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
