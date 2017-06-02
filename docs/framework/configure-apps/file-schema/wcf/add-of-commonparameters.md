---
title: "&lt;add&gt; для &lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3713bf25-20c8-455f-bb85-de46b6487932
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;add&gt; для &lt;commonParameters&gt;
Определяет пару параметров «имя\-значение», которые используются глобально в нескольких службах.  Как правило, этот параметр включает строку подключения базы данных, которая может совместно использоваться долговременными службами.  
  
## Синтаксис  
  
```  
  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Имя параметра, заданного для службы.|  
|value|Значение параметра, заданного для службы.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<commonParameters\>](http://msdn.microsoft.com/ru-ru/d0e1e6fc-985a-4713-b7da-194e30dfab4c)|Коллекция общих параметров, используемых службой.  Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.|  
  
## Заметки  
 Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
 Для служб, фиксирующих рабочие пакеты в постоянных хранилищах, таких как <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> и <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>, можно включить режим повторения попытки транзакции, используя параметр `EnableRetries`, как показано в следующем примере.  
  
```  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 Учтите, что параметр `EnableRetries` может быть задан и на глобальном уровне \(как показано в разделе *CommonParameters*\), и для отдельных служб, поддерживающих `EnableRetries` \(как показано в разделе *Services*\).  
  
 Дополнительные сведения об использовании файла конфигурации для управления поведением объекта <xref:System.Workflow.Runtime.WorkflowRuntime> ведущего приложения Windows Workflow Foundation см. в разделе [Workflow Configuration Files](http://msdn.microsoft.com/ru-ru/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909).  
  
## Пример  
  
```  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>   
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>   
 [Workflow Configuration Files](http://msdn.microsoft.com/ru-ru/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)   
 [\<commonParameters\>](http://msdn.microsoft.com/ru-ru/d0e1e6fc-985a-4713-b7da-194e30dfab4c)