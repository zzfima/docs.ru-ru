---
title: "&lt;workflowInstanceManagement&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 63ac89ba-c844-4ae2-96ae-cd752a90a109
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;workflowInstanceManagement&gt;
Поведение службы, которое позволяет указать параметры, управляющие выполнением экземпляров рабочего процесса, включая сохраняемость, необработанное поведение исключения и неактивное поведение.  
  
## Синтаксис  
  
```  
  
<behaviors>  
  <serviceBehaviors>  
    <behavior name=String">  
      <workflowInstanceManagement authorizedWindowsGroup=”” />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|authorizedWindowsGroup||  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<behavior\> для \<serviceBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/behavior-of-servicebehaviors-of-workflow.md)|Указывает элемент поведения.|  
  
## См. также  
 <xref:System.ServiceModel.Activities.Description.WorkflowInstanceManagementBehavior>   
 <xref:System.ServiceModel.Activities.Configuration.WorkflowInstanceManagementElement>