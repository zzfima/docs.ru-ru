---
title: "&lt;add&gt; для &lt;services&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6bdc4590-aa9c-4ec8-9345-879d780cd141
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# &lt;add&gt; для &lt;services&gt;
Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], основанных на рабочих процессах.  Это элемент типа <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## Синтаксис  
  
```  
  
<workflowRuntime>  
   <services>  
      <add type="String"/>  
   </services>  
</workflowRuntime>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|тип|Строка, задающая имя типа с указанием сборки для службы, которую необходимо инициализировать.  Заданная служба должна соответствовать определенным правилам, связанным с сигнатурами их конструкторов.  Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<службы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/services-of-workflowruntime.md)|Коллекция служб, добавляемая в механизм <xref:System.Workflow.Runtime.WorkflowRuntime>.  Элементы имеют тип <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  Службы, указанные в коллекции, инициализируются механизмом среды выполнения рабочих процессов и добавляются в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.  Таким образом, службы, указанные в коллекции, должны отвечать определенным правилам в отношении сигнатур конструкторов.  Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.|  
  
## Заметки  
 Служба, указанная в данном элементе, инициализируется механизмом среды выполнения рабочих процессов и добавляется в службы при вызове соответствующего конструктора <xref:System.Workflow.Runtime.WorkflowRuntime>.  Поэтому заданная служба должна соответствовать определенным правилам, относящимся к сигнатурам конструкторов.  Дополнительные сведения см. в разделе <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>.  
  
## Пример  
  
```  
<serviceBehaviors>  
   <behavior name="ServiceBehavior">  
      <workflowRuntime name="WorkflowServiceHostRuntime"  
                       validateOnCreate="true"  
                       enablePerformanceCounters="true">  
         <services>  
             <add type="NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common.TestPersistenceService.FilePersistenceService, NetFx.Checkin.Scenario.WorkflowServices.WorkflowBasedServices.Common"/>  
         </services>  
      </workflowRuntime>  
   </behavior>  
</serviceBehaviors>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 [Workflow Configuration Files](http://msdn.microsoft.com/ru-ru/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)