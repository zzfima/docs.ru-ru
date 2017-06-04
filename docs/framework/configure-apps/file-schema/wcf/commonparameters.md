---
title: "&lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;commonParameters&gt;
Представляет коллекцию параметров, используемых глобально в нескольких службах.  Эта коллекция, как правило, включает строку подключения базы данных, которая может совместно использоваться постоянными службами.  
  
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
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|Добавляет в коллекцию пару общих параметров вида «имя\-значение», используемых службами.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<workflowRuntime\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|Задает параметры для экземпляра <xref:System.Workflow.Runtime.WorkflowRuntime> для размещения служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)], основанных на рабочих процессах.|  
  
## Заметки  
 Элемент `<commonParameters>` определяет любые параметры, которые используются глобально несколькими службами, например `ConnectionString` при использовании <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>.  
  
> [!NOTE]
>  Служба отслеживания SQL не использует постоянно значение `ConnectionString`, если оно задано в разделе `<commonParameters>`.  В некоторых операциях, например при извлечении свойства `StateMachineWorkflowInstance.StateHistory`, может произойти ошибка.  Чтобы обойти эту проблему, задайте атрибут `ConnectionString` в разделе конфигурации для поставщика отслеживания, как показано в следующем примере.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
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
  
 Следует заметить, что параметр `EnableRetries` может быть задан как на глобальном уровне \(как показано в разделе *Общие параметры*\), так и для отдельных служб, поддерживающих `EnableRetries` \(как показано в разделе *Службы*\).  
  
 В следующем примере кода показано, как изменять общие параметры программным образом.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
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
 [\<добавление;\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)