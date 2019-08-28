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
ms.openlocfilehash: 32df98852b28963ffb748895156f7d9977c74b92
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046140"
---
# <a name="walkthrough-demonstrating-visual-inheritance"></a><span data-ttu-id="bcefc-102">Пошаговое руководство. Демонстрация визуального наследования</span><span class="sxs-lookup"><span data-stu-id="bcefc-102">Walkthrough: Demonstrating Visual Inheritance</span></span>

<span data-ttu-id="bcefc-103">Визуальное наследование позволяет просматривать элементы управления в базовой форме и добавлять новые элементы управления.</span><span class="sxs-lookup"><span data-stu-id="bcefc-103">Visual inheritance enables you to see the controls on the base form and to add new controls.</span></span> <span data-ttu-id="bcefc-104">В этом пошаговом руководстве рассматривается создание базовой формы и ее компиляция  в библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="bcefc-104">In this walkthrough you will create a base form and compile it into a class library.</span></span> <span data-ttu-id="bcefc-105">После этого данная библиотека классов импортируется в другой проект и создается новая форма, которая наследуется от базовой формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-105">You will import this class library into another project and create a new form that inherits from the base form.</span></span> <span data-ttu-id="bcefc-106">В этом пошаговом руководстве описаны следующие процедуры.</span><span class="sxs-lookup"><span data-stu-id="bcefc-106">During this walkthrough, you will learn how to:</span></span>

- <span data-ttu-id="bcefc-107">Создание проекта библиотеки классов, содержащей базовую форму.</span><span class="sxs-lookup"><span data-stu-id="bcefc-107">Create a class library project containing a base form.</span></span>

- <span data-ttu-id="bcefc-108">Добавление кнопки со свойствами, которые могут изменяться производными классами базовой формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-108">Add a button with properties that derived classes of the base form can modify.</span></span>

- <span data-ttu-id="bcefc-109">Добавление кнопки, которая не может изменяться наследниками базовой формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-109">Add a button that cannot be modified by inheritors of the base form.</span></span>

- <span data-ttu-id="bcefc-110">Создание проекта, содержащего форму, которая наследуется от `BaseForm`.</span><span class="sxs-lookup"><span data-stu-id="bcefc-110">Create a project containing a form that inherits from `BaseForm`.</span></span>

<span data-ttu-id="bcefc-111">В конечном счете в этом пошаговом руководстве показано различие между частным и защищенным элементами управления в производной форме.</span><span class="sxs-lookup"><span data-stu-id="bcefc-111">Ultimately, this walkthrough will demonstrate the difference between private and protected controls on an inherited form.</span></span>

> [!CAUTION]
> <span data-ttu-id="bcefc-112">Не все элементы управления поддерживают визуальное наследование от базовой формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-112">Not all controls support visual inheritance from a base form.</span></span> <span data-ttu-id="bcefc-113">Не поддерживают сценарий, описанный в этом пошаговом руководстве, следующие элементы управления:</span><span class="sxs-lookup"><span data-stu-id="bcefc-113">The following controls do not support the scenario described in this walkthrough:</span></span>
>
> - <xref:System.Windows.Forms.WebBrowser>
>
> - <xref:System.Windows.Forms.ToolStrip>
>
> - <xref:System.Windows.Forms.ToolStripPanel>
>
> - <xref:System.Windows.Forms.TableLayoutPanel>
>
> - <xref:System.Windows.Forms.FlowLayoutPanel>
>
> - <xref:System.Windows.Forms.DataGridView>
>
> <span data-ttu-id="bcefc-114">Эти элементы управления в производной форме всегда доступны только для чтения, независимо от используемых модификаторов (`private`, `protected` или `public`).</span><span class="sxs-lookup"><span data-stu-id="bcefc-114">These controls in the inherited form are always read-only regardless of the modifiers you use (`private`, `protected`, or `public`).</span></span>

## <a name="create-a-class-library-project-containing-a-base-form"></a><span data-ttu-id="bcefc-115">Создание проекта библиотеки классов, содержащего базовую форму</span><span class="sxs-lookup"><span data-stu-id="bcefc-115">Create a class library project containing a base form</span></span>

