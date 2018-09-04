---
title: Пример. Наследование элементов управления форм Windows Forms с помощью Visual Basic
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- inheritance [Windows Forms], custom controls
- inheritance [Windows Forms], control
- Windows Forms controls, inheritance
- inheritance [Windows Forms], walkthroughs
- custom controls [Windows Forms], inheritance
ms.assetid: fb58d7c8-b702-4478-ad31-b00cae118882
ms.openlocfilehash: 6c70de1bf6a5340b6f5b2c652110ed9be5536665
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43541082"
---
# <a name="walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic"></a><span data-ttu-id="4c430-102">Пример. Наследование элементов управления форм Windows Forms с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c430-102">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>
<span data-ttu-id="4c430-103">Visual Basic позволяет создавать эффективные настраиваемые элементы управления *наследования*.</span><span class="sxs-lookup"><span data-stu-id="4c430-103">With Visual Basic, you can create powerful custom controls through *inheritance*.</span></span> <span data-ttu-id="4c430-104">Наследование позволяет создавать элементы управления, сохраняющие все унаследованные функциональные возможности элементов управления Windows Forms и в то же время обладающие дополнительными функциями.</span><span class="sxs-lookup"><span data-stu-id="4c430-104">Through inheritance you are able to create controls that retain all of the inherent functionality of standard Windows Forms controls but also incorporate custom functionality.</span></span> <span data-ttu-id="4c430-105">В этом пошаговом руководстве вы создадите простой производный элемент управления с именем `ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="4c430-105">In this walkthrough, you will create a simple inherited control called `ValueButton`.</span></span> <span data-ttu-id="4c430-106">Эта кнопка наследует функциональные возможности стандартных форм Windows <xref:System.Windows.Forms.Button> управления и предоставляет настраиваемое свойство `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="4c430-106">This button will inherit functionality from the standard Windows Forms <xref:System.Windows.Forms.Button> control, and will expose a custom property called `ButtonValue`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c430-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="4c430-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4c430-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="4c430-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4c430-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4c430-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4c430-110">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4c430-110">Creating the Project</span></span>  
 <span data-ttu-id="4c430-111">Создавая проект, вы указываете для него имя, чтобы задать корневое пространство имен, имя сборки и имя проекта, и необходимо убедиться в том, что компонент по умолчанию попадет в нужное пространство имен.</span><span class="sxs-lookup"><span data-stu-id="4c430-111">When you create a new project, you specify its name in order to set the root namespace, assembly name, and project name, and to ensure that the default component will be in the correct namespace.</span></span>  
  
#### <a name="to-create-the-valuebuttonlib-control-library-and-the-valuebutton-control"></a><span data-ttu-id="4c430-112">Создание библиотеки элементов управления ValueButtonLib и элемента управления ValueButton</span><span class="sxs-lookup"><span data-stu-id="4c430-112">To create the ValueButtonLib control library and the ValueButton control</span></span>  
  
