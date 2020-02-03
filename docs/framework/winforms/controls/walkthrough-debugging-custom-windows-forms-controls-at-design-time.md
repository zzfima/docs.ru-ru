---
title: Отладка пользовательских элементов управления во время разработки
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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: d9e292a1219c24571bcb35db2fe357b0197c8812
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740194"
---
# <a name="walkthrough-debug-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="4255a-102">Пошаговое руководство. Отладка пользовательских элементов управления Windows Forms во время разработки</span><span class="sxs-lookup"><span data-stu-id="4255a-102">Walkthrough: Debug Custom Windows Forms Controls at Design Time</span></span>

<span data-ttu-id="4255a-103">При создании пользовательского элемента управления часто возникает необходимость в отладке его поведения во время разработки.</span><span class="sxs-lookup"><span data-stu-id="4255a-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="4255a-104">Это особенно справедливо при создании пользовательского конструктора для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4255a-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="4255a-105">Дополнительные сведения см. [в разделе Пошаговое руководство. Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="4255a-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

<span data-ttu-id="4255a-106">Вы можете выполнять отладку пользовательских элементов управления с помощью Visual Studio точно так же, как при отладке любых других классов .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4255a-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="4255a-107">Разница заключается в том, что будет выполняться отладка отдельного экземпляра Visual Studio, на котором выполняется код пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4255a-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="4255a-108">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4255a-108">Create the project</span></span>

<span data-ttu-id="4255a-109">Первым шагом является создание проекта приложения.</span><span class="sxs-lookup"><span data-stu-id="4255a-109">The first step is to create the application project.</span></span> <span data-ttu-id="4255a-110">Этот проект будет использоваться для создания приложения, в котором размещается пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4255a-110">You will use this project to build the application that hosts the custom control.</span></span>

<span data-ttu-id="4255a-111">В Visual Studio создайте проект приложения Windows и назовите его **дебуггинжексампле**.</span><span class="sxs-lookup"><span data-stu-id="4255a-111">In Visual Studio, create a Windows Application project, and name it **DebuggingExample**.</span></span>

## <a name="create-the-control-library-project"></a><span data-ttu-id="4255a-112">Создание проекта библиотеки элементов управления</span><span class="sxs-lookup"><span data-stu-id="4255a-112">Create the control library project</span></span>

1. <span data-ttu-id="4255a-113">Добавьте в решение проект **библиотеки элементов управления Windows** .</span><span class="sxs-lookup"><span data-stu-id="4255a-113">Add a **Windows Control Library** project to the solution.</span></span>

2. <span data-ttu-id="4255a-114">Добавьте новый элемент **UserControl** в проект дебугконтроллибрари.</span><span class="sxs-lookup"><span data-stu-id="4255a-114">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="4255a-115">Назовите его **дебугконтрол**.</span><span class="sxs-lookup"><span data-stu-id="4255a-115">Name it **DebugControl**.</span></span>

3. <span data-ttu-id="4255a-116">В **Обозреватель решений**удалите элемент управления проекта по умолчанию, удалив файл кода с базовым именем UserControl1.</span><span class="sxs-lookup"><span data-stu-id="4255a-116">In **Solution Explorer**, delete the project's default control by deleting the code file with a base name of UserControl1.</span></span>

4. <span data-ttu-id="4255a-117">Создайте решение.</span><span class="sxs-lookup"><span data-stu-id="4255a-117">Build the solution.</span></span>

## <a name="checkpoint"></a><span data-ttu-id="4255a-118">Контрольная точка</span><span class="sxs-lookup"><span data-stu-id="4255a-118">Checkpoint</span></span>

<span data-ttu-id="4255a-119">На этом этапе вы сможете увидеть пользовательский элемент управления на **панели элементов**.</span><span class="sxs-lookup"><span data-stu-id="4255a-119">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>

<span data-ttu-id="4255a-120">Чтобы проверить ход выполнения, найдите новую вкладку с именем **компоненты дебугконтроллибрари** и щелкните, чтобы выбрать ее.</span><span class="sxs-lookup"><span data-stu-id="4255a-120">To check your progress, find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="4255a-121">При открытии элемент управления отображается в списке как **дебугконтрол** со значком по умолчанию рядом с ним.</span><span class="sxs-lookup"><span data-stu-id="4255a-121">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>

## <a name="add-a-property-to-your-custom-control"></a><span data-ttu-id="4255a-122">Добавление свойства в пользовательский элемент управления</span><span class="sxs-lookup"><span data-stu-id="4255a-122">Add a property to your custom control</span></span>

<span data-ttu-id="4255a-123">Чтобы продемонстрировать, что код пользовательского элемента управления выполняется во время разработки, добавьте свойство и задайте точку останова в коде, который реализует свойство.</span><span class="sxs-lookup"><span data-stu-id="4255a-123">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>