1. <span data-ttu-id="bcefc-116">В Visual Studio в меню **файл** выберите пункт **создать** > **проект** , чтобы открыть диалоговое окно **Создание проекта** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-116">In Visual Studio, from the **File** menu, choose **New** > **Project** to open the **New Project** dialog box.</span></span>

2. <span data-ttu-id="bcefc-117">Создайте приложение Windows Forms с именем `BaseFormLibrary`.</span><span class="sxs-lookup"><span data-stu-id="bcefc-117">Create a Windows Forms application named `BaseFormLibrary`.</span></span>

3. <span data-ttu-id="bcefc-118">Чтобы создать библиотеку классов вместо стандартного Windows Forms приложения, в **Обозреватель решений**щелкните правой кнопкой мыши узел проекта **басеформлибрари** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-118">To create a class library instead of a standard Windows Forms application, in **Solution Explorer**, right-click the **BaseFormLibrary** project node and then select **Properties**.</span></span>

4. <span data-ttu-id="bcefc-119">В свойствах проекта измените **тип выходных данных** с **приложения Windows** на **библиотеку классов**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-119">In the properties for the project, change the **Output type** from **Windows Application** to **Class Library**.</span></span>

5. <span data-ttu-id="bcefc-120">В меню **файл** выберите **сохранить все** , чтобы сохранить проект и файлы в расположение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bcefc-120">From the **File** menu, choose **Save All** to save the project and files to the default location.</span></span>

<span data-ttu-id="bcefc-121">Следующие две процедуры выполняют добавление кнопок на базовую форму.</span><span class="sxs-lookup"><span data-stu-id="bcefc-121">The next two procedures add buttons to the base form.</span></span> <span data-ttu-id="bcefc-122">Чтобы продемонстрировать визуальное наследование, кнопкам будет заданы разные уровни доступа с помощью свойств `Modifiers`.</span><span class="sxs-lookup"><span data-stu-id="bcefc-122">To demonstrate visual inheritance, you will give the buttons different access levels by setting their `Modifiers` properties.</span></span>

## <a name="add-a-button-that-inheritors-of-the-base-form-can-modify"></a><span data-ttu-id="bcefc-123">Добавление кнопки, которая может быть изменена наследниками базовой формы</span><span class="sxs-lookup"><span data-stu-id="bcefc-123">Add a button that inheritors of the base form can modify</span></span>

1. <span data-ttu-id="bcefc-124">Откройте **Form1** в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="bcefc-124">Open **Form1** in the designer.</span></span>

2. <span data-ttu-id="bcefc-125">На вкладке **все Windows Forms** **панели элементов**дважды щелкните кнопку, чтобы добавить кнопку в форму.</span><span class="sxs-lookup"><span data-stu-id="bcefc-125">On the **All Windows Forms** tab of the **Toolbox**, double-click **Button** to add a button to the form.</span></span> <span data-ttu-id="bcefc-126">Измените положение и размер кнопки с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="bcefc-126">Use the mouse to position and resize the button.</span></span>

3. <span data-ttu-id="bcefc-127">В окне "Свойства" задайте следующие свойства кнопки.</span><span class="sxs-lookup"><span data-stu-id="bcefc-127">In the Properties window, set the following properties of the button:</span></span>

    - <span data-ttu-id="bcefc-128">Присвойте свойству **Text** значение **Привет**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-128">Set the **Text** property to **Say Hello**.</span></span>

    - <span data-ttu-id="bcefc-129">Присвойте свойству **(Name)** значение **бтнпротектед**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-129">Set the **(Name)** property to **btnProtected**.</span></span>

    - <span data-ttu-id="bcefc-130">Присвойте свойству **Modifiers** значение **protected**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-130">Set the **Modifiers** property to **Protected**.</span></span> <span data-ttu-id="bcefc-131">Это позволяет формам, наследующим от **Form1** , изменять свойства **бтнпротектед**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-131">This makes it possible for forms that inherit from **Form1** to modify the properties of **btnProtected**.</span></span>

4. <span data-ttu-id="bcefc-132">Дважды щелкните кнопку " **Привет!** ", чтобы добавить обработчик событий для события **щелчка** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-132">Double-click the **Say Hello** button to add an event handler for the **Click** event.</span></span>

