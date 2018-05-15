---
title: Создание действия в среде выполнения с динамическим действием
ms.date: 03/30/2017
ms.assetid: 1af85cc6-912d-449e-90c5-c5db3eca5ace
ms.openlocfilehash: 0450a56059083f355f3fd71d95c83bf8dd1cf0e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="creating-an-activity-at-runtime-with-dynamicactivity"></a><span data-ttu-id="eddb6-102">Создание действия в среде выполнения с динамическим действием</span><span class="sxs-lookup"><span data-stu-id="eddb6-102">Creating an Activity at Runtime with DynamicActivity</span></span>
<span data-ttu-id="eddb6-103"><xref:System.Activities.DynamicActivity> представляет собой конкретный запечатанный класс с открытым конструктором.</span><span class="sxs-lookup"><span data-stu-id="eddb6-103"><xref:System.Activities.DynamicActivity> is a concrete, sealed class with a public constructor.</span></span> <span data-ttu-id="eddb6-104"><xref:System.Activities.DynamicActivity> может использоваться для объединения функций действий во время выполнения с помощью действия DOM.</span><span class="sxs-lookup"><span data-stu-id="eddb6-104"><xref:System.Activities.DynamicActivity> can be used to assemble activity functionality at runtime using an activity DOM.</span></span>  
  
## <a name="dynamicactivity-features"></a><span data-ttu-id="eddb6-105">Функции DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="eddb6-105">DynamicActivity Features</span></span>  
 <span data-ttu-id="eddb6-106"><xref:System.Activities.DynamicActivity> имеет доступ к свойствам, аргументам и переменным выполнения, но не имеет доступа к службам среды выполнения, таким как дочерние действия планирования и отслеживание.</span><span class="sxs-lookup"><span data-stu-id="eddb6-106"><xref:System.Activities.DynamicActivity> has access to execution properties, arguments and variables, but no access to run-time services such as scheduling child activities or tracking.</span></span>  
  
 <span data-ttu-id="eddb6-107">Значения свойств верхнего уровня можно задавать при помощи объектов рабочих процессов <xref:System.Activities.Argument>.</span><span class="sxs-lookup"><span data-stu-id="eddb6-107">Top-level properties can be set using workflow <xref:System.Activities.Argument> objects.</span></span> <span data-ttu-id="eddb6-108">В императивном коде эти аргументы создаются при помощи свойств среды CLR в новом типе.</span><span class="sxs-lookup"><span data-stu-id="eddb6-108">In imperative code, these arguments are created using CLR properties on a new type.</span></span> <span data-ttu-id="eddb6-109">На языке XAML такие аргументы объявляются при помощи тегов `x:Class` и `x:Member`.</span><span class="sxs-lookup"><span data-stu-id="eddb6-109">In XAML, they are declared using `x:Class` and `x:Member` tags.</span></span>  
  
 <span data-ttu-id="eddb6-110">Действия, построенные при помощи интерфейса <xref:System.Activities.DynamicActivity> в конструкторе, использующем <xref:System.ComponentModel.ICustomTypeDescriptor>.</span><span class="sxs-lookup"><span data-stu-id="eddb6-110">Activities constructed using <xref:System.Activities.DynamicActivity> interface with the designer using <xref:System.ComponentModel.ICustomTypeDescriptor>.</span></span> <span data-ttu-id="eddb6-111">Действия, созданные в конструкторе, можно загружать динамически с помощью <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, как показано в следующей процедуре.</span><span class="sxs-lookup"><span data-stu-id="eddb6-111">Activities created in the designer can be loaded dynamically using <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A>, as demonstrated in the following procedure.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-imperative-code"></a><span data-ttu-id="eddb6-112">Создание действия во время выполнения при помощи императивного кода</span><span class="sxs-lookup"><span data-stu-id="eddb6-112">To create an activity at runtime using imperative code</span></span>  
  