1. <span data-ttu-id="4255a-124">Откройте **дебугконтрол** в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="4255a-124">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="4255a-125">Добавьте следующий код в определение класса:</span><span class="sxs-lookup"><span data-stu-id="4255a-125">Add the following code to the class definition:</span></span>

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

2. <span data-ttu-id="4255a-126">Создайте решение.</span><span class="sxs-lookup"><span data-stu-id="4255a-126">Build the solution.</span></span>

## <a name="add-your-custom-control-to-the-host-form"></a><span data-ttu-id="4255a-127">Добавление пользовательского элемента управления в форму размещения</span><span class="sxs-lookup"><span data-stu-id="4255a-127">Add your custom control to the host form</span></span>

<span data-ttu-id="4255a-128">Чтобы отладить поведение пользовательского элемента управления во время разработки, необходимо разместить экземпляр класса пользовательского элемента управления в форме узла.</span><span class="sxs-lookup"><span data-stu-id="4255a-128">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>

1. <span data-ttu-id="4255a-129">В проекте "Дебуггинжексампле" откройте Form1 в **конструктор Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="4255a-129">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>

2. <span data-ttu-id="4255a-130">На **панели элементов**откройте вкладку **компоненты дебугконтроллибрари** и перетащите экземпляр **дебугконтрол** на форму.</span><span class="sxs-lookup"><span data-stu-id="4255a-130">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>

3. <span data-ttu-id="4255a-131">Найдите пользовательское свойство `DemoString` в окне **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="4255a-131">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="4255a-132">Обратите внимание, что его значение можно изменить так же, как любое другое свойство.</span><span class="sxs-lookup"><span data-stu-id="4255a-132">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="4255a-133">Также обратите внимание, что при выборе свойства `DemoString` строка описания свойства отображается в нижней части окна **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="4255a-133">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>

## <a name="set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="4255a-134">Настройка проекта для отладки во время разработки</span><span class="sxs-lookup"><span data-stu-id="4255a-134">Set up the project for design-time debugging</span></span>

<span data-ttu-id="4255a-135">Для отладки поведения пользовательского элемента управления во время разработки будет выполняться отладка отдельного экземпляра Visual Studio, на котором выполняется код пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4255a-135">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>

1. <span data-ttu-id="4255a-136">Щелкните правой кнопкой мыши проект **дебугконтроллибрари** в **Обозреватель решений** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4255a-136">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>

2. <span data-ttu-id="4255a-137">На странице свойств **дебугконтроллибрари** выберите вкладку **Отладка** .</span><span class="sxs-lookup"><span data-stu-id="4255a-137">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>

     <span data-ttu-id="4255a-138">В разделе **действие при запуске** выберите **Запуск внешней программы**.</span><span class="sxs-lookup"><span data-stu-id="4255a-138">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="4255a-139">Вы будете выполнять отладку отдельного экземпляра Visual Studio, поэтому нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы найти интегрированную среду разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4255a-139">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="4255a-140">Имя исполняемого файла — **devenv. exe**, и если вы установили в расположение по умолчанию, его путь: *% ProgramFiles (x86)% \ Microsoft Visual Studio\2019\\\<Edition > \Common7\IDE*.</span><span class="sxs-lookup"><span data-stu-id="4255a-140">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is *%ProgramFiles(x86)%\Microsoft Visual Studio\2019\\\<edition>\Common7\IDE*.</span></span>

3. <span data-ttu-id="4255a-141">Чтобы закрыть диалоговое окно, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4255a-141">Select **OK** to close the dialog box.</span></span>

4. <span data-ttu-id="4255a-142">Щелкните правой кнопкой мыши проект **дебугконтроллибрари** и выберите **Назначить запускаемым проектом** , чтобы включить эту конфигурацию отладки.</span><span class="sxs-lookup"><span data-stu-id="4255a-142">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>

## <a name="debug-your-custom-control-at-design-time"></a><span data-ttu-id="4255a-143">Отладка пользовательского элемента управления во время разработки</span><span class="sxs-lookup"><span data-stu-id="4255a-143">Debug your custom control at design time</span></span>

<span data-ttu-id="4255a-144">Теперь вы готовы к отладке пользовательского элемента управления, как он выполняется в режиме конструктора.</span><span class="sxs-lookup"><span data-stu-id="4255a-144">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="4255a-145">При запуске сеанса отладки будет создан новый экземпляр Visual Studio, который будет использоваться для загрузки решения "Дебуггинжексампле".</span><span class="sxs-lookup"><span data-stu-id="4255a-145">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="4255a-146">При открытии формы Form1 в **конструкторе форм**будет создан экземпляр пользовательского элемента управления и начнется его выполнение.</span><span class="sxs-lookup"><span data-stu-id="4255a-146">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>

