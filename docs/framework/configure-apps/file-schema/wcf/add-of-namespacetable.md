---
title: '&lt;add&gt; для &lt;namespaceTable&gt;'
ms.date: 03/30/2017
ms.assetid: cf7b5b75-63bd-49a6-abac-4bfdab377e36
ms.openlocfilehash: ef4f1c46a0ee3b94e5548b752e4e0a6a759fd45b
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149518"
---
# <a name="ltaddgt-of-ltnamespacetablegt"></a>&lt;add&gt; для &lt;namespaceTable&gt;
Представляет элемент конфигурации, содержащий пространство имен, используемое в качестве префикса сопоставления, которое затем можно использовать в фильтрах XPath для маршрутизации.  
  
 \<system.serviceModel >  
\<Маршрутизация >  
\<namespaceTable >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<routing>
  <namespaceTable>
    <add namespace="String"
         prefix="String" />
  </namespaceTable>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|namespace|Строка, содержащая пространство имен.|  
|prefix|Строка, содержащая префикс этого пространства имен.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<namespaceTable >](../../../../../docs/framework/configure-apps/file-schema/wcf/namespacetable.md)|Представляет секцию конфигурации для определения набора элементов, содержащих пространство имен для использования в качестве префиксов сопоставлений, которые в дальнейшем могут быть использованы в фильтрах XPath для маршрутизации.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Routing.Configuration.NamespaceElement?displayProperty=nameWithType>    
