---
title: <defaultPorts>
ms.date: 03/30/2017
ms.assetid: 725d4ee5-bd46-4f0e-9c20-30ba75d6eb2c
ms.openlocfilehash: 595970a56e05c4fc1c9b2c0eb669ec3b3a120fe1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55262397"
---
# <a name="defaultports"></a>\<defaultPorts>
Коллекция портов по умолчанию со списком конечных точек связи по умолчанию, которые прослушивает клиентское приложение.  
  
\<system.ServiceModel>  
\<варианты поведения >  
\<serviceBehaviors >  
\<поведение >  
\<useRequestHeadersForMetadataAddress>  
\<defaultPorts>  
  
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
 Отсутствует.  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<Добавить > из \<defaultPorts >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-defaultports.md)|Конечная точка связи по умолчанию, которую прослушивает клиентское приложение.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<useRequestHeadersForMetadataAddress >](../../../../../docs/framework/configure-apps/file-schema/wcf/userequestheadersformetadataaddress.md)|Список портов по умолчанию.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Configuration.DefaultPortElementCollection>