1.  <span data-ttu-id="4c430-113">В меню **Файл** наведите указатель мыши на пункт **Создать** и выберите **Проект**, чтобы открыть диалоговое окно **Создание проекта**.</span><span class="sxs-lookup"><span data-stu-id="4c430-113">On the **File** menu, point to **New** and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="4c430-114">Выберите **Библиотека элементов управления Windows Forms** шаблон проекта из списка проектов Visual Basic и тип `ValueButtonLib` в **имя** поле.</span><span class="sxs-lookup"><span data-stu-id="4c430-114">Select the **Windows Forms Control Library** project template from the list of Visual Basic projects, and type `ValueButtonLib` in the **Name** box.</span></span>  
  
     <span data-ttu-id="4c430-115">Имя проекта, `ValueButtonLib`, по умолчанию также назначается корневому пространству имен.</span><span class="sxs-lookup"><span data-stu-id="4c430-115">The project name, `ValueButtonLib`, is also assigned to the root namespace by default.</span></span> <span data-ttu-id="4c430-116">Корневое пространство имен используется для определения имен компонентов в сборке.</span><span class="sxs-lookup"><span data-stu-id="4c430-116">The root namespace is used to qualify the names of components in the assembly.</span></span> <span data-ttu-id="4c430-117">Например, если в двух сборках содержатся компоненты с именем `ValueButton`, можно указать компонент `ValueButton`, используя `ValueButtonLib.ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="4c430-117">For example, if two assemblies provide components named `ValueButton`, you can specify your `ValueButton` component using `ValueButtonLib.ValueButton`.</span></span> <span data-ttu-id="4c430-118">Дополнительные сведения см. в разделе [Пространства имен в Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span><span class="sxs-lookup"><span data-stu-id="4c430-118">For more information, see [Namespaces in Visual Basic](~/docs/visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
3.  <span data-ttu-id="4c430-119">В **обозревателе решений** щелкните правой кнопкой мыши **UserControl1.vb** и выберите в контекстном меню команду **Переименовать**.</span><span class="sxs-lookup"><span data-stu-id="4c430-119">In **Solution Explorer**, right-click **UserControl1.vb**, then choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="4c430-120">Измените имя файла на `ValueButton.vb`.</span><span class="sxs-lookup"><span data-stu-id="4c430-120">Change the file name to `ValueButton.vb`.</span></span> <span data-ttu-id="4c430-121">Чтобы переименовать все ссылки на элемент кода UserControl1, в соответствующем запросе нажмите кнопку **Да**.</span><span class="sxs-lookup"><span data-stu-id="4c430-121">Click the **Yes** button when you are asked if you want to rename all references to the code element 'UserControl1'.</span></span>  
  
4.  <span data-ttu-id="4c430-122">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="4c430-122">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="4c430-123">Откройте узел **ValueButton.vb**, чтобы отобразить сформированный конструктором файл кода **ValueButton.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="4c430-123">Open the **ValueButton.vb** node to display the designer-generated code file, **ValueButton.Designer.vb**.</span></span> <span data-ttu-id="4c430-124">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="4c430-124">Open this file in the **Code Editor**.</span></span>  
  
6.  <span data-ttu-id="4c430-125">Найдите `Class` инструкции `Partial Public Class ValueButton`и измените тип, из которого наследуется этот элемент управления из <xref:System.Windows.Forms.UserControl> для <xref:System.Windows.Forms.Button>.</span><span class="sxs-lookup"><span data-stu-id="4c430-125">Locate the `Class` statement, `Partial Public Class ValueButton`, and change the type from which this control inherits from <xref:System.Windows.Forms.UserControl> to <xref:System.Windows.Forms.Button>.</span></span> <span data-ttu-id="4c430-126">Это позволяет элементу управления унаследовать все функции из <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c430-126">This allows your inherited control to inherit all the functionality of the <xref:System.Windows.Forms.Button> control.</span></span>  
  
7.  <span data-ttu-id="4c430-127">Найдите `InitializeComponent` метод и удалить строку, назначающую <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4c430-127">Locate the `InitializeComponent` method and remove the line that assigns the <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> property.</span></span> <span data-ttu-id="4c430-128">Это свойство не существует в <xref:System.Windows.Forms.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c430-128">This property does not exist in the <xref:System.Windows.Forms.Button> control.</span></span>  
  
8.  <span data-ttu-id="4c430-129">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4c430-129">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
     <span data-ttu-id="4c430-130">Обратите внимание, что визуальный конструктор больше не доступен.</span><span class="sxs-lookup"><span data-stu-id="4c430-130">Note that a visual designer is no longer available.</span></span> <span data-ttu-id="4c430-131">Так как <xref:System.Windows.Forms.Button> элемент управления имеет собственное оформление, вы не сможете изменить его внешний вид в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="4c430-131">Because the <xref:System.Windows.Forms.Button> control does its own painting, you are unable to modify its appearance in the designer.</span></span> <span data-ttu-id="4c430-132">Визуальное представление будет иметь точно так же, как он наследует от класса (то есть <xref:System.Windows.Forms.Button>) Если изменения в код.</span><span class="sxs-lookup"><span data-stu-id="4c430-132">Its visual representation will be exactly the same as that of the class it inherits from (that is, <xref:System.Windows.Forms.Button>) unless modified in the code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c430-133">В область конструктора по-прежнему можно добавлять компоненты, не имеющие элементов пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="4c430-133">You can still add components, which have no UI elements, to the design surface.</span></span>  
  
## <a name="adding-a-property-to-your-inherited-control"></a><span data-ttu-id="4c430-134">Добавление свойства в наследуемый элемент управления</span><span class="sxs-lookup"><span data-stu-id="4c430-134">Adding a Property to Your Inherited Control</span></span>  
 <span data-ttu-id="4c430-135">Один из возможных способов использования наследуемых элементов управления форм Windows Forms — это создание элементов управления, имеющих такой же внешний вид и функции, как у стандартных элементов управления Windows Forms, но предоставляющих настраиваемые свойства.</span><span class="sxs-lookup"><span data-stu-id="4c430-135">One possible use of inherited Windows Forms controls is the creation of controls that are identical in appearance and behavior (look and feel) to standard Windows Forms controls, but expose custom properties.</span></span> <span data-ttu-id="4c430-136">В этом разделе вы добавите в элемент управления свойство с именем `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="4c430-136">In this section, you will add a property called `ButtonValue` to your control.</span></span>  
  
