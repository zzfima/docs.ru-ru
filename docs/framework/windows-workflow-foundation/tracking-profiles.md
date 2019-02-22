---
title: Профили отслеживания
ms.date: 03/30/2017
ms.assetid: 22682566-1cd9-4672-9791-fb3523638e18
ms.openlocfilehash: 95f14cff9c60158f0ce188d031a94870c0b0ac5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559259"
---
# <a name="tracking-profiles"></a><span data-ttu-id="f8523-102">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f8523-102">Tracking Profiles</span></span>
<span data-ttu-id="f8523-103">Профили отслеживания содержат запросы отслеживания, позволяющие участнику подписываться на события рабочего потока, создаваемые в момент изменения состояния экземпляра рабочего процесса во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="f8523-103">Tracking profiles contain tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span>  
  
## <a name="tracking-profiles"></a><span data-ttu-id="f8523-104">Профили отслеживания</span><span class="sxs-lookup"><span data-stu-id="f8523-104">Tracking Profiles</span></span>  
 <span data-ttu-id="f8523-105">С помощью профилей отслеживания можно определять, какие данные отслеживания создаются для экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f8523-105">Tracking profiles are used to specify which tracking information is emitted for a workflow instance.</span></span> <span data-ttu-id="f8523-106">Если этот профиль не указан, создаются все события отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-106">If no profile is specified, then all tracking events are emitted.</span></span> <span data-ttu-id="f8523-107">Если профиль указан, будут создаваться события, определенные в профиле отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-107">If a profile is specified, then the tracking events specified in the profile will be emitted.</span></span> <span data-ttu-id="f8523-108">Исходя из потребностей можно написать профиль с обычной гранулярностью, который будет подписан на небольшой набор изменений состояния высокого уровня в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="f8523-108">Depending on your monitoring requirements, you may write a profile that is very general, which subscribes to a small set of high-level state changes on a workflow.</span></span> <span data-ttu-id="f8523-109">И наоборот, можно создать очень детальный профиль, результирующие события которого будут достаточно подробными для воспроизведения всего потока выполнения в дальнейшем.</span><span class="sxs-lookup"><span data-stu-id="f8523-109">Conversely, you may create a very detailed profile whose resulting events are rich enough to reconstruct a detailed execution flow later.</span></span>  
  
 <span data-ttu-id="f8523-110">Профили отслеживания ведут себя как XML-элементы в файле стандартной конфигурации [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] или как заданный блок кода.</span><span class="sxs-lookup"><span data-stu-id="f8523-110">Tracking profiles manifest themselves as XML elements within a standard [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration file or specified in code.</span></span> <span data-ttu-id="f8523-111">В следующем примере показан профиль отслеживания [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] в файле конфигурации, который позволяет участнику отслеживания подписаться на события рабочих процессов `Started` и `Completed`.</span><span class="sxs-lookup"><span data-stu-id="f8523-111">The following example is of a [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] tracking profile in a configuration file that allows a tracking participant to subscribe to the `Started` and `Completed` workflow events.</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
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
    </profiles>  
  </tracking>  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="f8523-112">В следующем примере показан соответствующий профиль отслеживания, созданный с помощью кода.</span><span class="sxs-lookup"><span data-stu-id="f8523-112">The following example shows the equivalent tracking profile created using code.</span></span>  
  
```csharp  
TrackingProfile profile = new TrackingProfile()  
{  
    Name = "CustomTrackingProfile",  
    Queries =   
    {  
        new WorkflowInstanceQuery()  
        {  
            // Limit workflow instance tracking records for started and  
            // completed workflow states.  
            States = { WorkflowInstanceStates.Started, WorkflowInstanceStates.Completed },  
        }  
    }  
};  
```  
  
 <span data-ttu-id="f8523-113">Записи отслеживания фильтруются посредством режима видимости в рамках профиля отслеживания при помощи атрибута <xref:System.Activities.Tracking.ImplementationVisibility>.</span><span class="sxs-lookup"><span data-stu-id="f8523-113">Tracking records are filtered through the visibility mode within a tracking profile by using the <xref:System.Activities.Tracking.ImplementationVisibility> attribute.</span></span> <span data-ttu-id="f8523-114">Составное действие является действием верхнего уровня, которое содержит другие действия, образующие его реализацию.</span><span class="sxs-lookup"><span data-stu-id="f8523-114">A composite activity is a top-level activity that contains other activities that form its implementation.</span></span> <span data-ttu-id="f8523-115">Режим видимости задает записи отслеживания, созданные из композитных действий в действии рабочего процесса, с целью указания, отслеживаются ли действия, образующие реализацию.</span><span class="sxs-lookup"><span data-stu-id="f8523-115">The visibility mode specifies the tracking records emitted from composite activities within a workflow activity, to specify if activities that form the implementation are being tracked.</span></span>  <span data-ttu-id="f8523-116">Режим видимости применяется на уровне профиля отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-116">The visibility mode applies at the tracking profile level.</span></span> <span data-ttu-id="f8523-117">Фильтрацией записей отслеживания для отдельно взятых действий в рабочем процессе управляют при помощи запросов в профиле отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-117">The filtering of tracking records for individual activities within a workflow is controlled by the queries within the tracking profile.</span></span> <span data-ttu-id="f8523-118">Дополнительные сведения см. в разделе **типы запросов профиля отслеживания** настоящего документа.</span><span class="sxs-lookup"><span data-stu-id="f8523-118">For more information, see the **Tracking Profile Query Types** section in this document.</span></span>  
  
 <span data-ttu-id="f8523-119">Два режима видимости, задаваемые атрибутом `implementationVisibility` в профиле отслеживания, - `RootScope` и `All`.</span><span class="sxs-lookup"><span data-stu-id="f8523-119">The two visibility modes specified by the `implementationVisibility` attribute in the tracking profile are `RootScope` and `All`.</span></span> <span data-ttu-id="f8523-120">Использование режима `RootScope` удаляет записи отслеживания для действий, образующих реализацию действия в том случае, когда композитное действие не является корневым действием в рабочем процессе.</span><span class="sxs-lookup"><span data-stu-id="f8523-120">Using the `RootScope` mode suppresses the tracking records for activities that form the implementation of an activity in the case where a composite activity is not the root of a workflow.</span></span>  <span data-ttu-id="f8523-121">Это предполагает, что, когда действие, реализуемое при помощи других действий, добавляется в рабочий процесс и параметр `implementationVisibility` имеет значение RootScope, будут отслеживаться только события верхнего уровня внутри этого композитного действия.</span><span class="sxs-lookup"><span data-stu-id="f8523-121">This implies that, when an activity that is implemented using other activities is added to a workflow, and the `implementationVisibility` set to RootScope, only the top-level activity within that composite activity is tracked.</span></span> <span data-ttu-id="f8523-122">Если действие является корневым для рабочего процесса, реализация действия - это сам рабочий процесс, а записи отслеживания создаются для действий, образующих реализацию.</span><span class="sxs-lookup"><span data-stu-id="f8523-122">If an activity is the root of the workflow, then the implementation of the activity is the workflow itself and tracking records are emitted for activities that form the implementation.</span></span> <span data-ttu-id="f8523-123">Использование режима «Все» позволяет создавать записи отслеживания для корневого действия и всех его композитных действий.</span><span class="sxs-lookup"><span data-stu-id="f8523-123">Using the All mode permits all tracking records to be emitted for the root activity and all its composite activities.</span></span>  
  
 <span data-ttu-id="f8523-124">Например, предположим, что *MyActivity* является составным действием, реализация которого содержит два действия *Activity1* и *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="f8523-124">For example, suppose *MyActivity* is a composite activity whose implementation contains two activities, *Activity1* and *Activity2*.</span></span>  <span data-ttu-id="f8523-125">При добавлении действия в рабочий процесс и включено отслеживание с профилем отслеживания с `implementationVisibility` присвоено `RootScope`, записи отслеживания создаются только для *MyActivity*.</span><span class="sxs-lookup"><span data-stu-id="f8523-125">When this activity is added to a workflow and tracking is enabled with a tracking profile with `implementationVisibility` set to `RootScope`, tracking records are emitted only for *MyActivity*.</span></span>  <span data-ttu-id="f8523-126">Однако записи не создаются для действий *Activity1* и *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="f8523-126">However, no records are emitted for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="f8523-127">Тем не менее если `implementationVisisbility` атрибут задается профиль отслеживания `All`, то записи отслеживания создаются не только для *MyActivity*, но также для действий *Activity1* и  *Activity2*.</span><span class="sxs-lookup"><span data-stu-id="f8523-127">However, if the `implementationVisisbility` attribute for the tracking profile is  set to `All`, then tracking records are emitted not only for *MyActivity*, but also for activities *Activity1* and *Activity2*.</span></span>  
  
 <span data-ttu-id="f8523-128">Флажок `implementationVisibility` применяется для следующих типов записей отслеживания:</span><span class="sxs-lookup"><span data-stu-id="f8523-128">The `implementationVisibility` flag applies to following tracking record types:</span></span>  
  
-   <span data-ttu-id="f8523-129">ActivityStateRecord</span><span class="sxs-lookup"><span data-stu-id="f8523-129">ActivityStateRecord</span></span>  
  
-   <span data-ttu-id="f8523-130">FaultPropagationRecord</span><span class="sxs-lookup"><span data-stu-id="f8523-130">FaultPropagationRecord</span></span>  
  
-   <span data-ttu-id="f8523-131">CancelRequestedRecord</span><span class="sxs-lookup"><span data-stu-id="f8523-131">CancelRequestedRecord</span></span>  
  
-   <span data-ttu-id="f8523-132">ActivityScheduledRecord</span><span class="sxs-lookup"><span data-stu-id="f8523-132">ActivityScheduledRecord</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f8523-133">Запись CustomTrackingRecords, создаваемая из реализации действия, не фильтруется параметром implementationVisibility.</span><span class="sxs-lookup"><span data-stu-id="f8523-133">CustomTrackingRecords emitted from activity implementation are not filtered out by the implementationVisibility setting.</span></span>  
  
 <span data-ttu-id="f8523-134">Функция `implementationVisibility` задается как <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> в профиле отслеживания в коде следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8523-134">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.RootScope> on the tracking profile in code as follows:</span></span>  
  
```  
TrackingProfile sampleTrackingProfile = new TrackingProfile()  
{  
    Name = "Sample Tracking Profile",  
    ImplementationVisibility = ImplementationVisibility.RootScope  
};  
```  
  
 <span data-ttu-id="f8523-135">Функция `implementationVisibility` может задается как <xref:System.Activities.Tracking.ImplementationVisibility.All> в профиле отслеживания в файле конфигурации следующим образом:</span><span class="sxs-lookup"><span data-stu-id="f8523-135">The `implementationVisibility` functionality is specified as <xref:System.Activities.Tracking.ImplementationVisibility.All> on the tracking profile in a configuration file as follows:</span></span>  
  
```xml  
<tracking>  
      <profiles>  
        <trackingProfile name="Shipping Monitoring" implementationVisibility="All">  
          <workflow activityDefinitionId="*">  
...  
         </workflow>  
        </trackingProfile>  
      </profiles>  
</tracking>  
```  
  
 <span data-ttu-id="f8523-136">Параметр `ImplementationVisibility` в профиле отслеживания является необязательным.</span><span class="sxs-lookup"><span data-stu-id="f8523-136">The `ImplementationVisibility` setting on the tracking profile is optional.</span></span> <span data-ttu-id="f8523-137">По умолчанию он имеет значение `RootScope`.</span><span class="sxs-lookup"><span data-stu-id="f8523-137">By default, its value is set to `RootScope`.</span></span> <span data-ttu-id="f8523-138">Значения для этого атрибута также учитывают регистр.</span><span class="sxs-lookup"><span data-stu-id="f8523-138">The values for this attribute are also case-sensitive.</span></span>  
  
### <a name="tracking-profile-query-types"></a><span data-ttu-id="f8523-139">Отслеживание типов запросов профиля</span><span class="sxs-lookup"><span data-stu-id="f8523-139">Tracking Profile Query Types</span></span>  
 <span data-ttu-id="f8523-140">Профили отслеживания структурированы в форме объявляющих подписок на записи отслеживания, которые позволяют выполнять запросы к среде выполнения рабочего процесса в отношении определенных записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-140">Tracking profiles are structured as declarative subscriptions for tracking records that allow you to query the workflow runtime for specific tracking records.</span></span> <span data-ttu-id="f8523-141">Существует множество типов запросов, которые позволяют подписаться на различные классы объектов <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-141">There are several query types that allow you subscribe to different classes of <xref:System.Activities.Tracking.TrackingRecord> objects.</span></span> <span data-ttu-id="f8523-142">Профили отслеживания могут быть заданы в конфигурации или посредством кода.</span><span class="sxs-lookup"><span data-stu-id="f8523-142">Tracking profiles can be specified in configuration or through code.</span></span> <span data-ttu-id="f8523-143">Ниже приводятся наиболее распространенные типы запросов.</span><span class="sxs-lookup"><span data-stu-id="f8523-143">Here are the most common query types:</span></span>  
  
-   <span data-ttu-id="f8523-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - используйте этот запрос для отслеживания изменений жизненного цикла экземпляра рабочего процесса, таких как ранее представленные события `Started` и `Completed`.</span><span class="sxs-lookup"><span data-stu-id="f8523-144"><xref:System.Activities.Tracking.WorkflowInstanceQuery> - Use this to track workflow instance life cycle changes like the previously-demonstrated `Started` and `Completed`.</span></span> <span data-ttu-id="f8523-145">Запрос <xref:System.Activities.Tracking.WorkflowInstanceQuery> используется для подписки на следующие объекты <xref:System.Activities.Tracking.TrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-145">The <xref:System.Activities.Tracking.WorkflowInstanceQuery> is used to subscribe to the following <xref:System.Activities.Tracking.TrackingRecord> objects:</span></span>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceAbortedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceUnhandledExceptionRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceTerminatedRecord>  
  
    -   <xref:System.Activities.Tracking.WorkflowInstanceSuspendedRecord>  
  
     <span data-ttu-id="f8523-146">Состояния, на которые можно подписаться, задаются классом <xref:System.Activities.Tracking.WorkflowInstanceStates>.</span><span class="sxs-lookup"><span data-stu-id="f8523-146">The states that can be subscribed to are specified in the <xref:System.Activities.Tracking.WorkflowInstanceStates> class.</span></span>  
  
     <span data-ttu-id="f8523-147">Конфигурация или код, используемые для подписки на записи отслеживания на уровне экземпляра рабочего процесса для состояния экземпляра `Started` при помощи запроса <xref:System.Activities.Tracking.WorkflowInstanceQuery>, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-147">The configuration or code used to subscribe to workflow instance-level tracking records for the `Started` instance state using the <xref:System.Activities.Tracking.WorkflowInstanceQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <workflowInstanceQueries>  
        <workflowInstanceQuery>  
          <states>  
            <state name="Started"/>  
          </states>  
        </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new WorkflowInstanceQuery()  
            {  
                States = { WorkflowInstanceStates.Started}                                                                     
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="f8523-148"><xref:System.Activities.Tracking.ActivityStateQuery> - используйте этот запрос для отслеживания изменений жизненного цикла действий, составляющих экземпляр рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f8523-148"><xref:System.Activities.Tracking.ActivityStateQuery> - Use this to track life cycle changes of the activities that make up a workflow instance.</span></span> <span data-ttu-id="f8523-149">Например можно хранить список всякий раз по завершении действия «Send E-Mail» внутри рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f8523-149">For example, you may want to keep track of every time the "Send E-Mail" activity completes within a workflow instance.</span></span> <span data-ttu-id="f8523-150">Этот запрос необходим, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.ActivityStateRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-150">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityStateRecord> objects.</span></span> <span data-ttu-id="f8523-151">Состояния, доступные для подписки, указаны в <xref:System.Activities.Tracking.ActivityStates>.</span><span class="sxs-lookup"><span data-stu-id="f8523-151">The available states to subscribe to are specified in <xref:System.Activities.Tracking.ActivityStates>.</span></span>  
  
     <span data-ttu-id="f8523-152">Конфигурация и код, используемые для подписки на записи отслеживания состояний действий при помощи запроса <xref:System.Activities.Tracking.ActivityStateQuery> для действия `SendEmailActivity`, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-152">The configuration and code used to subscribe activity state tracking records that use the <xref:System.Activities.Tracking.ActivityStateQuery> for the `SendEmailActivity` activity is shown in the following example.</span></span>  
  
    ```xml  
    <activityStateQueries>  
      <activityStateQuery activityName="SendEmailActivity">  
        <states>  
          <state name="Closed"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new ActivityStateQuery()  
            {                              
                ActivityName = "SendEmailActivity",  
                States = { ActivityStates.Closed }  
            }  
        }  
    };  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="f8523-153">Если несколько элементов activityStateQuery имеют одинаковые имена, то только состояния в последнем элементе используются в профиле отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-153">If multiple activityStateQuery elements have the same name, only the states in the last element are used in the tracking profile.</span></span>  
  
-   <span data-ttu-id="f8523-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - этот запрос позволяет отслеживать действие, запланированное к исполнению родительским действием.</span><span class="sxs-lookup"><span data-stu-id="f8523-154"><xref:System.Activities.Tracking.ActivityScheduledQuery> - This query allows you to track an activity scheduled for execution by a parent activity.</span></span> <span data-ttu-id="f8523-155">Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.ActivityScheduledRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-155">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.ActivityScheduledRecord> objects.</span></span>  
  
     <span data-ttu-id="f8523-156">Конфигурация и код, используемые для подписки на записи, связанные с дочерним действием `SendEmailActivity`, планируемым при помощи запроса <xref:System.Activities.Tracking.ActivityScheduledQuery>, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-156">The configuration and code used to subscribe to records related to the `SendEmailActivity` child activity being scheduled using the <xref:System.Activities.Tracking.ActivityScheduledQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <activityScheduledQueries>  
      <activityScheduledQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
     </activityScheduledQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new ActivityScheduledQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="f8523-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - используйте такой запрос для отслеживания обработки ошибок, возникающих во время действия.</span><span class="sxs-lookup"><span data-stu-id="f8523-157"><xref:System.Activities.Tracking.FaultPropagationQuery> - Use this to track the handling of faults that occur within an activity.</span></span> <span data-ttu-id="f8523-158">Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.FaultPropagationRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-158">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.FaultPropagationRecord> objects.</span></span>  
  
     <span data-ttu-id="f8523-159">Конфигурация и код, используемые для подписки на записи, связанные с распространением ошибок при помощи запроса <xref:System.Activities.Tracking.FaultPropagationQuery>, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-159">The configuration and code used to subscribe to records related to fault propagation using <xref:System.Activities.Tracking.FaultPropagationQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <faultPropagationQueries>  
      <faultPropagationQuery faultSourceActivityName="SendEmailActivity" faultHandlerActivityName="NotificationsFaultHandler" />  
    </faultPropagationQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =  
        {  
            new FaultPropagationQuery()  
            {  
                FaultSourceActivityName = "SendEmailActivity",  
                FaultHandlerActivityName = "NotificationsFaultHandler"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="f8523-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - используйте этот запрос для отслеживания запросов по отмене дочернего действия родительским действием.</span><span class="sxs-lookup"><span data-stu-id="f8523-160"><xref:System.Activities.Tracking.CancelRequestedQuery> - Use this to track requests to cancel a child activity by the parent activity.</span></span> <span data-ttu-id="f8523-161">Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.CancelRequestedRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-161">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CancelRequestedRecord> objects.</span></span>  
  
     <span data-ttu-id="f8523-162">Конфигурация и код, используемый для подписки на записи, связанные с отменой действий при помощи <xref:System.Activities.Tracking.CancelRequestedQuery> показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-162">The configuration and code used to subscribe to records related to activity cancellation using <xref:System.Activities.Tracking.CancelRequestedQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <cancelRequestedQueries>  
      <cancelRequestedQuery activityName="ProcessNotificationsActivity" childActivityName="SendEmailActivity" />  
    </cancelRequestedQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CancelRequestedQuery()  
            {  
                ActivityName = "ProcessNotificationsActivity",  
                ChildActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="f8523-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - используйте этот запрос для отслеживания событий, определенных в действиях кода.</span><span class="sxs-lookup"><span data-stu-id="f8523-163"><xref:System.Activities.Tracking.CustomTrackingQuery> - Use this to track events that you define in your code activities.</span></span> <span data-ttu-id="f8523-164">Этот запрос необходимо, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.CustomTrackingRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-164">The query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.CustomTrackingRecord> objects.</span></span>  
  
     <span data-ttu-id="f8523-165">Конфигурация и код, используемые для подписки на записи, связанные с пользовательскими записями отслеживания при помощи запроса <xref:System.Activities.Tracking.CustomTrackingQuery>, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-165">The configuration and code used to subscribe to records related to custom tracking records using <xref:System.Activities.Tracking.CustomTrackingQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <customTrackingQueries>  
      <customTrackingQuery name="EmailAddress" activityName="SendEmailActivity" />  
    </customTrackingQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new CustomTrackingQuery()   
            {  
                Name = "EmailAddress",  
                ActivityName = "SendEmailActivity"  
            }  
        }  
    };  
    ```  
  
-   <span data-ttu-id="f8523-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - используйте этот запрос для отслеживания возобновления закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="f8523-166"><xref:System.Activities.Tracking.BookmarkResumptionQuery> - Use this to track resumption of a bookmark within a workflow instance.</span></span> <span data-ttu-id="f8523-167">Этот запрос необходим, чтобы участник <xref:System.Activities.Tracking.TrackingParticipant> мог подписаться на объекты <xref:System.Activities.Tracking.BookmarkResumptionRecord>.</span><span class="sxs-lookup"><span data-stu-id="f8523-167">This query is necessary for a <xref:System.Activities.Tracking.TrackingParticipant> to subscribe to <xref:System.Activities.Tracking.BookmarkResumptionRecord> objects.</span></span>  
  
     <span data-ttu-id="f8523-168">Конфигурация и код, используемые для подписки на записи, связанные с возобновлением закладок при помощи запроса <xref:System.Activities.Tracking.BookmarkResumptionQuery>, показаны в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-168">The configuration and code used to subscribe to records related to bookmark resumption using <xref:System.Activities.Tracking.BookmarkResumptionQuery> is shown in the following example.</span></span>  
  
    ```xml  
    <bookmarkResumptionQueries>  
      <bookmarkResumptionQuery name="SentEmailBookmark" />  
    </bookmarkResumptionQueries>  
    ```  
  
    ```  
    TrackingProfile sampleTrackingProfile = new TrackingProfile()  
    {  
        Name = "Sample Tracking Profile",  
        Queries =   
        {  
            new BookmarkResumptionQuery()  
            {  
                Name = "sentEmailBookmark"  
            }  
        }  
    };  
    ```  
  
### <a name="annotations"></a><span data-ttu-id="f8523-169">Заметки</span><span class="sxs-lookup"><span data-stu-id="f8523-169">Annotations</span></span>  
 <span data-ttu-id="f8523-170">Заметки позволяют произвольно добавлять теги для записей отслеживания со значением, которое можно изменить после построения.</span><span class="sxs-lookup"><span data-stu-id="f8523-170">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="f8523-171">Например, может потребоваться нескольким записям отслеживания из нескольких рабочих процессов, следует пометить как «Mail Server» == «Mail Server1».</span><span class="sxs-lookup"><span data-stu-id="f8523-171">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="f8523-172">Это упростит поиск всех записей с этим тегом при последующем составлении запроса записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-172">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
 <span data-ttu-id="f8523-173">Для этого к запросу отслеживания добавляется заметка, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="f8523-173">To accomplish this, an annotation is added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
### <a name="how-to-create-a-tracking-profile"></a><span data-ttu-id="f8523-174">Создание профиля отслеживания</span><span class="sxs-lookup"><span data-stu-id="f8523-174">How to Create a Tracking Profile</span></span>  
 <span data-ttu-id="f8523-175">Элементы запроса отслеживания используются для создания профиля отслеживания при помощи XML-файла конфигурации либо кода [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f8523-175">Tracking query elements are used to create a tracking profile using either an XML configuration file or [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]code.</span></span>  <span data-ttu-id="f8523-176">Ниже приводится пример профиля отслеживания, созданного при помощи файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8523-176">Here is an example of a tracking profile created using a configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
  <tracking>  
    <profiles>  
      <trackingProfile name="Sample Tracking Profile ">  
        <workflow activityDefinitionId="*">  
          <!--Specify the tracking profile query elements to subscribe for tracking records-->  
        </workflow>  
      </trackingProfile>  
    </profiles>  
  </tracking>  
</system.serviceModel>  
```  
  
> [!WARNING]
>  <span data-ttu-id="f8523-177">Для WF с использованием узла служб рабочих процессов профиль отслеживания обычно создается при помощи файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f8523-177">For a WF using the Workflow service host, the tracking profile is typically created using a configuration file.</span></span> <span data-ttu-id="f8523-178">Также можно создать профиль отслеживания при помощи кода, используя профиль отслеживания и API-интерфейс запросов отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-178">It is also possible to create a tracking profile with code using the tracking profile and tracking query API.</span></span>  
  
 <span data-ttu-id="f8523-179">Профиль, настроенный как XML-файл конфигурации, применяется к участнику отслеживания при помощи расширения поведения.</span><span class="sxs-lookup"><span data-stu-id="f8523-179">A profile configured as an XML configuration file is applied to a tracking participant using a behavior extension.</span></span> <span data-ttu-id="f8523-180">Поведение добавляется к WorkflowServiceHost, как описано в разделе [Настройка отслеживания для рабочего процесса](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f8523-180">This is added to a WorkflowServiceHost as described in the later section [Configuring Tracking for a Workflow](../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
 <span data-ttu-id="f8523-181">Детализация записей отслеживания, создаваемых узлом, определяется параметрами конфигурации в профиле отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-181">The verbosity of the tracking records emitted by the host is determined by configuration settings within the tracking profile.</span></span> <span data-ttu-id="f8523-182">Участник отслеживания подписывается на записи отслеживания путем добавления запросов в профиль отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-182">A tracking participant subscribes to tracking records by adding queries to a tracking profile.</span></span> <span data-ttu-id="f8523-183">Чтобы подписаться на все записи отслеживания, необходимо указать все запросы отслеживания, используя профиль отслеживания «\*» в полях имен для каждого из запросов.</span><span class="sxs-lookup"><span data-stu-id="f8523-183">To subscribe to all tracking records, the tracking profile needs to specify all tracking queries using "\*" in the name fields in each of the queries.</span></span>  
  
 <span data-ttu-id="f8523-184">Ниже приводятся некоторые распространенные примеры профилей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-184">Here are some of the common examples of tracking profiles.</span></span>  
  
-   <span data-ttu-id="f8523-185">Профиль отслеживания для получения записей экземпляра рабочего процесса и ошибок.</span><span class="sxs-lookup"><span data-stu-id="f8523-185">A tracking profile to obtain workflow instance records and faults.</span></span>  
  
```xml  
<trackingProfile name="Instance and Fault Records">  
  <workflow activityDefinitionId="*">  
    <workflowInstanceQueries>  
      <workflowInstanceQuery>  
        <states>  
          <state name="*" />  
        </states>  
      </workflowInstanceQuery>  
    </workflowInstanceQueries>  
    <activityStateQueries>  
      <activityStateQuery activityName="*">  
        <states>  
          <state name="Faulted"/>  
        </states>  
      </activityStateQuery>  
    </activityStateQueries>  
  </workflow>  
</trackingProfile>  
```  
  
1.  <span data-ttu-id="f8523-186">Профиль отслеживания для получения всех пользовательских записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="f8523-186">A tracking profile to obtain all custom tracking records.</span></span>  
  
```xml  
<trackingProfile name="Instance_And_Custom_Records">  
  <workflow activityDefinitionId="*">  
    <customTrackingQueries>  
      <customTrackingQuery name="*" activityName="*" />  
    </customTrackingQueries>  
  </workflow>  
</trackingProfile>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8523-187">См. также</span><span class="sxs-lookup"><span data-stu-id="f8523-187">See also</span></span>
- [<span data-ttu-id="f8523-188">Отслеживание SQL</span><span class="sxs-lookup"><span data-stu-id="f8523-188">SQL Tracking</span></span>](../../../docs/framework/windows-workflow-foundation/samples/sql-tracking.md)
- [<span data-ttu-id="f8523-189">Мониторинг Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f8523-189">Windows Server App Fabric Monitoring</span></span>](https://go.microsoft.com/fwlink/?LinkId=201273)
- [<span data-ttu-id="f8523-190">Мониторинг приложений с помощью фабрики приложения</span><span class="sxs-lookup"><span data-stu-id="f8523-190">Monitoring Applications with App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkId=201275)
