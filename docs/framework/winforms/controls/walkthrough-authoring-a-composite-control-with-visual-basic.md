---
title: Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Visual Basic]
- user controls [Visual Basic]
- UserControl class [Windows Forms], walkthroughs
- user controls [Windows Forms], creating with Visual Basic
- controls [Windows Forms], composite controls
- composite controls [Windows Forms], creating
- custom controls [Windows Forms], creating
ms.assetid: f50e270e-4db2-409a-8319-6db6ca5c7daf
ms.openlocfilehash: abfb91c61ef72bfc1626b4cc4dcea42b75e2ab35
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040246"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-basic"></a><span data-ttu-id="4b4bf-102">Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4b4bf-102">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>
<span data-ttu-id="4b4bf-103">Составные элементы управления предоставляют средства для создания и повторного использования настраиваемых графических интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="4b4bf-104">Составной элемент управления — это компонент, имеющий визуальное представление.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="4b4bf-105">Таким образом, он может состоять из одного или нескольких элементов управления, компонентов или блоков кода Windows Forms, позволяющих расширить функциональные возможности за счет проверки введенных пользователем данных, изменения свойств отображения или выполнения других предусмотренных разработчиком действий.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="4b4bf-106">Составные элементы управления можно вставлять в Windows Forms точно так же, как другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="4b4bf-107">В первой части этого пошагового руководства мы создадим простой составной элемент управления с именем `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="4b4bf-108">Во второй части мы расширим функциональность `ctlClock` за счет наследования.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="4b4bf-109">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4b4bf-109">Creating the Project</span></span>
 <span data-ttu-id="4b4bf-110">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-110">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="4b4bf-111">Создание библиотеки элементов управления ctlClockLib и элемента управления ctlClock</span><span class="sxs-lookup"><span data-stu-id="4b4bf-111">To create the ctlClockLib control library and the ctlClock control</span></span>

1. <span data-ttu-id="4b4bf-112">В меню **Файл** наведите указатель мыши на пункт **Создать** и выберите **Проект**, чтобы открыть диалоговое окно **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-112">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="4b4bf-113">В списке проектов Visual Basic выберите шаблон проект **библиотеки элементов управления Windows** , введите `ctlClockLib` в поле **имя** и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-113">From the list of Visual Basic projects, select the **Windows Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>

     <span data-ttu-id="4b4bf-114">Имя проекта, `ctlClockLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-114">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="4b4bf-115">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-115">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="4b4bf-116">Например, если в двух сборках содержатся компоненты с именем `ctlClock`, можно указать компонент `ctlClock`, используя `ctlClockLib.ctlClock.`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-116">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>

3. <span data-ttu-id="4b4bf-117">В обозревателе решений щелкните файл **UserControl1.vb** правой кнопкой мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-117">In Solution Explorer, right-click **UserControl1.vb**, and then click **Rename**.</span></span> <span data-ttu-id="4b4bf-118">Измените имя файла на `ctlClock.vb`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-118">Change the file name to `ctlClock.vb`.</span></span> <span data-ttu-id="4b4bf-119">Чтобы переименовать все ссылки на элемент кода UserControl1, в соответствующем запросе нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-119">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4b4bf-120">По умолчанию составной элемент управления наследует от <xref:System.Windows.Forms.UserControl> класса, предоставляемого системой.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-120">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="4b4bf-121"><xref:System.Windows.Forms.UserControl> Класс предоставляет функциональные возможности, необходимые для всех составных элементов управления, и реализует стандартные методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-121">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>

4. <span data-ttu-id="4b4bf-122">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-122">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="4b4bf-123">Добавление элементов управления и компонентов Windows в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-123">Adding Windows Controls and Components to the Composite Control</span></span>
 <span data-ttu-id="4b4bf-124">Визуальный интерфейс представляет собой важную часть составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-124">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="4b4bf-125">Он реализуется путем добавления одного или нескольких элементов управления Windows на поверхность конструктора.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-125">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="4b4bf-126">В следующем примере мы добавим элементы управления Windows в составной элемент управления и напишем код для реализации функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-126">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>

### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="4b4bf-127">Добавление метки и таймера в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-127">To add a Label and a Timer to your composite control</span></span>

1. <span data-ttu-id="4b4bf-128">В обозревателе решений щелкните файл **ctlClock.vb** правой кнопкой мыши и выберите пункт **Открыть в конструкторе**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-128">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="4b4bf-129">На панели элементов разверните узел **Общие элементы управления**, а затем дважды щелкните пункт **Метка**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-129">In the Toolbox, expand the **Common Controls** node, and then double-click **Label**.</span></span>

     <span data-ttu-id="4b4bf-130">Элемент управления с `Label1` именем добавляется к элементу управления в области конструктора. <xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="4b4bf-130">A <xref:System.Windows.Forms.Label> control named `Label1` is added to your control on the designer surface.</span></span>