#### <a name="to-add-the-value-property"></a><span data-ttu-id="4c430-137">Добавьте значение свойства</span><span class="sxs-lookup"><span data-stu-id="4c430-137">To add the Value property</span></span>  
  
1.  <span data-ttu-id="4c430-138">В **обозревателе решений** щелкните правой кнопкой мыши **ValueButton.vb** и выберите в контекстном меню пункт **Просмотреть код**.</span><span class="sxs-lookup"><span data-stu-id="4c430-138">In **Solution Explorer**, right-click **ValueButton.vb**, and then click **View Code** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4c430-139">Найдите оператор `Public Class ValueButton`.</span><span class="sxs-lookup"><span data-stu-id="4c430-139">Locate the `Public Class ValueButton` statement.</span></span> <span data-ttu-id="4c430-140">Под открывающей скобкой этого оператора введите следующий код.</span><span class="sxs-lookup"><span data-stu-id="4c430-140">Immediately beneath this statement, type the following code:</span></span>  
  
    ```vb  
    ' Creates the private variable that will store the value of your   
    ' property.  
    Private varValue as integer  
    ' Declares the property.  
    Property ButtonValue() as Integer  
    ' Sets the method for retrieving the value of your property.  
       Get  
          Return varValue  
       End Get  
    ' Sets the method for setting the value of your property.  
       Set(ByVal Value as Integer)  
          varValue = Value  
       End Set  
    End Property  
    ```  
  
     <span data-ttu-id="4c430-141">Этот код определяет методы хранения и извлечения свойства `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="4c430-141">This code sets the methods by which the `ButtonValue` property is stored and retrieved.</span></span> <span data-ttu-id="4c430-142">Оператор `Get` определяет значение, возвращаемое значению, которое хранится в закрытой переменной `varValue`, а оператор `Set` задает значение закрытой переменной с помощью ключевого слова `Value`.</span><span class="sxs-lookup"><span data-stu-id="4c430-142">The `Get` statement sets the value returned to the value that is stored in the private variable `varValue`, and the `Set` statement sets the value of the private variable by use of the `Value` keyword.</span></span>  
  
3.  <span data-ttu-id="4c430-143">Сохраните проект, выбрав в меню **Файл** команду **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="4c430-143">From the **File** menu, choose **Save All** to save the project.</span></span>  
  
## <a name="testing-your-control"></a><span data-ttu-id="4c430-144">Тестирование элемента управления</span><span class="sxs-lookup"><span data-stu-id="4c430-144">Testing Your Control</span></span>  
 <span data-ttu-id="4c430-145">Элементы управления не являются автономными проектами и должны размещаться в контейнере.</span><span class="sxs-lookup"><span data-stu-id="4c430-145">Controls are not stand-alone projects; they must be hosted in a container.</span></span> <span data-ttu-id="4c430-146">Чтобы протестировать элемент управления, необходимо предоставить тестовый проект, в котором он будет выполняться.</span><span class="sxs-lookup"><span data-stu-id="4c430-146">In order to test your control, you must provide a test project for it to run in.</span></span> <span data-ttu-id="4c430-147">Кроме того, нужно сделать элемент управления доступным для тестового проекта, выполнив сборку (компиляцию).</span><span class="sxs-lookup"><span data-stu-id="4c430-147">You must also make your control accessible to the test project by building (compiling) it.</span></span> <span data-ttu-id="4c430-148">В этом разделе вы выполните сборку элемента управления и протестируете его в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4c430-148">In this section, you will build your control and test it in a Windows Form.</span></span>  
  
#### <a name="to-build-your-control"></a><span data-ttu-id="4c430-149">Сборка элемента управления</span><span class="sxs-lookup"><span data-stu-id="4c430-149">To build your control</span></span>  
  
1.  <span data-ttu-id="4c430-150">В меню **Сборка** выберите **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="4c430-150">On the **Build** menu, click **Build Solution**.</span></span>  
  
     <span data-ttu-id="4c430-151">Сборка должна быть выполнена без ошибок компилятора и предупреждений.</span><span class="sxs-lookup"><span data-stu-id="4c430-151">The build should be successful with no compiler errors or warnings.</span></span>  
  
#### <a name="to-create-a-test-project"></a><span data-ttu-id="4c430-152">Создание тестового проекта</span><span class="sxs-lookup"><span data-stu-id="4c430-152">To create a test project</span></span>  
  
1.  <span data-ttu-id="4c430-153">В меню **Файл** наведите указатель мыши на пункт **Добавить** и выберите **Проект**, чтобы открыть диалоговое окно **Добавление нового проекта**.</span><span class="sxs-lookup"><span data-stu-id="4c430-153">On the **File** menu, point to **Add** and then click **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="4c430-154">Выберите узел проектов Visual Basic и нажмите кнопку **приложение Windows Forms**.</span><span class="sxs-lookup"><span data-stu-id="4c430-154">Select the Visual Basic projects node, and click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="4c430-155">В поле **Имя** введите `Test`.</span><span class="sxs-lookup"><span data-stu-id="4c430-155">In the **Name** box, type `Test`.</span></span>  
  
4.  <span data-ttu-id="4c430-156">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="4c430-156">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
5.  <span data-ttu-id="4c430-157">В **обозревателе решений** щелкните узел **Ссылки** для тестового проекта правой кнопкой мыши и выберите в контекстном меню пункт **Добавить ссылку**, чтобы открыть диалоговое окно **Добавление ссылки**.</span><span class="sxs-lookup"><span data-stu-id="4c430-157">In **Solution Explorer**, right-click the **References** node for your test project, then select **Add Reference** from the shortcut menu to display the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="4c430-158">Щелкните вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="4c430-158">Click the **Projects** tab.</span></span>  
  
7.  <span data-ttu-id="4c430-159">Выберите вкладку **Проекты**.</span><span class="sxs-lookup"><span data-stu-id="4c430-159">Click the tab labeled **Projects**.</span></span> <span data-ttu-id="4c430-160">Проект `ValueButtonLib` будет указан под полем **Имя проекта**.</span><span class="sxs-lookup"><span data-stu-id="4c430-160">Your `ValueButtonLib` project will be listed under **Project Name**.</span></span> <span data-ttu-id="4c430-161">Дважды щелкните проект, чтобы добавить ссылку на тестовый проект.</span><span class="sxs-lookup"><span data-stu-id="4c430-161">Double-click the project to add the reference to the test project.</span></span>  
  
8.  <span data-ttu-id="4c430-162">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите пункт **Построить**.</span><span class="sxs-lookup"><span data-stu-id="4c430-162">In **Solution Explorer,** right-click **Test** and select **Build**.</span></span>  
  
#### <a name="to-add-your-control-to-the-form"></a><span data-ttu-id="4c430-163">Добавление элемента управления в форму</span><span class="sxs-lookup"><span data-stu-id="4c430-163">To add your control to the form</span></span>  
  
1.  <span data-ttu-id="4c430-164">В **обозревателе решений** щелкните правой кнопкой мыши файл **Form1.vb** и выберите в контекстном меню пункт **Конструктор представлений**.</span><span class="sxs-lookup"><span data-stu-id="4c430-164">In **Solution Explorer**, right-click **Form1.vb** and choose **View Designer** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="4c430-165">На **панели элементов** выберите **Компоненты ValueButtonLib**.</span><span class="sxs-lookup"><span data-stu-id="4c430-165">In the **Toolbox**, click **ValueButtonLib Components**.</span></span> <span data-ttu-id="4c430-166">Дважды щелкните **ValueButton**.</span><span class="sxs-lookup"><span data-stu-id="4c430-166">Double-click **ValueButton**.</span></span>  
  
     <span data-ttu-id="4c430-167">Объект **ValueButton** появится в форме.</span><span class="sxs-lookup"><span data-stu-id="4c430-167">A **ValueButton** appears on the form.</span></span>  
  
3.  <span data-ttu-id="4c430-168">Щелкните **ValueButton** правой кнопкой мыши и выберите в контекстном меню пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="4c430-168">Right-click the **ValueButton** and select **Properties** from the shortcut menu.</span></span>  
  
4.  <span data-ttu-id="4c430-169">В окне **Свойства** проверьте свойства этого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c430-169">In the **Properties** window, examine the properties of this control.</span></span> <span data-ttu-id="4c430-170">Обратите внимание, что они идентичны свойствам стандартной кнопки, кроме дополнительного свойства `ButtonValue`.</span><span class="sxs-lookup"><span data-stu-id="4c430-170">Note that they are identical to the properties exposed by a standard button, except that there is an additional property, `ButtonValue`.</span></span>  
  
5.  <span data-ttu-id="4c430-171">Задайте для свойства `ButtonValue` значение `5`.</span><span class="sxs-lookup"><span data-stu-id="4c430-171">Set the `ButtonValue` property to `5`.</span></span>  
  
6.  <span data-ttu-id="4c430-172">На **все формы Windows Forms** вкладке **элементов**, дважды щелкните **метка** добавление <xref:System.Windows.Forms.Label> форму элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4c430-172">On the **All Windows Forms** tab of the **Toolbox**, double-click **Label** to add a <xref:System.Windows.Forms.Label> control to your form.</span></span>  
  
7.  <span data-ttu-id="4c430-173">Переместите метку в центр формы.</span><span class="sxs-lookup"><span data-stu-id="4c430-173">Relocate the label to the center of the form.</span></span>  
  
8.  <span data-ttu-id="4c430-174">Дважды щелкните файл `ValueButton1`.</span><span class="sxs-lookup"><span data-stu-id="4c430-174">Double-click `ValueButton1`.</span></span>  
  
     <span data-ttu-id="4c430-175">В **редакторе кода** откроется событие `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="4c430-175">The **Code Editor** opens to the `ValueButton1_Click` event.</span></span>  
  
