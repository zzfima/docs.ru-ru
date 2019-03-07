---
title: Предоставление данных с помощью CacheMetadata
ms.date: 03/30/2017
ms.assetid: 34832f23-e93b-40e6-a80b-606a855a00d9
ms.openlocfilehash: a044c896e56541ee954fc33853376eb8293c6ede
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482682"
---
# <a name="exposing-data-with-cachemetadata"></a><span data-ttu-id="f8333-102">Предоставление данных с помощью CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="f8333-102">Exposing data with CacheMetadata</span></span>

<span data-ttu-id="f8333-103">Перед выполнением действия среда выполнения рабочих процессов получает все сведения, которые необходимы для его поддержки.</span><span class="sxs-lookup"><span data-stu-id="f8333-103">Before executing an activity, the workflow runtime obtains all of the information about the activity that it needs in order to maintain its execution.</span></span> <span data-ttu-id="f8333-104">Среда выполнения получает эти данные во время выполнения метода <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8333-104">The workflow runtime gets this information during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="f8333-105">Реализация этого метода по умолчанию предоставляет среде выполнения все открытые аргументы, переменные и дочерние действия этого действия, доступные во время выполнения. Если действие требует передачи среде выполнения дополнительных сведений (например, закрытых элементов или действий, планируемых этим действием), то этот метод может быть переопределен.</span><span class="sxs-lookup"><span data-stu-id="f8333-105">The default implementation of this method provides the runtime with all of the public arguments, variables, and child activities exposed by the activity at the time it is executed; if the activity needs to give more information to the runtime than this (such as private members, or activities to be scheduled by the activity), this method can be overridden to provide it.</span></span>

## <a name="default-cachemetadata-behavior"></a><span data-ttu-id="f8333-106">Поведение CacheMetadata по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f8333-106">Default CacheMetadata behavior</span></span>

<span data-ttu-id="f8333-107">Реализация <xref:System.Activities.NativeActivity.CacheMetadata%2A> по умолчанию для действий, производных от <xref:System.Activities.NativeActivity>, обрабатывает следующие типы методов следующими способами:</span><span class="sxs-lookup"><span data-stu-id="f8333-107">The default implementation of <xref:System.Activities.NativeActivity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.NativeActivity> processes the following method types in the following ways:</span></span>

- <span data-ttu-id="f8333-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, или <xref:System.Activities.InOutArgument%601> (универсальные аргументы): Эти аргументы предоставляются среде выполнения как аргументы с именем и типом имя открытого свойства и тип, с соответствующим направлением аргумента и некоторыми проверочными данными.</span><span class="sxs-lookup"><span data-stu-id="f8333-108"><xref:System.Activities.InArgument%601>, <xref:System.Activities.OutArgument%601>, or <xref:System.Activities.InOutArgument%601> (generic arguments): These arguments are exposed to the runtime as arguments with a name and type equal to the exposed property name and type, the appropriate argument direction, and some validation data.</span></span>

- <span data-ttu-id="f8333-109"><xref:System.Activities.Variable> или любой его подкласс: Эти элементы предоставляются среде выполнения в виде открытых переменных.</span><span class="sxs-lookup"><span data-stu-id="f8333-109"><xref:System.Activities.Variable> or any subclass thereof: These members are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="f8333-110"><xref:System.Activities.Activity> или любой его подкласс: Эти элементы предоставляются среде выполнения в виде открытых дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="f8333-110"><xref:System.Activities.Activity> or any subclass thereof: These members are exposed to the runtime as public child activities.</span></span> <span data-ttu-id="f8333-111">Поведение по умолчанию можно реализовать явно, вызвав <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>с передачей дочернего действия.</span><span class="sxs-lookup"><span data-stu-id="f8333-111">The default behavior can be implemented explicitly by calling <xref:System.Activities.ActivityMetadata.AddImportedChild%2A>, passing in the child activity.</span></span>

- <span data-ttu-id="f8333-112"><xref:System.Activities.ActivityDelegate> или любой его подкласс: Эти элементы предоставляются среде выполнения в виде открытых делегатов.</span><span class="sxs-lookup"><span data-stu-id="f8333-112"><xref:System.Activities.ActivityDelegate> or any subclass thereof: These members are exposed to the runtime as public delegates.</span></span>

- <span data-ttu-id="f8333-113"><xref:System.Collections.ICollection> типа <xref:System.Activities.Variable>: Все элементы в коллекции передаются среде выполнения виде открытых переменных.</span><span class="sxs-lookup"><span data-stu-id="f8333-113"><xref:System.Collections.ICollection> of type <xref:System.Activities.Variable>: All elements in the collection are exposed to the runtime as public variables.</span></span>

- <span data-ttu-id="f8333-114"><xref:System.Collections.ICollection> типа <xref:System.Activities.Activity>: Все элементы в коллекции передаются в среду выполнения в виде открытых дочерних действий.</span><span class="sxs-lookup"><span data-stu-id="f8333-114"><xref:System.Collections.ICollection> of type <xref:System.Activities.Activity>: All elements in the collection are exposed to the runtime as public children.</span></span>

- <span data-ttu-id="f8333-115"><xref:System.Collections.ICollection> типа <xref:System.Activities.ActivityDelegate>: Все элементы в коллекции передаются в среду выполнения в виде открытых делегатов.</span><span class="sxs-lookup"><span data-stu-id="f8333-115"><xref:System.Collections.ICollection> of type <xref:System.Activities.ActivityDelegate>: All elements in the collection are exposed to the runtime as public delegates.</span></span>

