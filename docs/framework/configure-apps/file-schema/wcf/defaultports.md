---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 462a06e5a773310b6364838ae2ebc14da0a2ee1b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925888"
---
# <a name="defaultports"></a>\<Дефаултпортс >
Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.  
  
\<системой. > ServiceModel  
\<> поведения  
\<serviceBehaviors >  
\<> поведения  
\<Усерекуессеадерсформетадатааддресс >  
\<Дефаултпортс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<useRequestHeadersForMetadataAddress>
  <defaultPorts>
    <add scheme="http"
         port="integer" />
  </defaultPorts>
</useRequestHeadersForMetadataAddress>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Добавление > \<> дефаултпортс](add-of-defaultports.md)|Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Усерекуессеадерсформетадатааддресс >](userequestheadersformetadataaddress.md)|Список портов по умолчанию.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
