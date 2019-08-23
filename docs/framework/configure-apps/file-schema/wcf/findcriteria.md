---
title: <findCriteria>
ms.date: 03/30/2017
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
ms.openlocfilehash: eb8ff3905f7696f4c71a79e31db1b8f82c9f0d3b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925584"
---
# <a name="findcriteria"></a>\<findCriteria >
Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения. Критерии можно сгруппировать в критерии поиска (указав интересующие вас службы) и найти критерии завершения (срок поиска в прошлом).  
  
 \<системой. > ServiceModel  
\<Стандардендпоинтс >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
        <discoveryClientSettings discoveryEndpoint="String">
          <findCriteria duration="TimeSpan"
                        maxResults="Integer"
                        scopeMatchBy="Uri">
            <contractTypeNames>
              <add name="String"
                   namespace="String" />
            </contractTypeNames>
            <extensions />
            <scopes>
              <add scope="URI" />
            </scopes>
          </findCriteria>
        </discoveryClientSettings>
      </standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|длительность|Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети. Значение времени ожидания по умолчанию - 20 секунд.|  
|maxResults|Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет. Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.|  
|scopeMatchBy|URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.<br /><br /> Поддерживаются пять правил сопоставления областей. Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`. Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Контракттипенамес >](contracttypenames.md)|Коллекция элементов конфигурации, содержащих имена типов контрактов службы рабочего процесса.|  
|\<расширения > \<> findCriteria|Коллекция объектов элементов XML, предоставляющих расширения.|  
|[\<области >](scopes.md)|Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.<br /><br /> Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Стандардендпоинтс >](standardendpoints.md)|Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Discovery.FindCriteria>
- <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>
