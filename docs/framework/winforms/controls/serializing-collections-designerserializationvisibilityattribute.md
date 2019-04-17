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
ms.openlocfilehash: c113dcf814a252808ae3232751028947c26821ba
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2019
ms.locfileid: "59614146"
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="6ad2f-102">Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="6ad2f-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>

<span data-ttu-id="6ad2f-103">Пользовательские элементы управления, иногда будет предоставлять коллекции как свойство.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="6ad2f-104">В этом пошаговом руководстве демонстрируется использование <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> класс для управления способом сериализации коллекции во время разработки.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="6ad2f-105">Применение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> значение для свойства коллекции гарантирует, что будет сериализовано свойство.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>

 <span data-ttu-id="6ad2f-106">Чтобы скопировать код из этого раздела единым блоком, см. раздел [Практическое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="6ad2f-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120)).</span></span>

> [!NOTE]
> <span data-ttu-id="6ad2f-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="6ad2f-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="6ad2f-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="6ad2f-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="6ad2f-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6ad2f-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="6ad2f-110">Prerequisites</span></span>
 <span data-ttu-id="6ad2f-111">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="6ad2f-111">In order to complete this walkthrough, you will need:</span></span>

- <span data-ttu-id="6ad2f-112">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, на котором установлена Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>

## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="6ad2f-113">Создание элемента управления, который имеет коллекцию сериализуемый</span><span class="sxs-lookup"><span data-stu-id="6ad2f-113">Creating a Control That Has a Serializable Collection</span></span>
 <span data-ttu-id="6ad2f-114">Первым шагом является создание элемента управления, имеющего сериализуемые коллекции как свойство.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="6ad2f-115">Можно изменить содержимое этой коллекции с помощью **редактор коллекции**, к которому можно получить из **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>

### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="6ad2f-116">Создание элемента управления с сериализуемой коллекцией</span><span class="sxs-lookup"><span data-stu-id="6ad2f-116">To create a control with a serializable collection</span></span>

1. <span data-ttu-id="6ad2f-117">Создайте проект библиотеки элементов управления Windows с именем `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="6ad2f-118">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="6ad2f-118">For more information, see [Windows Control Library Template](https://docs.microsoft.com/previous-versions/kxczf775(v=vs.100)).</span></span>

2. <span data-ttu-id="6ad2f-119">Переименуйте `UserControl1` для `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="6ad2f-120">Дополнительные сведения см. в разделе [переименование рефакторинга кода символа](/visualstudio/ide/reference/rename).</span><span class="sxs-lookup"><span data-stu-id="6ad2f-120">For more information, see [Rename a code symbol refactoring](/visualstudio/ide/reference/rename).</span></span>

3. <span data-ttu-id="6ad2f-121">В **свойства** окна, установите для параметра <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> свойства `10`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>

4. <span data-ttu-id="6ad2f-122">Место <xref:System.Windows.Forms.TextBox> контролировать `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>

5. <span data-ttu-id="6ad2f-123">Выберите элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="6ad2f-124">В **свойства** окна, задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-124">In the **Properties** window, set the following properties.</span></span>

    |<span data-ttu-id="6ad2f-125">Свойство</span><span class="sxs-lookup"><span data-stu-id="6ad2f-125">Property</span></span>|<span data-ttu-id="6ad2f-126">Измените на</span><span class="sxs-lookup"><span data-stu-id="6ad2f-126">Change to</span></span>|
    |--------------|---------------|
    |<span data-ttu-id="6ad2f-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="6ad2f-127">**Multiline**</span></span>|`true`|
    |<span data-ttu-id="6ad2f-128">**Dock**</span><span class="sxs-lookup"><span data-stu-id="6ad2f-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|
    |<span data-ttu-id="6ad2f-129">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="6ad2f-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|
    |<span data-ttu-id="6ad2f-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="6ad2f-130">**ReadOnly**</span></span>|`true`|

6. <span data-ttu-id="6ad2f-131">В **редактор кода**, объявите поле строкового массива с именем `stringsValue` в `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>

     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]

7. <span data-ttu-id="6ad2f-132">Определение `Strings` свойство `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>

> [!NOTE]
> <span data-ttu-id="6ad2f-133"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Значение используется для включения сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>

 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]

1. <span data-ttu-id="6ad2f-134">Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>

2. <span data-ttu-id="6ad2f-135">Найти `Strings` свойство в <xref:System.Windows.Forms.PropertyGrid> из **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="6ad2f-136">Нажмите кнопку `Strings` свойство, нажмите кнопку обзора (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

3. <span data-ttu-id="6ad2f-137">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="6ad2f-138">Разделяйте их, нажав клавишу ВВОД в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="6ad2f-139">Нажмите кнопку **ОК** при завершении.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-139">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="6ad2f-140">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

## <a name="serializing-a-collection-property"></a><span data-ttu-id="6ad2f-141">Сериализация свойства коллекции</span><span class="sxs-lookup"><span data-stu-id="6ad2f-141">Serializing a Collection Property</span></span>

<span data-ttu-id="6ad2f-142">Для тестирования поведения сериализации элемента управления, вы поместите его на форму и изменить содержимое коллекции с **редактор коллекции**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="6ad2f-143">Вы увидите состояния сериализации, просмотрев специальный файл конструктора, в который **конструктор Windows Forms** выдает код.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>

### <a name="to-serialize-a-collection"></a><span data-ttu-id="6ad2f-144">Для сериализации коллекции</span><span class="sxs-lookup"><span data-stu-id="6ad2f-144">To serialize a collection</span></span>

1. <span data-ttu-id="6ad2f-145">Добавьте в решение проект приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="6ad2f-146">Задайте для проекта имя `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-146">Name the project `SerializationDemoControlTest`.</span></span>

