---
title: <timeOuts>
ms.date: 03/30/2017
ms.assetid: 7fccd436-b326-48ec-8de1-c16817a09e0d
ms.openlocfilehash: b159488efa2a80a9dea625e4c6dfe2f215dfc457
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939187"
---
# <a name="timeouts"></a>\<> времени ожидания
Элемент конфигурации, который задает допустимый интервал времени для открытия или закрытия узла службы.  
  
 \<системой. > ServiceModel  
\<> клиента  
\<> конечной точки  
\<> узла  
\<> времени ожидания  
  
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
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> узла](host.md)|Элемент конфигурации, который задает параметры узла службы.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.HostElement>
- <xref:System.ServiceModel.ServiceHost>
- [Размещение](../../../wcf/feature-details/hosting.md)
