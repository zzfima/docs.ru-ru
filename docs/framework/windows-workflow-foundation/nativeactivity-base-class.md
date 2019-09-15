---
title: Базовый класс NativeActivity
ms.date: 03/30/2017
ms.assetid: 254a4c50-425b-426d-a32f-0f7234925bac
ms.openlocfilehash: 604535e39937a75c6d268cf1abbc90dbcd506a16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989550"
---
# <a name="nativeactivity-base-class"></a><span data-ttu-id="1cf79-102">Базовый класс NativeActivity</span><span class="sxs-lookup"><span data-stu-id="1cf79-102">NativeActivity Base Class</span></span>

<span data-ttu-id="1cf79-103"><xref:System.Activities.NativeActivity> является абстрактным классом с защищенным конструктором.</span><span class="sxs-lookup"><span data-stu-id="1cf79-103"><xref:System.Activities.NativeActivity> is an abstract class with a protected constructor.</span></span> <span data-ttu-id="1cf79-104">Подобно <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> используется для записи принудительного поведения посредством реализации метода <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-104">Like <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> is used for writing imperative behavior by implementing an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span> <span data-ttu-id="1cf79-105">В отличие от <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> имеет доступ ко всем предоставляемым функциональным возможностям среды выполнения рабочего процесса с помощью объекта <xref:System.Activities.NativeActivityContext>, передаваемого методу <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-105">Unlike <xref:System.Activities.CodeActivity>, <xref:System.Activities.NativeActivity> has access to all of the exposed features of the workflow runtime through the <xref:System.Activities.NativeActivityContext> object passed to the <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

## <a name="using-nativeactivitycontext"></a><span data-ttu-id="1cf79-106">Использование NativeActivityContext</span><span class="sxs-lookup"><span data-stu-id="1cf79-106">Using NativeActivityContext</span></span>
 <span data-ttu-id="1cf79-107">Доступ к функциям среды выполнения рабочего процесса можно получить из метода <xref:System.Activities.NativeActivity.Execute%2A> при помощи элементов параметра `context` типа <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-107">Features of the workflow runtime can be accessed from within the <xref:System.Activities.NativeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.NativeActivityContext>.</span></span> <span data-ttu-id="1cf79-108">Функции, доступные посредством <xref:System.Activities.NativeActivityContext>:</span><span class="sxs-lookup"><span data-stu-id="1cf79-108">The features available through <xref:System.Activities.NativeActivityContext> include the following:</span></span>

- <span data-ttu-id="1cf79-109">Возвращение и задание аргументов и переменных.</span><span class="sxs-lookup"><span data-stu-id="1cf79-109">Getting and setting of arguments and variables.</span></span>

- <span data-ttu-id="1cf79-110">Планирование дочерних действий с помощью <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span><span class="sxs-lookup"><span data-stu-id="1cf79-110">Scheduling child activities with <xref:System.Activities.NativeActivityContext.ScheduleActivity%2A></span></span>

- <span data-ttu-id="1cf79-111">Прерывание выполнения действия с помощью <xref:System.Activities.NativeActivityContext.Abort%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-111">Aborting activity execution using <xref:System.Activities.NativeActivityContext.Abort%2A>.</span></span>

- <span data-ttu-id="1cf79-112">Отмена выполнения дочернего действия с помощью <xref:System.Activities.NativeActivityContext.CancelChild%2A> и <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-112">Canceling child execution using <xref:System.Activities.NativeActivityContext.CancelChild%2A> and <xref:System.Activities.NativeActivityContext.CancelChildren%2A>.</span></span>

- <span data-ttu-id="1cf79-113">Получение доступа к закладкам действий при помощи таких методов, как <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A> и <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-113">Access to activity bookmarks using such methods as <xref:System.Activities.NativeActivityContext.CreateBookmark%2A>, <xref:System.Activities.NativeActivityContext.RemoveBookmark%2A>, and <xref:System.Activities.NativeActivityContext.ResumeBookmark%2A>.</span></span>

- <span data-ttu-id="1cf79-114">Пользовательские функции отслеживания с использованием <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-114">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

- <span data-ttu-id="1cf79-115">Получение доступа к свойствам выполнения действия и свойствам значений с помощью <xref:System.Activities.CodeActivityContext.GetProperty%2A> и <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-115">Access to the activity’s execution properties and value properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A> and <xref:System.Activities.NativeActivityContext.GetValue%2A>.</span></span>

