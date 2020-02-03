---
title: Наследование от элемента управления
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 713ccf97a73ce9684b9124a121369f22751861d0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740138"
---
# <a name="walkthrough-inherit-from-a-windows-forms-control-with-c"></a><span data-ttu-id="f3f1a-102">Пошаговое руководство. наследование от Windows Formsного элемента управления с помощью C\#</span><span class="sxs-lookup"><span data-stu-id="f3f1a-102">Walkthrough: Inherit from a Windows Forms Control with C\#</span></span>

<span data-ttu-id="f3f1a-103">С C#помощью можно создавать эффективные настраиваемые элементы управления с помощью *наследования*.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-103">With C#, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="f3f1a-104">Наследование позволяет создавать элементы управления, сохраняющие все унаследованные функциональные возможности элементов управления Windows Forms и в то же время обладающие дополнительными функциями.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="f3f1a-105">В этом пошаговом руководстве вы создадите простой производный элемент управления с именем `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="f3f1a-106">Эта кнопка наследует функциональные возможности стандартного элемента управления <xref:System.Windows.Forms.Button> Windows Forms и предоставит настраиваемое свойство с именем `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>

## <a name="create-the-project"></a><span data-ttu-id="f3f1a-107">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="f3f1a-107">Create the Project</span></span>

<span data-ttu-id="f3f1a-108">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-108">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>

### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="f3f1a-109">Создание библиотеки элементов управления ValueButtonLib и элемента управления ValueButton</span><span class="sxs-lookup"><span data-stu-id="f3f1a-109">To create the ValueButtonLib control library and the ValueButton control</span></span>

1. <span data-ttu-id="f3f1a-110">В Visual Studio создайте новый проект **библиотеки элементов управления Windows Forms** и назовите его **ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-110">In Visual Studio, create a new **Windows Forms Control Library** project, and name it **ValueButtonLib**.</span></span>

     <span data-ttu-id="f3f1a-111">Имя проекта, `ValueButtonLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-111">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="f3f1a-112">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-112">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="f3f1a-113">Например, если в двух сборках содержатся компоненты с именем `ValueButton`, можно указать компонент `ValueButton`, используя `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-113">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="f3f1a-114">Дополнительные сведения см. в разделе [Пространства имен](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="f3f1a-114">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>

2. <span data-ttu-id="f3f1a-115">В **обозревателе решений** щелкните правой кнопкой мыши **UserControl1.cs** и выберите в контекстном меню команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-115">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="f3f1a-116">Измените имя файла на **ValueButton.CS**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-116">Change the file name to **ValueButton.cs**.</span></span> <span data-ttu-id="f3f1a-117">Чтобы переименовать все ссылки на элемент кода ' **', в соответствующем запросе нажмите кнопку** Да`UserControl1`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-117">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>

3. <span data-ttu-id="f3f1a-118">В **обозревателе решений** щелкните правой кнопкой мыши файл **ValueButton.cs** и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-118">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>

4. <span data-ttu-id="f3f1a-119">Перейдите к строке оператора `class`, `public partial class ValueButton`и измените тип, от которого этот элемент управления наследуется от <xref:System.Windows.Forms.UserControl> до <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-119">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="f3f1a-120">Это позволяет наследуемому элементу управления наследовать все функциональные возможности элемента управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-120">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>

5. <span data-ttu-id="f3f1a-121">В **обозревателе решений** откройте узел **ValueButton.cs**, чтобы отобразить сформированный конструктором файл кода **ValueButton.Designer.cs**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-121">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="f3f1a-122">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-122">Open this file in the **Code Editor**.</span></span>

6. <span data-ttu-id="f3f1a-123">Укажите метод `InitializeComponent` и удалите строку, которая назначает свойство <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-123">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="f3f1a-124">Это свойство не существует в элементе управления <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-124">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>

7. <span data-ttu-id="f3f1a-125">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-125">From the **File** menu, choose **Save All** to save the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f3f1a-126">Визуальный конструктор больше не доступен.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-126">A visual designer is no longer available.</span></span> <span data-ttu-id="f3f1a-127">Поскольку элемент управления <xref:System.Windows.Forms.Button> выполняет собственное рисование, изменить его внешний вид в конструкторе невозможно.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-127">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="f3f1a-128">Его визуальное представление будет точно таким же, как у класса, от которого он наследуется (то есть <xref:System.Windows.Forms.Button>), если только в коде не было изменено.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-128">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="f3f1a-129">В область конструктора по-прежнему можно добавлять компоненты, не имеющие элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-129">You can still add components, which have no UI elements, to the design surface.</span></span>

