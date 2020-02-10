---
title: Настраиваемое отслеживание
ms.date: 03/30/2017
ms.assetid: 2d191c9f-62f4-4c63-92dd-cda917fcf254
ms.openlocfilehash: 9a2ad2004c47ce76dcc35baf4ca28aa174409581
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094661"
---
# <a name="custom-tracking"></a><span data-ttu-id="fee0d-102">Настраиваемое отслеживание</span><span class="sxs-lookup"><span data-stu-id="fee0d-102">Custom Tracking</span></span>
<span data-ttu-id="fee0d-103">В данном образце демонстрируется создание настраиваемого участника отслеживания и запись содержимого данных отслеживания в консоль.</span><span class="sxs-lookup"><span data-stu-id="fee0d-103">This sample demonstrates how to create a custom tracking participant and write the contents of the tracking data to console.</span></span> <span data-ttu-id="fee0d-104">Помимо этого, в образце демонстрируется создание <xref:System.Activities.Tracking.CustomTrackingRecord> объектов, заполненных определенными пользователем данными.</span><span class="sxs-lookup"><span data-stu-id="fee0d-104">In addition, the sample demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects populated with user defined data.</span></span> <span data-ttu-id="fee0d-105">Консольный участник отслеживания фильтрует <xref:System.Activities.Tracking.TrackingRecord> объекты, выпущенные рабочим процессом, используя объект профиля отслеживания, созданный в коде.</span><span class="sxs-lookup"><span data-stu-id="fee0d-105">The console-based tracking participant filters the <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow using a tracking profile object created in code.</span></span>

## <a name="sample-details"></a><span data-ttu-id="fee0d-106">Подробные сведения об образце</span><span class="sxs-lookup"><span data-stu-id="fee0d-106">Sample Details</span></span>
 <span data-ttu-id="fee0d-107">Windows Workflow Foundation (WF) предоставляет инфраструктуру отслеживания для отслеживания выполнения экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-107">Windows Workflow Foundation (WF) provides a tracking infrastructure to track execution of a workflow instance.</span></span> <span data-ttu-id="fee0d-108">Среда выполнения для отслеживания реализует экземпляр рабочего процесса для создания событий, связанных с жизненным циклом рабочего процесса, действиями рабочего процесса и настраиваемыми событиями отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-108">The tracking runtime implements a workflow instance to emit events related to the workflow lifecycle, events from workflow activities and custom tracking events.</span></span> <span data-ttu-id="fee0d-109">В следующих сведениях о таблице подробно описаны основные компоненты инфраструктуры отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-109">The following table details the primary components of the tracking infrastructure.</span></span>

|<span data-ttu-id="fee0d-110">Компонент</span><span class="sxs-lookup"><span data-stu-id="fee0d-110">Component</span></span>|<span data-ttu-id="fee0d-111">Description</span><span class="sxs-lookup"><span data-stu-id="fee0d-111">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="fee0d-112">Среда выполнения отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-112">Tracking runtime</span></span>|<span data-ttu-id="fee0d-113">Предоставляет инфраструктуру для передачи записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-113">Provides the infrastructure to emit tracking records.</span></span>|
|<span data-ttu-id="fee0d-114">Участники отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-114">Tracking participants</span></span>|<span data-ttu-id="fee0d-115">Потребляет записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-115">Consumes the tracking records.</span></span> <span data-ttu-id="fee0d-116">.NET Framework 4 поставляется с участником отслеживания, который записывает записи отслеживания в качестве события трассировки событий Windows (ETW).</span><span class="sxs-lookup"><span data-stu-id="fee0d-116">.NET Framework 4 ships with a tracking participant that writes tracking records as Event Tracing for Windows (ETW) events.</span></span>|
|<span data-ttu-id="fee0d-117">Профиль отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-117">Tracking profile</span></span>|<span data-ttu-id="fee0d-118">Механизм фильтрации, который позволяет участнику отслеживания подписаться на подмножество записей отслеживания, передаваемых из экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-118">A filtering mechanism that allows a tracking participant to subscribe for a subset of the tracking records emitted from a workflow instance.</span></span>|

 <span data-ttu-id="fee0d-119">Следующая таблица содержит подробные сведения о записях отслеживания, создаваемых средой выполнения рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-119">The following table details the tracking records that the workflow runtime emits.</span></span>

