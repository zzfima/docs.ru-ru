---
title: '&lt;clientVia&gt;'
ms.date: 03/30/2017
ms.assetid: c27ee94e-babd-459b-9574-2a6d67d11314
ms.openlocfilehash: 48e56b79f47e84122ddd4d7f55d50044510bfa66
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149063"
---
# <a name="ltclientviagt"></a>&lt;clientVia&gt;
Задает универсальный код ресурса (URI), для которого необходимо создать канал транспорта. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Description.ClientViaBehavior>.  
  
 \<система. ServiceModel >  
\<варианты поведения >  
\<endpointBehaviors >  
\<поведение >  
\<clientVia >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<clientVia viaUri="String" />
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`viaUri`|Строка, задающая универсальный код ресурса (URI), который указывает маршрут для сообщения.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Задает поведение конечной точки.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ClientViaElement>  
 <xref:System.ServiceModel.Description.ClientViaBehavior>
