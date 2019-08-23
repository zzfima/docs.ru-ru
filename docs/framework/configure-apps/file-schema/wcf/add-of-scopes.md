---
title: <add> из <scopes>
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: b190cb72e21d47bdc62aab2daba0f6eea1ee04ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926634"
---
# <a name="add-of-scopes"></a>\<Добавление > \<областей >
Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.  
  
\<системой. > ServiceModel  
\<> поведения  
\<endpointBehaviors >  
\<> поведения  
\<Ендпоинтдисковери >  
\<области >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enable="Boolean">
        <scopes>
          <add scope="URI" />
        </scopes>
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|область|URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<области >](scopes.md)|Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