|<span data-ttu-id="fee0d-120">Запись отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-120">Tracking Record</span></span>|<span data-ttu-id="fee0d-121">Description</span><span class="sxs-lookup"><span data-stu-id="fee0d-121">Description</span></span>|
|---------------------|-----------------|
|<span data-ttu-id="fee0d-122">Записи отслеживания экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-122">Workflow instance tracking records.</span></span>|<span data-ttu-id="fee0d-123">Описывает жизненный цикл экземпляра рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-123">Describes the life cycle of the workflow instance.</span></span> <span data-ttu-id="fee0d-124">Например, запись экземпляра создается при запуске и завершении рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-124">For example, an instance record is emitted when the workflow starts or completes.</span></span>|
|<span data-ttu-id="fee0d-125">Записи отслеживания состояний действия.</span><span class="sxs-lookup"><span data-stu-id="fee0d-125">Activity state Tracking Records.</span></span>|<span data-ttu-id="fee0d-126">Подробные сведения о выполнении действия.</span><span class="sxs-lookup"><span data-stu-id="fee0d-126">Details activity execution.</span></span> <span data-ttu-id="fee0d-127">Эти записи сообщают о состоянии действия рабочего процесса, например о планировании выполнения действия, о завершении действия или о возникновении ошибки.</span><span class="sxs-lookup"><span data-stu-id="fee0d-127">These records indicate the state of a workflow activity such as when an activity is scheduled or when the activity completes or when a fault is thrown.</span></span>|
|<span data-ttu-id="fee0d-128">Запись возобновления закладки.</span><span class="sxs-lookup"><span data-stu-id="fee0d-128">Bookmark resumption record.</span></span>|<span data-ttu-id="fee0d-129">Создается при возобновлении закладки в экземпляре рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-129">Emitted whenever a bookmark within a workflow instance is resumed.</span></span>|
|<span data-ttu-id="fee0d-130">Пользовательские записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-130">Custom Tracking Records.</span></span>|<span data-ttu-id="fee0d-131">Автор рабочего процесса может создавать настраиваемые записи отслеживания и выдавать их в рамках пользовательской операции.</span><span class="sxs-lookup"><span data-stu-id="fee0d-131">A workflow author can create Custom Tracking Records and emit them within the custom activity.</span></span>|

 <span data-ttu-id="fee0d-132">Участник отслеживания подписывается на часть создаваемых объектов <xref:System.Activities.Tracking.TrackingRecord>, используя профили отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-132">The tracking participant subscribes for a subset of the emitted <xref:System.Activities.Tracking.TrackingRecord> objects using tracking profiles.</span></span> <span data-ttu-id="fee0d-133">Профиль отслеживания содержит запросы отслеживания, которые позволяют подписываться на определенный тип записей отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-133">A tracking profile contains tracking queries that allow subscribing for a particular tracking record type.</span></span> <span data-ttu-id="fee0d-134">Профили отслеживания можно указывать в коде или в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fee0d-134">Tracking profiles can be specified in code or in configuration.</span></span>

### <a name="custom-tracking-participant"></a><span data-ttu-id="fee0d-135">Настраиваемый участник отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-135">Custom Tracking Participant</span></span>
 <span data-ttu-id="fee0d-136">API участника отслеживания позволяет расширить среду выполнения отслеживания с помощью пользовательского участника отслеживания, который может включать настраиваемую логику для обработки <xref:System.Activities.Tracking.TrackingRecord> объектов, созданных средой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-136">The tracking participant API allows extension of the tracking runtime with a user provided tracking participant that can include custom logic to handle <xref:System.Activities.Tracking.TrackingRecord> objects emitted by the workflow runtime.</span></span>

 <span data-ttu-id="fee0d-137">Чтобы создать участника отслеживания, пользователь должен реализовать <xref:System.Activities.Tracking.TrackingParticipant>.</span><span class="sxs-lookup"><span data-stu-id="fee0d-137">To write a tracking participant the user must implement <xref:System.Activities.Tracking.TrackingParticipant>.</span></span> <span data-ttu-id="fee0d-138">В частности, метод <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> должен быть реализован настраиваемым участником.</span><span class="sxs-lookup"><span data-stu-id="fee0d-138">Specifically, the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method has to be implemented by the custom participant.</span></span> <span data-ttu-id="fee0d-139">Этот метод вызывается, когда <xref:System.Activities.Tracking.TrackingRecord> создается средой рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-139">This method is called when a <xref:System.Activities.Tracking.TrackingRecord> is emitted by the workflow runtime.</span></span>

```csharp
public abstract class TrackingParticipant
{
    protected TrackingParticipant();

    public virtual TrackingProfile TrackingProfile { get; set; }
    public abstract void Track(TrackingRecord record, TimeSpan timeout);
}
```

 <span data-ttu-id="fee0d-140">Полный участник отслеживания реализуется в файле ConsoleTrackingParticipant.cs.</span><span class="sxs-lookup"><span data-stu-id="fee0d-140">The complete tracking participant is implemented in the ConsoleTrackingParticipant.cs file.</span></span> <span data-ttu-id="fee0d-141">В следующем примере кода показан метод <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> для настраиваемого участника отслеживания.</span><span class="sxs-lookup"><span data-stu-id="fee0d-141">The following code example is the <xref:System.Activities.Tracking.TrackingParticipant.Track%2A> method for the custom tracking participant.</span></span>

