---
title: "Архитектура рабочих процессов Windows"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d4c6495-d64a-46d0-896a-3a01fac90aa9
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ed13d7885cb8abd760aed6bd5812cb8b7c75bc02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="windows-workflow-architecture"></a><span data-ttu-id="4b076-102">Архитектура рабочих процессов Windows</span><span class="sxs-lookup"><span data-stu-id="4b076-102">Windows Workflow Architecture</span></span>
[!INCLUDE[wf](../../../includes/wf-md.md)]<span data-ttu-id="4b076-103"> поднимает уровень абстракции для разработки интерактивных длительных приложений.</span><span class="sxs-lookup"><span data-stu-id="4b076-103"> raises the abstraction level for developing interactive long-running applications.</span></span> <span data-ttu-id="4b076-104">Блоки обработки инкапсулируются в виде действий.</span><span class="sxs-lookup"><span data-stu-id="4b076-104">Units of work are encapsulated as activities.</span></span> <span data-ttu-id="4b076-105">Действия работают в среде, которая обеспечивает средства для управления потоком, обработки исключений, распространения ошибок, сохранения данных состояния, загрузки и выгрузки текущих рабочих процессов из памяти, отслеживания и управления потоком транзакций.</span><span class="sxs-lookup"><span data-stu-id="4b076-105">Activities run in an environment that provides facilities for flow control, exception handling, fault propagation, persistence of state data, loading and unloading of in-progress workflows from memory, tracking, and transaction flow.</span></span>  
  
## <a name="activity-architecture"></a><span data-ttu-id="4b076-106">Архитектура действий</span><span class="sxs-lookup"><span data-stu-id="4b076-106">Activity Architecture</span></span>  
 <span data-ttu-id="4b076-107">Действия разрабатываются в виде типов среды CLR, которые являются производными либо от <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity> или <xref:System.Activities.NativeActivity>, либо от их вариантов, возвращающих значение, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601> или <xref:System.Activities.NativeActivity%601>.</span><span class="sxs-lookup"><span data-stu-id="4b076-107">Activities are developed as CLR types that derive from either <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>, or their variants that return a value, <xref:System.Activities.Activity%601>, <xref:System.Activities.CodeActivity%601>, <xref:System.Activities.AsyncCodeActivity%601>, or <xref:System.Activities.NativeActivity%601>.</span></span> <span data-ttu-id="4b076-108">Разработка действий, которые являются производными от действия <xref:System.Activities.Activity>, позволяет пользователю собирать существующие действия для быстрого создания блоков обработки, работающих в среде рабочих процессов.</span><span class="sxs-lookup"><span data-stu-id="4b076-108">Developing activities that derive from <xref:System.Activities.Activity> allows the user to assemble pre-existing activities to quickly create units of work that execute in the workflow environment.</span></span> <span data-ttu-id="4b076-109">С другой стороны, действие <xref:System.Activities.CodeActivity> позволяет создавать логику выполнения в управляемом коде с использованием <xref:System.Activities.CodeActivityContext> в основном для доступа к аргументам действий.</span><span class="sxs-lookup"><span data-stu-id="4b076-109"><xref:System.Activities.CodeActivity>, on the other hand, enables execution logic to be authored in managed code using <xref:System.Activities.CodeActivityContext> primarily for access to activity arguments.</span></span> <span data-ttu-id="4b076-110"><xref:System.Activities.AsyncCodeActivity> аналогично <xref:System.Activities.CodeActivity>, за исключением того, что его можно использовать для реализации асинхронных задач.</span><span class="sxs-lookup"><span data-stu-id="4b076-110"><xref:System.Activities.AsyncCodeActivity> is similar to <xref:System.Activities.CodeActivity> except that it can be used to implement asynchronous tasks.</span></span> <span data-ttu-id="4b076-111">Разработка действий, которые являются производными от действия <xref:System.Activities.NativeActivity>, позволяет пользователям получать доступ к среде выполнения посредством <xref:System.Activities.NativeActivityContext> для таких функций, как планирование дочерних объектов, создание закладок, вызов асинхронной работы, регистрации транзакций и других операций.</span><span class="sxs-lookup"><span data-stu-id="4b076-111">Developing activities that derive from <xref:System.Activities.NativeActivity> allows users to access the runtime through the <xref:System.Activities.NativeActivityContext> for functionality like scheduling children, creating bookmarks, invoking asynchronous work, registering transactions, and more.</span></span>  
  
 <span data-ttu-id="4b076-112">Создание действий, которые происходят от действия <xref:System.Activities.Activity>, является декларативным, при этом эти действия не могут быть созданы на языке XAML.</span><span class="sxs-lookup"><span data-stu-id="4b076-112">Authoring activities that derive from <xref:System.Activities.Activity> is declarative and these activities can be authored in XAML.</span></span> <span data-ttu-id="4b076-113">В следующем примере действие `Prompt` создается при помощи других действий для тела выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b076-113">In the following example, an activity called `Prompt` is created using other activities for the execution body.</span></span>  
  