<span data-ttu-id="f8333-116">
  <xref:System.Activities.Activity.CacheMetadata%2A> для действий, производных от <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity> и <xref:System.Activities.AsyncCodeActivity>, работают, как описано выше, за исключением следующих отличий.</span><span class="sxs-lookup"><span data-stu-id="f8333-116">The <xref:System.Activities.Activity.CacheMetadata%2A> for activities that derive from <xref:System.Activities.Activity>, <xref:System.Workflow.Activities.CodeActivity>, and <xref:System.Activities.AsyncCodeActivity> also function as above, except for the following differences:</span></span>

- <span data-ttu-id="f8333-117">Классы, производные от <xref:System.Activities.Activity>, не могут планировать дочерние действия или делегаты, поэтому такие элементы предоставляются в виде импортируемых дочерних действий и делегатов.</span><span class="sxs-lookup"><span data-stu-id="f8333-117">Classes that derive from <xref:System.Activities.Activity> cannot schedule child activities or delegates, so such members are exposed as imported children and delegates; the</span></span>

- <span data-ttu-id="f8333-118">Классы, производные от <xref:System.Activities.CodeActivity> и <xref:System.Activities.AsyncCodeActivity>, не поддерживают переменные, дочерние элементы и делегаты, поэтому передаваться могут только аргументы.</span><span class="sxs-lookup"><span data-stu-id="f8333-118">Classes that derive from <xref:System.Activities.CodeActivity> and <xref:System.Activities.AsyncCodeActivity> do not support variables, children, or delegates, so only arguments will be exposed.</span></span>

## <a name="overriding-cachemetadata-to-provide-information-to-the-runtime"></a><span data-ttu-id="f8333-119">Переопределение метода CacheMetadata для передачи данных среде выполнения</span><span class="sxs-lookup"><span data-stu-id="f8333-119">Overriding CacheMetadata to provide information to the runtime</span></span>

<span data-ttu-id="f8333-120">В следующем фрагменте кода показано, как добавить сведения об элементах в метаданные любого действия во время выполнения метода <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8333-120">The following code snippet demonstrates how to add information about members to an activity’s metadata during the execution of the <xref:System.Activities.Activity.CacheMetadata%2A> method.</span></span> <span data-ttu-id="f8333-121">Следует иметь в виду, что основа метода вызывается для кэширования всех открытых данных о действии.</span><span class="sxs-lookup"><span data-stu-id="f8333-121">Note that the base of the method is called to cache all public data about the activity.</span></span>

```csharp
protected override void CacheMetadata(NativeActivityMetadata metadata)
{
    base.CacheMetadata(metadata);
    metadata.AddImplementationChild(this._writeLine);
    metadata.AddVariable(this._myVariable);
    metadata.AddImplementationVariable(this._myImplementationVariable);

    RuntimeArgument argument = new RuntimeArgument("MyArgument", ArgumentDirection.In, typeof(SomeType));
    metadata.Bind(argument, this.SomeName);
    metadata.AddArgument(argument);
}
```

## <a name="using-cachemetadata-to-expose-implementation-children"></a><span data-ttu-id="f8333-122">Доступ к дочерним элементам реализации через метод CacheMetadata</span><span class="sxs-lookup"><span data-stu-id="f8333-122">Using CacheMetadata to expose implementation children</span></span>

<span data-ttu-id="f8333-123">Чтобы передать данные дочерним действиям, которые должны быть запланированы действием с помощью переменных, необходимо добавить переменные в виде переменных реализации. Значения открытых переменных нельзя задать таким образом.</span><span class="sxs-lookup"><span data-stu-id="f8333-123">In order to pass data to child activities that are to be scheduled by an activity using variables, it is necessary to add the variables as implementation variables; public variables cannot have their values set this way.</span></span> <span data-ttu-id="f8333-124">Причина этого заключается в том, что действия должны выполняться скорее как реализации функций (имеющих параметры), а не как инкапсулированные классы (имеющие свойства).</span><span class="sxs-lookup"><span data-stu-id="f8333-124">The reason for this is that activities are intended to be executed more as implementations of functions (which have parameters), rather than encapsulated classes (which have properties).</span></span> <span data-ttu-id="f8333-125">Однако в некоторых ситуациях аргументы должны задаваться явным образом, например через <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, поскольку запланированное действие, в отличие от дочернего, не имеет доступа к аргументам родительского действия.</span><span class="sxs-lookup"><span data-stu-id="f8333-125">However, there are situations in which the arguments must be explicitly set, such as when using <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A>, since the scheduled activity doesn't have access to the parent activity's arguments in the way a child activity would.</span></span>

<span data-ttu-id="f8333-126">В следующем фрагменте кода показан способ передачи аргумента от исходного действия запланированному действию с помощью <xref:System.Activities.Activity.CacheMetadata%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8333-126">The following code snippet demonstrates how to pass an argument form a native activity into a scheduled activity using <xref:System.Activities.Activity.CacheMetadata%2A>.</span></span>

```csharp
public sealed class ChildActivity : NativeActivity
{
    public WriteLine _writeLine;
    public InArgument<string> Message { get; set; }
    private Variable<string> MessageVariable { get; set; }
    public ChildActivity()
    {
        MessageVariable = new Variable<string>();
        _writeLine = new WriteLine
        {
            Text = new InArgument<string>(MessageVariable),
        };
    }
    protected override void CacheMetadata(NativeActivityMetadata metadata)
    {
        base.CacheMetadata(metadata);
        metadata.AddImplementationVariable(this.MessageVariable);
        metadata.AddImplementationChild(this._writeLine);
    }
    protected override void Execute(NativeActivityContext context)
    {
        string configuredMessage = context.GetValue(Message);
        context.SetValue(MessageVariable, configuredMessage);
        context.ScheduleActivity(this._writeLine);
    }
}
```
