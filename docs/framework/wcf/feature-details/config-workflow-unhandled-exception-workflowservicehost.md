---
title: Практическое руководство. Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: cd3729019b5371b5313bba3814758c723c0d448a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59318751"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="114a3-102">Практическое руководство. Как настроить поведение необработанного исключения рабочего процесса при помощи WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="114a3-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="114a3-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> - это поведение, которое позволяет указать действие, предпринимаемое при возникновении необработанного исключения в рабочем процессе, размещенном в <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="114a3-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="114a3-104">В этом разделе описано, как настроить поведение в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="114a3-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="114a3-105">Настройка WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="114a3-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="114a3-106">Добавьте <`workflowUnhandledException`> элемент в <`behavior`> элемента <`serviceBehaviors`> элемент, с помощью `action` атрибут, чтобы указать действие, выполняемое при возникновении необработанного исключения, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="114a3-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="114a3-107">В предыдущем образце конфигурации используется упрощенная конфигурация.</span><span class="sxs-lookup"><span data-stu-id="114a3-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="114a3-108">Дополнительные сведения см. в разделе [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="114a3-109">Это поведение может быть настроено в коде, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="114a3-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="114a3-110">`action` Атрибут <`workflowUnhandledException`> элемент может быть присвоено одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="114a3-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="114a3-111">**прерывания**</span><span class="sxs-lookup"><span data-stu-id="114a3-111">**abandon**</span></span>  
     <span data-ttu-id="114a3-112">Прерывает работу экземпляра в памяти без обращения к сохраненному состоянию экземпляра (т.е. выполняет откат к последней сохраненной точке).</span><span class="sxs-lookup"><span data-stu-id="114a3-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="114a3-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="114a3-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="114a3-114">Прерывает работу экземпляра в памяти и обновляет приостанавливаемый сохраненный экземпляр.</span><span class="sxs-lookup"><span data-stu-id="114a3-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="114a3-115">**Отмена**</span><span class="sxs-lookup"><span data-stu-id="114a3-115">**cancel**</span></span>  
     <span data-ttu-id="114a3-116">Вызывает отмену обработчиков экземпляра, а затем завершает работу экземпляра в памяти, что может удалить его из хранилища экземпляров.</span><span class="sxs-lookup"><span data-stu-id="114a3-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="114a3-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="114a3-117">**terminate**</span></span>  
     <span data-ttu-id="114a3-118">Завершает работу экземпляра в памяти и удаляет его из хранилища экземпляров.</span><span class="sxs-lookup"><span data-stu-id="114a3-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="114a3-119">Дополнительные сведения о <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, см. в разделе [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="114a3-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="114a3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="114a3-120">See also</span></span>

- [<span data-ttu-id="114a3-121">Расширяемость узла службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="114a3-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)
- [<span data-ttu-id="114a3-122">Службы рабочих процессов</span><span class="sxs-lookup"><span data-stu-id="114a3-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
