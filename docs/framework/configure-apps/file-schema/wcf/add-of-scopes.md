---
title: '&lt;add&gt; для &lt;scopes&gt;'
ms.date: 03/30/2017
ms.assetid: 0563a7d8-fc84-4c85-9066-af32665857c2
ms.openlocfilehash: e2bf649259d6ccb0e55428ab3619fe561d051ff7
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54146244"
---
# <a name="ltaddgt-of-ltscopesgt"></a>&lt;add&gt; для &lt;scopes&gt;
Добавляет URI пользовательский области, который при выполнении запроса можно использовать для фильтрации конечных точек службы.  
  
\<система. ServiceModel >  
\<варианты поведения >  
\<endpointBehaviors >  
\<поведение >  
\<endpointDiscovery >  
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
|область действия|URI, содержащий сведения об области для конечной точки, которую можно использовать в критериях соответствия при поиске служб.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<области >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Содержит коллекцию элементов конфигурации, указывающие идентификаторы URI пользовательских областей, которые можно использовать для фильтрации конечных точек службы во время выполнения запроса.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
