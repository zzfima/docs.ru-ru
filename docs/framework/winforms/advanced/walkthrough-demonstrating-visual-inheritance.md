---
title: Пошаговое руководство. Демонстрация визуального наследования
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- form inheritance [Windows Forms], walkthroughs
- visual inheritance
- inheritance [Windows Forms], walkthroughs
- walkthroughs [Windows Forms], visual inheritance
- Windows Forms, inheritance
ms.assetid: 01966086-3142-450e-8210-3fd4cb33f591
ms.openlocfilehash: 61239d9b547be73a14618d41feeb9aeea9f8ded6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="afe4c-102">Пошаговое руководство. Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="afe4c-102">Walkthrough: Demonstrating Visual Inheritance</span></span>
<span data-ttu-id="afe4c-103">Визуальное наследование позволяет просматривать элементы управления в базовой форме и добавлять новые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="afe4c-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="afe4c-104">В этом пошаговом руководстве рассматривается создание базовой формы и ее компиляция  в библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="afe4c-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="afe4c-105">После этого данная библиотека классов импортируется в другой проект и создается новая форма, которая наследуется от базовой формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="afe4c-106">В этом пошаговом руководстве описаны следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="afe4c-106">During this walkthrough, you will learn how to:</span></span>  
  
-   <span data-ttu-id="afe4c-107">Создание проекта библиотеки классов, содержащей базовую форму.</span><span class="sxs-lookup"><span data-stu-id="afe4c-107">Create a class library project containing a base form.</span></span>  
  
-   <span data-ttu-id="afe4c-108">Добавление кнопки со свойствами, которые могут изменяться производными классами базовой формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-108">Add a button with properties that derived classes of the base form can modify.</span></span>  
  
-   <span data-ttu-id="afe4c-109">Добавление кнопки, которая не может изменяться наследниками базовой формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-109">Add a button that cannot be modified by inheritors of the base form.</span></span>  
  
-   <span data-ttu-id="afe4c-110">Создание проекта, содержащего форму, которая наследуется от `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="afe4c-110">Create a project containing a form that inherits from `BaseForm`.</span></span>  
  
 <span data-ttu-id="afe4c-111">В конечном счете в этом пошаговом руководстве показано различие между частным и защищенным элементами управления в производной форме.</span><span class="sxs-lookup"><span data-stu-id="afe4c-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afe4c-112">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="afe4c-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="afe4c-113">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="afe4c-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="afe4c-114">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="afe4c-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="afe4c-115">Не все элементы управления поддерживают визуальное наследование от базовой формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-115">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="afe4c-116">Не поддерживают сценарий, описанный в этом пошаговом руководстве, следующие элементы управления:</span><span class="sxs-lookup"><span data-stu-id="afe4c-116">The following controls do not support the scenario described in this walkthrough:</span></span>  
>   
>  <xref:System.Windows.Forms.WebBrowser>  
>   
>  <xref:System.Windows.Forms.ToolStrip>  
>   
>  <xref:System.Windows.Forms.ToolStripPanel>  
>   
>  <xref:System.Windows.Forms.TableLayoutPanel>  
>   
>  <xref:System.Windows.Forms.FlowLayoutPanel>  
>   
>  <xref:System.Windows.Forms.DataGridView>  
>   
>  <span data-ttu-id="afe4c-117">Эти элементы управления в производной форме всегда доступны только для чтения, независимо от используемых модификаторов (`private`, `protected` или `public`).</span><span class="sxs-lookup"><span data-stu-id="afe4c-117">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>  
  
## <a name="scenario-steps"></a><span data-ttu-id="afe4c-118">Шаги сценария</span><span class="sxs-lookup"><span data-stu-id="afe4c-118">Scenario Steps</span></span>  
 <span data-ttu-id="afe4c-119">Первым шагом является создание базовой формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-119">The first step is to create the base form.</span></span>  
  
#### <a name="to-create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="afe4c-120">Создание проекта библиотеки классов, содержащей базовую форму</span><span class="sxs-lookup"><span data-stu-id="afe4c-120">To create a class library project containing a base form</span></span>  
  
1.  <span data-ttu-id="afe4c-121">Из **файл** меню, выберите **New**, а затем **проекта** Открытие **новый проект** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="afe4c-121">From the **File** menu, choose **New**, and then **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="afe4c-122">Создание приложения Windows Forms с именем `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="afe4c-122">Create a Windows Forms application named `BaseFormLibrary`.</span></span>  
  