9. <span data-ttu-id="4c430-176">Введите следующую строку кода.</span><span class="sxs-lookup"><span data-stu-id="4c430-176">Type the following line of code.</span></span>  
  
    ```vb  
    Label1.Text = CStr(ValueButton1.ButtonValue)  
    ```  
  
10. <span data-ttu-id="4c430-177">В **обозревателе решений** щелкните **Тест** правой кнопкой мыши и выберите в контекстном меню команду **Назначить автозагружаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="4c430-177">In **Solution Explorer**, right-click **Test**, and choose **Set as Startup Project** from the shortcut menu.</span></span>  
  
11. <span data-ttu-id="4c430-178">В меню **Отладка** выберите пункт **Начать отладку**.</span><span class="sxs-lookup"><span data-stu-id="4c430-178">From the **Debug** menu, select **Start Debugging**.</span></span>  
  
     <span data-ttu-id="4c430-179">Появится `Form1`.</span><span class="sxs-lookup"><span data-stu-id="4c430-179">`Form1` appears.</span></span>  
  
12. <span data-ttu-id="4c430-180">Нажмите кнопку `Valuebutton1`.</span><span class="sxs-lookup"><span data-stu-id="4c430-180">Click `Valuebutton1`.</span></span>  
  
     <span data-ttu-id="4c430-181">В `Label1` появится цифра 5, показывающая, что свойство `ButtonValue` унаследованного элемента управления передано `Label1` с помощью метода `ValueButton1_Click`.</span><span class="sxs-lookup"><span data-stu-id="4c430-181">The numeral '5' is displayed in `Label1`, demonstrating that the `ButtonValue` property of your inherited control has been passed to `Label1` through the `ValueButton1_Click` method.</span></span> <span data-ttu-id="4c430-182">Таким образом, ваш элемент управления `ValueButton` наследует функциональные возможности стандартной кнопки Windows Forms и при этом предоставляет дополнительное настраиваемое свойство.</span><span class="sxs-lookup"><span data-stu-id="4c430-182">Thus your `ValueButton` control inherits all the functionality of the standard Windows Forms button, but exposes an additional, custom property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c430-183">См. также</span><span class="sxs-lookup"><span data-stu-id="4c430-183">See Also</span></span>  
 [<span data-ttu-id="4c430-184">Пошаговое руководство. Создание составного элемента управления с помощью Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4c430-184">Walkthrough: Authoring a Composite Control with Visual Basic</span></span>](../../../../docs/framework/winforms/controls/walkthrough-authoring-a-composite-control-with-visual-basic.md)  
 [<span data-ttu-id="4c430-185">Практическое руководство. Отображение элемента управления в диалоговом окне выбора элементов панели элементов</span><span class="sxs-lookup"><span data-stu-id="4c430-185">How to: Display a Control in the Choose Toolbox Items Dialog Box</span></span>](../../../../docs/framework/winforms/controls/how-to-display-a-control-in-the-choose-toolbox-items-dialog-box.md)  
 [<span data-ttu-id="4c430-186">Разработка пользовательских элементов управления Windows Forms в .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4c430-186">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)  
 [<span data-ttu-id="4c430-187">Основы наследования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4c430-187">Inheritance basics (Visual Basic)</span></span>](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [<span data-ttu-id="4c430-188">Примеры создания компонентов</span><span class="sxs-lookup"><span data-stu-id="4c430-188">Component Authoring Walkthroughs</span></span>](https://msdn.microsoft.com/library/c414cca9-2489-4208-8b38-954586d91c13)
