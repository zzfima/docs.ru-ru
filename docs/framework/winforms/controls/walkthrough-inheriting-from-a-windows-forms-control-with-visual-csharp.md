---
title: Пример. Наследование элементов управления форм Windows Forms с помощью Visual C#
ms.date: 03/30/2017
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: 09476da0-8d4c-4a4c-b969-649519dfb438
ms.openlocfilehash: 1e9231065369640fa49e04a491b92ebfb1e91912
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-c"></a><span data-ttu-id="5bb99-102">Пример. Наследование элементов управления форм Windows Forms с помощью Visual C#</span><span class="sxs-lookup"><span data-stu-id="5bb99-102">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span> #
<span data-ttu-id="5bb99-103">С помощью [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)] можно создавать эффективные настраиваемые элементы управления путем *наследования*.</span><span class="sxs-lookup"><span data-stu-id="5bb99-103">With [!INCLUDE[csprcslong](../../../../includes/csprcslong-md.md)], you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="5bb99-104">Наследование позволяет создавать элементы управления, сохраняющие все унаследованные функциональные возможности элементов управления Windows Forms и в то же время обладающие дополнительными функциями.</span><span class="sxs-lookup"><span data-stu-id="5bb99-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="5bb99-105">В этом пошаговом руководстве вы создадите простой производный элемент управления с именем `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="5bb99-106">Эта кнопка наследует функциональные возможности стандартных форм Windows <xref:System.Windows.Forms.Button> управления и предоставляет настраиваемое свойство `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5bb99-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5bb99-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5bb99-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5bb99-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5bb99-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="5bb99-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5bb99-110">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="5bb99-110">Creating the Project</span></span>  
 <span data-ttu-id="5bb99-111">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="5bb99-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="5bb99-112">Создание библиотеки элементов управления ValueButtonLib и элемента управления ValueButton</span><span class="sxs-lookup"><span data-stu-id="5bb99-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="5bb99-113">В меню **Файл** наведите указатель мыши на пункт **Создать** и выберите **Проект**, чтобы открыть диалоговое окно **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="5bb99-114">Выберите **Библиотека элементов управления Windows Forms** шаблон проекта из списка проектов Visual C#, а также тип `ValueButtonLib` в **имя** поле.</span><span class="sxs-lookup"><span data-stu-id="5bb99-114">Select the **Windows Forms Control Library** project template from the list of Visual C# Projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="5bb99-115">Имя проекта, `ValueButtonLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="5bb99-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="5bb99-116">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="5bb99-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="5bb99-117">Например, если в двух сборках содержатся компоненты с именем `ValueButton`, можно указать компонент `ValueButton`, используя `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="5bb99-118">Дополнительные сведения см. в разделе [Пространства имен](../../../csharp/programming-guide/namespaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="5bb99-118">For more information, see [Namespaces](../../../csharp/programming-guide/namespaces/index.md).</span></span>  
  
3.  <span data-ttu-id="5bb99-119">В **обозревателе решений** щелкните правой кнопкой мыши **UserControl1.cs** и выберите в контекстном меню команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-119">In **Solution Explorer**, right-click **UserControl1.cs**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="5bb99-120">Измените имя файла на `ValueButton.cs`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-120">Change the file name to `ValueButton.cs`.</span></span> <span data-ttu-id="5bb99-121">Чтобы переименовать все ссылки на элемент кода '`UserControl1`', в соответствующем запросе нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-121">Click the **Yes** button when you are asked if you want to rename all references to the code element '`UserControl1`'.</span></span>  
  
4.  <span data-ttu-id="5bb99-122">В **обозревателе решений** щелкните правой кнопкой мыши файл **ValueButton.cs** и выберите команду **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-122">In **Solution Explorer**, right-click **ValueButton.cs** and select **View Code**.</span></span>  
  
