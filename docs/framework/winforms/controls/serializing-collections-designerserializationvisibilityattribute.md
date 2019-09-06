---
title: Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- serialization [Windows Forms], collections
- standard types [Windows Forms], collections
- collections [Windows Forms], serializing
- collections [Windows Forms], standard types
ms.assetid: 020c9df4-fdc5-4dae-815a-963ecae5668c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4fd1f1dc0c2c0ad9ae2009ed592e48b8eeaa2783
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2019
ms.locfileid: "70373684"
---
# <a name="walkthrough-serialize-collections-of-standard-types"></a><span data-ttu-id="7334c-102">Пошаговое руководство. Сериализация коллекций стандартных типов</span><span class="sxs-lookup"><span data-stu-id="7334c-102">Walkthrough: Serialize collections of standard types</span></span>

<span data-ttu-id="7334c-103">Иногда пользовательские элементы управления предоставляют коллекцию в качестве свойства.</span><span class="sxs-lookup"><span data-stu-id="7334c-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="7334c-104">В этом пошаговом руководстве показано <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> , как использовать класс для управления сериализацией коллекции во время разработки.</span><span class="sxs-lookup"><span data-stu-id="7334c-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="7334c-105"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Применение значения к свойству коллекции гарантирует, что свойство будет сериализовано.</span><span class="sxs-lookup"><span data-stu-id="7334c-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="7334c-106">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Сериализация коллекций стандартных типов с помощью Десигнерсериализатионвисибилитяттрибуте](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="7334c-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7334c-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="7334c-107">Prerequisites</span></span>

<span data-ttu-id="7334c-108">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="7334c-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="7334c-109">Создание элемента управления с сериализуемой коллекцией</span><span class="sxs-lookup"><span data-stu-id="7334c-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="7334c-110">Первым шагом является создание элемента управления с сериализуемой коллекцией в качестве свойства.</span><span class="sxs-lookup"><span data-stu-id="7334c-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="7334c-111">Содержимое этой коллекции можно изменить с помощью **редактора коллекции**, доступ к которому можно получить из окна **свойства** .</span><span class="sxs-lookup"><span data-stu-id="7334c-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="7334c-112">В Visual Studio создайте проект библиотеки элементов управления Windows и назовите его **сериализатиондемоконтроллиб**.</span><span class="sxs-lookup"><span data-stu-id="7334c-112">In Visual Studio, create a Windows Control Library project, and name it **SerializationDemoControlLib**.</span></span>

