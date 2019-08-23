---
title: Раздел <extensions>
ms.date: 03/30/2017
ms.assetid: 53a59fb6-dede-47ec-9384-b3c2e8f0c1fa
ms.openlocfilehash: 4c8b5fe6eef1863ee3f02cb761a3aac61406e446
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918970"
---
# <a name="extensions-section"></a>\<раздел > расширений
Данный раздел конфигурации содержит коллекцию расширений, которые позволяют пользователю создавать пользовательские привязки, поведения и другие возможности расширений.  
  
\<системой. > ServiceModel  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
    </bindingExtensions>
    <behaviorExtensions>
    </behaviorExtensions>
    <bindingElementExtensions>
    </bindingElementExtensions>
    <endpointExtensions>
    </endpointExtensions>
  </extensions>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Бехавиорекстенсионс >](behaviorextensions.md)|Этот раздел содержит дочерние элементы, которые задают расширения поведений, которые позволяют пользователю настроить поведения службы или конечной точки.|  
|[\<Биндинжелементекстенсионс >](bindingelementextensions.md)|В этом разделе описывается, как обеспечивается использование пользовательского элемента привязки в файле конфигурации компьютера или приложения.|  
|[\<Биндинжекстенсионс >](bindingextensions.md)|Этот раздел содержит дочерние элементы, которые задают расширения привязки, которые позволяют пользователю настроить привязки.|  
|[\<Ендпоинтекстенсионс >](endpointextensions.md)|Этот раздел содержит дочерние элементы, которые регистрируют стандартные конечные точки.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|system.ServiceModel|Корневой элемент всех элементов конфигурации WCF.|
