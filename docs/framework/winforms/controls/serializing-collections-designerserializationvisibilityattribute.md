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
ms.openlocfilehash: c8321f98b25026e32e7c69f7029f2c589d0567f7
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211604"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="9bf0f-102">Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="9bf0f-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="9bf0f-103">Пользовательские элементы управления, иногда будет предоставлять коллекции как свойство.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="9bf0f-104">В этом пошаговом руководстве демонстрируется использование <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> класс для управления способом сериализации коллекции во время разработки.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="9bf0f-105">Применение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> значение для свойства коллекции гарантирует, что будет сериализовано свойство.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

<span data-ttu-id="9bf0f-106">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="9bf0f-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bf0f-107">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="9bf0f-107">Prerequisites</span></span>

<span data-ttu-id="9bf0f-108">Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-108">You need Visual Studio to complete this walkthrough.</span></span>

## <a name="create-a-control-with-a-serializable-collection"></a><span data-ttu-id="9bf0f-109">Создание элемента управления с сериализуемой коллекцией</span><span class="sxs-lookup"><span data-stu-id="9bf0f-109">Create a control with a serializable collection</span></span>

<span data-ttu-id="9bf0f-110">Первым шагом является создание элемента управления, имеющего сериализуемые коллекции как свойство.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-110">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="9bf0f-111">Можно изменить содержимое этой коллекции с помощью **редактор коллекции**, к которому можно получить из **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-111">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

