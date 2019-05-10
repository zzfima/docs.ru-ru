---
title: Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: a8f228d334785cd880b06dbeda8f96550471599a
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211548"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="ecc4f-102">Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="ecc4f-103">При создании пользовательского элемента управления, вам будет часто понадобиться для отладки его поведение во время разработки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="ecc4f-104">Это особенно верно в случае, если вы создаете пользовательский конструктор для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="ecc4f-105">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание Windows Forms элемент управления, который использует преимущества средств разработки Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="ecc4f-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="ecc4f-106">Можно выполнять отладку пользовательских элементов управления с помощью Visual Studio, так же, как отладка любого других классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="ecc4f-107">Разница заключается в том, что необходимо отладить отдельный экземпляр Visual Studio, на котором выполняется код настраиваемого элемента управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>

<span data-ttu-id="ecc4f-108">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="ecc4f-109">Создание проекта Windows Forms для размещения пользовательского элемента управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-109">Creating a Windows Forms project to host your custom control</span></span>

- <span data-ttu-id="ecc4f-110">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-110">Creating a control library project</span></span>

- <span data-ttu-id="ecc4f-111">Добавление свойства в элемент управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-111">Adding a property to your custom control</span></span>

- <span data-ttu-id="ecc4f-112">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="ecc4f-112">Adding your custom control to the host form</span></span>

- <span data-ttu-id="ecc4f-113">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-113">Setting up the project for design-time debugging</span></span>

- <span data-ttu-id="ecc4f-114">Отладка пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-114">Debugging your custom control at design time</span></span>

<span data-ttu-id="ecc4f-115">Когда вы закончите, вы получите представление о задачи, необходимые для отладки поведения времени разработки пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="ecc4f-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="ecc4f-116">Create the project</span></span>