5. <span data-ttu-id="bcefc-133">Добавьте следующий код в обработчик событий:</span><span class="sxs-lookup"><span data-stu-id="bcefc-133">Add the following line of code to the event handler:</span></span>

    ```vb
    MessageBox.Show("Hello, World!")
    ```

    ```csharp
    MessageBox.Show("Hello, World!");
    ```

## <a name="add-a-button-that-cannot-be-modified-by-inheritors-of-the-base-form"></a><span data-ttu-id="bcefc-134">Добавление кнопки, которая не может быть изменена наследниками базовой формы</span><span class="sxs-lookup"><span data-stu-id="bcefc-134">Add a button that cannot be modified by inheritors of the base form</span></span>

1. <span data-ttu-id="bcefc-135">Переключитесь в режим конструктора, щелкнув вкладку **Form1. vb [Design], Form1.cs [Design] или Form1. ЖСЛ [Design]** над редактором кода или нажав клавишу F7.</span><span class="sxs-lookup"><span data-stu-id="bcefc-135">Switch to design view by clicking the **Form1.vb [Design], Form1.cs [Design], or Form1.jsl [Design]** tab above the code editor, or by pressing F7.</span></span>

2. <span data-ttu-id="bcefc-136">Добавьте вторую кнопку и задайте ее свойства следующим образом.</span><span class="sxs-lookup"><span data-stu-id="bcefc-136">Add a second button and set its properties as follows:</span></span>

    - <span data-ttu-id="bcefc-137">Присвойте свойству **Text** значение « **пока**».</span><span class="sxs-lookup"><span data-stu-id="bcefc-137">Set the **Text** property to **Say Goodbye**.</span></span>

    - <span data-ttu-id="bcefc-138">Присвойте свойству **(Name)** значение **бтнпривате**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-138">Set the **(Name)** property to **btnPrivate**.</span></span>

    - <span data-ttu-id="bcefc-139">Присвойте свойству **Modifiers** значение **Private**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-139">Set the **Modifiers** property to **Private**.</span></span> <span data-ttu-id="bcefc-140">Это делает невозможным изменение свойств **бтнпривате**с помощью форм, наследующих от **Form1** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-140">This makes it impossible for forms that inherit from **Form1** to modify the properties of **btnPrivate**.</span></span>

3. <span data-ttu-id="bcefc-141">Дважды щелкните кнопку « о продолжении», чтобы добавить обработчик событий для события **щелчка** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-141">Double-click the **Say Goodbye** button to add an event handler for the **Click** event.</span></span> <span data-ttu-id="bcefc-142">Добавьте следующую строку кода в процедуру обработки события.</span><span class="sxs-lookup"><span data-stu-id="bcefc-142">Place the following line of code in the event procedure:</span></span>

    ```vb
    MessageBox.Show("Goodbye!")
    ```

    ```csharp
    MessageBox.Show("Goodbye!");
    ```

4. <span data-ttu-id="bcefc-143">В меню **Сборка** выберите **Build басеформ Library** (сборка библиотеки), чтобы создать библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="bcefc-143">From the **Build** menu, choose **Build BaseForm Library** to build the class library.</span></span>

     <span data-ttu-id="bcefc-144">После сборки библиотеки можно создать новый проект, наследуемый от только что созданной формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-144">Once the library is built, you can create a new project that inherits from the form you just created.</span></span>

## <a name="create-a-project-containing-a-form-that-inherits-from-the-base-form"></a><span data-ttu-id="bcefc-145">Создание проекта, содержащего форму, которая наследуется от базовой формы</span><span class="sxs-lookup"><span data-stu-id="bcefc-145">Create a project containing a form that inherits from the base form</span></span>

1. <span data-ttu-id="bcefc-146">В меню **файл** выберите **Добавить** , а затем **Новый проект** , чтобы открыть диалоговое окно **Добавление нового проекта** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-146">From the **File** menu, choose **Add** and then **New Project** to open the **Add New Project** dialog box.</span></span>

2. <span data-ttu-id="bcefc-147">Создайте приложение Windows Forms с именем `InheritanceTest`.</span><span class="sxs-lookup"><span data-stu-id="bcefc-147">Create a Windows Forms application named `InheritanceTest`.</span></span>

