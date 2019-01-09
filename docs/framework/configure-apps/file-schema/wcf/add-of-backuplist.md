---
title: '&lt;add&gt; для &lt;backupList&gt;'
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 4a8eb3df9be6b6b5bfe43aee330f3174ddca66ab
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54151479"
---
# <a name="ltaddgt-of-ltbackuplistgt"></a>&lt;add&gt; для &lt;backupList&gt;
Представляет элемент конфигурации, в котором задается элемент резервной конечной точки.  
  
 \<system.serviceModel >  
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Содержит список конечных точек, которые вы хотите использовать служба маршрутизации в случае, если основная конечная точка становится недоступной.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType> 