3.  <span data-ttu-id="afe4c-123">Чтобы создать библиотеку классов вместо стандартного приложения Windows Forms, в **обозревателе решений**, щелкните правой кнопкой мыши **BaseFormLibrary** узел проекта, а затем выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-123">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>  
  
4.  <span data-ttu-id="afe4c-124">В свойствах проекта измените **тип вывода** из **приложение Windows** для **библиотеки классов**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-124">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>  
  
5.  <span data-ttu-id="afe4c-125">Из **файл** меню, выберите **сохранить все** сохранить проект и файлы в папке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="afe4c-125">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>  
  
 <span data-ttu-id="afe4c-126">Следующие две процедуры выполняют добавление кнопок на базовую форму.</span><span class="sxs-lookup"><span data-stu-id="afe4c-126">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="afe4c-127">Чтобы продемонстрировать визуальное наследование, кнопкам будет заданы разные уровни доступа с помощью свойств `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="afe4c-127">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>  
  
#### <a name="to-add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="afe4c-128">Добавление кнопки, которую могут изменить наследники базовой формы</span><span class="sxs-lookup"><span data-stu-id="afe4c-128">To add a button that inheritors of the base form can modify</span></span>  
  
1.  <span data-ttu-id="afe4c-129">Откройте **Form1** в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="afe4c-129">Open **Form1** in the designer.</span></span>  
  
2.  <span data-ttu-id="afe4c-130">На **все формы Windows Forms** вкладке **элементов**, дважды щелкните **кнопку** Чтобы добавить кнопку в форму.</span><span class="sxs-lookup"><span data-stu-id="afe4c-130">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="afe4c-131">Измените положение и размер кнопки с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="afe4c-131">Use the mouse to position and resize the button.</span></span>  
  
3.  <span data-ttu-id="afe4c-132">В окне "Свойства" задайте следующие свойства кнопки.</span><span class="sxs-lookup"><span data-stu-id="afe4c-132">In the Properties window, set the following properties of the button:</span></span>  
  
    -   <span data-ttu-id="afe4c-133">Задать **текст** свойства **Say Hello**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-133">Set the **Text** property to **Say Hello**.</span></span>  
  
    -   <span data-ttu-id="afe4c-134">Задать **(имя)** свойства **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-134">Set the **(Name)** property to **btnProtected**.</span></span>  
  
    -   <span data-ttu-id="afe4c-135">Задать**модификаторы** свойства **Protected**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-135">Set the**Modifiers** property to **Protected**.</span></span> <span data-ttu-id="afe4c-136">Это позволяет формам, производным от **Form1** для изменения свойств **btnProtected**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-136">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>  
  
4.  <span data-ttu-id="afe4c-137">Дважды щелкните **Say Hello** кнопку, чтобы добавить обработчик событий для **щелкните** событий.</span><span class="sxs-lookup"><span data-stu-id="afe4c-137">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>  
  
5.  <span data-ttu-id="afe4c-138">Добавьте следующий код в обработчик событий:</span><span class="sxs-lookup"><span data-stu-id="afe4c-138">Add the following line of code to the event handler:</span></span>  
  
    ```vb  
    MessageBox.Show("Hello, World!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Hello, World!");  
    ```  
  
#### <a name="to-add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="afe4c-139">Добавление кнопки, которая не может изменяться наследующими объектами базовой формы</span><span class="sxs-lookup"><span data-stu-id="afe4c-139">To add a button that cannot be modified by inheritors of the base form</span></span>  
  
1.  <span data-ttu-id="afe4c-140">Перейдите в представление конструктора, щелкнув **Form1.vb [Design], Form1.cs [Design] или [Design] Form1.jsl** вкладка редактора кода или нажав клавишу F7.</span><span class="sxs-lookup"><span data-stu-id="afe4c-140">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>  
  
2.  <span data-ttu-id="afe4c-141">Добавьте вторую кнопку и задайте ее свойства следующим образом.</span><span class="sxs-lookup"><span data-stu-id="afe4c-141">Add a second button and set its properties as follows:</span></span>  
  
    -   <span data-ttu-id="afe4c-142">Задать **текст** свойства **свидания**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-142">Set the **Text** property to **Say Goodbye**.</span></span>  
  
    -   <span data-ttu-id="afe4c-143">Задать **(имя)** свойства **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-143">Set the **(Name)** property to **btnPrivate**.</span></span>  
  
    -   <span data-ttu-id="afe4c-144">Задать **модификаторы** свойства **частного**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-144">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="afe4c-145">Это не позволяет формам, производным от **Form1** для изменения свойств **btnPrivate**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-145">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>  
  
3.  <span data-ttu-id="afe4c-146">Дважды щелкните **свидания** кнопку, чтобы добавить обработчик событий для **щелкните** событий.</span><span class="sxs-lookup"><span data-stu-id="afe4c-146">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="afe4c-147">Добавьте следующую строку кода в процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="afe4c-147">Place the following line of code in the event procedure:</span></span>  
  
    ```vb  
    MessageBox.Show("Goodbye!")  
    ```  
  
    ```csharp  
    MessageBox.Show("Goodbye!");  
    ```  
  
4.  <span data-ttu-id="afe4c-148">Из **построения** меню, выберите **собрать библиотеку BaseForm** в сборку библиотеки классов.</span><span class="sxs-lookup"><span data-stu-id="afe4c-148">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>  
  
     <span data-ttu-id="afe4c-149">После сборки библиотеки можно создать новый проект, наследуемый от только что созданной формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-149">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>  
  
#### <a name="to-create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="afe4c-150">Создание проекта, содержащего форму, которая наследуется от базовой формы</span><span class="sxs-lookup"><span data-stu-id="afe4c-150">To create a project containing a form that inherits from the base form</span></span>  
  
1.  <span data-ttu-id="afe4c-151">Из **файл** меню, выберите **добавить** и затем **новый проект** Открытие **Добавление нового проекта** диалоговое окно.</span><span class="sxs-lookup"><span data-stu-id="afe4c-151">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="afe4c-152">Создание приложения Windows Forms с именем `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="afe4c-152">Create a Windows Forms application named `InheritanceTest`.</span></span>  
  
