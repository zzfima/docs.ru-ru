---
title: Практическое руководство. Как настроить отслеживание с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: e0631cdb47bc88f7f588f4dfe6c44ea3d44f4e60
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59336568"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="d630b-102">Практическое руководство. Как настроить отслеживание с помощью WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="d630b-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="d630b-103">В этом разделе описывается настройка отслеживания для рабочего процесса платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="d630b-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="d630b-104">Она осуществляется с помощью файла Web.config, в котором задается поведение службы.</span><span class="sxs-lookup"><span data-stu-id="d630b-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="d630b-105">Настройка отслеживания в конфигурации</span><span class="sxs-lookup"><span data-stu-id="d630b-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="d630b-106">Добавить <xref:System.Activities.Tracking.EtwTrackingParticipant> с помощью <`behavior`> элемент в файле конфигурации, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d630b-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
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
    >  <span data-ttu-id="d630b-107">В предыдущем образце конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="d630b-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="d630b-108">Дополнительные сведения см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="d630b-109">В предыдущем образце конфигурации добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d630b-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="d630b-110">Профили отслеживания создаются в <`trackingProfile`> элемента <`tracking`> элемента.</span><span class="sxs-lookup"><span data-stu-id="d630b-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="d630b-111">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в момент изменения состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="d630b-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="d630b-112">Создание профиля отслеживания показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d630b-112">The following example shows how to create a tracking profile.</span></span>  
  
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
  
     <span data-ttu-id="d630b-113">Дополнительные сведения о профилях отслеживания см. в разделе [профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="d630b-114">Дополнительные сведения об отслеживании в целом см. в разделе [отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="d630b-115">Настройка отслеживания в коде</span><span class="sxs-lookup"><span data-stu-id="d630b-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="d630b-116">С помощью объекта <xref:System.Activities.Tracking.EtwTrackingParticipant> добавьте в код участника <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="d630b-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="d630b-117">В предыдущем образце кода добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="d630b-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="d630b-118">Профили отслеживания создаются в <`trackingProfile`> элемента <`tracking`> элемента, как показано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="d630b-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="d630b-119">Дополнительные сведения о профилях отслеживания см. в разделе [профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="d630b-120">Дополнительные сведения об отслеживании в целом см. в разделе [отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="d630b-121">Например, настроить отслеживание программным способом см. в разделе [Настройка отслеживания для рабочего процесса](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="d630b-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d630b-122">См. также</span><span class="sxs-lookup"><span data-stu-id="d630b-122">See also</span></span>

- [<span data-ttu-id="d630b-123">Упрощенная конфигурация служб WCF</span><span class="sxs-lookup"><span data-stu-id="d630b-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="d630b-124">Службы рабочего процесса</span><span class="sxs-lookup"><span data-stu-id="d630b-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="d630b-125">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="d630b-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