- <span data-ttu-id="1cf79-116">Планирование задач и функций действий с помощью <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> и <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-116">Scheduling activity actions and functions using <xref:System.Activities.NativeActivityContext.ScheduleAction%2A> and <xref:System.Activities.NativeActivityContext.ScheduleFunc%2A>.</span></span>

### <a name="to-create-a-custom-activity-that-inherits-from-nativeactivity"></a><span data-ttu-id="1cf79-117">Создание пользовательского действия, которое наследуется от NativeActivity</span><span class="sxs-lookup"><span data-stu-id="1cf79-117">To create a custom activity that inherits from NativeActivity</span></span>

1. <span data-ttu-id="1cf79-118">Опенвисуал Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="1cf79-118">OpenVisual Studio 2010.</span></span>

2. <span data-ttu-id="1cf79-119">Выберите **файл**, **создать**, а затем **проект**.</span><span class="sxs-lookup"><span data-stu-id="1cf79-119">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="1cf79-120">Выберите **Рабочий процесс 4,0** в поле **визуальный C#**  элемент в окне **типы проектов** и выберите узел **v2010** .</span><span class="sxs-lookup"><span data-stu-id="1cf79-120">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="1cf79-121">В окне **шаблоны** выберите пункт **Библиотека действий** .</span><span class="sxs-lookup"><span data-stu-id="1cf79-121">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="1cf79-122">Задайте имя для нового проекта HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="1cf79-122">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="1cf79-123">Щелкните правой кнопкой мыши Activity1. XAML в проекте Хеллоактивити и выберите **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="1cf79-123">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="1cf79-124">Щелкните правой кнопкой мыши проект Хеллоактивити и выберите **Добавить**, а затем — **класс**.</span><span class="sxs-lookup"><span data-stu-id="1cf79-124">Right-click the HelloActivity project and select **Add**, and then **Class**.</span></span> <span data-ttu-id="1cf79-125">Задайте имя для нового класса HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="1cf79-125">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="1cf79-126">В файле HelloActivity.cs добавьте следующие директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="1cf79-126">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="1cf79-127">Сделайте так, чтобы новый класс наследовал от действия <xref:System.Activities.NativeActivity> путем добавления базового класса к объявлению класса.</span><span class="sxs-lookup"><span data-stu-id="1cf79-127">Make the new class inherit from <xref:System.Activities.NativeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : NativeActivity
    ```

7. <span data-ttu-id="1cf79-128">Добавьте функциональные возможности к классу путем добавления метода <xref:System.Activities.NativeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-128">Add functionality to the class by adding an <xref:System.Activities.NativeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="1cf79-129">Переопределите метод <xref:System.Activities.NativeActivity.CacheMetadata%2A> и вызовите соответствующий метод Add, чтобы сообщить среде выполнения рабочего процесса о переменных, аргументах, дочерних элементах и делегатах пользовательского действия.</span><span class="sxs-lookup"><span data-stu-id="1cf79-129">Override the <xref:System.Activities.NativeActivity.CacheMetadata%2A> method and call the appropriate Add method to let the workflow runtime know about the custom activity’s variables, arguments, children, and delegates.</span></span> <span data-ttu-id="1cf79-130">Дополнительные сведения см. в описании класса <xref:System.Activities.NativeActivityMetadata>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-130">For more information see the <xref:System.Activities.NativeActivityMetadata> class.</span></span>

9. <span data-ttu-id="1cf79-131">Для планирования закладок используйте объект <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-131">Use the <xref:System.Activities.NativeActivityContext> object to schedule a bookmark.</span></span> <span data-ttu-id="1cf79-132">Подробные сведения о том, как создавать, планировать и возобновлять закладки, см. в разделе <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A>.</span><span class="sxs-lookup"><span data-stu-id="1cf79-132">See <xref:System.Activities.WorkflowApplicationIdleEventArgs.Bookmarks%2A> for details on how to create, schedule, and resume a bookmark.</span></span>

    ```csharp
    protected override void Execute(NativeActivityContext context)
        {
            // Create a Bookmark and wait for it to be resumed.
            context.CreateBookmark(BookmarkName.Get(context),
                new BookmarkCallback(OnResumeBookmark));
        }
    ```
