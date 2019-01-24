---
title: Как выполнить настроить отслеживание с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 8ed8775a8eb13a8e69566c1d413dcd2eba6d8b6c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577575"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Как выполнить настроить отслеживание с помощью WorkflowServiceHost
В этом разделе описывается настройка отслеживания для рабочего процесса платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Она осуществляется с помощью файла Web.config, в котором задается поведение службы.  
  
### <a name="configure-tracking-in-configuration"></a>Настройка отслеживания в конфигурации  
  
1.  Добавьте участника <xref:System.Activities.Tracking.EtwTrackingParticipant> с помощью элемента <`behavior`> в файле конфигурации, как показано в следующем примере.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
    ```  
  
    > [!NOTE]
    >  В предыдущем образце конфигурации используется упрощенная конфигурация. Дополнительные сведения см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     В предыдущем образце конфигурации добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания. Профили отслеживания создаются в элементе <`trackingProfile`> внутри элемента <`tracking`>. Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в момент изменения состояния экземпляра рабочего процесса в ходе выполнения. Создание профиля отслеживания показано в следующем примере.  
  
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
  
     Дополнительные сведения о профилях отслеживания см. в разделе [профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     Дополнительные сведения об отслеживании в целом см. в разделе [отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).  
  
### <a name="configure-tracking-in-code"></a>Настройка отслеживания в коде  
  
1.  С помощью объекта <xref:System.Activities.Tracking.EtwTrackingParticipant> добавьте в код участника <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     В предыдущем образце кода добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания. Профили отслеживания создаются в элементе <`trackingProfile`> внутри элемента <`tracking`>, как показано в предыдущем разделе.  
  
     Дополнительные сведения о профилях отслеживания см. в разделе [профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
     Дополнительные сведения об отслеживании в целом см. в разделе [отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md). Например, настроить отслеживание программным способом см. в разделе [Настройка отслеживания для рабочего процесса](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
## <a name="see-also"></a>См. также
- [Упрощенная конфигурация служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [Службы рабочих процессов](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
