---
title: Разработка действий рабочих процессов с помощью класса CodeActivity
ms.date: 03/30/2017
ms.assetid: cfe315c1-f86d-43ec-b9ce-2f8c469b1106
ms.openlocfilehash: 549acec8b8101312d48bd20e63a4a988b798ff38
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331290"
---
# <a name="workflow-activity-authoring-using-the-codeactivity-class"></a><span data-ttu-id="8ecaa-102">Разработка действий рабочих процессов с помощью класса CodeActivity</span><span class="sxs-lookup"><span data-stu-id="8ecaa-102">Workflow Activity Authoring Using the CodeActivity Class</span></span>
<span data-ttu-id="8ecaa-103">Действия, созданные путем наследования от <xref:System.Activities.CodeActivity>, могут реализовывать базовое императивное поведение путем переопределения метода <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-103">Activities created by inheriting from <xref:System.Activities.CodeActivity> can implement basic imperative behavior by overriding the <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

## <a name="using-codeactivitycontext"></a><span data-ttu-id="8ecaa-104">Использование CodeActivityContext</span><span class="sxs-lookup"><span data-stu-id="8ecaa-104">Using CodeActivityContext</span></span>
 <span data-ttu-id="8ecaa-105">Доступ к функциям среды выполнения рабочего процесса можно получить из метода <xref:System.Activities.CodeActivity.Execute%2A> при помощи элементов параметра `context` типа <xref:System.Activities.CodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-105">Features of the workflow runtime can be accessed from within the <xref:System.Activities.CodeActivity.Execute%2A> method by using members of the `context` parameter, of type <xref:System.Activities.CodeActivityContext>.</span></span> <span data-ttu-id="8ecaa-106">Функции, доступные посредством <xref:System.Activities.CodeActivityContext>:</span><span class="sxs-lookup"><span data-stu-id="8ecaa-106">The features available through <xref:System.Activities.CodeActivityContext> include the following:</span></span>

-   <span data-ttu-id="8ecaa-107">Возврат и задание значений аргументов и переменных.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-107">Getting and setting the values of variables and arguments.</span></span>

-   <span data-ttu-id="8ecaa-108">Пользовательские функции отслеживания с использованием <xref:System.Activities.CodeActivityContext.Track%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-108">Custom tracking features using <xref:System.Activities.CodeActivityContext.Track%2A>.</span></span>

-   <span data-ttu-id="8ecaa-109">Доступ к свойствам выполнения действия с помощью <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-109">Access to the activity’s execution properties using <xref:System.Activities.CodeActivityContext.GetProperty%2A>.</span></span>

#### <a name="to-create-a-custom-activity-that-inherits-from-codeactivity"></a><span data-ttu-id="8ecaa-110">Создание настраиваемого действия, которое наследуется от CodeActivity</span><span class="sxs-lookup"><span data-stu-id="8ecaa-110">To create a custom activity that inherits from CodeActivity</span></span>

1. <span data-ttu-id="8ecaa-111">Откройте Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-111">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="8ecaa-112">Выберите **файл**, **новый**, а затем **проекта**.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-112">Select **File**, **New**, and then **Project**.</span></span> <span data-ttu-id="8ecaa-113">Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-113">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="8ecaa-114">Выберите **библиотеки действий** в **шаблоны** окна.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-114">Select **Activity Library** in the **Templates** window.</span></span> <span data-ttu-id="8ecaa-115">Задайте имя для нового проекта HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-115">Name the new project HelloActivity.</span></span>

3. <span data-ttu-id="8ecaa-116">Щелкните правой кнопкой мыши Activity1.xaml в проекте HelloActivity и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-116">Right-click Activity1.xaml in the HelloActivity project and select **Delete**.</span></span>

4. <span data-ttu-id="8ecaa-117">Щелкните правой кнопкой мыши проект HelloActivity и выберите **добавить** , а затем **класс**.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-117">Right-click the HelloActivity project and select **Add** , and then **Class**.</span></span> <span data-ttu-id="8ecaa-118">Задайте имя для нового класса HelloActivity.cs.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-118">Name the new class HelloActivity.cs.</span></span>

5. <span data-ttu-id="8ecaa-119">В файле HelloActivity.cs добавьте следующие директивы `using`.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-119">In the HelloActivity.cs file, add the following `using` directives.</span></span>

    ```csharp
    using System.Activities;
    using System.Activities.Statements;
    ```

6. <span data-ttu-id="8ecaa-120">Сделайте так, чтобы новый класс наследовал от действия <xref:System.Activities.CodeActivity> путем добавления базового класса к объявлению класса.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-120">Make the new class inherit from <xref:System.Activities.CodeActivity> by adding a base class to the class declaration.</span></span>

    ```csharp
    class HelloActivity : CodeActivity
    ```

7. <span data-ttu-id="8ecaa-121">Добавьте функциональные возможности к классу путем добавления метода <xref:System.Activities.CodeActivity.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-121">Add functionality to the class by adding an <xref:System.Activities.CodeActivity.Execute%2A> method.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
    }
    ```

8. <span data-ttu-id="8ecaa-122">Используйте объект <xref:System.Activities.CodeActivityContext> для создания записи отслеживания.</span><span class="sxs-lookup"><span data-stu-id="8ecaa-122">Use the <xref:System.Activities.CodeActivityContext> to create a tracking record.</span></span>

    ```csharp
    protected override void Execute(CodeActivityContext context)
    {
        Console.WriteLine("Hello World!");
        CustomTrackingRecord record = new CustomTrackingRecord("MyRecord");
        record.Data.Add(new KeyValuePair<String, Object>("ExecutionTime", DateTime.Now));
        context.Track(record);
    }
    ```