```csharp
protected override void Track(TrackingRecord record, TimeSpan timeout)
{
    ...
    WorkflowInstanceRecord workflowInstanceRecord = record as WorkflowInstanceRecord;
    if (workflowInstanceRecord != null)
    {
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " Workflow InstanceID: {0} Workflow instance state: {1}",
            record.InstanceId, workflowInstanceRecord.State));
    }

    ActivityStateRecord activityStateRecord = record as ActivityStateRecord;
    if (activityStateRecord != null)
    {
        IDictionary<String, object> variables = activityStateRecord.Variables;
        StringBuilder vars = new StringBuilder();

        if (variables.Count > 0)
        {
            vars.AppendLine("\n\tVariables:");
            foreach (KeyValuePair<string, object> variable in variables)
            {
                vars.AppendLine(String.Format(
                    "\t\tName: {0} Value: {1}", variable.Key, variable.Value));
            }
        }
        Console.WriteLine(String.Format(CultureInfo.InvariantCulture,
            " :Activity DisplayName: {0} :ActivityInstanceState: {1} {2}",
                activityStateRecord.Activity.Name, activityStateRecord.State,
            ((variables.Count > 0) ? vars.ToString() : String.Empty)));
    }

    CustomTrackingRecord customTrackingRecord = record as CustomTrackingRecord;

    if ((customTrackingRecord != null) && (customTrackingRecord.Data.Count > 0))
    {
        ...
    }
    Console.WriteLine();

}
```

 <span data-ttu-id="fee0d-142">Следующий пример кода добавляет консольного участника к средству вызова рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="fee0d-142">The following code example adds the console participant to the workflow invoker.</span></span>

```csharp
ConsoleTrackingParticipant customTrackingParticipant = new ConsoleTrackingParticipant()
{
    ...
    // The tracking profile is set here, refer to Program.CS
...
}

WorkflowInvoker invoker = new WorkflowInvoker(BuildSampleWorkflow());
invoker.Extensions.Add(customTrackingParticipant);
```

### <a name="emitting-custom-tracking-records"></a><span data-ttu-id="fee0d-143">Выдача пользовательских записей отслеживания</span><span class="sxs-lookup"><span data-stu-id="fee0d-143">Emitting Custom Tracking Records</span></span>
 <span data-ttu-id="fee0d-144">В этом образце также демонстрируется возможность создания <xref:System.Activities.Tracking.CustomTrackingRecord> объектов из пользовательских действий рабочего процесса:</span><span class="sxs-lookup"><span data-stu-id="fee0d-144">This sample also demonstrates the ability to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects from a custom workflow activity:</span></span>

- <span data-ttu-id="fee0d-145">Объекты <xref:System.Activities.Tracking.CustomTrackingRecord> создаются и заполняются определенными пользователем данными, которые, по замыслу пользователя, будут выдаваться вместе с записью.</span><span class="sxs-lookup"><span data-stu-id="fee0d-145">The <xref:System.Activities.Tracking.CustomTrackingRecord> objects are created and populated with user-defined data that is desired to be emitted with the record.</span></span>

- <span data-ttu-id="fee0d-146"><xref:System.Activities.Tracking.CustomTrackingRecord> создается путем вызова метода Track <xref:System.Activities.ActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="fee0d-146">The <xref:System.Activities.Tracking.CustomTrackingRecord> is emitted by calling the track method of the <xref:System.Activities.ActivityContext>.</span></span>

 <span data-ttu-id="fee0d-147">В следующем примере продемонстрировано создание <xref:System.Activities.Tracking.CustomTrackingRecord> объектов в рамках пользовательской операции.</span><span class="sxs-lookup"><span data-stu-id="fee0d-147">The following example demonstrates how to emit <xref:System.Activities.Tracking.CustomTrackingRecord> objects within a custom activity.</span></span>

```csharp
// Create the Custom Tracking Record
CustomTrackingRecord customRecord = new CustomTrackingRecord("OrderIn")
{
    Data =
    {
        {"OrderId", 200},
        {"OrderDate", "20 Aug 2001"}
    }
};

// Emit custom tracking record
context.Track(customRecord);
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="fee0d-148">Использование этого образца</span><span class="sxs-lookup"><span data-stu-id="fee0d-148">To use this sample</span></span>

1. <span data-ttu-id="fee0d-149">С помощью Visual Studio 2010 откройте файл решения Кустомтраккингсампле. sln.</span><span class="sxs-lookup"><span data-stu-id="fee0d-149">Using Visual Studio 2010, open the CustomTrackingSample.sln solution file.</span></span>

2. <span data-ttu-id="fee0d-150">Для построения решения нажмите CTRL+SHIFT+B.</span><span class="sxs-lookup"><span data-stu-id="fee0d-150">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="fee0d-151">Чтобы запустить решение, нажмите клавиши CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="fee0d-151">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fee0d-152">Образцы уже могут быть установлены на компьютере.</span><span class="sxs-lookup"><span data-stu-id="fee0d-152">The samples may already be installed on your computer.</span></span> <span data-ttu-id="fee0d-153">Перед продолжением проверьте следующий каталог (по умолчанию).</span><span class="sxs-lookup"><span data-stu-id="fee0d-153">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="fee0d-154">Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples.</span><span class="sxs-lookup"><span data-stu-id="fee0d-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fee0d-155">Этот образец расположен в следующем каталоге.</span><span class="sxs-lookup"><span data-stu-id="fee0d-155">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\CustomTracking`  
  
## <a name="see-also"></a><span data-ttu-id="fee0d-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fee0d-156">See also</span></span>

- <span data-ttu-id="fee0d-157">[Примеры мониторинга AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="fee0d-157">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
