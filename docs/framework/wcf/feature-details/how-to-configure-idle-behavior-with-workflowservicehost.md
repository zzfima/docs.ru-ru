---
title: Как настроить неактивное поведение с помощью WorkflowServiceHost
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 55cc10357e8ae6b5458ca3440e1728cb578208b3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="a1608-102">Как настроить неактивное поведение с помощью WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="a1608-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="a1608-103">Рабочие процессы переходят в режим бездействия, когда обнаруживают закладку, выполнение которой должно быть возобновлено по внешнему сигналу, например когда экземпляр рабочего процесса ожидает доставки сообщения с помощью действия <xref:System.ServiceModel.Activities.Receive> .</span><span class="sxs-lookup"><span data-stu-id="a1608-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="a1608-104">Поведение<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> позволяет задать время между переходом экземпляра службы в неактивное состояние и его сохранением или выгрузкой.</span><span class="sxs-lookup"><span data-stu-id="a1608-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="a1608-105">Содержит два свойства, которые позволяют задавать значения для этих периодов времени.</span><span class="sxs-lookup"><span data-stu-id="a1608-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="a1608-106">Атрибут<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> определяет период времени между переходом экземпляра службы Workflow Service в состояние бездействия и сохранением экземпляра службы Workflow Service.</span><span class="sxs-lookup"><span data-stu-id="a1608-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="a1608-107">Свойство<xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> определяет период времени между переходом экземпляра службы Workflow Service в состояние бездействия и моментом выгрузки экземпляра рабочего процесса, где выгрузка означает сохранение экземпляра в хранилище экземпляров с удалением из памяти.</span><span class="sxs-lookup"><span data-stu-id="a1608-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="a1608-108">В этом разделе описана настройка <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a1608-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="a1608-109">Настройка WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="a1608-109">To configure WorkflowIdleBehavior</span></span>  
  
1.  <span data-ttu-id="a1608-110">Добавить <`workflowIdle`> элемента <`behavior`> элемента <`serviceBehaviors`> элемента, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="a1608-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="a1608-111">Атрибут `timeToUnload` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и выгрузкой службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a1608-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="a1608-112">Атрибут `timeToPersist` определяет период времени между переходом экземпляра службы рабочего процесса в состояние бездействия и сохранением экземпляра службы рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="a1608-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="a1608-113">Значение `timeToUnload` по умолчанию составляет 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="a1608-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="a1608-114">По умолчанию для объекта `timeToPersist` установлено значение <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="a1608-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="a1608-115">Если ожидающие экземпляры нужно оставить в памяти, но сохранить для надежности, задайте значения так, чтобы выполнялось неравенство `timeToPersist` < `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="a1608-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="a1608-116">Если требуется, чтобы ожидающие экземпляры не выгружались, задайте параметру `timeToUnload` значение <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="a1608-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a1608-117"> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, в разделе [расширяемость узла службы рабочего процесса](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="a1608-117"> <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1608-118">В предыдущем образце конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="a1608-118">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="a1608-119">Дополнительные сведения см. в разделе [упрощенной конфигурации](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a1608-119">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="a1608-120">Изменение поведения во время ожидания в коде</span><span class="sxs-lookup"><span data-stu-id="a1608-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="a1608-121">В следующем примере программным способом изменяется время ожидания перед сохранением и выгрузкой.</span><span class="sxs-lookup"><span data-stu-id="a1608-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a1608-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a1608-122">See Also</span></span>  
 [<span data-ttu-id="a1608-123">Расширяемость узла службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a1608-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="a1608-124">Упрощенная конфигурация</span><span class="sxs-lookup"><span data-stu-id="a1608-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="a1608-125">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="a1608-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
