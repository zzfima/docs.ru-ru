---
title: '&lt;время ожидания&gt;'
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: 42f4db1d954834cbfa3c526328cca45443751506
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54629662"
---
# <a name="lttimeoutsgt"></a>&lt;время ожидания&gt;
Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.  
  
 \<system.ServiceModel>  
\<Клиент >  
\<endpoint>  
\<узел >  
\<время ожидания >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<timeOuts closeTimeout="TimeSpan"
          openTimeout="TimeSpan" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`closeTimeout`|Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции закрытия узла службы.|  
|`openTimeout`|Значение <xref:System.TimeSpan>, которое задает временной интервал, выделенный для операции открытия узла службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<узел >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Элемент конфигурации, который задает параметры узла службы.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
