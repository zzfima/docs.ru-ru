---
title: '&lt;add&gt; для &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 2cc7cce62082317bb86218d68bd2881b74649771
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54670190"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a>&lt;add&gt; для &lt;backupList&gt;
Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.  
  
 \<system.serviceModel>  
\<Маршрутизация >  
\<backupLists >  
\<backupList >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|имя|Строка, задающая имя резервной конечной точки.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