<span data-ttu-id="ecc4f-117">Первым шагом является создание проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-117">The first step is to create the application project.</span></span> <span data-ttu-id="ecc4f-118">Этот проект будет использован для построения приложения, на котором размещается пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-118">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="ecc4f-119">В Visual Studio создайте проект приложения Windows с именем «DebuggingExample» (**файл** > **New** > **проекта**  >  **Visual C#**  или **Visual Basic** > **классический рабочий стол** > **Windows Forms Application**).</span><span class="sxs-lookup"><span data-stu-id="ecc4f-119">In Visual Studio, create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="ecc4f-120">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-120">Create the control library project</span></span>

1. <span data-ttu-id="ecc4f-121">Добавить **Windows Control Library** проекта к решению.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-121">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="ecc4f-122">Добавьте новый **UserControl** DebugControlLibrary проект.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-122">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="ecc4f-123">Подробную информацию см. в разделе [Практическое руководство. Добавление новых элементов проекта](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ecc4f-123">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="ecc4f-124">Предоставить новый исходный файл «DebugControl» базовым именем.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-124">Give the new source file a base name of "DebugControl".</span></span>

3. <span data-ttu-id="ecc4f-125">С помощью **обозревателе решений**, удалите элемент управления проекта по умолчанию путем удаления файла с базовым именем "`UserControl1`«.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-125">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="ecc4f-126">Подробную информацию см. в разделе [Практическое руководство. Удалить, удаление и исключить элементы](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="ecc4f-126">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>

4. <span data-ttu-id="ecc4f-127">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-127">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="ecc4f-128">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="ecc4f-128">Checkpoint</span></span>

<span data-ttu-id="ecc4f-129">На этом этапе вы сможете для пользовательского элемента управления в см. в разделе **элементов**.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-129">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="ecc4f-130">Чтобы проверить ход, найдите новый вкладку с именем **компоненты DebugControlLibrary** и установите его.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-130">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="ecc4f-131">Когда она откроется, вы увидите в списке управления **DebugControl** со значком по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-131">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="ecc4f-132">Добавление свойства в элемент управления</span><span class="sxs-lookup"><span data-stu-id="ecc4f-132">Add a property to your custom control</span></span>

<span data-ttu-id="ecc4f-133">Чтобы продемонстрировать, выполнение кода пользовательского элемента управления во время разработки, будет добавить свойство и установите точку останова в коде, который реализует свойство.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-133">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="ecc4f-134">Откройте **DebugControl** в **редактор кода**.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-134">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="ecc4f-135">Добавьте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="ecc4f-135">Add the following code to the class definition:</span></span>

    ```vb
    Private demoStringValue As String = Nothing
    <BrowsableAttribute(true)>
    Public Property DemoString() As String

        Get
            Return Me.demoStringValue
        End Get

        Set(ByVal value As String)
            Me.demoStringValue = value
        End Set

    End Property
    ```

    ```csharp
    private string demoStringValue = null;
    [Browsable(true)]
    public string DemoString
    {
        get
        {
            return this.demoStringValue;
        }
        set
        {
            demoStringValue = value;
        }
    }
    ```

2. <span data-ttu-id="ecc4f-136">Постройте решение.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-136">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="ecc4f-137">Добавление пользовательского элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="ecc4f-137">Add your custom control to the host form</span></span>

<span data-ttu-id="ecc4f-138">Для отладки поведения времени разработки пользовательского элемента управления, поместите экземпляр класса пользовательского элемента управления в форму.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-138">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="ecc4f-139">В проекте «DebuggingExample», откройте форму Form1 в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-139">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="ecc4f-140">В **элементов**откройте **компоненты DebugControlLibrary** вкладку и перетащите **DebugControl** экземпляра на форму.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-140">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="ecc4f-141">Найти `DemoString` пользовательское свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-141">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="ecc4f-142">Обратите внимание на то, что его значение можно изменить, как любое другое свойство.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-142">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="ecc4f-143">Также Обратите внимание, что при `DemoString` было выбрано свойство, строка описания свойства отображается в нижней части **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-143">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="ecc4f-144">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-144">Set up the project for design-time debugging</span></span>

<span data-ttu-id="ecc4f-145">Для отладки поведения пользовательского элемента управления во время разработки, необходимо отладить отдельный экземпляр Visual Studio, на котором выполняется код настраиваемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-145">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="ecc4f-146">Щелкните правой кнопкой мыши **DebugControlLibrary** в проекте **обозревателе решений** и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-146">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="ecc4f-147">В **DebugControlLibrary** свойств, выберите **Отладка** вкладки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-147">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="ecc4f-148">В **действие при запуске** выберите **запуск внешней программы**.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-148">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="ecc4f-149">Вы будете отладка отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) чтобы перейти в интегрированной среде разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-149">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="ecc4f-150">Имя исполняемого файла — **devenv.exe**, и если вы установили в расположение по умолчанию, его путь — 9.0\Common7\IDE\devenv.exe %programfiles%\Microsoft Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-150">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>

3. <span data-ttu-id="ecc4f-151">Нажмите кнопку **ОК**, чтобы закрыть диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-151">Click **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="ecc4f-152">Щелкните правой кнопкой мыши **DebugControlLibrary** проекта и выберите **Назначить запускаемым проектом** включить конфигурацию отладки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-152">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="ecc4f-153">Отладка пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-153">Debug your custom control at design time</span></span>

<span data-ttu-id="ecc4f-154">Теперь вы готовы к отладке пользовательского элемента управления в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-154">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="ecc4f-155">При запуске сеанса отладки, будет создан новый экземпляр Visual Studio, и он будет использоваться для загрузки решения «DebuggingExample».</span><span class="sxs-lookup"><span data-stu-id="ecc4f-155">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="ecc4f-156">При открытии Form1 в **конструктор форм**, экземпляр пользовательского элемента управления будет создан и запущен.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-156">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="ecc4f-157">Откройте **DebugControl** исходный файл в **редактор кода** и поместите точку останова на `Set` метод доступа `DemoString` свойство.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-157">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="ecc4f-158">Нажмите клавишу F5, чтобы запустить сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-158">Press F5 to start the debugging session.</span></span> <span data-ttu-id="ecc4f-159">Обратите внимание на то, что создается новый экземпляр Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-159">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="ecc4f-160">Может различать экземпляры двумя способами:</span><span class="sxs-lookup"><span data-stu-id="ecc4f-160">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="ecc4f-161">Экземпляр отладки имеет слово **под управлением** в заголовке окна</span><span class="sxs-lookup"><span data-stu-id="ecc4f-161">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="ecc4f-162">У экземпляра отладки **запустить** кнопку на его **Отладка** инструментов отключена</span><span class="sxs-lookup"><span data-stu-id="ecc4f-162">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

     <span data-ttu-id="ecc4f-163">Точка останова устанавливается в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-163">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="ecc4f-164">В новом экземпляре Visual Studio откройте решение «DebuggingExample».</span><span class="sxs-lookup"><span data-stu-id="ecc4f-164">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="ecc4f-165">Решение можно легко найти, выбрав **последние проекты** из **файл** меню.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-165">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="ecc4f-166">Файл решения «DebuggingExample.sln» отображаются как последних использовавшихся файлов.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-166">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="ecc4f-167">Откройте форму Form1 в **конструктор форм** и выберите **DebugControl** элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-167">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="ecc4f-168">Измените значение свойства `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="ecc4f-168">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="ecc4f-169">Обратите внимание, что при фиксации изменений, отладочный экземпляр Visual Studio получает фокус, и выполнение остановится в точке останова.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-169">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="ecc4f-170">Вы можете пошагово выполнить метод доступа к свойству так же, как к любой другой код.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-170">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="ecc4f-171">Когда вы закончите с сеанс отладки, можно выйти из закрыв второй экземпляр Visual Studio или щелкнув **остановить отладку** кнопки в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-171">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ecc4f-172">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="ecc4f-172">Next steps</span></span>

<span data-ttu-id="ecc4f-173">Теперь, когда можно отлаживать пользовательские элементы управления во время разработки, существует множество возможностей для расширения взаимодействия элемента управления с помощью Visual Studio IDE.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-173">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="ecc4f-174">Можно использовать <xref:System.ComponentModel.Component.DesignMode%2A> свойство <xref:System.ComponentModel.Component> для написания кода, который будет выполняться только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-174">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="ecc4f-175">Дополнительные сведения см. в разделе <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-175">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="ecc4f-176">Существует несколько атрибутов можно применить к свойствам элемента управления для управления взаимодействием элемента управления с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-176">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="ecc4f-177">Вы найдете эти атрибуты в <xref:System.ComponentModel?displayProperty=nameWithType> пространства имен.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-177">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="ecc4f-178">Можно написать пользовательский конструктор для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-178">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="ecc4f-179">Это дает полный контроль над разработкой с помощью расширяемой инфраструктуры конструкторов в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-179">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="ecc4f-180">Дополнительные сведения см. в разделе [Пошаговое руководство: Создание Windows Forms элемент управления, который использует преимущества средств разработки Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="ecc4f-180">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ecc4f-181">См. также</span><span class="sxs-lookup"><span data-stu-id="ecc4f-181">See also</span></span>

- [<span data-ttu-id="ecc4f-182">Пошаговое руководство: Создание элемента управления Windows Forms, используются преимущества функций Visual Studio во время разработки</span><span class="sxs-lookup"><span data-stu-id="ecc4f-182">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="ecc4f-183">[Практическое руководство. Доступа к службам времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ecc4f-183">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="ecc4f-184">[Практическое руководство. Поддержка разработки доступа в Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="ecc4f-184">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