2. <span data-ttu-id="6ad2f-147">В **элементов**, найдите вкладку с именем **компоненты SerializationDemoControlLib**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="6ad2f-148">На этой вкладке вы найдете `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="6ad2f-149">Дополнительные сведения см. в разделе [Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="6ad2f-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>

3. <span data-ttu-id="6ad2f-150">Место `SerializationDemoControl` в форме.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-150">Place a `SerializationDemoControl` on your form.</span></span>

4. <span data-ttu-id="6ad2f-151">Найти `Strings` свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="6ad2f-152">Нажмите кнопку `Strings` свойство, нажмите кнопку обзора (![экрана VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>

5. <span data-ttu-id="6ad2f-153">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="6ad2f-154">Разделяйте их, нажав клавишу ВВОД в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="6ad2f-155">Нажмите кнопку **ОК** при завершении.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-155">Click **OK** when you are finished entering strings.</span></span>

> [!NOTE]
> <span data-ttu-id="6ad2f-156">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>

1. <span data-ttu-id="6ad2f-157">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>

2. <span data-ttu-id="6ad2f-158">Откройте **Form1** узла.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-158">Open the **Form1** node.</span></span> <span data-ttu-id="6ad2f-159">Ниже это файл с именем **Form1.Designer.cs** или **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="6ad2f-160">Это файл, в который **конструктор Windows Forms** выдает код, представляющий состояние разработки формы и его дочерним элементам.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="6ad2f-161">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-161">Open this file in the **Code Editor**.</span></span>

3. <span data-ttu-id="6ad2f-162">Откройте область, называемую **код, созданный конструктором форм Windows** и найдите раздел **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="6ad2f-163">Под этой метки — это код, представляющий сериализованное состояние элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="6ad2f-164">Строки, введенного в шаге 5 будут отображаться в операторе присваивания для `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="6ad2f-165">В следующих примерах кода в C# и Visual Basic, Показывать код, аналогичны тем, что отображается при вводе строки «red», «оранжевый» и «желтый».</span><span class="sxs-lookup"><span data-stu-id="6ad2f-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>

    ```csharp
    this.serializationDemoControl1.Strings = new string[] {
            "red",
            "orange",
            "yellow"};
    ```

    ```vb
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}
    ```

4. <span data-ttu-id="6ad2f-166">В **редактор кода**, измените значение свойства <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> на `Strings` свойства <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>

    ```csharp
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]
    ```

    ```vb
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _
    ```

5. <span data-ttu-id="6ad2f-167">Перестройте решение и повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-167">Rebuild the solution and repeat steps 3 and 4.</span></span>

> [!NOTE]
> <span data-ttu-id="6ad2f-168">В этом случае **конструктор Windows Forms** не выдает назначения `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6ad2f-169">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="6ad2f-169">Next Steps</span></span>

<span data-ttu-id="6ad2f-170">Когда вы знаете, как для сериализации коллекции стандартных типов, рассмотрите возможность более глубоко интеграции пользовательских элементов управления в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="6ad2f-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="6ad2f-171">Как улучшить интеграцию разработки пользовательских элементов управления в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="6ad2f-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>

- <span data-ttu-id="6ad2f-172">[Архитектура времени разработки](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6ad2f-172">[Design-Time Architecture](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/c5z9s1h4(v=vs.120))</span></span>

- [<span data-ttu-id="6ad2f-173">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6ad2f-173">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)

- <span data-ttu-id="6ad2f-174">[Общие сведения о сериализации конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6ad2f-174">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>

- [<span data-ttu-id="6ad2f-175">Пошаговое руководство: Создание элемента управления Windows Forms, используются преимущества функций Visual Studio во время разработки</span><span class="sxs-lookup"><span data-stu-id="6ad2f-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)

## <a name="see-also"></a><span data-ttu-id="6ad2f-176">См. также</span><span class="sxs-lookup"><span data-stu-id="6ad2f-176">See also</span></span>

- <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>
- <span data-ttu-id="6ad2f-177">[Общие сведения о сериализации конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6ad2f-177">[Designer Serialization Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171834(v=vs.120))</span></span>
- <span data-ttu-id="6ad2f-178">[Практическое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="6ad2f-178">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
- [<span data-ttu-id="6ad2f-179">Пошаговое руководство: Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="6ad2f-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