3. <span data-ttu-id="4b4bf-131">В конструкторе щелкните пункт **Label1**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-131">In the designer, click **Label1**.</span></span> <span data-ttu-id="4b4bf-132">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-132">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="4b4bf-133">Свойство.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-133">Property</span></span>|<span data-ttu-id="4b4bf-134">Измените на</span><span class="sxs-lookup"><span data-stu-id="4b4bf-134">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="4b4bf-135">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-135">**Name**</span></span>|`lblDisplay`|
    |<span data-ttu-id="4b4bf-136">**Text**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-136">**Text**</span></span>|`(blank space)`|
    |<span data-ttu-id="4b4bf-137">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-137">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="4b4bf-138">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-138">**Font.Size**</span></span>|`14`|

4. <span data-ttu-id="4b4bf-139">На **панели элементов** разверните узел **Компоненты**, а затем дважды щелкните пункт **Таймер**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-139">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>

     <span data-ttu-id="4b4bf-140">Поскольку элемент <xref:System.Windows.Forms.Timer> является компонентом, он не имеет визуального представления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-140">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="4b4bf-141">В связи с этим он отображается не с элементами управления на поверхности конструктора, а в конструкторе компонентов (область в нижней части поверхности конструктора).</span><span class="sxs-lookup"><span data-stu-id="4b4bf-141">Therefore, it does not appear with the controls on the designer surface, but rather in the Component Designer (a tray at the bottom of the designer surface).</span></span>

5. <span data-ttu-id="4b4bf-142">В конструкторе компонентов щелкните **timer1**, а затем <xref:System.Windows.Forms.Timer.Interval%2A> присвойте <xref:System.Windows.Forms.Timer.Enabled%2A> свойству `1000` значение, а свойству `True`— значение.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-142">In the Component Designer, click **Timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `True`.</span></span>

     <span data-ttu-id="4b4bf-143"><xref:System.Windows.Forms.Timer.Interval%2A> Свойство определяет частоту, с которой компонент Timer тикает.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-143">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the timer component ticks.</span></span> <span data-ttu-id="4b4bf-144">При каждом такте `Timer1` оно запускает код в событии `Timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-144">Each time `Timer1` ticks, it runs the code in the `Timer1_Tick` event.</span></span> <span data-ttu-id="4b4bf-145">Интервал представляет время между тактами в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-145">The interval represents the number of milliseconds between ticks.</span></span>