1. <span data-ttu-id="4255a-147">Откройте исходный файл **дебугконтрол** в **редакторе кода** и поместите точку останова в `Set`ный метод доступа свойства `DemoString`.</span><span class="sxs-lookup"><span data-stu-id="4255a-147">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>

2. <span data-ttu-id="4255a-148">Нажмите клавишу **F5** , чтобы запустить сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="4255a-148">Press **F5** to start the debugging session.</span></span> <span data-ttu-id="4255a-149">Создается новый экземпляр Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4255a-149">A new instance of Visual Studio is created.</span></span> <span data-ttu-id="4255a-150">Можно различать экземпляры двумя способами:</span><span class="sxs-lookup"><span data-stu-id="4255a-150">You can distinguish between the instances in two ways:</span></span>

    - <span data-ttu-id="4255a-151">Экземпляр отладки содержит слово, которое **выполняется** в заголовке окна</span><span class="sxs-lookup"><span data-stu-id="4255a-151">The debugging instance has the word **Running** in its title bar</span></span>

    - <span data-ttu-id="4255a-152">В экземпляре отладки на панели инструментов **отладки** отключена кнопка " **Пуск** "</span><span class="sxs-lookup"><span data-stu-id="4255a-152">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>

   <span data-ttu-id="4255a-153">Точка останова задается в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="4255a-153">Your breakpoint is set in the debugging instance.</span></span>

3. <span data-ttu-id="4255a-154">В новом экземпляре Visual Studio откройте решение "Дебуггинжексампле".</span><span class="sxs-lookup"><span data-stu-id="4255a-154">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="4255a-155">Решение можно легко найти, выбрав **последние проекты** в меню **файл** .</span><span class="sxs-lookup"><span data-stu-id="4255a-155">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="4255a-156">Файл решения "Дебуггинжексампле. sln" будет указан как самый последний использовавшийся файл.</span><span class="sxs-lookup"><span data-stu-id="4255a-156">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>

4. <span data-ttu-id="4255a-157">Откройте форму Form1 в **конструкторе форм** и выберите элемент управления **дебугконтрол** .</span><span class="sxs-lookup"><span data-stu-id="4255a-157">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>

5. <span data-ttu-id="4255a-158">Измените значение свойства `DemoString` .</span><span class="sxs-lookup"><span data-stu-id="4255a-158">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="4255a-159">При фиксации изменения экземпляр отладки Visual Studio получает фокус и выполнение останавливается в точке останова.</span><span class="sxs-lookup"><span data-stu-id="4255a-159">When you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="4255a-160">Метод доступа к свойству можно выполнить одним шагом, как и любой другой код.</span><span class="sxs-lookup"><span data-stu-id="4255a-160">You can single-step through the property accessor just as your would any other code.</span></span>

6. <span data-ttu-id="4255a-161">Чтобы прекратить отладку, выйдите из размещенного экземпляра Visual Studio или нажмите кнопку " **прекратить отладку** " в экземпляре отладки.</span><span class="sxs-lookup"><span data-stu-id="4255a-161">To stop debugging, exit the hosted instance of Visual Studio or select the **Stop Debugging** button in the debugging instance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4255a-162">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4255a-162">Next steps</span></span>

<span data-ttu-id="4255a-163">Теперь, когда вы можете выполнять отладку пользовательских элементов управления во время разработки, существует множество возможностей расширения взаимодействия элемента управления с интегрированной средой разработки Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4255a-163">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>

- <span data-ttu-id="4255a-164">Можно использовать свойство <xref:System.ComponentModel.Component.DesignMode%2A> класса <xref:System.ComponentModel.Component> для написания кода, который будет выполняться только во время разработки.</span><span class="sxs-lookup"><span data-stu-id="4255a-164">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="4255a-165">Дополнительные сведения см. в разделе <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="4255a-165">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>

- <span data-ttu-id="4255a-166">Существует несколько атрибутов, которые можно применить к свойствам элемента управления, чтобы управлять взаимодействием пользовательского элемента управления с конструктором.</span><span class="sxs-lookup"><span data-stu-id="4255a-166">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="4255a-167">Эти атрибуты можно найти в пространстве имен <xref:System.ComponentModel?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4255a-167">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>

- <span data-ttu-id="4255a-168">Можно написать пользовательский конструктор для пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4255a-168">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="4255a-169">Это дает полный контроль над процессом разработки с помощью расширяемой инфраструктуры конструктора, предоставляемой Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4255a-169">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="4255a-170">Дополнительные сведения см. [в разделе Пошаговое руководство. Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="4255a-170">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4255a-171">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="4255a-171">See also</span></span>

- [<span data-ttu-id="4255a-172">Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки</span><span class="sxs-lookup"><span data-stu-id="4255a-172">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
