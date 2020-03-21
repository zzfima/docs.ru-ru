---
title: Как настроить отслеживание с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 962dfda9fc5780cc3ac7211464bb3a9be8b7fa90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185067"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Как настроить отслеживание с помощью WorkflowServiceHost
В этом разделе описывается настройка отслеживания для рабочего процесса платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Она осуществляется с помощью файла Web.config, в котором задается поведение службы.  
  
### <a name="configure-tracking-in-configuration"></a>Настройка отслеживания в конфигурации  
  
1. Добавьте <xref:System.Activities.Tracking.EtwTrackingParticipant> использование `behavior` элемента <> в файл конфигурации, как показано в следующем примере.  
  
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
    > В предыдущем образце конфигурации используется упрощенная конфигурация. Для получения дополнительной информации [см.](../../../../docs/framework/wcf/simplified-configuration.md)  
  
     В предыдущем образце конфигурации добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания. Профили отслеживания создаются `trackingProfile` в элементе `tracking`> <в элементе <>. Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в момент изменения состояния экземпляра рабочего процесса в ходе выполнения. Создание профиля отслеживания показано в следующем примере.  
  
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
  
     Для получения дополнительной информации о [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)профилях отслеживания см.  
  
     Для получения дополнительной информации о отслеживании в целом, [см.](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
  
### <a name="configure-tracking-in-code"></a>Настройка отслеживания в коде  
  
1. С помощью объекта <xref:System.Activities.Tracking.EtwTrackingParticipant> добавьте в код участника <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>, как показано в следующем примере.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     В предыдущем образце кода добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания. Профили отслеживания создаются `trackingProfile` в элементе `tracking` <> элементе в элементе <>, как показано в предыдущем разделе.  
  
     Для получения дополнительной информации о [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)профилях отслеживания см.  
  
     Для получения дополнительной информации о отслеживании в целом, [см.](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md) На примере настройки отслеживания программно [см. Настройка отслеживания для рабочего процесса.](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)  
  
## <a name="see-also"></a>См. также раздел

- [Упрощенная конфигурация служб WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [Службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