## <a name="add-an-inherited-form"></a><span data-ttu-id="bcefc-148">Добавление наследуемой формы</span><span class="sxs-lookup"><span data-stu-id="bcefc-148">Add an inherited form</span></span>

1. <span data-ttu-id="bcefc-149">В **Обозреватель решений**щелкните правой кнопкой мыши проект **InheritanceTest** , выберите **Добавить**, а затем щелкните **новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-149">In **Solution Explorer**, right-click the **InheritanceTest** project, select **Add**, and then select **New Item**.</span></span>

2. <span data-ttu-id="bcefc-150">В диалоговом окне **Добавление нового элемента** выберите категорию **Windows Forms** (если имеется список категорий), а затем выберите производный шаблон **формы** .</span><span class="sxs-lookup"><span data-stu-id="bcefc-150">In the **Add New Item** dialog box, select the **Windows Forms** category (if you have a list of categories) and then select the **Inherited Form** template.</span></span>

3. <span data-ttu-id="bcefc-151">Оставьте имя `Form2` по умолчанию и нажмите кнопку **добавить**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-151">Leave the default name of `Form2` and then click **Add**.</span></span>

4. <span data-ttu-id="bcefc-152">В диалоговом окне **Выбор наследования** выберите **Form1** из проекта **басеформлибрари** в качестве формы для наследования и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-152">In the **Inheritance Picker** dialog box, select **Form1** from the **BaseFormLibrary** project as the form to inherit from and click **OK**.</span></span>

     <span data-ttu-id="bcefc-153">При этом в проекте **InheritanceTest** создается форма, производная от формы в **басеформлибрари**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-153">This creates a form in the **InheritanceTest** project that derives from the form in **BaseFormLibrary**.</span></span>

