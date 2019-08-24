---
title: Пошаговое руководство. Создание составного элемента управления с помощью C#
ms.date: 03/30/2017
dev_langs:
- CSharp
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d1af6c0e013f82569eed8d085df0249f4fb991bb
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015684"
---
# <a name="walkthrough-author-a-composite-control-with-c"></a><span data-ttu-id="fd4ff-102">Пошаговое руководство. Создание составного элемента управления с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="fd4ff-102">Walkthrough: Author a Composite Control with C\#</span></span>

<span data-ttu-id="fd4ff-103">Составные элементы управления предоставляют средства для создания и повторного использования настраиваемых графических интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="fd4ff-104">Составной элемент управления — это компонент, имеющий визуальное представление.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="fd4ff-105">Таким образом, он может состоять из одного или нескольких элементов управления, компонентов или блоков кода Windows Forms, позволяющих расширить функциональные возможности за счет проверки введенных пользователем данных, изменения свойств отображения или выполнения других предусмотренных разработчиком действий.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="fd4ff-106">Составные элементы управления можно вставлять в Windows Forms точно так же, как другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="fd4ff-107">В первой части этого пошагового руководства мы создадим простой составной элемент управления с именем `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="fd4ff-108">Во второй части мы расширим функциональность `ctlClock` за счет наследования.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="fd4ff-109">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="fd4ff-109">Create the Project</span></span>

<span data-ttu-id="fd4ff-110">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="fd4ff-111">Создание библиотеки элементов управления ctlClockLib и элемента управления ctlClock</span><span class="sxs-lookup"><span data-stu-id="fd4ff-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="fd4ff-112">В Visual Studio создайте новый проект **библиотеки элементов управления Windows Forms** и назовите его **ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-112">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ctlClockLib**.</span></span>

     <span data-ttu-id="fd4ff-113">Имя проекта, `ctlClockLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-113">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="fd4ff-114">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-114">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="fd4ff-115">Например, если в двух сборках содержатся компоненты с именем `ctlClock`, можно указать компонент `ctlClock`, используя `ctlClockLib.ctlClock.`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-115">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

2. <span data-ttu-id="fd4ff-116">В **Обозреватель решений**щелкните правой кнопкой мыши **UserControl1.CS**и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-116">In **Solution Explorer**, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="fd4ff-117">Измените имя файла на `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-117">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="fd4ff-118">Чтобы переименовать все ссылки на элемент кода UserControl1, в соответствующем запросе нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-118">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd4ff-119">По умолчанию составной элемент управления наследует от <xref:System.Windows.Forms.UserControl> класса, предоставляемого системой.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-119">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="fd4ff-120"><xref:System.Windows.Forms.UserControl> Класс предоставляет функциональные возможности, необходимые для всех составных элементов управления, и реализует стандартные методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-120">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

3. <span data-ttu-id="fd4ff-121">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-121">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="fd4ff-122">Добавление элементов управления и компонентов Windows в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-122">Add Windows Controls and Components to the Composite Control</span></span>

