---
title: Практическое руководство. Как настроить отслеживание с помощью WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 5781878270272f5ef894c68dc23b9433029e1d41
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968494"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="b197c-102">Практическое руководство. Как настроить отслеживание с помощью WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="b197c-102">How to: Configure Tracking with WorkflowServiceHost</span></span>
<span data-ttu-id="b197c-103">В этом разделе описывается настройка отслеживания для рабочего процесса платформы [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)], размещенного в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b197c-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="b197c-104">Она осуществляется с помощью файла Web.config, в котором задается поведение службы.</span><span class="sxs-lookup"><span data-stu-id="b197c-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="b197c-105">Настройка отслеживания в конфигурации</span><span class="sxs-lookup"><span data-stu-id="b197c-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="b197c-106">Добавьте с помощью элемента <`behavior`> в файл конфигурации, как показано в следующем примере. <xref:System.Activities.Tracking.EtwTrackingParticipant></span><span class="sxs-lookup"><span data-stu-id="b197c-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
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
    > <span data-ttu-id="b197c-107">В предыдущем образце конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="b197c-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="b197c-108">Дополнительные сведения см. в разделе [упрощенная конфигурация](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="b197c-109">В предыдущем образце конфигурации добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b197c-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b197c-110">Профили отслеживания создаются в элементе <`trackingProfile`> в элементе <`tracking`>.</span><span class="sxs-lookup"><span data-stu-id="b197c-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="b197c-111">Профиль отслеживания содержит запросы отслеживания, позволяющие участнику отслеживания подписываться на события рабочего процесса, создаваемые в момент изменения состояния экземпляра рабочего процесса в ходе выполнения.</span><span class="sxs-lookup"><span data-stu-id="b197c-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="b197c-112">Создание профиля отслеживания показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b197c-112">The following example shows how to create a tracking profile.</span></span>  
  
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
  
     <span data-ttu-id="b197c-113">Дополнительные сведения о профилях отслеживания см. в разделе [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-113">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b197c-114">Дополнительные сведения об отслеживании в целом см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="b197c-115">Настройка отслеживания в коде</span><span class="sxs-lookup"><span data-stu-id="b197c-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="b197c-116">С помощью объекта <xref:System.Activities.Tracking.EtwTrackingParticipant> добавьте в код участника <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior>, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="b197c-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="b197c-117">В предыдущем образце кода добавляется участник <xref:System.Activities.Tracking.EtwTrackingParticipant> и задается имя профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="b197c-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="b197c-118">Профили отслеживания создаются в элементе <`trackingProfile`> в элементе <`tracking`>, как показано в предыдущем разделе.</span><span class="sxs-lookup"><span data-stu-id="b197c-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="b197c-119">Дополнительные сведения о профилях отслеживания см. в разделе [Профили отслеживания](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-119">For more information about tracking profiles, see [Tracking Profiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="b197c-120">Дополнительные сведения об отслеживании в целом см. в разделе [Отслеживание и трассировка рабочих процессов](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="b197c-121">Пример настройки отслеживания программным способом см. в разделе [Настройка отслеживания для рабочего процесса](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="b197c-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b197c-122">См. также</span><span class="sxs-lookup"><span data-stu-id="b197c-122">See also</span></span>

- [<span data-ttu-id="b197c-123">Упрощенная конфигурация служб WCF</span><span class="sxs-lookup"><span data-stu-id="b197c-123">Simplified Configuration for WCF Services</span></span>](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="b197c-124">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="b197c-124">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [<span data-ttu-id="b197c-125">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="b197c-125">Tracking Profiles</span></span>](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
