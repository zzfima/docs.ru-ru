---
title: Пример. Создание составного элемента управления с помощью C#
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [C#]
- user controls [Windows Forms], creating with Visual C#
- UserControl class [Windows Forms], walkthroughs
- user controls [C#]
- custom controls [Windows Forms], creating
ms.assetid: f88481a8-c746-4a36-9479-374ce5f2e91f
ms.openlocfilehash: 5f8384140b813400e106ad959684264304541c93
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2018
ms.locfileid: "45639020"
---
# <a name="walkthrough-authoring-a-composite-control-with-visual-c"></a><span data-ttu-id="82ba7-102">Пример. Создание составного элемента управления с помощью C#</span><span class="sxs-lookup"><span data-stu-id="82ba7-102">Walkthrough: Authoring a Composite Control with Visual C#</span></span> #
<span data-ttu-id="82ba7-103">Составные элементы управления предоставляют средства для создания и повторного использования настраиваемых графических интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-103">Composite controls provide a means by which custom graphical interfaces can be created and reused.</span></span> <span data-ttu-id="82ba7-104">Составной элемент управления — это компонент, имеющий визуальное представление.</span><span class="sxs-lookup"><span data-stu-id="82ba7-104">A composite control is essentially a component with a visual representation.</span></span> <span data-ttu-id="82ba7-105">Таким образом, он может состоять из одного или нескольких элементов управления, компонентов или блоков кода Windows Forms, позволяющих расширить функциональные возможности за счет проверки введенных пользователем данных, изменения свойств отображения или выполнения других предусмотренных разработчиком действий.</span><span class="sxs-lookup"><span data-stu-id="82ba7-105">As such, it might consist of one or more Windows Forms controls, components, or blocks of code that can extend functionality by validating user input, modifying display properties, or performing other tasks required by the author.</span></span> <span data-ttu-id="82ba7-106">Составные элементы управления можно вставлять в Windows Forms точно так же, как другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-106">Composite controls can be placed on Windows Forms in the same manner as other controls.</span></span> <span data-ttu-id="82ba7-107">В первой части этого пошагового руководства мы создадим простой составной элемент управления с именем `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-107">In the first part of this walkthrough, you create a simple composite control called `ctlClock`.</span></span> <span data-ttu-id="82ba7-108">Во второй части мы расширим функциональность `ctlClock` за счет наследования.</span><span class="sxs-lookup"><span data-stu-id="82ba7-108">In the second part of the walkthrough, you extend the functionality of `ctlClock` through inheritance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82ba7-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="82ba7-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="82ba7-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="82ba7-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="82ba7-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="82ba7-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="82ba7-112">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="82ba7-112">Creating the Project</span></span>  
 <span data-ttu-id="82ba7-113">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="82ba7-113">When you create a new project, you specify its name to set the root namespace, assembly name, and project name, and ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-ctlclocklib-control-library-and-the-ctlclock-control"></a><span data-ttu-id="82ba7-114">Создание библиотеки элементов управления ctlClockLib и элемента управления ctlClock</span><span class="sxs-lookup"><span data-stu-id="82ba7-114">To create the ctlClockLib control library and the ctlClock control</span></span>  
  
1.  <span data-ttu-id="82ba7-115">В меню **Файл** наведите указатель мыши на пункт **Создать** и выберите **Проект**, чтобы открыть диалоговое окно **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-115">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="82ba7-116">В списке проектов Visual C#, выберите **Библиотека элементов управления Windows Forms** шаблон проекта, тип `ctlClockLib` в **имя** , а затем щелкните **ОК**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-116">From the list of Visual C# projects, select the **Windows Forms Control Library** project template, type `ctlClockLib` in the **Name** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="82ba7-117">Имя проекта, `ctlClockLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="82ba7-117">The project name, `ctlClockLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="82ba7-118">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="82ba7-118">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="82ba7-119">Например, если в двух сборках содержатся компоненты с именем `ctlClock`, можно указать компонент `ctlClock`, используя `ctlClockLib.ctlClock.`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-119">For example, if two assemblies provide components named `ctlClock`, you can specify your `ctlClock` component using `ctlClockLib.ctlClock.`</span></span>  
  
3.  <span data-ttu-id="82ba7-120">В обозревателе решений щелкните файл **UserControl1.cs** правой клавишей мыши и выберите команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-120">In Solution Explorer, right-click **UserControl1.cs**, and then click **Rename**.</span></span> <span data-ttu-id="82ba7-121">Измените имя файла на `ctlClock.cs`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-121">Change the file name to `ctlClock.cs`.</span></span> <span data-ttu-id="82ba7-122">Чтобы переименовать все ссылки на элемент кода UserControl1, в соответствующем запросе нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-122">Click the **Yes** button when you are asked if you want to rename all references to the code element "UserControl1".</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82ba7-123">По умолчанию составной элемент управления наследует от <xref:System.Windows.Forms.UserControl> класса, предоставляемого системой.</span><span class="sxs-lookup"><span data-stu-id="82ba7-123">By default, a composite control inherits from the <xref:System.Windows.Forms.UserControl> class provided by the system.</span></span> <span data-ttu-id="82ba7-124"><xref:System.Windows.Forms.UserControl> Класс обеспечивает функциональность, необходимую всем составным элементам управления и реализует стандартные методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="82ba7-124">The <xref:System.Windows.Forms.UserControl> class provides functionality required by all composite controls, and implements standard methods and properties.</span></span>  
  
4.  <span data-ttu-id="82ba7-125">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-125">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-windows-controls-and-components-to-the-composite-control"></a><span data-ttu-id="82ba7-126">Добавление элементов управления и компонентов Windows в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-126">Adding Windows Controls and Components to the Composite Control</span></span>  
 <span data-ttu-id="82ba7-127">Визуальный интерфейс представляет собой важную часть составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-127">A visual interface is an essential part of your composite control.</span></span> <span data-ttu-id="82ba7-128">Он реализуется путем добавления одного или нескольких элементов управления Windows на поверхность конструктора.</span><span class="sxs-lookup"><span data-stu-id="82ba7-128">This visual interface is implemented by the addition of one or more Windows controls to the designer surface.</span></span> <span data-ttu-id="82ba7-129">В следующем примере мы добавим элементы управления Windows в составной элемент управления и напишем код для реализации функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="82ba7-129">In the following demonstration, you will incorporate Windows controls into your composite control and write code to implement functionality.</span></span>  
  
#### <a name="to-add-a-label-and-a-timer-to-your-composite-control"></a><span data-ttu-id="82ba7-130">Добавление метки и таймера в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-130">To add a Label and a Timer to your composite control</span></span>  
  
1.  <span data-ttu-id="82ba7-131">В обозревателе решений щелкните файл **ctlClock.cs** правой кнопкой мыши и выберите пункт **Открыть в конструкторе**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-131">In Solution Explorer, right-click **ctlClock.cs**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="82ba7-132">На **панели элементов** разверните узел **Общие элементы управления**, а затем дважды щелкните пункт **Метка**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-132">In the **Toolbox**, expand the **Common Controls** node, and then double-click **Label**.</span></span>  
  
     <span data-ttu-id="82ba7-133">Объект <xref:System.Windows.Forms.Label> управления с именем `label1` добавляется в элемент управления на поверхности конструктора.</span><span class="sxs-lookup"><span data-stu-id="82ba7-133">A <xref:System.Windows.Forms.Label> control named `label1` is added to your control on the designer surface.</span></span>  
  
3.  <span data-ttu-id="82ba7-134">В конструкторе щелкните пункт **Label1**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-134">In the designer, click **label1**.</span></span> <span data-ttu-id="82ba7-135">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="82ba7-135">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="82ba7-136">Свойство.</span><span class="sxs-lookup"><span data-stu-id="82ba7-136">Property</span></span>|<span data-ttu-id="82ba7-137">Измените на</span><span class="sxs-lookup"><span data-stu-id="82ba7-137">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="82ba7-138">**Name**</span><span class="sxs-lookup"><span data-stu-id="82ba7-138">**Name**</span></span>|`lblDisplay`|  
    |<span data-ttu-id="82ba7-139">**Text**</span><span class="sxs-lookup"><span data-stu-id="82ba7-139">**Text**</span></span>|`(blank space)`|  
    |<span data-ttu-id="82ba7-140">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="82ba7-140">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="82ba7-141">**Font.Size**</span><span class="sxs-lookup"><span data-stu-id="82ba7-141">**Font.Size**</span></span>|`14`|  
  
4.  <span data-ttu-id="82ba7-142">На **панели элементов** разверните узел **Компоненты**, а затем дважды щелкните пункт **Таймер**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-142">In the **Toolbox**, expand the **Components** node, and then double-click **Timer**.</span></span>  
  
     <span data-ttu-id="82ba7-143">Так как <xref:System.Windows.Forms.Timer> — это компонент, он не имеет визуального представления во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="82ba7-143">Because a <xref:System.Windows.Forms.Timer> is a component, it has no visual representation at run time.</span></span> <span data-ttu-id="82ba7-144">В связи с этим он отображается не с элементами управления на поверхности конструктора, а в **конструкторе компонентов** (область в нижней части поверхности конструктора).</span><span class="sxs-lookup"><span data-stu-id="82ba7-144">Therefore, it does not appear with the controls on the designer surface, but rather in the **Component Designer** (a tray at the bottom of the designer surface).</span></span>  
  
5.  <span data-ttu-id="82ba7-145">В **конструктор компонентов**, нажмите кнопку **timer1**и задайте <xref:System.Windows.Forms.Timer.Interval%2A> свойства `1000` и <xref:System.Windows.Forms.Timer.Enabled%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-145">In the **Component Designer**, click **timer1**, and then set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `1000` and the <xref:System.Windows.Forms.Timer.Enabled%2A> property to `true`.</span></span>  
  
     <span data-ttu-id="82ba7-146"><xref:System.Windows.Forms.Timer.Interval%2A> Свойство определяет частоту, с которой <xref:System.Windows.Forms.Timer> тактов для компонента.</span><span class="sxs-lookup"><span data-stu-id="82ba7-146">The <xref:System.Windows.Forms.Timer.Interval%2A> property controls the frequency with which the <xref:System.Windows.Forms.Timer> component ticks.</span></span> <span data-ttu-id="82ba7-147">При каждом такте `timer1` оно запускает код в событии `timer1_Tick`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-147">Each time `timer1` ticks, it runs the code in the `timer1_Tick` event.</span></span> <span data-ttu-id="82ba7-148">Интервал представляет время между тактами в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="82ba7-148">The interval represents the number of milliseconds between ticks.</span></span>  
  
6.  <span data-ttu-id="82ba7-149">В **конструкторе компонентов** дважды щелкните **timer1**, чтобы перейти к событию `timer1_Tick` для `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-149">In the **Component Designer**, double-click **timer1** to go to the `timer1_Tick` event for `ctlClock`.</span></span>  
  
7.  <span data-ttu-id="82ba7-150">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="82ba7-150">Modify the code so that it resembles the following code sample.</span></span> <span data-ttu-id="82ba7-151">Измените модификатор доступа с `private` на `protected`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-151">Be sure to change the access modifier from `private` to `protected`.</span></span>  
  
    ```csharp  
    protected void timer1_Tick(object sender, System.EventArgs e)  
    {  
        // Causes the label to display the current time.  
        lblDisplay.Text = DateTime.Now.ToLongTimeString();   
    }  
    ```  
  
     <span data-ttu-id="82ba7-152">Этот код вызывает отображение текущего времени в `lblDisplay`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-152">This code will cause the current time to be shown in `lblDisplay`.</span></span> <span data-ttu-id="82ba7-153">Поскольку для интервала `timer1` было задано значение `1000`, это событие возникает через каждую тысячу миллисекунд, а значит, текущее время обновляется каждую секунду.</span><span class="sxs-lookup"><span data-stu-id="82ba7-153">Because the interval of `timer1` was set to `1000`, this event will occur every thousand milliseconds, thus updating the current time every second.</span></span>  
  
8.  <span data-ttu-id="82ba7-154">Измените метод, разрешив его переопределение с помощью ключевого слова `virtual`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-154">Modify the method to be overridable with the `virtual` keyword.</span></span> <span data-ttu-id="82ba7-155">Дополнительные сведения см. ниже в разделе "Наследование из пользовательского элемента управления".</span><span class="sxs-lookup"><span data-stu-id="82ba7-155">For more information, see the  "Inheriting from a User Control" section below.</span></span>  
  
    ```csharp  
    protected virtual void timer1_Tick(object sender, System.EventArgs e)  
    ```  
  
9. <span data-ttu-id="82ba7-156">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-156">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="adding-properties-to-the-composite-control"></a><span data-ttu-id="82ba7-157">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-157">Adding Properties to the Composite Control</span></span>  
 <span data-ttu-id="82ba7-158">Теперь инкапсулирует элемент управления <xref:System.Windows.Forms.Label> управления и <xref:System.Windows.Forms.Timer> компонента, каждый из которых свой собственный набор унаследованных свойств.</span><span class="sxs-lookup"><span data-stu-id="82ba7-158">Your clock control now encapsulates a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.Timer> component, each with its own set of inherent properties.</span></span> <span data-ttu-id="82ba7-159">Несмотря на то что отдельные свойства этих элементов управления не будут доступны последующим пользователям вашего элемента управления, вы можете создать и предоставить настраиваемые свойства, написав соответствующие блоки кода.</span><span class="sxs-lookup"><span data-stu-id="82ba7-159">While the individual properties of these controls will not be accessible to subsequent users of your control, you can create and expose custom properties by writing the appropriate blocks of code.</span></span> <span data-ttu-id="82ba7-160">Выполняя следующую процедуру, вы добавите в элемент управления свойства, позволяющие пользователю изменять цвет фона и текста.</span><span class="sxs-lookup"><span data-stu-id="82ba7-160">In the following procedure, you will add properties to your control that enable the user to change the color of the background and text.</span></span>  
  
#### <a name="to-add-a-property-to-your-composite-control"></a><span data-ttu-id="82ba7-161">Добавление свойства в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-161">To add a property to your composite control</span></span>  
  
1.  <span data-ttu-id="82ba7-162">В обозревателе решений щелкните файл **ctlClock.cs** правой кнопкой мыши и выберите пункт **Показать код**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-162">In Solution Explorer, right-click **ctlClock.cs**, and then click **View Code**.</span></span>  
  
     <span data-ttu-id="82ba7-163">Откроется **редактор кода** для элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-163">The **Code Editor** for your control opens.</span></span>  
  
2.  <span data-ttu-id="82ba7-164">Найдите оператор `public partial class ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-164">Locate the `public partial class ctlClock` statement.</span></span> <span data-ttu-id="82ba7-165">Под открывающей скобкой (`{)` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="82ba7-165">Beneath the opening brace (`{)`, type the following code.</span></span>  
  
    ```csharp  
    private Color colFColor;  
    private Color colBColor;  
    ```  
  
     <span data-ttu-id="82ba7-166">Эти операторы создают закрытые переменные для хранения значений свойств, которые вы собираетесь создать.</span><span class="sxs-lookup"><span data-stu-id="82ba7-166">These statements create the private variables that you will use to store the values for the properties you are about to create.</span></span>  
  
3.  <span data-ttu-id="82ba7-167">Введите следующий код под объявлениями переменных, созданными в шаге 2.</span><span class="sxs-lookup"><span data-stu-id="82ba7-167">Type the following code beneath the variable declarations from step 2.</span></span>  
  
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
  
     <span data-ttu-id="82ba7-168">Приведенный выше код обеспечивает доступ к двум настраиваемым свойствам, `ClockForeColor` и `ClockBackColor`, для последующих пользователей данного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-168">The preceding code makes two custom properties, `ClockForeColor` and `ClockBackColor`, available to subsequent users of this control.</span></span> <span data-ttu-id="82ba7-169">Операторы `get` и `set` позволяют хранить и извлекать значение свойства, а также предоставляют код для реализации соответствующих этому свойству функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="82ba7-169">The `get` and `set` statements provide for storage and retrieval of the property value, as well as code to implement functionality appropriate to the property.</span></span>  
  
4.  <span data-ttu-id="82ba7-170">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-170">On the **File** menu, click **Save All** to save the project.</span></span>  
  
## <a name="testing-the-control"></a><span data-ttu-id="82ba7-171">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-171">Testing the Control</span></span>  
 <span data-ttu-id="82ba7-172">Элементы управления не являются автономными приложениями и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="82ba7-172">Controls are not stand-alone applications; they must be hosted in a container.</span></span> <span data-ttu-id="82ba7-173">Проверьте поведение элемента управления в среде выполнения и испытайте его свойства в **тестовом контейнере пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-173">Test your control's run-time behavior and exercise its properties with the **UserControl Test Container**.</span></span> <span data-ttu-id="82ba7-174">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="82ba7-174">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
#### <a name="to-test-your-control"></a><span data-ttu-id="82ba7-175">Проверка элемента управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-175">To test your control</span></span>  
  
1.  <span data-ttu-id="82ba7-176">Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-176">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="82ba7-177">В таблице свойств тестового контейнера выберите свойство `ClockBackColor`, а затем свойство, чтобы открыть палитру цветов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-177">In the test container's property grid, locate the `ClockBackColor` property, and then select the property to display the color palette.</span></span>  
  
3.  <span data-ttu-id="82ba7-178">Щелкните нужный цвет.</span><span class="sxs-lookup"><span data-stu-id="82ba7-178">Choose a color by clicking it.</span></span>  
  
     <span data-ttu-id="82ba7-179">Цвет фона элемента управления изменится на выбранный.</span><span class="sxs-lookup"><span data-stu-id="82ba7-179">The background color of your control changes to the color you selected.</span></span>  
  
4.  <span data-ttu-id="82ba7-180">Используя аналогичную последовательность событий, проверьте, функционирует ли свойство `ClockForeColor` должным образом.</span><span class="sxs-lookup"><span data-stu-id="82ba7-180">Use a similar sequence of events to verify that the `ClockForeColor` property is functioning as expected.</span></span>  
  
     <span data-ttu-id="82ba7-181">Из этого и предыдущих разделов вы узнали, как объединить компоненты и элементы управления Windows с кодом и упаковкой и, таким образом, предоставить настраиваемые функциональные возможности в виде составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-181">In this section and the preceding sections, you have seen how components and Windows controls can be combined with code and packaging to provide custom functionality in the form of a composite control.</span></span> <span data-ttu-id="82ba7-182">Вы узнали, как вывести свойства в составной элемент управления и проверить элемент управления после того, как он будет готов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-182">You have learned to expose properties in your composite control, and how to test your control after it is complete.</span></span> <span data-ttu-id="82ba7-183">В следующем разделе вы узнаете, как сконструировать производный составной элемент управления, используя в качестве базы `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-183">In the next section you will learn how to construct an inherited composite control using `ctlClock` as a base.</span></span>  
  
## <a name="inheriting-from-a-composite-control"></a><span data-ttu-id="82ba7-184">Наследование из составного элемента управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-184">Inheriting from a Composite Control</span></span>  
 <span data-ttu-id="82ba7-185">В предыдущих разделах вы узнали, как объединить элементы управления, компоненты и код Windows в составные элементы управления, доступные для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="82ba7-185">In the previous sections, you learned how to combine Windows controls, components, and code into reusable composite controls.</span></span> <span data-ttu-id="82ba7-186">После этого составной элемент управления можно использовать как базу, на основе которой будут создаваться другие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-186">Your composite control can now be used as a base upon which other controls can be built.</span></span> <span data-ttu-id="82ba7-187">Процесс создания класса, производного от базового, называется *наследованием*.</span><span class="sxs-lookup"><span data-stu-id="82ba7-187">The process of deriving a class from a base class is called *inheritance*.</span></span> <span data-ttu-id="82ba7-188">В этом разделе вы создадите составной элемент управления с именем `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-188">In this section, you will create a composite control called `ctlAlarmClock`.</span></span> <span data-ttu-id="82ba7-189">Он будет производным от родительского элемента управления, `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-189">This control will be derived from its parent control, `ctlClock`.</span></span> <span data-ttu-id="82ba7-190">Вы узнаете, как расширить функциональные возможности `ctlClock`, переопределив методы родительского класса и добавив новые методы и свойства.</span><span class="sxs-lookup"><span data-stu-id="82ba7-190">You will learn to extend the functionality of `ctlClock` by overriding parent methods and adding new methods and properties.</span></span>  
  
 <span data-ttu-id="82ba7-191">Первый шаг в создании производного элемента управления — это его наследование из родительского элемента.</span><span class="sxs-lookup"><span data-stu-id="82ba7-191">The first step in creating an inherited control is to derive it from its parent.</span></span> <span data-ttu-id="82ba7-192">Это действие создает новый элемент управления, обладающий всеми свойствами, методами и графическими характеристиками родительского элемента управления, а также может служить основой для добавления или изменения функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="82ba7-192">This action creates a new control that has all of the properties, methods, and graphical characteristics of the parent control, but can also act as a base for the addition of new or modified functionality.</span></span>  
  
#### <a name="to-create-the-inherited-control"></a><span data-ttu-id="82ba7-193">Создание производного элемента управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-193">To create the inherited control</span></span>  
  
1.  <span data-ttu-id="82ba7-194">В обозревателе решений щелкните файл **ctlClockLib** правой кнопкой мыши, наведите указатель мыши на пункт **Добавить** и выберите **Пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-194">In Solution Explorer, right-click **ctlClockLib**, point to **Add**, and then click **User Control**.</span></span>  
  
     <span data-ttu-id="82ba7-195">Откроется диалоговое окно **Добавление нового элемента**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-195">The **Add New Item** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="82ba7-196">Выберите шаблон **Производный пользовательский элемент управления**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-196">Select the **Inherited User Control** template.</span></span>  
  
3.  <span data-ttu-id="82ba7-197">В поле **Имя** введите `ctlAlarmClock.cs` и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-197">In the **Name** box, type `ctlAlarmClock.cs`, and then click **Add**.</span></span>  
  
     <span data-ttu-id="82ba7-198">Откроется диалоговое окно **Выбор компонентов для наследования**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-198">The **Inheritance Picker** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="82ba7-199">В разделе **Имя компонента** дважды щелкните файл **ctlClock**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-199">Under **Component Name**, double-click **ctlClock**.</span></span>  
  
5.  <span data-ttu-id="82ba7-200">В обозревателе решений просмотрите список текущих проектов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-200">In Solution Explorer, browse through the current projects.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82ba7-201">Файл с именем **элемент ctlAlarmClock. cs** будет добавлен в текущий проект.</span><span class="sxs-lookup"><span data-stu-id="82ba7-201">A file called **ctlAlarmClock.cs** has been added to the current project.</span></span>  
  
### <a name="adding-the-alarm-properties"></a><span data-ttu-id="82ba7-202">Добавление свойств будильника</span><span class="sxs-lookup"><span data-stu-id="82ba7-202">Adding the Alarm Properties</span></span>  
 <span data-ttu-id="82ba7-203">Свойства, добавляются в производный элемент управления точно так же, как в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-203">Properties are added to an inherited control in the same way they are added to a composite control.</span></span> <span data-ttu-id="82ba7-204">Теперь, используя синтаксис объявления свойств, добавим в элемент управления два свойства: свойство `AlarmTime`, в котором хранится значение даты и времени отключения будильника, и свойство `AlarmSet`, определяющее время срабатывания будильника.</span><span class="sxs-lookup"><span data-stu-id="82ba7-204">You will now use the property declaration syntax to add two properties to your control: `AlarmTime`, which will store the value of the date and time the alarm is to go off, and `AlarmSet`, which will indicate whether the alarm is set.</span></span>  
  
##### <a name="to-add-properties-to-your-composite-control"></a><span data-ttu-id="82ba7-205">Добавление свойств в составной элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-205">To add properties to your composite control</span></span>  
  
1.  <span data-ttu-id="82ba7-206">В обозревателе решений щелкните файл **ctlAlarmClock** правой кнопкой мыши и выберите пункт **Показать код**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-206">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Code**.</span></span>  
  
2.  <span data-ttu-id="82ba7-207">Найдите оператор `public class`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-207">Locate the `public class` statement.</span></span> <span data-ttu-id="82ba7-208">Обратите внимание, что элемент управления наследуется из `ctlClockLib.ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-208">Note that your control inherits from `ctlClockLib.ctlClock`.</span></span> <span data-ttu-id="82ba7-209">Под открывающей скобкой оператора (`{)` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="82ba7-209">Beneath the opening brace (`{)` statement, type the following code.</span></span>  
  
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
  
### <a name="adding-to-the-graphical-interface-of-the-control"></a><span data-ttu-id="82ba7-210">Добавление графического интерфейса элементу управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-210">Adding to the Graphical Interface of the Control</span></span>  
 <span data-ttu-id="82ba7-211">Производный элемент управления получает такой же графический интерфейс, как у того элемента, из которого он наследуется.</span><span class="sxs-lookup"><span data-stu-id="82ba7-211">Your inherited control has a visual interface that is identical to the control it inherits from.</span></span> <span data-ttu-id="82ba7-212">Кроме того, он включает те же составные элементы управления, что и родительский элемент управления, однако свойства этих составных элементов будут доступны, только если предоставить их напрямую.</span><span class="sxs-lookup"><span data-stu-id="82ba7-212">It possesses the same constituent controls as its parent control, but the properties of the constituent controls will not be available unless they were specifically exposed.</span></span> <span data-ttu-id="82ba7-213">Графический интерфейс производного элемента управления добавляется точно так же, как и для любого составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-213">You may add to the graphical interface of an inherited composite control in the same manner as you would add to any composite control.</span></span> <span data-ttu-id="82ba7-214">Чтобы продолжить добавление графического интерфейса для будильника, добавим элемент управления Label, который будет мигать при срабатывании будильника.</span><span class="sxs-lookup"><span data-stu-id="82ba7-214">To continue adding to your alarm clock's visual interface, you will add a label control that will flash when the alarm is sounding.</span></span>  
  
##### <a name="to-add-the-label-control"></a><span data-ttu-id="82ba7-215">Добавление элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="82ba7-215">To add the label control</span></span>  
  
1.  <span data-ttu-id="82ba7-216">В обозревателе решений щелкните файл **ctlAlarmClock** правой кнопкой мыши и выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-216">In Solution Explorer, right-click **ctlAlarmClock**, and then click **View Designer**.</span></span>  
  
     <span data-ttu-id="82ba7-217">Конструктор для `ctlAlarmClock` откроется в главном окне.</span><span class="sxs-lookup"><span data-stu-id="82ba7-217">The designer for `ctlAlarmClock` opens in the main window.</span></span>  
  
2.  <span data-ttu-id="82ba7-218">Нажмите на отображаемую область элемента управления и просмотрите окно свойств.</span><span class="sxs-lookup"><span data-stu-id="82ba7-218">Click the display portion of the control, and view the Properties window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82ba7-219">Все свойства отображаются, но недоступны.</span><span class="sxs-lookup"><span data-stu-id="82ba7-219">While all the properties are displayed, they are dimmed.</span></span> <span data-ttu-id="82ba7-220">Это означает, что эти свойства являются собственными свойствами `lblDisplay`, в окне свойств изменить их или получить к ним доступ нельзя.</span><span class="sxs-lookup"><span data-stu-id="82ba7-220">This indicates that these properties are native to `lblDisplay` and cannot be modified or accessed in the Properties window.</span></span> <span data-ttu-id="82ba7-221">По умолчанию элементы управления, входящие в составной элемент управления, имеют статус `private` и их свойства недоступны.</span><span class="sxs-lookup"><span data-stu-id="82ba7-221">By default, controls contained in a composite control are `private`, and their properties are not accessible by any means.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82ba7-222">Чтобы последующие пользователи составного элемента управления получили доступ к входящим в него элементам управления, объявите их как `public` или `protected`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-222">If you want subsequent users of your composite control to have access to its internal controls, declare them as `public` or `protected`.</span></span> <span data-ttu-id="82ba7-223">Это позволит вам задавать и изменять свойства элементов управления в составном элементе управления, используя соответствующий код.</span><span class="sxs-lookup"><span data-stu-id="82ba7-223">This will allow you to set and modify properties of controls contained within your composite control by using the appropriate code.</span></span>  
  
3.  <span data-ttu-id="82ba7-224">Добавление <xref:System.Windows.Forms.Label> элемента управления в составной элемент управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-224">Add a <xref:System.Windows.Forms.Label> control to your composite control.</span></span>  
  
4.  <span data-ttu-id="82ba7-225">С помощью мыши, перетащите <xref:System.Windows.Forms.Label> управления непосредственно под окно отображения.</span><span class="sxs-lookup"><span data-stu-id="82ba7-225">Using the mouse, drag the <xref:System.Windows.Forms.Label> control immediately beneath the display box.</span></span> <span data-ttu-id="82ba7-226">В окне "Свойства" задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="82ba7-226">In the Properties window, set the following properties.</span></span>  
  
    |<span data-ttu-id="82ba7-227">Свойство.</span><span class="sxs-lookup"><span data-stu-id="82ba7-227">Property</span></span>|<span data-ttu-id="82ba7-228">Параметр</span><span class="sxs-lookup"><span data-stu-id="82ba7-228">Setting</span></span>|  
    |--------------|-------------|  
    |<span data-ttu-id="82ba7-229">**Name**</span><span class="sxs-lookup"><span data-stu-id="82ba7-229">**Name**</span></span>|`lblAlarm`|  
    |<span data-ttu-id="82ba7-230">**Text**</span><span class="sxs-lookup"><span data-stu-id="82ba7-230">**Text**</span></span>|<span data-ttu-id="82ba7-231">**Alarm!**</span><span class="sxs-lookup"><span data-stu-id="82ba7-231">**Alarm!**</span></span>|  
    |<span data-ttu-id="82ba7-232">**TextAlign**</span><span class="sxs-lookup"><span data-stu-id="82ba7-232">**TextAlign**</span></span>|`MiddleCenter`|  
    |<span data-ttu-id="82ba7-233">**Visible**</span><span class="sxs-lookup"><span data-stu-id="82ba7-233">**Visible**</span></span>|`false`|  
  
### <a name="adding-the-alarm-functionality"></a><span data-ttu-id="82ba7-234">Добавление функциональных возможностей будильника</span><span class="sxs-lookup"><span data-stu-id="82ba7-234">Adding the Alarm Functionality</span></span>  
 <span data-ttu-id="82ba7-235">Выполняя предыдущие процедуры, вы добавили свойства и элемент управления, которые обеспечат функциональность будильника в составном элементе управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-235">In the previous procedures, you added properties and a control that will enable alarm functionality in your composite control.</span></span> <span data-ttu-id="82ba7-236">В ходе этой процедуры вы добавите код, который будет сравнивать текущее время со временем будильника и, если они совпадают, запускать мигающее оповещение.</span><span class="sxs-lookup"><span data-stu-id="82ba7-236">In this procedure, you will add code to compare the current time to the alarm time and, if they are the same, to flash an alarm.</span></span> <span data-ttu-id="82ba7-237">Переопределив метод `timer1_Tick` в `ctlClock` и добавив в него дополнительный код, вы расширите возможности `ctlAlarmClock`, сохранив при этом все унаследованные функции `ctlClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-237">By overriding the `timer1_Tick` method of `ctlClock` and adding additional code to it, you will extend the capability of `ctlAlarmClock` while retaining all of the inherent functionality of `ctlClock`.</span></span>  
  
##### <a name="to-override-the-timer1tick-method-of-ctlclock"></a><span data-ttu-id="82ba7-238">Переопределение метода Timer1_Tick в ctlClock</span><span class="sxs-lookup"><span data-stu-id="82ba7-238">To override the timer1_Tick method of ctlClock</span></span>  
  
1.  <span data-ttu-id="82ba7-239">В **редакторе кода** найдите оператор `private bool blnAlarmSet;`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-239">In the **Code Editor**, locate the `private bool blnAlarmSet;` statement.</span></span> <span data-ttu-id="82ba7-240">Сразу после него добавьте следующий оператор.</span><span class="sxs-lookup"><span data-stu-id="82ba7-240">Immediately beneath it, add the following statement.</span></span>  
  
    ```csharp  
    private bool blnColorTicker;  
    ```  
  
2.  <span data-ttu-id="82ba7-241">В **редакторе кода** найдите закрывающую скобку (`})` в конце класса.</span><span class="sxs-lookup"><span data-stu-id="82ba7-241">In the **Code Editor**, locate the closing brace (`})` at the end of the class.</span></span> <span data-ttu-id="82ba7-242">Непосредственно перед скобкой добавьте следующий код.</span><span class="sxs-lookup"><span data-stu-id="82ba7-242">Just before the brace, add the following code.</span></span>  
  
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
  
     <span data-ttu-id="82ba7-243">Добавление этого кода решает сразу несколько задач.</span><span class="sxs-lookup"><span data-stu-id="82ba7-243">The addition of this code accomplishes several tasks.</span></span> <span data-ttu-id="82ba7-244">Оператор `override` указывает элементу управления использовать этот метод вместо метода, унаследованного из базового элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-244">The `override` statement directs the control to use this method in place of the method that was inherited from the base control.</span></span> <span data-ttu-id="82ba7-245">При вызове этого метода он вызывает переопределяемый метод, используя оператор `base.timer1_Tick`, и следит за тем, чтобы в этом элементе управления были реализованы все функции исходного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-245">When this method is called, it calls the method it overrides by invoking the `base.timer1_Tick` statement, ensuring that all of the functionality incorporated in the original control is reproduced in this control.</span></span> <span data-ttu-id="82ba7-246">Затем он выполняет дополнительный код, реализующий функции будильника.</span><span class="sxs-lookup"><span data-stu-id="82ba7-246">It then runs additional code to incorporate the alarm functionality.</span></span> <span data-ttu-id="82ba7-247">Когда будильник срабатывает, появляется мигающая метка.</span><span class="sxs-lookup"><span data-stu-id="82ba7-247">A flashing label control will appear when the alarm occurs.</span></span>  
  
     <span data-ttu-id="82ba7-248">Элемент управления "Будильник" почти готов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-248">Your alarm clock control is almost complete.</span></span> <span data-ttu-id="82ba7-249">Осталось реализовать только его отключение.</span><span class="sxs-lookup"><span data-stu-id="82ba7-249">The only thing that remains is to implement a way to turn it off.</span></span> <span data-ttu-id="82ba7-250">Для этого нужно добавить код в метод `lblAlarm_Click`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-250">To do this, you will add code to the `lblAlarm_Click` method.</span></span>  
  
##### <a name="to-implement-the-shutoff-method"></a><span data-ttu-id="82ba7-251">Реализация метода отключения</span><span class="sxs-lookup"><span data-stu-id="82ba7-251">To implement the shutoff method</span></span>  
  
1.  <span data-ttu-id="82ba7-252">В обозревателе решений щелкните файл **ctlAlarmClock.cs** правой кнопкой мыши и выберите пункт **Показать конструктор**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-252">In Solution Explorer, right-click **ctlAlarmClock.cs**, and then click **View Designer**.</span></span>  
  
     <span data-ttu-id="82ba7-253">Откроется конструктор.</span><span class="sxs-lookup"><span data-stu-id="82ba7-253">The designer opens.</span></span>  
  
2.  <span data-ttu-id="82ba7-254">Добавьте кнопку в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-254">Add a button to the control.</span></span> <span data-ttu-id="82ba7-255">Задайте свойства для этой кнопки следующим образом.</span><span class="sxs-lookup"><span data-stu-id="82ba7-255">Set the properties of the button as follows.</span></span>  
  
    |<span data-ttu-id="82ba7-256">Свойство.</span><span class="sxs-lookup"><span data-stu-id="82ba7-256">Property</span></span>|<span data-ttu-id="82ba7-257">Значение</span><span class="sxs-lookup"><span data-stu-id="82ba7-257">Value</span></span>|  
    |--------------|-----------|  
    |<span data-ttu-id="82ba7-258">**Name**</span><span class="sxs-lookup"><span data-stu-id="82ba7-258">**Name**</span></span>|`btnAlarmOff`|  
    |<span data-ttu-id="82ba7-259">**Text**</span><span class="sxs-lookup"><span data-stu-id="82ba7-259">**Text**</span></span>|<span data-ttu-id="82ba7-260">**Отключить оповещение**</span><span class="sxs-lookup"><span data-stu-id="82ba7-260">**Disable Alarm**</span></span>|  
  
3.  <span data-ttu-id="82ba7-261">В конструкторе дважды щелкните элемент управления **btnAlarmOff**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-261">In the designer, double-click **btnAlarmOff**.</span></span>  
  
     <span data-ttu-id="82ba7-262">Откроется **редактор кода** со строкой `private void btnAlarmOff_Click`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-262">The **Code Editor** opens to the `private void btnAlarmOff_Click` line.</span></span>  
  
4.  <span data-ttu-id="82ba7-263">Измените метод, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="82ba7-263">Modify this method so that it resembles the following code.</span></span>  
  
    ```csharp  
    private void btnAlarmOff_Click(object sender, System.EventArgs e)  
    {  
        // Turns off the alarm.  
        AlarmSet = false;  
        // Hides the flashing label.  
        lblAlarm.Visible = false;  
    }  
    ```  
  
5.  <span data-ttu-id="82ba7-264">Сохраните проект, открыв меню **Файл** и выбрав пункт **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-264">On the **File** menu, click **Save All** to save the project.</span></span>  
  
### <a name="using-the-inherited-control-on-a-form"></a><span data-ttu-id="82ba7-265">Использование производного элемента управления в форме</span><span class="sxs-lookup"><span data-stu-id="82ba7-265">Using the Inherited Control on a Form</span></span>  
 <span data-ttu-id="82ba7-266">Производный элемент управления проверяется точно так же, как элемент управления базового класса `ctlClock`: нажмите клавишу F5, чтобы выполнить сборку проекта и запустить элемент управления в **тестовом контейнере пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-266">You can test your inherited control the same way you tested the base class control, `ctlClock`: Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span> <span data-ttu-id="82ba7-267">Дополнительные сведения см. в разделе [Практическое руководство. Тестирование поведения элемента UserControl во время выполнения](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span><span class="sxs-lookup"><span data-stu-id="82ba7-267">For more information, see [How to: Test the Run-Time Behavior of a UserControl](../../../../docs/framework/winforms/controls/how-to-test-the-run-time-behavior-of-a-usercontrol.md).</span></span>  
  
 <span data-ttu-id="82ba7-268">Чтобы элемент управления можно было использовать, необходимо поместить его в форму.</span><span class="sxs-lookup"><span data-stu-id="82ba7-268">To put your control to use, you will need to host it on a form.</span></span> <span data-ttu-id="82ba7-269">Производный составной элемент управления, как и стандартный, не может быть автономным и должен быть размещен в форме или другом контейнере.</span><span class="sxs-lookup"><span data-stu-id="82ba7-269">As with a standard composite control, an inherited composite control cannot stand alone and must be hosted in a form or other container.</span></span> <span data-ttu-id="82ba7-270">Поскольку `ctlAlarmClock` отличается более широкими функциональными возможностями, для его проверки требуется дополнительный код.</span><span class="sxs-lookup"><span data-stu-id="82ba7-270">Since `ctlAlarmClock` has a greater depth of functionality, additional code is required to test it.</span></span> <span data-ttu-id="82ba7-271">В ходе этой процедуры вы напишете простую программу для проверки функциональных возможностей `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-271">In this procedure, you will write a simple program to test the functionality of `ctlAlarmClock`.</span></span> <span data-ttu-id="82ba7-272">Вы напишете код, задающий и отображающий свойство `AlarmTime` в `ctlAlarmClock` и проверяющий его унаследованные функции.</span><span class="sxs-lookup"><span data-stu-id="82ba7-272">You will write code to set and display the `AlarmTime` property of `ctlAlarmClock`, and will test its inherent functions.</span></span>  
  
##### <a name="to-build-and-add-your-control-to-a-test-form"></a><span data-ttu-id="82ba7-273">Сборка и добавление элемента управления в тестовую форму</span><span class="sxs-lookup"><span data-stu-id="82ba7-273">To build and add your control to a test form</span></span>  
  
1.  <span data-ttu-id="82ba7-274">В обозревателе решений щелкните файл **ctlClockLib** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-274">In Solution Explorer, right-click **ctlClockLib**, and then click **Build**.</span></span>  
  
2.  <span data-ttu-id="82ba7-275">Добавьте в решение новый проект **приложения Windows** с именем `Test`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-275">Add a new **Windows Application** project to the solution, and name it `Test`.</span></span>  
  
3.  <span data-ttu-id="82ba7-276">В обозревателе решений щелкните правой кнопкой мыши узел **Ссылки** для своего тестового проекта.</span><span class="sxs-lookup"><span data-stu-id="82ba7-276">In Solution Explorer, right-click the **References** node for your test project.</span></span> <span data-ttu-id="82ba7-277">Щелкните **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-277">Click **Add Reference** to display the **Add Reference** dialog box.</span></span> <span data-ttu-id="82ba7-278">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-278">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="82ba7-279">Проект `ctlClockLib` будет указан под полем **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-279">Your `ctlClockLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="82ba7-280">Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="82ba7-280">Double-click the project to add the reference to the test project.</span></span>  
  
4.  <span data-ttu-id="82ba7-281">В обозревателе решений щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-281">In Solution Explorer, right-click **Test**, and then click **Build**.</span></span>  
  
5.  <span data-ttu-id="82ba7-282">На **панели элементов** разверните узел **Компоненты ctlClockLib**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-282">In the **Toolbox**, expand the **ctlClockLib Components** node.</span></span>  
  
6.  <span data-ttu-id="82ba7-283">Дважды щелкните **ctlAlarmClock**, чтобы добавить копию `ctlAlarmClock` в свою форму.</span><span class="sxs-lookup"><span data-stu-id="82ba7-283">Double-click **ctlAlarmClock** to add a copy of `ctlAlarmClock` to your form.</span></span>  
  
7.  <span data-ttu-id="82ba7-284">В **элементов**, найдите и дважды щелкните **DateTimePicker** добавление <xref:System.Windows.Forms.DateTimePicker> в форму элемент управления, а затем добавьте <xref:System.Windows.Forms.Label> элемента управления, дважды щелкнув **метка**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-284">In the **Toolbox**, locate and double-click **DateTimePicker** to add a <xref:System.Windows.Forms.DateTimePicker> control to your form, and then add a <xref:System.Windows.Forms.Label> control by double-clicking **Label**.</span></span>  
  
8.  <span data-ttu-id="82ba7-285">С помощью мыши разместите элементы управления в удобном месте формы.</span><span class="sxs-lookup"><span data-stu-id="82ba7-285">Use the mouse to position the controls in a convenient place on the form.</span></span>  
  
9. <span data-ttu-id="82ba7-286">Задайте свойства этих элементов управления следующим образом.</span><span class="sxs-lookup"><span data-stu-id="82ba7-286">Set the properties of these controls in the following manner.</span></span>  
  
    |<span data-ttu-id="82ba7-287">Элемент управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-287">Control</span></span>|<span data-ttu-id="82ba7-288">Свойство</span><span class="sxs-lookup"><span data-stu-id="82ba7-288">Property</span></span>|<span data-ttu-id="82ba7-289">Значение</span><span class="sxs-lookup"><span data-stu-id="82ba7-289">Value</span></span>|  
    |-------------|--------------|-----------|  
    |`label1`|<span data-ttu-id="82ba7-290">**Text**</span><span class="sxs-lookup"><span data-stu-id="82ba7-290">**Text**</span></span>|`(blank space)`|  
    ||<span data-ttu-id="82ba7-291">**Name**</span><span class="sxs-lookup"><span data-stu-id="82ba7-291">**Name**</span></span>|`lblTest`|  
    |`dateTimePicker1`|<span data-ttu-id="82ba7-292">**Name**</span><span class="sxs-lookup"><span data-stu-id="82ba7-292">**Name**</span></span>|`dtpTest`|  
    ||<span data-ttu-id="82ba7-293">**Формат**</span><span class="sxs-lookup"><span data-stu-id="82ba7-293">**Format**</span></span>|<xref:System.Windows.Forms.DateTimePickerFormat.Time>|  
  
10. <span data-ttu-id="82ba7-294">В конструкторе дважды щелкните **dtpTest**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-294">In the designer, double-click **dtpTest**.</span></span>  
  
     <span data-ttu-id="82ba7-295">В **редакторе кода** откроется `private void dtpTest_ValueChanged`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-295">The **Code Editor** opens to `private void dtpTest_ValueChanged`.</span></span>  
  
11. <span data-ttu-id="82ba7-296">Измените код, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="82ba7-296">Modify the code so that it resembles the following.</span></span>  
  
    ```csharp  
    private void dtpTest_ValueChanged(object sender, System.EventArgs e)  
    {  
        ctlAlarmClock1.AlarmTime = dtpTest.Value;  
        ctlAlarmClock1.AlarmSet = true;  
        lblTest.Text = "Alarm Time is " +  
            ctlAlarmClock1.AlarmTime.ToShortTimeString();  
    }  
    ```  
  
12. <span data-ttu-id="82ba7-297">В обозревателе решений щелкните правой кнопкой мыши **Тест** и выберите пункт **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-297">In Solution Explorer, right-click **Test**, and then click **Set as StartUp Project**.</span></span>  
  
13. <span data-ttu-id="82ba7-298">В меню **Отладка** щелкните **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="82ba7-298">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="82ba7-299">Запустится тестовая программа.</span><span class="sxs-lookup"><span data-stu-id="82ba7-299">The test program starts.</span></span> <span data-ttu-id="82ba7-300">Обратите внимание, что текущее время обновляется в `ctlAlarmClock` управления и отображение время начала в <xref:System.Windows.Forms.DateTimePicker> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-300">Note that the current time is updated in the `ctlAlarmClock` control, and that the starting time is shown in the <xref:System.Windows.Forms.DateTimePicker> control.</span></span>  
  
14. <span data-ttu-id="82ba7-301">Нажмите кнопку <xref:System.Windows.Forms.DateTimePicker> где отображаются минуты часа.</span><span class="sxs-lookup"><span data-stu-id="82ba7-301">Click the <xref:System.Windows.Forms.DateTimePicker> where the minutes of the hour are displayed.</span></span>  
  
15. <span data-ttu-id="82ba7-302">С помощью клавиатуры укажите значение минут, составляющее на одну минуту больше текущего времени, отображаемого `ctlAlarmClock`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-302">Using the keyboard, set a value for minutes that is one minute greater than the current time shown by `ctlAlarmClock`.</span></span>  
  
     <span data-ttu-id="82ba7-303">Время включения будильника отображается в `lblTest`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-303">The time for the alarm setting is shown in `lblTest`.</span></span> <span data-ttu-id="82ba7-304">Дождитесь момента, когда отображаемое время совпадет с установленным временем будильника.</span><span class="sxs-lookup"><span data-stu-id="82ba7-304">Wait for the displayed time to reach the alarm setting time.</span></span> <span data-ttu-id="82ba7-305">Когда это произойдет, `lblAlarm` начнет мигать.</span><span class="sxs-lookup"><span data-stu-id="82ba7-305">When the displayed time reaches the time to which the alarm is set, the `lblAlarm` will flash.</span></span>  
  
16. <span data-ttu-id="82ba7-306">Отключите сигнал, нажав `btnAlarmOff`.</span><span class="sxs-lookup"><span data-stu-id="82ba7-306">Turn off the alarm by clicking `btnAlarmOff`.</span></span> <span data-ttu-id="82ba7-307">Теперь будильник можно сбросить.</span><span class="sxs-lookup"><span data-stu-id="82ba7-307">You may now reset the alarm.</span></span>  
  
     <span data-ttu-id="82ba7-308">В этом пошаговом руководстве был проиллюстрирован ряд ключевых понятий.</span><span class="sxs-lookup"><span data-stu-id="82ba7-308">This walkthrough has covered a number of key concepts.</span></span> <span data-ttu-id="82ba7-309">Вы узнали, как создать составной элемент управления, объединив элементы управления и компоненты в контейнер составного элемента управления.</span><span class="sxs-lookup"><span data-stu-id="82ba7-309">You have learned to create a composite control by combining controls and components into a composite control container.</span></span> <span data-ttu-id="82ba7-310">Вы узнали, как добавить свойства в элемент управления и написать код для реализации настраиваемых функциональных возможностей.</span><span class="sxs-lookup"><span data-stu-id="82ba7-310">You have learned to add properties to your control, and to write code to implement custom functionality.</span></span> <span data-ttu-id="82ba7-311">В последнем разделе вы узнали, как расширять функциональные возможности заданного составного элемента управления с помощью наследования и как изменять функциональные возможности методов узла путем переопределения методов.</span><span class="sxs-lookup"><span data-stu-id="82ba7-311">In the last section, you learned to extend the functionality of a given composite control through inheritance, and to alter the functionality of host methods by overriding those methods.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ba7-312">См. также</span><span class="sxs-lookup"><span data-stu-id="82ba7-312">See Also</span></span>  
 [<span data-ttu-id="82ba7-313">Разновидности пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="82ba7-313">Varieties of Custom Controls</span></span>](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 [<span data-ttu-id="82ba7-314">Программирование с использованием компонентов</span><span class="sxs-lookup"><span data-stu-id="82ba7-314">Programming with Components</span></span>](https://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
 [<span data-ttu-id="82ba7-315">Примеры создания компонентов</span><span class="sxs-lookup"><span data-stu-id="82ba7-315">Component Authoring Walkthroughs</span></span>](https://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 [<span data-ttu-id="82ba7-316">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="82ba7-316">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="82ba7-317">Пошаговое руководство. Наследование элементов управления форм Windows Forms с помощью Visual C#</span><span class="sxs-lookup"><span data-stu-id="82ba7-317">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