5.  <span data-ttu-id="5bb99-123">Найдите `class` строка инструкции `public partial class ValueButton`и измените тип, от которого наследует этот элемент управления <xref:System.Windows.Forms.UserControl> для <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="5bb99-123">Locate the `class` statement line, `public partial class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="5bb99-124">Это позволит элементу управления могут наследовать все функциональные возможности <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb99-124">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
6.  <span data-ttu-id="5bb99-125">В **обозревателе решений** откройте узел **ValueButton.cs**, чтобы отобразить сформированный конструктором файл кода **ValueButton.Designer.cs**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-125">In **Solution Explorer**, open the **ValueButton.cs** node to display the designer-generated code file, **ValueButton.Designer.cs**.</span></span> <span data-ttu-id="5bb99-126">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-126">Open this file in the **Code Editor**.</span></span>  
  
7.  <span data-ttu-id="5bb99-127">Найдите `InitializeComponent` метод и удалите строку, которая присваивает <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="5bb99-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="5bb99-128">Это свойство не существует в <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb99-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="5bb99-129">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5bb99-130">Визуальный конструктор больше не доступен.</span><span class="sxs-lookup"><span data-stu-id="5bb99-130">A visual designer is no longer available.</span></span> <span data-ttu-id="5bb99-131">Поскольку <xref:System.Windows.Forms.Button> управления обладает своим собственным оформлением, их нельзя изменить в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="5bb99-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="5bb99-132">Визуальное представление будет иметь точно таким же, что он наследуется от класса (то есть, <xref:System.Windows.Forms.Button>), если в коде.</span><span class="sxs-lookup"><span data-stu-id="5bb99-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span> <span data-ttu-id="5bb99-133">В область конструктора по-прежнему можно добавлять компоненты, не имеющие элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5bb99-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="5bb99-134">Добавление свойства в наследуемый элемент управления</span><span class="sxs-lookup"><span data-stu-id="5bb99-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="5bb99-135">Один из возможных способов использования наследуемых элементов управления форм Windows Forms — это создание элементов управления, имеющих такой же внешний вид и функции, как у стандартных элементов управления Windows Forms, но предоставляющих настраиваемые свойства.</span><span class="sxs-lookup"><span data-stu-id="5bb99-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in look and feel of standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="5bb99-136">В этом разделе вы добавите в элемент управления свойство с именем `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="5bb99-137">Добавьте значение свойства</span><span class="sxs-lookup"><span data-stu-id="5bb99-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="5bb99-138">В **обозревателе решений** щелкните правой кнопкой мыши **ValueButton.cs** и выберите в контекстном меню пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-138">In **Solution Explorer**, right-click **ValueButton.cs**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5bb99-139">Найдите оператор `class`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-139">Locate the `class` statement.</span></span> <span data-ttu-id="5bb99-140">Сразу после `{` введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="5bb99-140">Immediately after the `{`, type the following code:</span></span>  
  
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
  
     <span data-ttu-id="5bb99-141">Этот код определяет методы хранения и извлечения свойства `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="5bb99-142">Оператор `get` определяет значение, возвращаемое значению, которое хранится в закрытой переменной `varValue`, а оператор `set` задает значение закрытой переменной с помощью ключевого слова `value`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-142">The `get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `set` statement sets the value of the private variable by use of the `value` keyword.</span></span>  
  
3.  <span data-ttu-id="5bb99-143">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="5bb99-144">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="5bb99-144">Testing Your Control</span></span>  
 <span data-ttu-id="5bb99-145">Элементы управления не являются автономными проектами и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="5bb99-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="5bb99-146">Чтобы протестировать элемент управления, необходимо предоставить тестовый проект, в котором он будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="5bb99-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="5bb99-147">Кроме того, нужно сделать элемент управления доступным для тестового проекта, выполнив сборку (компиляцию).</span><span class="sxs-lookup"><span data-stu-id="5bb99-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="5bb99-148">В этом разделе вы выполните сборку элемента управления и протестируете его в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5bb99-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="5bb99-149">Сборка элемента управления</span><span class="sxs-lookup"><span data-stu-id="5bb99-149">To build your control</span></span>  
  
