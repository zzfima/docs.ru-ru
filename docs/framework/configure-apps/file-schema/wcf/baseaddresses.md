---
title: '&lt;Среди базовых адресов&gt;'
ms.date: 03/30/2017
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
ms.openlocfilehash: 0af5dee41c6adf560c90874e6e9a44b62c5decc6
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147360"
---
# <a name="ltbaseaddressesgt"></a>&lt;Среди базовых адресов&gt;
Представляет коллекцию элементов `baseAddress`, которые являются базовыми адресам для узла службы в резидентной среде. Если указан базовый адрес, конечные точки можно настроить, используя относительные (по отношению к базовому адресу) адреса.  
  
 \<система. ServiceModel >  
\<Клиент >  
\<Конечная точка >  
\<узел >  
\<baseAddresses >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<baseAddresses>
  <add baseAddress="string" />
</baseAddresses>
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md)|Элемент конфигурации, который задает базовые адреса, используемые узлом службы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<узел >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Элемент конфигурации, который задает параметры узла службы.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