1.  <span data-ttu-id="eddb6-113">Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eddb6-113">Open[!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="eddb6-114">Выберите **файл**, **новый**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="eddb6-114">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="eddb6-115">Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла.</span><span class="sxs-lookup"><span data-stu-id="eddb6-115">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="eddb6-116">Выберите **консольного приложения последовательного рабочего процесса** в **шаблоны** окна.</span><span class="sxs-lookup"><span data-stu-id="eddb6-116">Select **Sequential Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="eddb6-117">Задайте имя для нового проекта DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="eddb6-117">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="eddb6-118">Щелкните правой кнопкой мыши файл Workflow1.xaml в проекте HelloActivity и выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="eddb6-118">Right-click Workflow1.xaml in the HelloActivity project and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="eddb6-119">Откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="eddb6-119">Open Program.cs.</span></span> <span data-ttu-id="eddb6-120">Добавьте следующую директиву в начало файла.</span><span class="sxs-lookup"><span data-stu-id="eddb6-120">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Collections.Generic;  
    ```  
  
5.  <span data-ttu-id="eddb6-121">Замените содержимое метода `Main` следующим кодом, который создаст действие <xref:System.Activities.Statements.Sequence>, содержащее отдельное действие <xref:System.Activities.Statements.WriteLine>, и назначит его свойству <xref:System.Activities.DynamicActivity.Implementation%2A> нового динамического действия.</span><span class="sxs-lookup"><span data-stu-id="eddb6-121">Replace the contents of the `Main` method with the following code, which creates a <xref:System.Activities.Statements.Sequence> activity that contains a single <xref:System.Activities.Statements.WriteLine> activity and assigns it to the <xref:System.Activities.DynamicActivity.Implementation%2A> property of a new dynamic activity.</span></span>  
  
    ```csharp  
    //Define the input argument for the activity  
    var textOut = new InArgument<string>();  
    //Create the activity, property, and implementation  
                Activity dynamicWorkflow = new DynamicActivity()  
                {  
                    Properties =   
                    {  
                        new DynamicActivityProperty  
                        {  
                            Name = "Text",  
                            Type = typeof(InArgument<String>),  
                            Value = textOut  
                        }  
                    },  
                    Implementation = () => new Sequence()  
                    {  
                        Activities =   
                        {  
                            new WriteLine()  
                            {  
                                Text = new InArgument<string>(env => textOut.Get(env))  
                            }  
                        }  
                    }  
                };  
    //Execute the activity with a parameter dictionary  
                WorkflowInvoker.Invoke(dynamicWorkflow, new Dictionary<string, object> { { "Text", "Hello World!" } });  
                Console.ReadLine();  
    ```  
  
6.  <span data-ttu-id="eddb6-122">Выполните приложение.</span><span class="sxs-lookup"><span data-stu-id="eddb6-122">Execute the application.</span></span> <span data-ttu-id="eddb6-123">Окно консоли с текстом «Hello World!»</span><span class="sxs-lookup"><span data-stu-id="eddb6-123">A console window with the text "Hello World!"</span></span> <span data-ttu-id="eddb6-124">Отображает.</span><span class="sxs-lookup"><span data-stu-id="eddb6-124">displays.</span></span>  
  
#### <a name="to-create-an-activity-at-runtime-using-xaml"></a><span data-ttu-id="eddb6-125">Создание действия во время выполнения при помощи языка XAML</span><span class="sxs-lookup"><span data-stu-id="eddb6-125">To create an activity at runtime using XAML</span></span>  
  
1.  <span data-ttu-id="eddb6-126">Откройте [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eddb6-126">Open [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="eddb6-127">Выберите **файл**, **новый**, **проекта**.</span><span class="sxs-lookup"><span data-stu-id="eddb6-127">Select **File**, **New**, **Project**.</span></span> <span data-ttu-id="eddb6-128">Выберите **Workflow 4.0** под **Visual C#** в **типы проектов** затем выберите **v2010** узла.</span><span class="sxs-lookup"><span data-stu-id="eddb6-128">Select **Workflow 4.0** under **Visual C#** in the **Project Types** window, and select the **v2010** node.</span></span> <span data-ttu-id="eddb6-129">Выберите **консольное приложение рабочего процесса** в **шаблоны** окна.</span><span class="sxs-lookup"><span data-stu-id="eddb6-129">Select  **Workflow Console Application** in the **Templates** window.</span></span> <span data-ttu-id="eddb6-130">Задайте имя для нового проекта DynamicActivitySample.</span><span class="sxs-lookup"><span data-stu-id="eddb6-130">Name the new project DynamicActivitySample.</span></span>  
  
3.  <span data-ttu-id="eddb6-131">Откройте файл Workflow1.xaml в проекте HelloActivity.</span><span class="sxs-lookup"><span data-stu-id="eddb6-131">Open Workflow1.xaml in the HelloActivity project.</span></span> <span data-ttu-id="eddb6-132">Нажмите кнопку **аргументы** в нижней части конструктора.</span><span class="sxs-lookup"><span data-stu-id="eddb6-132">Click the **Arguments** option at the bottom of the designer.</span></span> <span data-ttu-id="eddb6-133">Создайте новый аргумент `In`, вызываемый методом `TextToWrite` типа `String`.</span><span class="sxs-lookup"><span data-stu-id="eddb6-133">Create a new `In` argument called `TextToWrite` of type `String`.</span></span>  
  
4.  <span data-ttu-id="eddb6-134">Перетащите **WriteLine** действия из **примитивы** области элементов в область конструктора.</span><span class="sxs-lookup"><span data-stu-id="eddb6-134">Drag a **WriteLine** activity from the **Primitives** section of the toolbox onto the designer surface.</span></span> <span data-ttu-id="eddb6-135">Присвойте значение `TextToWrite` для **текст** свойства действия.</span><span class="sxs-lookup"><span data-stu-id="eddb6-135">Assign the value `TextToWrite` to the **Text** property of the activity.</span></span>  
  
5.  <span data-ttu-id="eddb6-136">Откройте файл Program.cs.</span><span class="sxs-lookup"><span data-stu-id="eddb6-136">Open Program.cs.</span></span> <span data-ttu-id="eddb6-137">Добавьте следующую директиву в начало файла.</span><span class="sxs-lookup"><span data-stu-id="eddb6-137">Add the following directive to the top of the file.</span></span>  
  
    ```  
    using System.Activities.XamlIntegration;  
    ```  
  
6.  <span data-ttu-id="eddb6-138">Замените содержимое метода `Main` следующим кодом.</span><span class="sxs-lookup"><span data-stu-id="eddb6-138">Replace the contents of the `Main` method with the following code.</span></span>  
  
    ```  
    Activity act2 = ActivityXamlServices.Load(@"Workflow1.xaml");  
                    results = WorkflowInvoker.Invoke(act2, new Dictionary<string, object> { { "TextToWrite", "HelloWorld!" } });  
    Console.ReadLine();  
    ```  
  
7.  <span data-ttu-id="eddb6-139">Выполните приложение.</span><span class="sxs-lookup"><span data-stu-id="eddb6-139">Execute the application.</span></span> <span data-ttu-id="eddb6-140">Окно консоли с текстом «Hello World!»</span><span class="sxs-lookup"><span data-stu-id="eddb6-140">A console window with the text "Hello World!"</span></span> <span data-ttu-id="eddb6-141">отображается.</span><span class="sxs-lookup"><span data-stu-id="eddb6-141">appears.</span></span>  
  
8.  <span data-ttu-id="eddb6-142">Щелкните правой кнопкой мыши файл Workflow1.xaml в **обозревателе решений** и выберите **Просмотр кода**.</span><span class="sxs-lookup"><span data-stu-id="eddb6-142">Right-click the Workflow1.xaml file in the **Solution Explorer** and select **View Code**.</span></span> <span data-ttu-id="eddb6-143">Следует отметить, что класс действия создается при помощи `x:Class`, а свойство - при помощи `x:Property`.</span><span class="sxs-lookup"><span data-stu-id="eddb6-143">Note that the activity class is created with `x:Class` and the property is created with `x:Property`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eddb6-144">См. также</span><span class="sxs-lookup"><span data-stu-id="eddb6-144">See Also</span></span>  
 [<span data-ttu-id="eddb6-145">Разработка рабочих процессов, действий и выражений с использованием императивного кода</span><span class="sxs-lookup"><span data-stu-id="eddb6-145">Authoring Workflows, Activities, and Expressions Using Imperative Code</span></span>](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)  
 [<span data-ttu-id="eddb6-146">Создание действия DynamicActivity</span><span class="sxs-lookup"><span data-stu-id="eddb6-146">DynamicActivity Creation</span></span>](../../../docs/framework/windows-workflow-foundation/samples/dynamicactivity-creation.md)
