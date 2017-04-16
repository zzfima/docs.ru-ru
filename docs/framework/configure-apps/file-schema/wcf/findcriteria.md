---
title: "&lt;findCriteria&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5454cd19-6bf5-4ba8-94d1-f58d10dc1917
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;findCriteria&gt;
Элемент конфигурации, который предоставляет набор критериев, используемых клиентским приложением для поиска службы обнаружения.  Критерии могут быть сгруппированы в критерии поиска \(с указанием искомых служб\) и критерии прекращения поиска \(как долго должен длиться поиск\).  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <standardEndpoints>  
       <dynamicEndpoint>   
          <standardEndpoint>  
             <discoveryClientSettings discoveryEndpoint=”String” >  
               <findCriteria duration=”TimeSpan”  
                  maxResults=”Integer”   
                  scopeMatchBy=”Uri” >  
                  <contractTypeNames>  
                     <add name="String" namespace="String" />  
                  <contractTypeNames>  
                  <extensions />  
                  <scopes>  
                    <add scope="URI"/>  
                  </scopes>  
               </findCriteria>  
             </discoveryClientSettings>  
          <standardEndpoint>  
       </dynamicEndpoint>          
    </standardEndpoints>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|duration|Значение Timespan, указывающее максимальное время ожидания ответа от служб в сети.  Значение по умолчанию \- 20 секунд.|  
|maxResults|Целочисленное значение, указывающее максимальное количество ответов, ожидаемых от служб по сети или через Интернет.  Операция поиска завершается, если максимальное число ответов достигнуто до истечения срока, указанного в атрибуте `duration`.|  
|scopeMatchBy|URI, указывающий алгоритм сопоставления, который используется для сопоставления областей из сообщения зонда с областями из конечной точки.<br /><br /> Поддерживаются пять правил сопоставления областей.  Если правило сопоставления областей не указано, используется `ScopeMatchByPrefix`.  Дополнительные сведения см. в разделе <xref:System.ServiceModel.Discovery.FindCriteria>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<contractTypeNames\>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|Коллекция элементов конфигурации, которые содержат имена типов контрактов службы рабочего процесса.|  
|\<расширения\> из \<критерии\_поиска\>|Коллекция объектов элементов XML, предоставляющих расширения.|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|Коллекция объектов, содержащих абсолютные URI, по которым определяется расположение отдельных служб в ходе операции поиска.<br /><br /> Если найдена определенная служба, URI службы и URI области были успешно сопоставлены, иногда с помощью правил области, предназначенных для преодоления сложностей совпадения.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<standardEndpoints\>](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|Содержит параметры, необходимые приложению для участия в процессе обнаружения служб в качестве клиента.|  
  
## См. также  
 <xref:System.ServiceModel.Discovery.FindCriteria>   
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>