5. <span data-ttu-id="bcefc-154">Откройте наследуемую форму (**Form2**) в конструкторе, дважды щелкнув ее, если она еще не открыта.</span><span class="sxs-lookup"><span data-stu-id="bcefc-154">Open the inherited form (**Form2**) in the designer by double-clicking it, if it is not already open.</span></span>

    <span data-ttu-id="bcefc-155">В конструкторе наследуемые кнопки имеют символ (</span><span class="sxs-lookup"><span data-stu-id="bcefc-155">In the designer, the inherited buttons have a symbol (</span></span>![Снимок экрана: символ наследования Visual Basic.](./media/walkthrough-demonstrating-visual-inheritance/visual-basic-inheritance-glyph.gif)<span data-ttu-id="bcefc-157">) в верхнем углу, указывая, что они унаследованы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-157">) in their upper corner, indicating they are inherited.</span></span>

6. <span data-ttu-id="bcefc-158">Нажмите кнопку **Привет** , чтобы увидеть маркеры изменения размера.</span><span class="sxs-lookup"><span data-stu-id="bcefc-158">Select the **Say Hello** button and observe the resize handles.</span></span> <span data-ttu-id="bcefc-159">Так как данная кнопка защищена, то наследники могут ее перемещать, изменять размер, название и вносить другие изменения.</span><span class="sxs-lookup"><span data-stu-id="bcefc-159">Because this button is protected, the inheritors can move it, resize it, change its caption, and make other modifications.</span></span>

7. <span data-ttu-id="bcefc-160">Выберите закрытую кнопку и обратите внимание, что у нее нет маркеров изменения размера.</span><span class="sxs-lookup"><span data-stu-id="bcefc-160">Select the private **Say Goodbye** button, and notice that it does not have resize handles.</span></span> <span data-ttu-id="bcefc-161">Кроме того, в окне **Свойства** свойства этой кнопки отображаются серым цветом, что означает, что их нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="bcefc-161">Additionally, in the **Properties** window, the properties of this button are grayed to indicate they cannot be modified.</span></span>

8. <span data-ttu-id="bcefc-162">При использовании визуального элемента C#:</span><span class="sxs-lookup"><span data-stu-id="bcefc-162">If you are using Visual C#:</span></span>

    1. <span data-ttu-id="bcefc-163">В **Обозреватель решений**щелкните правой кнопкой мыши **форму Form1** в проекте **InheritanceTest** и выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-163">In **Solution Explorer**, right-click **Form1** in the **InheritanceTest** project and then choose **Delete**.</span></span> <span data-ttu-id="bcefc-164">В появившемся окне сообщения нажмите кнопку **ОК** , чтобы подтвердить удаление.</span><span class="sxs-lookup"><span data-stu-id="bcefc-164">In the message box that appears, click **OK** to confirm the deletion.</span></span>

    2. <span data-ttu-id="bcefc-165">Откройте файл Program.cs и измените строку `Application.Run(new Form1());` на `Application.Run(new Form2());`.</span><span class="sxs-lookup"><span data-stu-id="bcefc-165">Open the Program.cs file and change the line `Application.Run(new Form1());` to `Application.Run(new Form2());`.</span></span>

9. <span data-ttu-id="bcefc-166">В **Обозреватель решений**щелкните правой кнопкой мыши проект **InheritanceTest** и выберите **Назначить запускаемым проектом**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-166">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Set As Startup Project**.</span></span>

10. <span data-ttu-id="bcefc-167">В **Обозреватель решений**щелкните правой кнопкой мыши проект **InheritanceTest** и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-167">In **Solution Explorer**, right-click the **InheritanceTest** project and select **Properties**.</span></span>

11. <span data-ttu-id="bcefc-168">На страницах свойств **InheritanceTest** установите **начальный объект** в качестве наследуемой формы (**Form2**).</span><span class="sxs-lookup"><span data-stu-id="bcefc-168">In the **InheritanceTest** property pages, set the **Startup object** to be the inherited form (**Form2**).</span></span>

12. <span data-ttu-id="bcefc-169">Нажмите клавишу **F5** , чтобы запустить приложение, и обратите внимание на поведение наследуемой формы.</span><span class="sxs-lookup"><span data-stu-id="bcefc-169">Press **F5** to run the application, and observe the behavior of the inherited form.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bcefc-170">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="bcefc-170">Next steps</span></span>

<span data-ttu-id="bcefc-171">Наследование для пользовательских элементов управления работает таким же образом.</span><span class="sxs-lookup"><span data-stu-id="bcefc-171">Inheritance for user controls works in much the same way.</span></span> <span data-ttu-id="bcefc-172">Откройте новый проект библиотеки классов и добавьте пользовательский элемент управления.</span><span class="sxs-lookup"><span data-stu-id="bcefc-172">Open a new class library project and add a user control.</span></span> <span data-ttu-id="bcefc-173">Поместите на него составные элементы управления и скомпилируйте проект.</span><span class="sxs-lookup"><span data-stu-id="bcefc-173">Place constituent controls on it and compile the project.</span></span> <span data-ttu-id="bcefc-174">Откройте еще один новый проект библиотеки классов и добавьте ссылку на скомпилированную библиотеку классов.</span><span class="sxs-lookup"><span data-stu-id="bcefc-174">Open another new class library project and add a reference to the compiled class library.</span></span> <span data-ttu-id="bcefc-175">Кроме того, попробуйте добавить наследуемый элемент управления (с помощью диалогового окна " **Добавление новых элементов** ") в проект и с помощью **средства выбора наследования**.</span><span class="sxs-lookup"><span data-stu-id="bcefc-175">Also, try adding an inherited control (through the **Add New Items** dialog box) to the project and using the **Inheritance Picker**.</span></span> <span data-ttu-id="bcefc-176">Добавьте пользовательский элемент управления и измените `Inherits` оператор (`:` в Visual C#).</span><span class="sxs-lookup"><span data-stu-id="bcefc-176">Add a user control, and change the `Inherits` (`:` in Visual C#) statement.</span></span> <span data-ttu-id="bcefc-177">Дополнительные сведения см. в разделе [Практическое руководство. Наследовать](how-to-inherit-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bcefc-177">For more information, see [How to: Inherit Windows Forms](how-to-inherit-windows-forms.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcefc-178">См. также</span><span class="sxs-lookup"><span data-stu-id="bcefc-178">See also</span></span>

- [<span data-ttu-id="bcefc-179">Практическое руководство. Наследовать Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bcefc-179">How to: Inherit Windows Forms</span></span>](how-to-inherit-windows-forms.md)
- [<span data-ttu-id="bcefc-180">Визуальное наследование в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bcefc-180">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
- [<span data-ttu-id="bcefc-181">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bcefc-181">Windows Forms</span></span>](../index.md)