#### <a name="to-add-an-inherited-form"></a><span data-ttu-id="afe4c-153">Добавление производной формы</span><span class="sxs-lookup"><span data-stu-id="afe4c-153">To add an inherited form</span></span>  
  
1.  <span data-ttu-id="afe4c-154">В **обозревателе решений**, щелкните правой кнопкой мыши **InheritanceTest** проекта, выберите **добавить**, а затем выберите**новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-154">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select**New Item**.</span></span>  
  
2.  <span data-ttu-id="afe4c-155">В **Добавление нового элемента** выберите **Windows Forms** категории (если имеется список категорий) и выберите **производная форма** шаблона.</span><span class="sxs-lookup"><span data-stu-id="afe4c-155">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>  
  
3.  <span data-ttu-id="afe4c-156">Оставьте имя по умолчанию `Form2` и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-156">Leave the default name of `Form2` and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="afe4c-157">В **Выбор компонентов для наследования** выберите **Form1** из **BaseFormLibrary** проект как форма наследование, и нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="afe4c-157">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>  
  
     <span data-ttu-id="afe4c-158">Это создает форму в **InheritanceTest** проект, который является производным от формы в **BaseFormLibrary**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-158">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>  
  
5.  <span data-ttu-id="afe4c-159">Откройте производную форму (**Form2**) в конструкторе, дважды щелкнув ее, если он еще не открыт.</span><span class="sxs-lookup"><span data-stu-id="afe4c-159">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>  
  
     <span data-ttu-id="afe4c-160">В конструкторе унаследованные кнопки имеют символ (![экрана VisualBasicInheritanceSymbol](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) в верхнем углу, указывающее, они унаследованы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-160">In the designer, the inherited buttons have a symbol (![VisualBasicInheritanceSymbol screenshot](../../../../docs/framework/winforms/advanced/media/vbinheritanceglyph.gif "vbInheritanceGlyph")) in their upper corner, indicating they are inherited.</span></span>  
  
6.  <span data-ttu-id="afe4c-161">Выберите **Say Hello** кнопку и понаблюдайте за маркеры изменения размера.</span><span class="sxs-lookup"><span data-stu-id="afe4c-161">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="afe4c-162">Так как данная кнопка защищена, то наследники могут ее перемещать, изменять размер, название и вносить другие изменения.</span><span class="sxs-lookup"><span data-stu-id="afe4c-162">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>  
  
7.  <span data-ttu-id="afe4c-163">Выберите частную **свидания** кнопки и обратите внимание, что он не имеет маркеров изменения размера.</span><span class="sxs-lookup"><span data-stu-id="afe4c-163">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="afe4c-164">Кроме того, в **свойства** свойства этой кнопки отображены серым цветом, чтобы указать, их нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="afe4c-164">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>  
  
8.  <span data-ttu-id="afe4c-165">Если вы используете Visual C#:</span><span class="sxs-lookup"><span data-stu-id="afe4c-165">If you are using Visual C#:</span></span>  
  
    1.  <span data-ttu-id="afe4c-166">В **обозревателе решений**, щелкните правой кнопкой мыши **Form1** в **InheritanceTest** проекта, а затем выберите **удалить**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-166">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="afe4c-167">В появившемся диалоговом окне выберите **ОК** для подтверждения удаления.</span><span class="sxs-lookup"><span data-stu-id="afe4c-167">In the message box that appears, click **OK** to confirm the deletion.</span></span>  
  
    2.  <span data-ttu-id="afe4c-168">Откройте файл Program.cs и измените строку `Application.Run(new Form1());` на `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="afe4c-168">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>  
  
9. <span data-ttu-id="afe4c-169">В **обозревателе решений**, щелкните правой кнопкой мыши **InheritanceTest** проект и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-169">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>  
  
10. <span data-ttu-id="afe4c-170">В **обозревателе решений**, щелкните правой кнопкой мыши **InheritanceTest** проект и выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-170">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>  
  
11. <span data-ttu-id="afe4c-171">В **InheritanceTest** страницы свойств, задайте **автоматически запускаемый объект** наследуемую форму (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="afe4c-171">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>  
  
12. <span data-ttu-id="afe4c-172">Нажмите клавишу F5 для запуска приложения и понаблюдайте за поведением производной формы.</span><span class="sxs-lookup"><span data-stu-id="afe4c-172">Press F5 to run the application, and observe the behavior of the inherited form.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="afe4c-173">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="afe4c-173">Next Steps</span></span>  
 <span data-ttu-id="afe4c-174">Наследование для пользовательских элементов управления работает таким же образом.</span><span class="sxs-lookup"><span data-stu-id="afe4c-174">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="afe4c-175">Откройте новый проект библиотеки классов и добавьте пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="afe4c-175">Open a new class library project and add a user control.</span></span> <span data-ttu-id="afe4c-176">Поместите на него составные элементы управления и скомпилируйте проект.</span><span class="sxs-lookup"><span data-stu-id="afe4c-176">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="afe4c-177">Откройте еще один новый проект библиотеки классов и добавьте ссылку на скомпилированную библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="afe4c-177">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="afe4c-178">Также попытайтесь добавить наследуемый элемент управления (через **добавить новые элементы** диалоговое окно «») в проект и с помощью **Выбор компонентов для наследования**.</span><span class="sxs-lookup"><span data-stu-id="afe4c-178">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="afe4c-179">Добавьте пользовательский элемент управления и измените `Inherits` (`:` в Visual C#) инструкции.</span><span class="sxs-lookup"><span data-stu-id="afe4c-179">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="afe4c-180">Дополнительные сведения см. в разделе [как: наследование форм Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="afe4c-180">For more information, see [How to: Inherit Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afe4c-181">См. также</span><span class="sxs-lookup"><span data-stu-id="afe4c-181">See Also</span></span>  
 [<span data-ttu-id="afe4c-182">Практическое руководство. Наследование форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afe4c-182">How to: Inherit Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [<span data-ttu-id="afe4c-183">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afe4c-183">Windows Forms Visual Inheritance</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)  
 [<span data-ttu-id="afe4c-184">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="afe4c-184">Windows Forms</span></span>](../../../../docs/framework/winforms/index.md)