## <a name="add-a-property-to-your-inherited-control"></a><span data-ttu-id="f3f1a-130">Добавление свойства в наследуемый элемент управления</span><span class="sxs-lookup"><span data-stu-id="f3f1a-130">Add a Property to Your Inherited Control</span></span>

<span data-ttu-id="f3f1a-131">Один из возможных способов использования наследуемых элементов управления форм Windows Forms — это создание элементов управления, имеющих такой же внешний вид и функции, как у стандартных элементов управления Windows Forms, но предоставляющих настраиваемые свойства.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-131">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="f3f1a-132">В этом разделе вы добавите в элемент управления свойство с именем `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-132">In this section, you will add a property called `ButtonValue` to your control.</span></span>

### <a name="to-add-the-value-property"></a><span data-ttu-id="f3f1a-133">Добавьте значение свойства</span><span class="sxs-lookup"><span data-stu-id="f3f1a-133">To add the Value property</span></span>

1. <span data-ttu-id="f3f1a-134">В **обозревателе решений** щелкните правой кнопкой мыши **ValueButton.cs** и выберите в контекстном меню пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-134">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>

2. <span data-ttu-id="f3f1a-135">Найдите оператор `class`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-135">Locate the `class` statement.</span></span> <span data-ttu-id="f3f1a-136">Сразу после `{` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-136">Immediately after the `{`, type the following code:</span></span>

    ```csharp
    // Creates the private variable that will store the value of your
    // property.
    private int varValue;
    // Declares the property.
    public int ButtonValue
    {
       // Sets the method for retrieving the value of your property.
       get
       {
          return varValue;
       }
       // Sets the method for setting the value of your property.
       set
       {
          varValue = value;
       }
    }
    ```

     <span data-ttu-id="f3f1a-137">Этот код определяет методы хранения и извлечения свойства `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-137">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="f3f1a-138">Оператор `get` определяет значение, возвращаемое значению, которое хранится в закрытой переменной `varValue`, а оператор `set` задает значение закрытой переменной с помощью ключевого слова `value`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-138">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>

3. <span data-ttu-id="f3f1a-139">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-139">From the **File** menu, choose **Save All** to save the project.</span></span>

## <a name="test-the-control"></a><span data-ttu-id="f3f1a-140">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="f3f1a-140">Test the control</span></span>

<span data-ttu-id="f3f1a-141">Элементы управления не являются автономными проектами и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-141">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="f3f1a-142">Чтобы протестировать элемент управления, необходимо предоставить тестовый проект, в котором он будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-142">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="f3f1a-143">Кроме того, нужно сделать элемент управления доступным для тестового проекта, выполнив сборку (компиляцию).</span><span class="sxs-lookup"><span data-stu-id="f3f1a-143">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="f3f1a-144">В этом разделе вы выполните сборку элемента управления и протестируете его в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-144">In this section, you will build your control and test it in a Windows Form.</span></span>

### <a name="to-build-your-control"></a><span data-ttu-id="f3f1a-145">Сборка элемента управления</span><span class="sxs-lookup"><span data-stu-id="f3f1a-145">To build your control</span></span>

<span data-ttu-id="f3f1a-146">В меню **Сборка** выберите **Построить решение**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-146">On the **Build** menu, click **Build Solution**.</span></span> <span data-ttu-id="f3f1a-147">Сборка должна быть выполнена без ошибок компилятора и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-147">The build should be successful with no compiler errors or warnings.</span></span>

### <a name="to-create-a-test-project"></a><span data-ttu-id="f3f1a-148">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="f3f1a-148">To create a test project</span></span>

1. <span data-ttu-id="f3f1a-149">В меню **Файл** наведите указатель мыши на пункт **Добавить** и выберите **Проект**, чтобы открыть диалоговое окно **Добавление нового проекта**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-149">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="f3f1a-150">Выберите узел **Windows** под узлом **Visual C#** и выберите **приложение Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-150">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>

3. <span data-ttu-id="f3f1a-151">В поле **имя** введите **Test**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-151">In the **Name** box, enter **Test**.</span></span>

4. <span data-ttu-id="f3f1a-152">В **обозревателе решений** щелкните узел **Ссылки** для тестового проекта правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-152">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>

5. <span data-ttu-id="f3f1a-153">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-153">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="f3f1a-154">Проект ValueButtonLib будет указан в списке **имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-154">Your ValueButtonLib project will be listed under **Project Name**.</span></span> <span data-ttu-id="f3f1a-155">Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-155">Double-click the project to add the reference to the test project.</span></span>

6. <span data-ttu-id="f3f1a-156">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-156">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>

### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="f3f1a-157">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="f3f1a-157">To add your control to the form</span></span>

1. <span data-ttu-id="f3f1a-158">В **обозревателе решений** щелкните правой кнопкой мыши файл **Form1.cs** и выберите в контекстном меню пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-158">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>

2. <span data-ttu-id="f3f1a-159">На **панели элементов**выберите **компоненты ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-159">In the **Toolbox**, select **ValueButtonLib Components**.</span></span> <span data-ttu-id="f3f1a-160">Дважды щелкните **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-160">Double-click **ValueButton**.</span></span>

     <span data-ttu-id="f3f1a-161">Объект **ValueButton** появится в форме.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-161">A **ValueButton** appears on the form.</span></span>

3. <span data-ttu-id="f3f1a-162">Щелкните **ValueButton** правой кнопкой мыши и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-162">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>

4. <span data-ttu-id="f3f1a-163">В окне **Свойства** проверьте свойства этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-163">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="f3f1a-164">Обратите внимание, что они идентичны свойствам, предоставляемым стандартной кнопкой, за исключением того, что имеется дополнительное свойство Буттонвалуе.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-164">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, ButtonValue.</span></span>

5. <span data-ttu-id="f3f1a-165">Задайте для свойства **буттонвалуе** значение **5**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-165">Set the **ButtonValue** property to **5**.</span></span>

6. <span data-ttu-id="f3f1a-166">На вкладке **все Windows Forms** **панели элементов**дважды щелкните **надпись** , чтобы добавить в форму элемент управления <xref:System.Windows.Forms.Label>.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-166">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>

7. <span data-ttu-id="f3f1a-167">Переместите метку в центр формы.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-167">Relocate the label to the center of the form.</span></span>

8. <span data-ttu-id="f3f1a-168">Дважды щелкните файл `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-168">Double-click `valueButton1`.</span></span>

     <span data-ttu-id="f3f1a-169">В **редакторе кода** откроется событие `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-169">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>

9. <span data-ttu-id="f3f1a-170">Вставьте следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-170">Insert the following line of code.</span></span>

    ```csharp
    label1.Text = valueButton1.ButtonValue.ToString();
    ```

10. <span data-ttu-id="f3f1a-171">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите в контекстном меню команду **Назначить автозагружаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-171">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>

11. <span data-ttu-id="f3f1a-172">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-172">From the **Debug** menu, select **Start Debugging**.</span></span>

     <span data-ttu-id="f3f1a-173">Появится `Form1`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-173">`Form1` appears.</span></span>

12. <span data-ttu-id="f3f1a-174">Нажмите кнопку `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-174">Click `valueButton1`.</span></span>

     <span data-ttu-id="f3f1a-175">В `label1` появится цифра 5, показывающая, что свойство `ButtonValue` унаследованного элемента управления передано `label1` с помощью метода `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-175">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="f3f1a-176">Таким образом, ваш элемент управления `ValueButton` наследует функциональные возможности стандартной кнопки Windows Forms и при этом предоставляет дополнительное настраиваемое свойство.</span><span class="sxs-lookup"><span data-stu-id="f3f1a-176">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3f1a-177">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f3f1a-177">See also</span></span>

- [<span data-ttu-id="f3f1a-178">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="f3f1a-178">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)
- [<span data-ttu-id="f3f1a-179">Пошаговое руководство. Создание составного элемента управления с помощью C#</span><span class="sxs-lookup"><span data-stu-id="f3f1a-179">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
