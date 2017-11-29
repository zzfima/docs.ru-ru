---
title: "&lt;среди базовых адресов&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78918102-2898-46e0-9ea8-6b8afe65603e
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4bf698b64b528b0ea109223a2d94e6725c8ce6b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltbaseaddressesgt"></a>&lt;среди базовых адресов&gt;
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
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<узел >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|Элемент конфигурации, который задает параметры узла службы.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