1.  <span data-ttu-id="5bb99-150">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="5bb99-151">Сборка должна быть выполнена без ошибок компилятора и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="5bb99-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="5bb99-152">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="5bb99-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="5bb99-153">В меню **Файл** наведите указатель мыши на пункт **Добавить** и выберите **Проект**, чтобы открыть диалоговое окно **Добавление нового проекта**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="5bb99-154">Выберите узел **Windows** под узлом **Visual C#** и выберите **приложение Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-154">Select the **Windows** node, beneath the **Visual C#** node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="5bb99-155">В поле **Имя** введите `Test`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="5bb99-156">В **обозревателе решений** щелкните узел **Ссылки** для тестового проекта правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-156">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
5.  <span data-ttu-id="5bb99-157">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-157">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="5bb99-158">Проект `ValueButtonLib` будет указан под полем **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-158">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="5bb99-159">Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="5bb99-159">Double-click the project to add the reference to the test project.</span></span>  
  
6.  <span data-ttu-id="5bb99-160">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-160">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="5bb99-161">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="5bb99-161">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="5bb99-162">В **обозревателе решений** щелкните правой кнопкой мыши файл **Form1.cs** и выберите в контекстном меню пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-162">In **Solution Explorer**, right-click **Form1.cs** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="5bb99-163">На **панели элементов** выберите **Компоненты ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-163">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="5bb99-164">Дважды щелкните **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-164">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="5bb99-165">Объект **ValueButton** появится в форме.</span><span class="sxs-lookup"><span data-stu-id="5bb99-165">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="5bb99-166">Щелкните **ValueButton** правой кнопкой мыши и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-166">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="5bb99-167">В окне **Свойства** проверьте свойства этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb99-167">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="5bb99-168">Обратите внимание, что они идентичны свойствам стандартной кнопки, кроме дополнительного свойства `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-168">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="5bb99-169">Задайте для свойства `ButtonValue` значение `5`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-169">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="5bb99-170">В **все формы Windows Forms** вкладке **элементов**, дважды щелкните **метка** добавление <xref:System.Windows.Forms.Label> форму элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5bb99-170">In the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="5bb99-171">Переместите метку в центр формы.</span><span class="sxs-lookup"><span data-stu-id="5bb99-171">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="5bb99-172">Дважды щелкните файл `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-172">Double-click `valueButton1`.</span></span>  
  
     <span data-ttu-id="5bb99-173">В **редакторе кода** откроется событие `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-173">The **Code Editor** opens to the `valueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="5bb99-174">Вставьте следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="5bb99-174">Insert the following line of code.</span></span>  
  
    ```csharp  
    label1.Text = valueButton1.ButtonValue.ToString();  
    ```  
  
10. <span data-ttu-id="5bb99-175">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите в контекстном меню команду **Назначить автозагружаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-175">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="5bb99-176">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="5bb99-176">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="5bb99-177">Появится `Form1`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-177">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="5bb99-178">Нажмите кнопку `valueButton1`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-178">Click `valueButton1`.</span></span>  
  
     <span data-ttu-id="5bb99-179">В `label1` появится цифра 5, показывающая, что свойство `ButtonValue` унаследованного элемента управления передано `label1` с помощью метода `valueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="5bb99-179">The numeral '5' is displayed in `label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `label1` through the `valueButton1_Click` method.</span></span> <span data-ttu-id="5bb99-180">Таким образом, ваш элемент управления `ValueButton` наследует функциональные возможности стандартной кнопки Windows Forms и при этом предоставляет дополнительное настраиваемое свойство.</span><span class="sxs-lookup"><span data-stu-id="5bb99-180">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bb99-181">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb99-181">See Also</span></span>  
 [<span data-ttu-id="5bb99-182">Программирование с использованием компонентов</span><span class="sxs-lookup"><span data-stu-id="5bb99-182">Programming with Components</span></span>](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)  
 [<span data-ttu-id="5bb99-183">Примеры создания компонентов</span><span class="sxs-lookup"><span data-stu-id="5bb99-183">Component Authoring Walkthroughs</span></span>](http://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)  
 [<span data-ttu-id="5bb99-184">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="5bb99-184">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="5bb99-185">Пошаговое руководство. Создание составного элемента управления с помощью C#</span><span class="sxs-lookup"><span data-stu-id="5bb99-185">Walkthrough: Authoring a Composite Control with Visual C#</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-csharp.md)