2. <span data-ttu-id="7334c-113">Переименовать `UserControl1` в `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="7334c-113">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="7334c-114">Дополнительные сведения см. [в разделе Переименование символа кода с помощью рефакторинга](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="7334c-114">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="7334c-115">В окне **Свойства** присвойте <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> свойству значение **10**.</span><span class="sxs-lookup"><span data-stu-id="7334c-115">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to **10**.</span></span>

4. <span data-ttu-id="7334c-116">Поместите элемент управления в `SerializationDemoControl`. <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="7334c-116">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="7334c-117">Выберите элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="7334c-117">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="7334c-118">В окне **Свойства** задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="7334c-118">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="7334c-119">Свойство.</span><span class="sxs-lookup"><span data-stu-id="7334c-119">Property</span></span>|<span data-ttu-id="7334c-120">Измените на</span><span class="sxs-lookup"><span data-stu-id="7334c-120">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="7334c-121">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="7334c-121">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="7334c-122">**Закрепить**</span><span class="sxs-lookup"><span data-stu-id="7334c-122">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="7334c-123">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="7334c-123">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="7334c-124">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="7334c-124">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="7334c-125">В **редакторе кода**объявите поле массива строк с именем `stringsValue` в. `SerializationDemoControl`</span><span class="sxs-lookup"><span data-stu-id="7334c-125">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="7334c-126">`Strings` Определите свойство`SerializationDemoControl`для.</span><span class="sxs-lookup"><span data-stu-id="7334c-126">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7334c-127"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Значение используется для включения сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="7334c-127">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="7334c-128">Нажмите клавишу **F5** , чтобы выполнить сборку проекта и запустить элемент управления в **тестовом контейнере UserControl**.</span><span class="sxs-lookup"><span data-stu-id="7334c-128">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="7334c-129">Найдите свойство **Strings** в <xref:System.Windows.Forms.PropertyGrid> **контейнере тестов пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="7334c-129">Find the **Strings** property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="7334c-130">Выберите свойство **Strings** , а затем нажмите кнопку с многоточием![(...) в окно свойств в Visual Studio](./media/visual-studio-ellipsis-button.png)), чтобы открыть **Редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="7334c-130">Select the **Strings** property, then select the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="7334c-131">Введите несколько строк в **редакторе коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="7334c-131">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="7334c-132">Разделите их, нажав клавишу **Ввод** в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="7334c-132">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="7334c-133">После завершения ввода строк нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="7334c-133">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7334c-134">Введенные строки отображаются в <xref:System.Windows.Forms.TextBox>. `SerializationDemoControl`</span><span class="sxs-lookup"><span data-stu-id="7334c-134">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serialize-a-collection-property"></a><span data-ttu-id="7334c-135">Сериализация свойства коллекции</span><span class="sxs-lookup"><span data-stu-id="7334c-135">Serialize a collection property</span></span>

<span data-ttu-id="7334c-136">Чтобы проверить поведение сериализации элемента управления, необходимо поместить его в форму и изменить содержимое коллекции с помощью **редактора коллекции**.</span><span class="sxs-lookup"><span data-stu-id="7334c-136">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="7334c-137">Состояние сериализованной коллекции можно просмотреть, просмотрев специальный файл конструктора, в который **конструктор Windows Forms** выдает код.</span><span class="sxs-lookup"><span data-stu-id="7334c-137">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

1. <span data-ttu-id="7334c-138">Добавьте в решение проект приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="7334c-138">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="7334c-139">Задайте для проекта имя `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="7334c-139">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="7334c-140">На **панели элементов**найдите вкладку с именем **компоненты сериализатиондемоконтроллиб**.</span><span class="sxs-lookup"><span data-stu-id="7334c-140">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="7334c-141">На этой вкладке можно найти `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="7334c-141">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="7334c-142">Дополнительные сведения см. в разделе [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="7334c-142">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="7334c-143">`SerializationDemoControl` Разместите в форме.</span><span class="sxs-lookup"><span data-stu-id="7334c-143">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="7334c-144">Найдите свойство в окне **Свойства.** `Strings`</span><span class="sxs-lookup"><span data-stu-id="7334c-144">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="7334c-145">Щелкните свойство, а затем нажмите кнопку с многоточием![(...) в окно свойств кнопки Visual Studio.](./media/visual-studio-ellipsis-button.png)), чтобы открыть **Редактор коллекции строк.** `Strings`</span><span class="sxs-lookup"><span data-stu-id="7334c-145">Click the `Strings` property, then click the ellipsis (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="7334c-146">Введите несколько строк в **редакторе коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="7334c-146">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="7334c-147">Разделите их, нажав клавишу **Ввод** в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="7334c-147">Separate them by pressing **Enter** at the end of each string.</span></span> <span data-ttu-id="7334c-148">После завершения ввода строк нажмите кнопку **ОК** .</span><span class="sxs-lookup"><span data-stu-id="7334c-148">Click **OK** when you are finished entering strings.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7334c-149">Введенные строки отображаются в <xref:System.Windows.Forms.TextBox>. `SerializationDemoControl`</span><span class="sxs-lookup"><span data-stu-id="7334c-149">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

6. <span data-ttu-id="7334c-150">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="7334c-150">In **Solution Explorer**, click the **Show All Files** button.</span></span>

7. <span data-ttu-id="7334c-151">Откройте узел **Form1** .</span><span class="sxs-lookup"><span data-stu-id="7334c-151">Open the **Form1** node.</span></span> <span data-ttu-id="7334c-152">Под ним находится файл с именем **Form1.Designer.CS** или **Form1. Designer. vb**.</span><span class="sxs-lookup"><span data-stu-id="7334c-152">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="7334c-153">Это файл, в который **конструктор Windows Forms** выдает код, представляющий состояние времени разработки формы и ее дочерних элементов управления.</span><span class="sxs-lookup"><span data-stu-id="7334c-153">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="7334c-154">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="7334c-154">Open this file in the **Code Editor**.</span></span>

8. <span data-ttu-id="7334c-155">Откройте область код, **созданный конструктором форм Windows Forms** , и найдите раздел с меткой **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="7334c-155">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="7334c-156">Под этой меткой находится код, представляющий сериализованное состояние элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7334c-156">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="7334c-157">Строки, введенные на шаге 5, отображаются в назначении для `Strings` свойства.</span><span class="sxs-lookup"><span data-stu-id="7334c-157">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="7334c-158">В следующих примерах кода C# в и Visual Basic показан код, аналогичный тому, что вы видите при вводе строк "Red", "оранжевый" и "желтый".</span><span class="sxs-lookup"><span data-stu-id="7334c-158">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

9. <span data-ttu-id="7334c-159">В **редакторе кода**измените значение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> `Strings` свойства <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>на.</span><span class="sxs-lookup"><span data-stu-id="7334c-159">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

10. <span data-ttu-id="7334c-160">Перестройте решение и повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="7334c-160">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="7334c-161">В этом случае **конструктор Windows Forms** не выдает никакого назначения `Strings` свойству.</span><span class="sxs-lookup"><span data-stu-id="7334c-161">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7334c-162">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="7334c-162">Next steps</span></span>

<span data-ttu-id="7334c-163">Когда вы узнаете, как сериализовать коллекцию стандартных типов, рассмотрите возможность интеграции пользовательских элементов управления более глубоко в среду времени разработки.</span><span class="sxs-lookup"><span data-stu-id="7334c-163">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="7334c-164">В следующих разделах описывается, как улучшить интеграцию пользовательских элементов управления во время разработки:</span><span class="sxs-lookup"><span data-stu-id="7334c-164">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="7334c-165">[Архитектура времени разработки](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="7334c-165">[Design-Time Architecture](/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="7334c-166">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7334c-166">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="7334c-167">[Общие сведения о сериализации конструктора](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="7334c-167">[Designer Serialization Overview](/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="7334c-168">Пошаговое руководство: Создание элемента управления Windows Forms, который использует преимущества функций времени разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7334c-168">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="7334c-169">См. также</span><span class="sxs-lookup"><span data-stu-id="7334c-169">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- [<span data-ttu-id="7334c-170">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="7334c-170">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