1. <span data-ttu-id="9bf0f-112">В Visual Studio создайте проект библиотеки элементов управления Windows с именем `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-112">In Visual Studio, create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="9bf0f-113">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="9bf0f-113">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="9bf0f-114">Переименуйте `UserControl1` для `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-114">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="9bf0f-115">Дополнительные сведения см. в разделе [переименование рефакторинга кода символа](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="9bf0f-115">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="9bf0f-116">В **свойства** окна, установите для параметра <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> свойства `10`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-116">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="9bf0f-117">Место <xref:System.Windows.Forms.TextBox> контролировать `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-117">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="9bf0f-118">Выберите элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-118">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="9bf0f-119">В **свойства** окна, задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-119">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="9bf0f-120">Свойство</span><span class="sxs-lookup"><span data-stu-id="9bf0f-120">Property</span></span>|<span data-ttu-id="9bf0f-121">Измените на</span><span class="sxs-lookup"><span data-stu-id="9bf0f-121">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="9bf0f-122">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="9bf0f-122">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="9bf0f-123">**Dock**</span><span class="sxs-lookup"><span data-stu-id="9bf0f-123">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="9bf0f-124">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="9bf0f-124">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="9bf0f-125">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="9bf0f-125">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="9bf0f-126">В **редактор кода**, объявите поле строкового массива с именем `stringsValue` в `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-126">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="9bf0f-127">Определение `Strings` свойство `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-127">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9bf0f-128"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Значение используется для включения сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-128">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

   [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
   [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
   [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

8. <span data-ttu-id="9bf0f-129">Нажмите клавишу **F5** построение проекта и запустить элемент управления **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-129">Press **F5** to build the project and run your control in the **UserControl Test Container**.</span></span>

9. <span data-ttu-id="9bf0f-130">Найти `Strings` свойство в <xref:System.Windows.Forms.PropertyGrid> из **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-130">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="9bf0f-131">Нажмите кнопку `Strings` свойство, нажмите кнопку обзора (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-131">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

10. <span data-ttu-id="9bf0f-132">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-132">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="9bf0f-133">Разделяйте их, нажав клавишу **ввод** ключа в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-133">Separate them by pressing the **Enter** key at the end of each string.</span></span> <span data-ttu-id="9bf0f-134">Нажмите кнопку **ОК** при завершении.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-134">Click **OK** when you are finished entering strings.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9bf0f-135">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-135">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="9bf0f-136">Сериализация свойства коллекции</span><span class="sxs-lookup"><span data-stu-id="9bf0f-136">Serializing a Collection Property</span></span>

<span data-ttu-id="9bf0f-137">Для тестирования поведения сериализации элемента управления, вы поместите его на форму и изменить содержимое коллекции с **редактор коллекции**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-137">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="9bf0f-138">Вы увидите состояния сериализации, просмотрев специальный файл конструктора, в который **конструктор Windows Forms** выдает код.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-138">You can see the serialized collection state by looking at a special designer file into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="9bf0f-139">Для сериализации коллекции</span><span class="sxs-lookup"><span data-stu-id="9bf0f-139">To serialize a collection</span></span>

1. <span data-ttu-id="9bf0f-140">Добавьте в решение проект приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-140">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="9bf0f-141">Задайте для проекта имя `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-141">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="9bf0f-142">В **элементов**, найдите вкладку с именем **компоненты SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-142">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="9bf0f-143">На этой вкладке вы найдете `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-143">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="9bf0f-144">Дополнительные сведения см. в разделе [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="9bf0f-144">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="9bf0f-145">Место `SerializationDemoControl` в форме.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-145">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="9bf0f-146">Найти `Strings` свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-146">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="9bf0f-147">Нажмите кнопку `Strings` свойство, нажмите кнопку обзора (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-147">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="9bf0f-148">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-148">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="9bf0f-149">Разделяйте их, нажав клавишу ВВОД в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-149">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="9bf0f-150">Нажмите кнопку **ОК** при завершении.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-150">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf0f-151">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-151">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="9bf0f-152">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-152">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="9bf0f-153">Откройте **Form1** узла.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-153">Open the **Form1** node.</span></span> <span data-ttu-id="9bf0f-154">Ниже это файл с именем **Form1.Designer.cs** или **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-154">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="9bf0f-155">Это файл, в который **конструктор Windows Forms** выдает код, представляющий состояние разработки формы и его дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-155">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="9bf0f-156">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-156">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="9bf0f-157">Откройте область, называемую **код, созданный конструктором форм Windows** и найдите раздел **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-157">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="9bf0f-158">Под этой метки — это код, представляющий сериализованное состояние элемента управления.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-158">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="9bf0f-159">Строки, введенного в шаге 5 будут отображаться в операторе присваивания для `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-159">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="9bf0f-160">В следующих примерах кода в C# и Visual Basic, Показывать код, аналогичны тем, что отображается при вводе строки «red», «оранжевый» и «желтый».</span><span class="sxs-lookup"><span data-stu-id="9bf0f-160">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="9bf0f-161">В **редактор кода**, измените значение свойства <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> на `Strings` свойства <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-161">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="9bf0f-162">Перестройте решение и повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-162">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="9bf0f-163">В этом случае **конструктор Windows Forms** не выдает назначения `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-163">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9bf0f-164">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="9bf0f-164">Next Steps</span></span>

<span data-ttu-id="9bf0f-165">Когда вы знаете, как для сериализации коллекции стандартных типов, рассмотрите возможность более глубоко интеграции пользовательских элементов управления в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="9bf0f-165">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="9bf0f-166">Как улучшить интеграцию разработки пользовательских элементов управления в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9bf0f-166">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="9bf0f-167">[Архитектура времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9bf0f-167">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="9bf0f-168">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9bf0f-168">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="9bf0f-169">[Общие сведения о сериализации конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9bf0f-169">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="9bf0f-170">Пошаговое руководство: Создание элемента управления Windows Forms, используются преимущества функций Visual Studio во время разработки</span><span class="sxs-lookup"><span data-stu-id="9bf0f-170">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="9bf0f-171">См. также</span><span class="sxs-lookup"><span data-stu-id="9bf0f-171">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="9bf0f-172">[Общие сведения о сериализации конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9bf0f-172">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="9bf0f-173">[Практическое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="9bf0f-173">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="9bf0f-174">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="9bf0f-174">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
