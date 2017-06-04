---
title: "Как настроить отслеживание с помощью WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# Как настроить отслеживание с помощью WorkflowServiceHost
В этом разделе описывается настройка отслеживания для рабочего процесса платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  Она осуществляется с помощью файла Web.config, в котором задается поведение службы.  
  
### Настройка отслеживания в конфигурации  
  
1.  Добавьте участника <xref:System.Activities.Tracking.EtwTrackingParticipant> с помощью элемента \<`behavior`\> в файле конфигурации, как показано в следующем примере.  
  
    ```  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
  
    ```  
  
    > [!NOTE]
    >  В предыдущем образце конфигурации используется упрощенная конфигурация.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     В предыдущем образце конфигурации добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.  Профили отслеживания создаются в элементе \<`trackingProfile`\> внутри элемента \<`tracking`\>.  Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в момент изменения состояния экземпляра рабочего процесса в ходе выполнения.  Создание профиля отслеживания показано в следующем примере.  
  
    ```xml  
    <system.serviceModel>  
        <tracking>   
         <trackingProfile name="Sample Tracking Profile">  
            <workflow activityDefinitionId="*">  
               <workflowInstanceQueries>  
                 <workflowInstanceQuery>  
                    <states>  
                       <state name="Started"/>  
                       <state name="Completed"/>  
                    </states>  
                </workflowInstanceQuery>  
             </workflowInstanceQueries>  
           </workflow>  
         </trackingProfile>   
       </tracking>  
    </system.serviceModel>  
  
    ```  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] профилях отслеживания см. в разделе [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] отслеживании в целом см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
### Настройка отслеживания в коде  
  
1.  С помощью объекта <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> добавьте в код участника <xref:System.Activities.Tracking.EtwTrackingParticipant>, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     В предыдущем образце кода добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.  Профили отслеживания создаются в элементе \<`trackingProfile`\> внутри элемента \<`tracking`\>, как показано в предыдущем разделе.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] профилях отслеживания см. в разделе [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] отслеживании в целом см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  Пример того, как настроить отслеживание программным способом, см. в разделе [Настройка отслеживания рабочего процесса](../../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md).  
  
## См. также  
 [Упрощенная конфигурация служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)   
 [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)