<span data-ttu-id="fd4ff-123">Визуальный интерфейс представляет собой важную часть составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-123">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="fd4ff-124">Он реализуется путем добавления одного или нескольких элементов управления Windows на поверхность конструктора.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-124">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="fd4ff-125">В следующем примере мы добавим элементы управления Windows в составной элемент управления и напишем код для реализации функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-125">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="fd4ff-126">Добавление метки и таймера в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-126">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="fd4ff-127">В **Обозреватель решений**щелкните правой кнопкой мыши **ctlClock.CS**и выберите пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-127">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="fd4ff-128">На **панели элементов** разверните узел **Общие элементы управления**, а затем дважды щелкните пункт **Метка**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-128">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="fd4ff-129">Элемент управления с `label1` именем добавляется к элементу управления в области конструктора. <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="fd4ff-129">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="fd4ff-130">В конструкторе щелкните пункт **Label1**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-130">In the designer, click **label1**.</span></span> <span data-ttu-id="fd4ff-131">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-131">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="fd4ff-132">Свойство.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-132">Property</span></span>|<span data-ttu-id="fd4ff-133">Измените на</span><span class="sxs-lookup"><span data-stu-id="fd4ff-133">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="fd4ff-134">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-134">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="fd4ff-135">**Text**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-135">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="fd4ff-136">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-136">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="fd4ff-137">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-137">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="fd4ff-138">На **панели элементов** разверните узел **Компоненты**, а затем дважды щелкните пункт **Таймер**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-138">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="fd4ff-139">Поскольку элемент <xref:System.Windows.Forms.Timer> является компонентом, он не имеет визуального представления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-139">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="fd4ff-140">В связи с этим он отображается не с элементами управления на поверхности конструктора, а в **конструкторе компонентов** (область в нижней части поверхности конструктора).</span><span class="sxs-lookup"><span data-stu-id="fd4ff-140">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="fd4ff-141">В **конструкторе компонентов**щелкните **timer1** <xref:System.Windows.Forms.Timer.Interval%2A> , а затем присвойте `true`свойству `1000` значение, а <xref:System.Windows.Forms.Timer.Enabled%2A> свойству — значение.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-141">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>

     <span data-ttu-id="fd4ff-142">Свойство определяет частоту, с <xref:System.Windows.Forms.Timer> которой компонент тикает. <xref:System.Windows.Forms.Timer.Interval%2A></span><span class="sxs-lookup"><span data-stu-id="fd4ff-142">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="fd4ff-143">При каждом такте `timer1` оно запускает код в событии `timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-143">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="fd4ff-144">Интервал представляет время между тактами в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-144">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="fd4ff-145">В **конструкторе компонентов** дважды щелкните **timer1**, чтобы перейти к событию `timer1_Tick` для `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-145">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="fd4ff-146">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-146">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="fd4ff-147">Измените модификатор доступа с `private` на `protected`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-147">Be sure to change the access modifier from `private` to `protected`.</span></span>

    ```csharp
    protected void timer1_Tick(object sender, System.EventArgs e)
    {
        // Causes the label to display the current time.
        lblDisplay.Text = DateTime.Now.ToLongTimeString();
    }
    ```

     <span data-ttu-id="fd4ff-148">Этот код вызывает отображение текущего времени в `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-148">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="fd4ff-149">Поскольку для интервала `timer1` было задано значение `1000`, это событие возникает через каждую тысячу миллисекунд, а значит, текущее время обновляется каждую секунду.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-149">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="fd4ff-150">Измените метод, разрешив его переопределение с помощью ключевого слова `virtual`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-150">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="fd4ff-151">Дополнительные сведения см. ниже в разделе "Наследование из пользовательского элемента управления".</span><span class="sxs-lookup"><span data-stu-id="fd4ff-151">For more information, see the  "Inheriting from a User Control" section below.</span></span>

    ```csharp
    protected virtual void timer1_Tick(object sender, System.EventArgs e)
    ```

9. <span data-ttu-id="fd4ff-152">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-152">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="add-properties-to-the-composite-control"></a><span data-ttu-id="fd4ff-153">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-153">Add Properties to the Composite Control</span></span>

<span data-ttu-id="fd4ff-154">Элемент управления "Часы" теперь инкапсулирует <xref:System.Windows.Forms.Label> элемент управления <xref:System.Windows.Forms.Timer> и компонент, каждый из которых имеет собственный набор встроенных свойств.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-154">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="fd4ff-155">Несмотря на то что отдельные свойства этих элементов управления не будут доступны последующим пользователям вашего элемента управления, вы можете создать и предоставить настраиваемые свойства, написав соответствующие блоки кода.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-155">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="fd4ff-156">Выполняя следующую процедуру, вы добавите в элемент управления свойства, позволяющие пользователю изменять цвет фона и текста.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-156">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="fd4ff-157">Добавление свойства в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-157">To add a property to your composite control</span></span>

1. <span data-ttu-id="fd4ff-158">В **Обозреватель решений**щелкните правой кнопкой мыши **ctlClock.CS**и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-158">In **Solution Explorer**, right-click **ctlClock.cs**, and then click **View Code**.</span></span>

     <span data-ttu-id="fd4ff-159">Откроется **редактор кода** для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-159">The **Code Editor** for your control opens.</span></span>

2. <span data-ttu-id="fd4ff-160">Найдите оператор `public partial class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-160">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="fd4ff-161">Под открывающей скобкой (`{)` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-161">Beneath the opening brace (`{)`, type the following code.</span></span>

    ```csharp
    private Color colFColor;
    private Color colBColor;
    ```

     <span data-ttu-id="fd4ff-162">Эти операторы создают закрытые переменные для хранения значений свойств, которые вы собираетесь создать.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-162">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="fd4ff-163">Введите или вставьте следующий код под объявлениями переменных из шага 2.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-163">Enter or paste the following code beneath the variable declarations from step 2.</span></span>

    ```csharp
    // Declares the name and type of the property.
    public Color ClockBackColor
    {
        // Retrieves the value of the private variable colBColor.
        get
        {
            return colBColor;
        }
        // Stores the selected value in the private variable colBColor, and
        // updates the background color of the label control lblDisplay.
        set
        {
            colBColor = value;
            lblDisplay.BackColor = colBColor;
        }
    }
    // Provides a similar set of instructions for the foreground color.
    public Color ClockForeColor
    {
        get
        {
            return colFColor;
        }
        set
        {
            colFColor = value;
            lblDisplay.ForeColor = colFColor;
        }
    }
    ```

     <span data-ttu-id="fd4ff-164">Приведенный выше код обеспечивает доступ к двум настраиваемым свойствам, `ClockForeColor` и `ClockBackColor`, для последующих пользователей данного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-164">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="fd4ff-165">Операторы `get` и `set` позволяют хранить и извлекать значение свойства, а также предоставляют код для реализации соответствующих этому свойству функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-165">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="fd4ff-166">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-166">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="fd4ff-167">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-167">Test the Control</span></span>

<span data-ttu-id="fd4ff-168">Элементы управления не являются автономными приложениями и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-168">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="fd4ff-169">Проверьте поведение элемента управления в среде выполнения и испытайте его свойства в **тестовом контейнере пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-169">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="fd4ff-170">Дополнительные сведения см. в разделе [Как Проверка поведения элемента управления UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-170">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="fd4ff-171">Проверка элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-171">To test your control</span></span>

1. <span data-ttu-id="fd4ff-172">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить элемент управления в **тестовом контейнере UserControl**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-172">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="fd4ff-173">В таблице свойств тестового контейнера выберите свойство `ClockBackColor`, а затем свойство, чтобы открыть палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-173">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>

3. <span data-ttu-id="fd4ff-174">Щелкните нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-174">Choose a color by clicking it.</span></span>

   <span data-ttu-id="fd4ff-175">Цвет фона элемента управления изменится на выбранный.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-175">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="fd4ff-176">Используя аналогичную последовательность событий, проверьте, функционирует ли свойство `ClockForeColor` должным образом.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-176">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

   <span data-ttu-id="fd4ff-177">Из этого и предыдущих разделов вы узнали, как объединить компоненты и элементы управления Windows с кодом и упаковкой и, таким образом, предоставить настраиваемые функциональные возможности в виде составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-177">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="fd4ff-178">Вы узнали, как вывести свойства в составной элемент управления и проверить элемент управления после того, как он будет готов.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-178">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="fd4ff-179">В следующем разделе вы узнаете, как сконструировать производный составной элемент управления, используя в качестве базы `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-179">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inherit-from-a-composite-control"></a><span data-ttu-id="fd4ff-180">Наследование от составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-180">Inherit from a Composite Control</span></span>

<span data-ttu-id="fd4ff-181">В предыдущих разделах вы узнали, как объединить элементы управления, компоненты и код Windows в составные элементы управления, доступные для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-181">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="fd4ff-182">После этого составной элемент управления можно использовать как базу, на основе которой будут создаваться другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-182">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="fd4ff-183">Процесс создания класса, производного от базового, называется *наследованием*.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-183">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="fd4ff-184">В этом разделе вы создадите составной элемент управления с именем `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-184">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="fd4ff-185">Он будет производным от родительского элемента управления, `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-185">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="fd4ff-186">Вы узнаете, как расширить функциональные возможности `ctlClock`, переопределив методы родительского класса и добавив новые методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-186">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

<span data-ttu-id="fd4ff-187">Первый шаг в создании производного элемента управления — это его наследование из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-187">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="fd4ff-188">Это действие создает новый элемент управления, обладающий всеми свойствами, методами и графическими характеристиками родительского элемента управления, а также может служить основой для добавления или изменения функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-188">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="fd4ff-189">Создание производного элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-189">To create the inherited control</span></span>

1. <span data-ttu-id="fd4ff-190">В **Обозреватель решений**щелкните правой кнопкой мыши **ctlClockLib**, наведите указатель на пункт **Добавить**и выберите пункт **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-190">In **Solution Explorer**, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="fd4ff-191">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-191">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="fd4ff-192">Выберите шаблон **Производный пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-192">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="fd4ff-193">В поле **Имя** введите `ctlAlarmClock.cs` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-193">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>

     <span data-ttu-id="fd4ff-194">Откроется диалоговое окно **Выбор компонентов для наследования**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-194">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="fd4ff-195">В разделе **Имя компонента** дважды щелкните файл **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-195">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="fd4ff-196">В **Обозреватель решений**просмотрите текущие проекты.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-196">In **Solution Explorer**, browse through the current projects.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd4ff-197">Файл с именем **элемент ctlAlarmClock. cs** будет добавлен в текущий проект.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-197">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>

### <a name="add-the-alarm-properties"></a><span data-ttu-id="fd4ff-198">Добавление свойств оповещения</span><span class="sxs-lookup"><span data-stu-id="fd4ff-198">Add the Alarm Properties</span></span>

<span data-ttu-id="fd4ff-199">Свойства, добавляются в производный элемент управления точно так же, как в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-199">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="fd4ff-200">Теперь, используя синтаксис объявления свойств, добавим в элемент управления два свойства: свойство `AlarmTime`, в котором хранится значение даты и времени отключения будильника, и свойство `AlarmSet`, определяющее время срабатывания будильника.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-200">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="fd4ff-201">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-201">To add properties to your composite control</span></span>

1. <span data-ttu-id="fd4ff-202">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ctlAlarmClock**и выберите пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-202">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="fd4ff-203">Найдите оператор `public class`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-203">Locate the `public class` statement.</span></span> <span data-ttu-id="fd4ff-204">Обратите внимание, что элемент управления наследуется из `ctlClockLib.ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-204">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="fd4ff-205">Под открывающей скобкой оператора (`{)` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-205">Beneath the opening brace (`{)` statement, type the following code.</span></span>

    ```csharp
    private DateTime dteAlarmTime;
    private bool blnAlarmSet;
    // These properties will be declared as public to allow future
    // developers to access them.
    public DateTime AlarmTime
    {
        get
        {
            return dteAlarmTime;
        }
        set
        {
            dteAlarmTime = value;
        }
    }
    public bool AlarmSet
    {
        get
        {
            return blnAlarmSet;
        }
        set
        {
            blnAlarmSet = value;
        }
    }
    ```

### <a name="add-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="fd4ff-206">Добавить в графический интерфейс элемента управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-206">Add to the Graphical Interface of the Control</span></span>

<span data-ttu-id="fd4ff-207">Производный элемент управления получает такой же графический интерфейс, как у того элемента, из которого он наследуется.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-207">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="fd4ff-208">Кроме того, он включает те же составные элементы управления, что и родительский элемент управления, однако свойства этих составных элементов будут доступны, только если предоставить их напрямую.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-208">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="fd4ff-209">Графический интерфейс производного элемента управления добавляется точно так же, как и для любого составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-209">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="fd4ff-210">Чтобы продолжить добавление графического интерфейса для будильника, добавим элемент управления Label, который будет мигать при срабатывании будильника.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-210">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="fd4ff-211">Добавление элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="fd4ff-211">To add the label control</span></span>

1. <span data-ttu-id="fd4ff-212">В **Обозреватель решений**щелкните правой кнопкой мыши элемент **ctlAlarmClock**и выберите пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-212">In **Solution Explorer**, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>

     <span data-ttu-id="fd4ff-213">Конструктор для `ctlAlarmClock` откроется в главном окне.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-213">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="fd4ff-214">Нажмите на отображаемую область элемента управления и просмотрите окно свойств.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-214">Click the display portion of the control, and view the Properties window.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd4ff-215">Все свойства отображаются, но недоступны.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-215">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="fd4ff-216">Это означает, что эти свойства являются собственными свойствами `lblDisplay`, в окне свойств изменить их или получить к ним доступ нельзя.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-216">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="fd4ff-217">По умолчанию элементы управления, входящие в составной элемент управления, имеют статус `private` и их свойства недоступны.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-217">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd4ff-218">Чтобы последующие пользователи составного элемента управления получили доступ к входящим в него элементам управления, объявите их как `public` или `protected`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-218">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="fd4ff-219">Это позволит вам задавать и изменять свойства элементов управления в составном элементе управления, используя соответствующий код.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-219">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="fd4ff-220"><xref:System.Windows.Forms.Label> Добавьте элемент управления в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-220">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="fd4ff-221">С помощью мыши перетащите <xref:System.Windows.Forms.Label> элемент управления непосредственно под полем.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-221">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="fd4ff-222">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-222">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="fd4ff-223">Свойство.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-223">Property</span></span>|<span data-ttu-id="fd4ff-224">Параметр</span><span class="sxs-lookup"><span data-stu-id="fd4ff-224">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="fd4ff-225">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-225">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="fd4ff-226">**Text**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-226">**Text**</span></span>|<span data-ttu-id="fd4ff-227">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-227">**Alarm!**</span></span>|
    |<span data-ttu-id="fd4ff-228">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-228">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="fd4ff-229">**Visible**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-229">**Visible**</span></span>|`false`|

### <a name="add-the-alarm-functionality"></a><span data-ttu-id="fd4ff-230">Добавление функции будильника</span><span class="sxs-lookup"><span data-stu-id="fd4ff-230">Add the Alarm Functionality</span></span>

<span data-ttu-id="fd4ff-231">Выполняя предыдущие процедуры, вы добавили свойства и элемент управления, которые обеспечат функциональность будильника в составном элементе управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-231">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="fd4ff-232">В ходе этой процедуры вы добавите код, который будет сравнивать текущее время со временем будильника и, если они совпадают, запускать мигающее оповещение.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-232">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="fd4ff-233">Переопределив метод `timer1_Tick` в `ctlClock` и добавив в него дополнительный код, вы расширите возможности `ctlAlarmClock`, сохранив при этом все унаследованные функции `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-233">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="fd4ff-234">Переопределение метода Timer1_Tick в ctlClock</span><span class="sxs-lookup"><span data-stu-id="fd4ff-234">To override the timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="fd4ff-235">В **редакторе кода** найдите оператор `private bool blnAlarmSet;`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-235">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="fd4ff-236">Сразу после него добавьте следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-236">Immediately beneath it, add the following statement.</span></span>

    ```csharp
    private bool blnColorTicker;
    ```

2. <span data-ttu-id="fd4ff-237">В **редакторе кода** найдите закрывающую скобку (`})` в конце класса.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-237">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="fd4ff-238">Непосредственно перед скобкой добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-238">Just before the brace, add the following code.</span></span>

    ```csharp
    protected override void timer1_Tick(object sender, System.EventArgs e)
    {
        // Calls the Timer1_Tick method of ctlClock.
        base.timer1_Tick(sender, e);
        // Checks to see if the alarm is set.
        if (AlarmSet == false)
            return;
        else
            // If the date, hour, and minute of the alarm time are the same as
            // the current time, flash an alarm.
        {
            if (AlarmTime.Date == DateTime.Now.Date && AlarmTime.Hour ==
                DateTime.Now.Hour && AlarmTime.Minute == DateTime.Now.Minute)
            {
                // Sets lblAlarmVisible to true, and changes the background color based on
                // the value of blnColorTicker. The background color of the label
                // will flash once per tick of the clock.
                lblAlarm.Visible = true;
                if (blnColorTicker == false)
                {
                    lblAlarm.BackColor = Color.Red;
                    blnColorTicker = true;
                }
                else
                {
                    lblAlarm.BackColor = Color.Blue;
                    blnColorTicker = false;
                }
            }
            else
            {
                // Once the alarm has sounded for a minute, the label is made
                // invisible again.
                lblAlarm.Visible = false;
            }
        }
    }
    ```

     <span data-ttu-id="fd4ff-239">Добавление этого кода решает сразу несколько задач.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-239">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="fd4ff-240">Оператор `override` указывает элементу управления использовать этот метод вместо метода, унаследованного из базового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-240">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="fd4ff-241">При вызове этого метода он вызывает переопределяемый метод, используя оператор `base.timer1_Tick`, и следит за тем, чтобы в этом элементе управления были реализованы все функции исходного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-241">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="fd4ff-242">Затем он выполняет дополнительный код, реализующий функции будильника.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-242">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="fd4ff-243">Когда будильник срабатывает, появляется мигающая метка.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-243">A flashing label control will appear when the alarm occurs.</span></span>

     <span data-ttu-id="fd4ff-244">Элемент управления "Будильник" почти готов.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-244">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="fd4ff-245">Осталось реализовать только его отключение.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-245">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="fd4ff-246">Для этого нужно добавить код в метод `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-246">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="fd4ff-247">Реализация метода отключения</span><span class="sxs-lookup"><span data-stu-id="fd4ff-247">To implement the shutoff method</span></span>

1. <span data-ttu-id="fd4ff-248">В **Обозреватель решений**щелкните правой кнопкой мыши **ctlAlarmClock.CS**и выберите пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-248">In **Solution Explorer**, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>

     <span data-ttu-id="fd4ff-249">Откроется конструктор.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-249">The designer opens.</span></span>

2. <span data-ttu-id="fd4ff-250">Добавьте кнопку в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-250">Add a button to the control.</span></span> <span data-ttu-id="fd4ff-251">Задайте свойства для этой кнопки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-251">Set the properties of the button as follows.</span></span>

    |<span data-ttu-id="fd4ff-252">Свойство.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-252">Property</span></span>|<span data-ttu-id="fd4ff-253">Значение</span><span class="sxs-lookup"><span data-stu-id="fd4ff-253">Value</span></span>|
    |--------------|-----------|
    |<span data-ttu-id="fd4ff-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-254">**Name**</span></span>|`btnAlarmOff`|
    |<span data-ttu-id="fd4ff-255">**Text**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-255">**Text**</span></span>|<span data-ttu-id="fd4ff-256">**Отключить оповещение**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-256">**Disable Alarm**</span></span>|

3. <span data-ttu-id="fd4ff-257">В конструкторе дважды щелкните элемент управления **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-257">In the designer, double-click **btnAlarmOff**.</span></span>

     <span data-ttu-id="fd4ff-258">Откроется **редактор кода** со строкой `private void btnAlarmOff_Click`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-258">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>

4. <span data-ttu-id="fd4ff-259">Измените метод, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-259">Modify this method so that it resembles the following code.</span></span>

    ```csharp
    private void btnAlarmOff_Click(object sender, System.EventArgs e)
    {
        // Turns off the alarm.
        AlarmSet = false;
        // Hides the flashing label.
        lblAlarm.Visible = false;
    }
    ```

5. <span data-ttu-id="fd4ff-260">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-260">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="use-the-inherited-control-on-a-form"></a><span data-ttu-id="fd4ff-261">Использование наследуемого элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="fd4ff-261">Use the Inherited Control on a Form</span></span>

<span data-ttu-id="fd4ff-262">Вы можете протестировать наследуемый элемент управления так же, как вы протестировали элемент управления `ctlClock`базового класса: Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить элемент управления в **тестовом контейнере UserControl**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-262">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="fd4ff-263">Дополнительные сведения см. в разделе [Практическое руководство. Проверка поведения элемента управления UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-263">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

<span data-ttu-id="fd4ff-264">Чтобы элемент управления можно было использовать, необходимо поместить его в форму.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-264">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="fd4ff-265">Производный составной элемент управления, как и стандартный, не может быть автономным и должен быть размещен в форме или другом контейнере.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-265">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="fd4ff-266">Поскольку `ctlAlarmClock` отличается более широкими функциональными возможностями, для его проверки требуется дополнительный код.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-266">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="fd4ff-267">В ходе этой процедуры вы напишете простую программу для проверки функциональных возможностей `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-267">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="fd4ff-268">Вы напишете код, задающий и отображающий свойство `AlarmTime` в `ctlAlarmClock` и проверяющий его унаследованные функции.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-268">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="fd4ff-269">Сборка и добавление элемента управления в тестовую форму</span><span class="sxs-lookup"><span data-stu-id="fd4ff-269">To build and add your control to a test form</span></span>

1. <span data-ttu-id="fd4ff-270">В **Обозреватель решений**щелкните правой кнопкой мыши **ctlClockLib**и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-270">In **Solution Explorer**, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="fd4ff-271">Добавьте в решение новый проект **приложения Windows** и назовите его **Test**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-271">Add a new **Windows Application** project to the solution, and name it **Test**.</span></span>

3. <span data-ttu-id="fd4ff-272">В **Обозреватель решений**щелкните правой кнопкой мыши узел **ссылки** для тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-272">In **Solution Explorer**, right-click the **References** node for your test project.</span></span> <span data-ttu-id="fd4ff-273">Щелкните **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-273">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="fd4ff-274">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-274">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="fd4ff-275">Проект `ctlClockLib` будет указан под полем **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-275">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="fd4ff-276">Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-276">Double-click the project to add the reference to the test project.</span></span>

4. <span data-ttu-id="fd4ff-277">В **Обозреватель решений**щелкните правой кнопкой мыши **тест**и выберите пункт **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-277">In **Solution Explorer**, right-click **Test**, and then click **Build**.</span></span>

5. <span data-ttu-id="fd4ff-278">На **панели элементов** разверните узел **Компоненты ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-278">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

6. <span data-ttu-id="fd4ff-279">Дважды щелкните **ctlAlarmClock**, чтобы добавить копию `ctlAlarmClock` в свою форму.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-279">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>

7. <span data-ttu-id="fd4ff-280">На **панели элементов**найдите и дважды щелкните элемент **DateTimePicker** , чтобы добавить его <xref:System.Windows.Forms.DateTimePicker> в <xref:System.Windows.Forms.Label> форму, а затем добавьте элемент управления, дважды щелкнув надпись.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-280">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

8. <span data-ttu-id="fd4ff-281">С помощью мыши разместите элементы управления в удобном месте формы.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-281">Use the mouse to position the controls in a convenient place on the form.</span></span>

9. <span data-ttu-id="fd4ff-282">Задайте свойства этих элементов управления следующим образом.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-282">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="fd4ff-283">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-283">Control</span></span>|<span data-ttu-id="fd4ff-284">Свойство</span><span class="sxs-lookup"><span data-stu-id="fd4ff-284">Property</span></span>|<span data-ttu-id="fd4ff-285">Значение</span><span class="sxs-lookup"><span data-stu-id="fd4ff-285">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="fd4ff-286">**Text**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-286">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="fd4ff-287">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-287">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="fd4ff-288">**Name**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-288">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="fd4ff-289">**Формат**</span><span class="sxs-lookup"><span data-stu-id="fd4ff-289">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

10. <span data-ttu-id="fd4ff-290">В конструкторе дважды щелкните **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-290">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="fd4ff-291">В **редакторе кода** откроется `private void dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-291">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>

11. <span data-ttu-id="fd4ff-292">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-292">Modify the code so that it resembles the following.</span></span>

    ```csharp
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)
    {
        ctlAlarmClock1.AlarmTime = dtpTest.Value;
        ctlAlarmClock1.AlarmSet = true;
        lblTest.Text = "Alarm Time is " +
            ctlAlarmClock1.AlarmTime.ToShortTimeString();
    }
    ```

12. <span data-ttu-id="fd4ff-293">В **Обозреватель решений**щелкните правой кнопкой мыши **тест**и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-293">In **Solution Explorer**, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

13. <span data-ttu-id="fd4ff-294">В меню **Отладка** щелкните **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-294">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="fd4ff-295">Запустится тестовая программа.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-295">The test program starts.</span></span> <span data-ttu-id="fd4ff-296">Обратите внимание, что текущее время обновляется в `ctlAlarmClock` элементе управления, а время начала отображается <xref:System.Windows.Forms.DateTimePicker> в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-296">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

14. <span data-ttu-id="fd4ff-297">Щелкните, <xref:System.Windows.Forms.DateTimePicker> где отображаются минуты часа.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-297">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

15. <span data-ttu-id="fd4ff-298">С помощью клавиатуры укажите значение минут, составляющее на одну минуту больше текущего времени, отображаемого `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-298">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="fd4ff-299">Время включения будильника отображается в `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-299">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="fd4ff-300">Дождитесь момента, когда отображаемое время совпадет с установленным временем будильника.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-300">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="fd4ff-301">Когда это произойдет, `lblAlarm` начнет мигать.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-301">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>

16. <span data-ttu-id="fd4ff-302">Отключите сигнал, нажав `btnAlarmOff`.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-302">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="fd4ff-303">Теперь будильник можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-303">You may now reset the alarm.</span></span>

<span data-ttu-id="fd4ff-304">В этой статье было рассмотрено несколько основных концепций.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-304">This article has covered a number of key concepts.</span></span> <span data-ttu-id="fd4ff-305">Вы узнали, как создать составной элемент управления, объединив элементы управления и компоненты в контейнер составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-305">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="fd4ff-306">Вы узнали, как добавить свойства в элемент управления и написать код для реализации настраиваемых функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-306">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="fd4ff-307">В последнем разделе вы узнали, как расширять функциональные возможности заданного составного элемента управления с помощью наследования и как изменять функциональные возможности методов узла путем переопределения методов.</span><span class="sxs-lookup"><span data-stu-id="fd4ff-307">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd4ff-308">См. также</span><span class="sxs-lookup"><span data-stu-id="fd4ff-308">See also</span></span>

- [<span data-ttu-id="fd4ff-309">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="fd4ff-309">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="fd4ff-310">Практическое руководство. Отображение элемента управления в диалоговом окне "Выбор элементов панели элементов"</span><span class="sxs-lookup"><span data-stu-id="fd4ff-310">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="fd4ff-311">Пошаговое руководство: Наследование от элемента управления Windows Forms с помощью VisualC#</span><span class="sxs-lookup"><span data-stu-id="fd4ff-311">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