6. <span data-ttu-id="4b4bf-146">В конструкторе компонентов дважды щелкните **Timer1**, чтобы перейти к событию `Timer1_Tick` для `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-146">In the Component Designer, double-click **Timer1** to go to the `Timer1_Tick` event for `ctlClock`.</span></span>

7. <span data-ttu-id="4b4bf-147">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-147">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="4b4bf-148">Измените модификатор доступа с `Private` на `Protected`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-148">Be sure to change the access modifier from `Private` to `Protected`.</span></span>

    ```vb
    Protected Sub Timer1_Tick(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles Timer1.Tick
        ' Causes the label to display the current time.
        lblDisplay.Text = Format(Now, "hh:mm:ss")
    End Sub
    ```

     <span data-ttu-id="4b4bf-149">Этот код вызывает отображение текущего времени в `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-149">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="4b4bf-150">Поскольку для интервала `Timer1` было задано значение `1000`, это событие возникает через каждую тысячу миллисекунд, а значит, текущее время обновляется каждую секунду.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-150">Because the interval of `Timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>

8. <span data-ttu-id="4b4bf-151">Измените метод для переопределения.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-151">Modify the method to be overridable.</span></span> <span data-ttu-id="4b4bf-152">Дополнительные сведения см. ниже в разделе "Наследование из пользовательского элемента управления".</span><span class="sxs-lookup"><span data-stu-id="4b4bf-152">For more information, see the "Inheriting from a User Control" section below.</span></span>

    ```vb
    Protected Overridable Sub Timer1_Tick(ByVal sender As Object, ByVal _
        e As System.EventArgs) Handles Timer1.Tick
    ```

9. <span data-ttu-id="4b4bf-153">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-153">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="4b4bf-154">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-154">Adding Properties to the Composite Control</span></span>
 <span data-ttu-id="4b4bf-155">Элемент управления "Часы" теперь инкапсулирует <xref:System.Windows.Forms.Label> элемент управления <xref:System.Windows.Forms.Timer> и компонент, каждый из которых имеет собственный набор встроенных свойств.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-155">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="4b4bf-156">Несмотря на то что отдельные свойства этих элементов управления не будут доступны последующим пользователям вашего элемента управления, вы можете создать и предоставить настраиваемые свойства, написав соответствующие блоки кода.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-156">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="4b4bf-157">Выполняя следующую процедуру, вы добавите в элемент управления свойства, позволяющие пользователю изменять цвет фона и текста.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-157">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>

### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="4b4bf-158">Добавление свойства в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-158">To add a property to your composite control</span></span>

1. <span data-ttu-id="4b4bf-159">В обозревателе решений щелкните файл **ctlClock.vb** правой кнопкой мыши и выберите пункт **Показать код**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-159">In Solution Explorer, right-click **ctlClock.vb**, and then click **View Code**.</span></span>

     <span data-ttu-id="4b4bf-160">Откроется редактор кода для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-160">The Code Editor for your control opens.</span></span>

2. <span data-ttu-id="4b4bf-161">Найдите оператор `Public Class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-161">Locate the `Public Class ctlClock` statement.</span></span> <span data-ttu-id="4b4bf-162">Под этим оператором введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-162">Beneath it, type the following code.</span></span>

    ```vb
    Private colFColor as Color
    Private colBColor as Color
    ```

     <span data-ttu-id="4b4bf-163">Эти операторы создают закрытые переменные для хранения значений свойств, которые вы собираетесь создать.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-163">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>

3. <span data-ttu-id="4b4bf-164">Вставьте следующий код под объявлениями переменных, созданными в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-164">Insert the following code beneath the variable declarations from step 2.</span></span>

    ```vb
    ' Declares the name and type of the property.
    Property ClockBackColor() as Color
        ' Retrieves the value of the private variable colBColor.
        Get
            Return colBColor
        End Get
        ' Stores the selected value in the private variable colBColor, and
        ' updates the background color of the label control lblDisplay.
        Set(ByVal value as Color)
            colBColor = value
            lblDisplay.BackColor = colBColor
        End Set

    End Property
    ' Provides a similar set of instructions for the foreground color.
    Property ClockForeColor() as Color
        Get
            Return colFColor
        End Get
        Set(ByVal value as Color)
            colFColor = value
            lblDisplay.ForeColor = colFColor
        End Set
    End Property
    ```

     <span data-ttu-id="4b4bf-165">Приведенный выше код обеспечивает доступ к двум настраиваемым свойствам, `ClockForeColor` и `ClockBackColor`, для последующих пользователей данного элемента управления, вызывая оператор `Property`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-165">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control by invoking the `Property` statement.</span></span> <span data-ttu-id="4b4bf-166">Операторы `Get` и `Set` позволяют хранить и извлекать значение свойства, а также предоставляют код для реализации соответствующих этому свойству функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-166">The `Get` and `Set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>

4. <span data-ttu-id="4b4bf-167">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-167">On the **File** menu, click **Save All** to save the project.</span></span>

## <a name="testing-the-control"></a><span data-ttu-id="4b4bf-168">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-168">Testing the Control</span></span>
 <span data-ttu-id="4b4bf-169">Элементы управления не являются автономными проектами и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-169">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="4b4bf-170">Проверьте поведение элемента управления в среде выполнения и испытайте его свойства в **тестовом контейнере пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-170">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="4b4bf-171">Дополнительные сведения см. в разделе [Как Проверка поведения элемента управления UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-171">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

### <a name="to-test-your-control"></a><span data-ttu-id="4b4bf-172">Проверка элемента управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-172">To test your control</span></span>

1. <span data-ttu-id="4b4bf-173">Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-173">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="4b4bf-174">В таблице свойств тестового контейнера выберите свойство `ClockBackColor`, а затем щелкните стрелку раскрывающегося списка, чтобы открыть палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-174">In the test container's property grid, select the `ClockBackColor` property, and then click the drop-down arrow to display the color palette.</span></span>

3. <span data-ttu-id="4b4bf-175">Щелкните нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-175">Choose a color by clicking it.</span></span>

     <span data-ttu-id="4b4bf-176">Цвет фона элемента управления изменится на выбранный.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-176">The background color of your control changes to the color you selected.</span></span>

4. <span data-ttu-id="4b4bf-177">Используя аналогичную последовательность событий, проверьте, функционирует ли свойство `ClockForeColor` должным образом.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-177">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>

5. <span data-ttu-id="4b4bf-178">Нажмите **Закрыть**, чтобы закрыть **тестовый контейнер пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-178">Click **Close** to close the **UserControl Test Container**.</span></span>

     <span data-ttu-id="4b4bf-179">Из этого и предыдущих разделов вы узнали, как объединить компоненты и элементы управления Windows с кодом и упаковкой и, таким образом, предоставить настраиваемые функциональные возможности в виде составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-179">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="4b4bf-180">Вы узнали, как вывести свойства в составной элемент управления и проверить элемент управления после того, как он будет готов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-180">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="4b4bf-181">В следующем разделе вы узнаете, как сконструировать производный составной элемент управления, используя в качестве базы `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-181">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>

## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="4b4bf-182">Наследование из составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-182">Inheriting from a Composite Control</span></span>
 <span data-ttu-id="4b4bf-183">В предыдущих разделах вы узнали, как объединить элементы управления, компоненты и код Windows в составные элементы управления, доступные для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-183">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="4b4bf-184">После этого составной элемент управления можно использовать как базу, на основе которой будут создаваться другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-184">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="4b4bf-185">Процесс создания класса, производного от базового, называется *наследованием*.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-185">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="4b4bf-186">В этом разделе вы создадите составной элемент управления с именем `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-186">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="4b4bf-187">Он будет производным от родительского элемента управления, `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-187">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="4b4bf-188">Вы узнаете, как расширить функциональные возможности `ctlClock`, переопределив методы родительского класса и добавив новые методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-188">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>

 <span data-ttu-id="4b4bf-189">Первый шаг в создании производного элемента управления — это его наследование из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-189">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="4b4bf-190">Это действие создает новый элемент управления, обладающий всеми свойствами, методами и графическими характеристиками родительского элемента управления, а также может служить основой для добавления или изменения функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-190">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>

### <a name="to-create-the-inherited-control"></a><span data-ttu-id="4b4bf-191">Создание производного элемента управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-191">To create the inherited control</span></span>

1. <span data-ttu-id="4b4bf-192">В обозревателе решений щелкните файл **ctlClockLib** правой кнопкой мыши, наведите указатель мыши на пункт **Добавить** и выберите **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-192">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>

     <span data-ttu-id="4b4bf-193">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-193">The **Add New Item** dialog box opens.</span></span>

2. <span data-ttu-id="4b4bf-194">Выберите шаблон **Производный пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-194">Select the **Inherited User Control** template.</span></span>

3. <span data-ttu-id="4b4bf-195">В поле **Имя** введите `ctlAlarmClock.vb` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-195">In the **Name** box, type `ctlAlarmClock.vb`, and then click **Add**.</span></span>

     <span data-ttu-id="4b4bf-196">Откроется диалоговое окно **Выбор компонентов для наследования**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-196">The **Inheritance Picker** dialog box appears.</span></span>

4. <span data-ttu-id="4b4bf-197">В разделе **Имя компонента** дважды щелкните файл **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-197">Under **Component Name**, double-click **ctlClock**.</span></span>

5. <span data-ttu-id="4b4bf-198">В обозревателе решений просмотрите список текущих проектов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-198">In Solution Explorer, browse through the current projects.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4b4bf-199">Файл с именем **элемент ctlAlarmClock.vb** будет добавлен в текущий проект.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-199">A file called **ctlAlarmClock.vb** has been added to the current project.</span></span>

### <a name="adding-the-alarm-properties"></a><span data-ttu-id="4b4bf-200">Добавление свойств будильника</span><span class="sxs-lookup"><span data-stu-id="4b4bf-200">Adding the Alarm Properties</span></span>
 <span data-ttu-id="4b4bf-201">Свойства, добавляются в производный элемент управления точно так же, как в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-201">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="4b4bf-202">Теперь, используя синтаксис объявления свойств, добавим в элемент управления два свойства: свойство `AlarmTime`, в котором хранится значение даты и времени отключения будильника, и свойство `AlarmSet`, определяющее время срабатывания будильника.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-202">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>

#### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="4b4bf-203">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-203">To add properties to your composite control</span></span>

1. <span data-ttu-id="4b4bf-204">В обозревателе решений щелкните файл **ctlAlarmClock** правой кнопкой мыши и выберите пункт **Показать код**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-204">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>

2. <span data-ttu-id="4b4bf-205">Найдите объявление класса для элемента управления ctlAlarmClock, которое выглядит как `Public Class ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-205">Locate the class declaration for the ctlAlarmClock control, which appears as `Public Class ctlAlarmClock`.</span></span>  <span data-ttu-id="4b4bf-206">В это объявление класса вставьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-206">In the class declaration, insert the following code.</span></span>

    ```vb
    Private dteAlarmTime As Date
    Private blnAlarmSet As Boolean
    ' These properties will be declared as Public to allow future
    ' developers to access them.
    Public Property AlarmTime() As Date
        Get
            Return dteAlarmTime
        End Get
        Set(ByVal value as Date)
            dteAlarmTime = value
        End Set
    End Property
    Public Property AlarmSet() As Boolean
        Get
            Return blnAlarmSet
        End Get
        Set(ByVal value as Boolean)
            blnAlarmSet = value
        End Set
    End Property
    ```

### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="4b4bf-207">Добавление графического интерфейса элементу управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-207">Adding to the Graphical Interface of the Control</span></span>
 <span data-ttu-id="4b4bf-208">Производный элемент управления получает такой же графический интерфейс, как у того элемента, из которого он наследуется.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-208">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="4b4bf-209">Кроме того, он включает те же составные элементы управления, что и родительский элемент управления, однако свойства этих составных элементов будут доступны, только если предоставить их напрямую.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-209">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="4b4bf-210">Графический интерфейс производного элемента управления добавляется точно так же, как и для любого составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-210">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="4b4bf-211">Чтобы продолжить добавление графического интерфейса для будильника, добавим элемент управления Label, который будет мигать при срабатывании будильника.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-211">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>

#### <a name="to-add-the-label-control"></a><span data-ttu-id="4b4bf-212">Добавление элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="4b4bf-212">To add the label control</span></span>

1. <span data-ttu-id="4b4bf-213">В обозревателе решений щелкните файл **ctlAlarmClock** правой кнопкой мыши и выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-213">In Solution Explorer, right-click **ctlAlarmClock**, and click **View Designer**.</span></span>

     <span data-ttu-id="4b4bf-214">Конструктор для `ctlAlarmClock` откроется в главном окне.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-214">The designer for `ctlAlarmClock` opens in the main window.</span></span>

2. <span data-ttu-id="4b4bf-215">Нажмите `lblDisplay` (отображаемая область элемента управления) и просмотрите окно свойств.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-215">Click `lblDisplay` (the display portion of the control), and view the Properties window.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4b4bf-216">Все свойства отображаются, но недоступны.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-216">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="4b4bf-217">Это означает, что эти свойства являются собственными свойствами `lblDisplay`, в окне свойств изменить их или получить к ним доступ нельзя.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-217">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="4b4bf-218">По умолчанию элементы управления, входящие в составной элемент управления, имеют статус `Private` и их свойства недоступны.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-218">By default, controls contained in a composite control are `Private`, and their properties are not accessible by any means.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4b4bf-219">Чтобы последующие пользователи составного элемента управления получили доступ к входящим в него элементам управления, объявите их как `Public` или `Protected`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-219">If you want subsequent users of your composite control to have access to its internal controls, declare them as `Public` or `Protected`.</span></span> <span data-ttu-id="4b4bf-220">Это позволит вам задавать и изменять свойства элементов управления в составном элементе управления, используя соответствующий код.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-220">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>

3. <span data-ttu-id="4b4bf-221"><xref:System.Windows.Forms.Label> Добавьте элемент управления в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-221">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>

4. <span data-ttu-id="4b4bf-222">С помощью мыши перетащите <xref:System.Windows.Forms.Label> элемент управления непосредственно под полем.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-222">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="4b4bf-223">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-223">In the Properties window, set the following properties.</span></span>

    |<span data-ttu-id="4b4bf-224">Свойство.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-224">Property</span></span>|<span data-ttu-id="4b4bf-225">Параметр</span><span class="sxs-lookup"><span data-stu-id="4b4bf-225">Setting</span></span>|
    |--------------|-------------|
    |<span data-ttu-id="4b4bf-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-226">**Name**</span></span>|`lblAlarm`|
    |<span data-ttu-id="4b4bf-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-227">**Text**</span></span>|<span data-ttu-id="4b4bf-228">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-228">**Alarm!**</span></span>|
    |<span data-ttu-id="4b4bf-229">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-229">**TextAlign**</span></span>|`MiddleCenter`|
    |<span data-ttu-id="4b4bf-230">**Visible**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-230">**Visible**</span></span>|`False`|

### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="4b4bf-231">Добавление функциональных возможностей будильника</span><span class="sxs-lookup"><span data-stu-id="4b4bf-231">Adding the Alarm Functionality</span></span>
 <span data-ttu-id="4b4bf-232">Выполняя предыдущие процедуры, вы добавили свойства и элемент управления, которые обеспечат функциональность будильника в составном элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-232">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="4b4bf-233">В ходе этой процедуры вы добавите код, который будет сравнивать текущее время со временем будильника и, если они совпадают, запускать звуковой сигнал и мигающее оповещение.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-233">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to sound and flash an alarm.</span></span> <span data-ttu-id="4b4bf-234">Переопределив метод `Timer1_Tick` в `ctlClock` и добавив в него дополнительный код, вы расширите возможности `ctlAlarmClock`, сохранив при этом все унаследованные функции `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-234">By overriding the `Timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>

#### <a name="to-override-the-timer1_tick-method-of-ctlclock"></a><span data-ttu-id="4b4bf-235">Переопределение метода Timer1_Tick в ctlClock</span><span class="sxs-lookup"><span data-stu-id="4b4bf-235">To override the Timer1_Tick method of ctlClock</span></span>

1. <span data-ttu-id="4b4bf-236">В обозревателе решений щелкните файл **ctlAlarmClock.vb** правой кнопкой мыши и выберите пункт **Показать код**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-236">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Code**.</span></span>

2. <span data-ttu-id="4b4bf-237">Найдите оператор `Private blnAlarmSet As Boolean`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-237">Locate the `Private blnAlarmSet As Boolean` statement.</span></span> <span data-ttu-id="4b4bf-238">Сразу после него добавьте следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-238">Immediately beneath it, add the following statement.</span></span>

    ```vb
    Dim blnColorTicker as Boolean
    ```

3. <span data-ttu-id="4b4bf-239">Найдите оператор `End Class` в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-239">Locate the `End Class` statement at the bottom of the page.</span></span> <span data-ttu-id="4b4bf-240">Непосредственно перед оператором `End Class` добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-240">Just before the `End Class` statement, add the following code.</span></span>

    ```vb
    Protected Overrides Sub Timer1_Tick(ByVal sender As Object, ByVal e _
        As System.EventArgs)
        ' Calls the Timer1_Tick method of ctlClock.
        MyBase.Timer1_Tick(sender, e)
        ' Checks to see if the Alarm is set.
        If AlarmSet = False Then
            Exit Sub
        End If
        ' If the date, hour, and minute of the alarm time are the same as
        ' now, flash and beep an alarm.
        If AlarmTime.Date = Now.Date And AlarmTime.Hour = Now.Hour And _
            AlarmTime.Minute = Now.Minute Then
            ' Sounds an audible beep.
            Beep()
            ' Sets lblAlarmVisible to True, and changes the background color based on the
            ' value of blnColorTicker. The background color of the label will
            ' flash once per tick of the clock.
            lblAlarm.Visible = True
            If blnColorTicker = False Then
                lblAlarm.BackColor = Color.PeachPuff
                blnColorTicker = True
            Else
                lblAlarm.BackColor = Color.Plum
                blnColorTicker = False
            End If
        Else
            ' Once the alarm has sounded for a minute, the label is made
            ' invisible again.
            lblAlarm.Visible = False
        End If
    End Sub
    ```

     <span data-ttu-id="4b4bf-241">Добавление этого кода решает сразу несколько задач.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-241">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="4b4bf-242">Оператор `Overrides` указывает элементу управления использовать этот метод вместо метода, унаследованного из базового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-242">The `Overrides` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="4b4bf-243">При вызове этого метода он вызывает переопределяемый метод, используя оператор `MyBase.Timer1_Tick`, и следит за тем, чтобы в этом элементе управления были реализованы все функции исходного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-243">When this method is called, it calls the method it overrides by invoking the `MyBase.Timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="4b4bf-244">Затем он выполняет дополнительный код, реализующий функции будильника.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-244">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="4b4bf-245">Когда будильник срабатывает, появляется мигающая метка и раздается звуковой сигнал.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-245">A flashing label control will appear when the alarm occurs, and an audible beep will be heard.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="4b4bf-246">Поскольку вы переопределяете производный обработчик событий, указывать событие с помощью ключевого слова `Handles` не требуется.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-246">Because you are overriding an inherited event handler, you do not have to specify the event with the `Handles` keyword.</span></span> <span data-ttu-id="4b4bf-247">Событие уже подключено.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-247">The event is already hooked up.</span></span> <span data-ttu-id="4b4bf-248">Переопределяется только реализация обработчика.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-248">All you are overriding is the implementation of the handler.</span></span>

     <span data-ttu-id="4b4bf-249">Элемент управления "Будильник" почти готов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-249">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="4b4bf-250">Осталось реализовать только его отключение.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-250">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="4b4bf-251">Для этого нужно добавить код в метод `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-251">To do this, you will add code to the `lblAlarm_Click` method.</span></span>

#### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="4b4bf-252">Реализация метода отключения</span><span class="sxs-lookup"><span data-stu-id="4b4bf-252">To implement the shutoff method</span></span>

1. <span data-ttu-id="4b4bf-253">В обозревателе решений щелкните файл **ctlAlarmClock.vb** правой кнопкой мыши и выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-253">In Solution Explorer, right-click **ctlAlarmClock.vb**, and then click **View Designer**.</span></span>

2. <span data-ttu-id="4b4bf-254">В конструкторе дважды щелкните **lblAlarm**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-254">In the designer, double-click **lblAlarm**.</span></span> <span data-ttu-id="4b4bf-255">Откроется **редактор кода** со строкой `Private Sub lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-255">The **Code Editor** opens to the `Private Sub lblAlarm_Click` line.</span></span>

3. <span data-ttu-id="4b4bf-256">Измените метод, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-256">Modify this method so that it resembles the following code.</span></span>

    ```vb
    Private Sub lblAlarm_Click(ByVal sender As Object, ByVal e As _
     System.EventArgs) Handles lblAlarm.Click
        ' Turns off the alarm.
        AlarmSet = False
        ' Hides the flashing label.
        lblAlarm.Visible = False
    End Sub
    ```

4. <span data-ttu-id="4b4bf-257">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-257">On the **File** menu, click **Save All** to save the project.</span></span>

### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="4b4bf-258">Использование производного элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="4b4bf-258">Using the Inherited Control on a Form</span></span>
 <span data-ttu-id="4b4bf-259">Вы можете протестировать наследуемый элемент управления так же, как вы протестировали элемент управления `ctlClock`базового класса: Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-259">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="4b4bf-260">Дополнительные сведения см. в разделе [Как Проверка поведения элемента управления UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md)во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-260">For more information, see [How to: Test the Run-Time Behavior of a UserControl](how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>

 <span data-ttu-id="4b4bf-261">Чтобы элемент управления можно было использовать, необходимо поместить его в форму.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-261">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="4b4bf-262">Производный составной элемент управления, как и стандартный, не может быть автономным и должен быть размещен в форме или другом контейнере.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-262">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="4b4bf-263">Поскольку `ctlAlarmClock` отличается более широкими функциональными возможностями, для его проверки требуется дополнительный код.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-263">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="4b4bf-264">В ходе этой процедуры вы напишете простую программу для проверки функциональных возможностей `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-264">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="4b4bf-265">Вы напишете код, задающий и отображающий свойство `AlarmTime` в `ctlAlarmClock` и проверяющий его унаследованные функции.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-265">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>

#### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="4b4bf-266">Сборка и добавление элемента управления в тестовую форму</span><span class="sxs-lookup"><span data-stu-id="4b4bf-266">To build and add your control to a test form</span></span>

1. <span data-ttu-id="4b4bf-267">В обозревателе решений щелкните файл **ctlClockLib** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-267">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>

2. <span data-ttu-id="4b4bf-268">В меню **Файл** выберите команду **Добавить**, а затем **Создать проект**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-268">On the **File** menu, point to **Add**, and then click **New Project**.</span></span>

3. <span data-ttu-id="4b4bf-269">Добавьте в решение новый проект **приложения Windows** с именем `Test`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-269">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>

     <span data-ttu-id="4b4bf-270">Проект **Test** будет добавлен в обозреватель решений.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-270">The **Test** project is added to Solution Explorer.</span></span>

4. <span data-ttu-id="4b4bf-271">В обозревателе решений щелкните правой кнопкой мыши узел проекта `Test` и выберите пункт **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-271">In Solution Explorer, right-click the `Test` project node, and then click **Add Reference** to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="4b4bf-272">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-272">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="4b4bf-273">Проект **ctlClockLib** будет указан под полем **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-273">The project **ctlClockLib** will be listed under **Project Name**.</span></span> <span data-ttu-id="4b4bf-274">Дважды щелкните файл **ctlClockLib**, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-274">Double-click **ctlClockLib** to add the reference to the test project.</span></span>

6. <span data-ttu-id="4b4bf-275">В обозревателе решений щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-275">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>

7. <span data-ttu-id="4b4bf-276">На **панели элементов** разверните узел **Компоненты ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-276">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>

8. <span data-ttu-id="4b4bf-277">Дважды щелкните **ctlAlarmClock**, чтобы добавить экземпляр `ctlAlarmClock` в свою форму.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-277">Double-click **ctlAlarmClock** to add an instance of `ctlAlarmClock` to your form.</span></span>

9. <span data-ttu-id="4b4bf-278">На **панели элементов**найдите и дважды щелкните элемент **DateTimePicker** , чтобы добавить его <xref:System.Windows.Forms.DateTimePicker> в <xref:System.Windows.Forms.Label> форму, а затем добавьте элемент управления, дважды щелкнув надпись.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-278">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>

10. <span data-ttu-id="4b4bf-279">С помощью мыши разместите элементы управления в удобном месте формы.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-279">Use the mouse to position the controls in a convenient place on the form.</span></span>

11. <span data-ttu-id="4b4bf-280">Задайте свойства этих элементов управления следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-280">Set the properties of these controls in the following manner.</span></span>

    |<span data-ttu-id="4b4bf-281">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-281">Control</span></span>|<span data-ttu-id="4b4bf-282">Свойство</span><span class="sxs-lookup"><span data-stu-id="4b4bf-282">Property</span></span>|<span data-ttu-id="4b4bf-283">Значение</span><span class="sxs-lookup"><span data-stu-id="4b4bf-283">Value</span></span>|
    |-------------|--------------|-----------|
    |`label1`|<span data-ttu-id="4b4bf-284">**Text**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-284">**Text**</span></span>|`(blank space)`|
    ||<span data-ttu-id="4b4bf-285">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-285">**Name**</span></span>|`lblTest`|
    |`dateTimePicker1`|<span data-ttu-id="4b4bf-286">**Name**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-286">**Name**</span></span>|`dtpTest`|
    ||<span data-ttu-id="4b4bf-287">**Формат**</span><span class="sxs-lookup"><span data-stu-id="4b4bf-287">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|

12. <span data-ttu-id="4b4bf-288">В конструкторе дважды щелкните **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-288">In the designer, double-click **dtpTest**.</span></span>

     <span data-ttu-id="4b4bf-289">В **редакторе кода** откроется `Private Sub dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-289">The **Code Editor** opens to `Private Sub dtpTest_ValueChanged`.</span></span>

13. <span data-ttu-id="4b4bf-290">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-290">Modify the code so that it resembles the following.</span></span>

    ```vb
    Private Sub dtpTest_ValueChanged(ByVal sender As Object, ByVal e As _
        System.EventArgs) Handles dtpTest.ValueChanged
        ctlAlarmClock1.AlarmTime = dtpTest.Value
        ctlAlarmClock1.AlarmSet = True
        lblTest.Text = "Alarm Time is " & Format(ctlAlarmClock1.AlarmTime, _
            "hh:mm")
    End Sub
    ```

14. <span data-ttu-id="4b4bf-291">В обозревателе решений щелкните правой кнопкой мыши **Тест** и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-291">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>

15. <span data-ttu-id="4b4bf-292">В меню **Отладка** щелкните **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-292">On the **Debug** menu, click **Start Debugging**.</span></span>

     <span data-ttu-id="4b4bf-293">Запустится тестовая программа.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-293">The test program starts.</span></span> <span data-ttu-id="4b4bf-294">Обратите внимание, что текущее время обновляется в `ctlAlarmClock` элементе управления, а время начала отображается <xref:System.Windows.Forms.DateTimePicker> в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-294">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>

16. <span data-ttu-id="4b4bf-295">Щелкните, <xref:System.Windows.Forms.DateTimePicker> где отображаются минуты часа.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-295">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>

17. <span data-ttu-id="4b4bf-296">С помощью клавиатуры укажите значение минут, составляющее на одну минуту больше текущего времени, отображаемого `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-296">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>

     <span data-ttu-id="4b4bf-297">Время включения будильника отображается в `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-297">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="4b4bf-298">Дождитесь момента, когда отображаемое время совпадет с установленным временем будильника.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-298">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="4b4bf-299">Когда это произойдет, раздастся звуковой сигнал, и `lblAlarm` начнет мигать.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-299">When the displayed time reaches the time to which the alarm is set, the beep will sound and `lblAlarm` will flash.</span></span>

18. <span data-ttu-id="4b4bf-300">Отключите сигнал, нажав `lblAlarm`.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-300">Turn off the alarm by clicking `lblAlarm`.</span></span> <span data-ttu-id="4b4bf-301">Теперь будильник можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-301">You may now reset the alarm.</span></span>

     <span data-ttu-id="4b4bf-302">В этом пошаговом руководстве был проиллюстрирован ряд ключевых понятий.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-302">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="4b4bf-303">Вы узнали, как создать составной элемент управления, объединив элементы управления и компоненты в контейнер составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-303">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="4b4bf-304">Вы узнали, как добавить свойства в элемент управления и написать код для реализации настраиваемых функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-304">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="4b4bf-305">В последнем разделе вы узнали, как расширять функциональные возможности заданного составного элемента управления с помощью наследования и как изменять функциональные возможности методов узла путем переопределения методов.</span><span class="sxs-lookup"><span data-stu-id="4b4bf-305">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b4bf-306">См. также</span><span class="sxs-lookup"><span data-stu-id="4b4bf-306">See also</span></span>

- [<span data-ttu-id="4b4bf-307">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-307">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="4b4bf-308">Практическое руководство. Создание составных элементов управления</span><span class="sxs-lookup"><span data-stu-id="4b4bf-308">How to: Author Composite Controls</span></span>](how-to-author-composite-controls.md)
- [<span data-ttu-id="4b4bf-309">Практическое руководство. Отображение элемента управления в диалоговом окне "Выбор элементов панели элементов"</span><span class="sxs-lookup"><span data-stu-id="4b4bf-309">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