```xml  
<Activity x:Class='Prompt'  
  xmlns:x='http://schemas.microsoft.com/winfx/2006/xaml'  
    xmlns:z='http://schemas.microsoft.com/netfx/2008/xaml/schema'  
xmlns:my='clr-namespace:XAMLActivityDefinition;assembly=XAMLActivityDefinition'  
xmlns:s="clr-namespace:System;assembly=mscorlib"  
xmlns="http://schemas.microsoft.com/2009/workflow">  
<z:SchemaType.Members>  
    <z:SchemaType.SchemaProperty Name='Text' Type=' InArgument(s:String)' />  
  <z:SchemaType.SchemaProperty Name='Response' Type='OutArgument(s:String)' />  
</z:SchemaType.Members>  
  <Sequence>  
    <my:WriteLine Text='[Text]' />  
    <my:ReadLine BookmarkName='r1' Result='[Response]' />  
  </Sequence>  
</Activity>  
```  
  
## <a name="activity-context"></a><span data-ttu-id="4b076-114">Контекст действия</span><span class="sxs-lookup"><span data-stu-id="4b076-114">Activity Context</span></span>  
 <span data-ttu-id="4b076-115"><xref:System.Activities.ActivityContext> представляет собой интерфейс автора действий со средой выполнения рабочих процессов и обеспечивает доступ ко многим функциям среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b076-115">The <xref:System.Activities.ActivityContext> is the activity author's interface to the workflow runtime and provides access to the runtime's wealth of features.</span></span> <span data-ttu-id="4b076-116">В следующем примере определяется действие, которое использует контекст выполнения для создания закладки (механизм, позволяющий действию зарегистрировать точку продолжения в ходе выполнения, которое может быть возобновлено при передаче узлом данных в действие).</span><span class="sxs-lookup"><span data-stu-id="4b076-116">In the following example, an activity is defined that uses the execution context to create a bookmark (the mechanism that allows an activity to register a continuation point in its execution that can be resumed by a host passing data into the activity).</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#15](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#15)]  
  
## <a name="activity-life-cycle"></a><span data-ttu-id="4b076-117">Жизненный цикл действия</span><span class="sxs-lookup"><span data-stu-id="4b076-117">Activity Life Cycle</span></span>  
 <span data-ttu-id="4b076-118">Экземпляр действия запускается в состоянии <xref:System.Activities.ActivityInstanceState.Executing>.</span><span class="sxs-lookup"><span data-stu-id="4b076-118">An instance of an activity starts out in the <xref:System.Activities.ActivityInstanceState.Executing> state.</span></span> <span data-ttu-id="4b076-119">Если исключения не обнаружены, экземпляр остается в этом состоянии до тех пор, пока дочерние действия и любые другие ожидающие операции (объекты <xref:System.Activities.Bookmark>, например) не завершены, после чего экземпляр переходит в состояние <xref:System.Activities.ActivityInstanceState.Closed>.</span><span class="sxs-lookup"><span data-stu-id="4b076-119">Unless exceptions are encountered, it remains in this state until all child activities are finished executing and any other pending work (<xref:System.Activities.Bookmark> objects, for instance) is completed, at which point it transitions to the <xref:System.Activities.ActivityInstanceState.Closed> state.</span></span> <span data-ttu-id="4b076-120">Родитель экземпляра действия может запросить прекращение работы дочернего действия; если дочернее действие может быть отменено, оно будет завершено в состоянии <xref:System.Activities.ActivityInstanceState.Canceled>.</span><span class="sxs-lookup"><span data-stu-id="4b076-120">The parent of an activity instance can request a child to cancel; if the child is able to be canceled it completes in the <xref:System.Activities.ActivityInstanceState.Canceled> state.</span></span> <span data-ttu-id="4b076-121">Если в ходе выполнения возникает исключение, среда выполнения переводит действие в состояние <xref:System.Activities.ActivityInstanceState.Faulted> и распространяет исключение по родительской цепочке действий.</span><span class="sxs-lookup"><span data-stu-id="4b076-121">If an exception is thrown during execution, the runtime puts the activity into the <xref:System.Activities.ActivityInstanceState.Faulted> state and propagates the exception up the parent chain of activities.</span></span> <span data-ttu-id="4b076-122">Далее приводятся три состояния завершения действия.</span><span class="sxs-lookup"><span data-stu-id="4b076-122">Following are the three completion states of an activity:</span></span>  
  
-   <span data-ttu-id="4b076-123">**Закрыть:** действие завершило работу и завершил работу.</span><span class="sxs-lookup"><span data-stu-id="4b076-123">**Closed:** The activity has completed its work and exited.</span></span>  
  
-   <span data-ttu-id="4b076-124">**Отменено:** действие правильно прекратило работу и завершил работу.</span><span class="sxs-lookup"><span data-stu-id="4b076-124">**Canceled:** The activity has gracefully abandoned its work and exited.</span></span> <span data-ttu-id="4b076-125">При переходе в это состояние откат операции не будет выполнен явным образом.</span><span class="sxs-lookup"><span data-stu-id="4b076-125">Work is not explicitly rolled back when this state is entered.</span></span>  
  
-   <span data-ttu-id="4b076-126">**В состоянии Faulted:** действие вызывает ошибку и выполнило выход без завершения работы.</span><span class="sxs-lookup"><span data-stu-id="4b076-126">**Faulted:** The activity has encountered an error and has exited without completing its work.</span></span>  
  
 <span data-ttu-id="4b076-127">Во время сохранения или выгрузки действия остаются в состоянии <xref:System.Activities.ActivityInstanceState.Executing>.</span><span class="sxs-lookup"><span data-stu-id="4b076-127">Activities remain in the <xref:System.Activities.ActivityInstanceState.Executing> state when they are persisted or unloaded.</span></span>
