---
title: "Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0267020f7e7a52e92b05a0bda0ee397e5c3393fc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-serializing-collections-of-standard-types-with-the-designerserializationvisibilityattribute"></a><span data-ttu-id="c7eae-102">Пошаговое руководство. Сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="c7eae-102">Walkthrough: Serializing Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>
<span data-ttu-id="c7eae-103">Пользовательские элементы управления, иногда будет предоставлять коллекции как свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-103">Your custom controls will sometimes expose a collection as a property.</span></span> <span data-ttu-id="c7eae-104">В этом пошаговом руководстве демонстрируется использование <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> класса для управления способом сериализации коллекции во время разработки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-104">This walkthrough demonstrates how to use the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> class to control how a collection is serialized at design time.</span></span> <span data-ttu-id="c7eae-105">Применение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> значение к свойству коллекции гарантирует, что будет сериализовано свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-105">Applying the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value to your collection property ensures that the property will be serialized.</span></span>  
  
 <span data-ttu-id="c7eae-106">Скопируйте код из этой темы, в разделе [как: сериализации коллекций из стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span><span class="sxs-lookup"><span data-stu-id="c7eae-106">To copy the code in this topic as a single listing, see [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7eae-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c7eae-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c7eae-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c7eae-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c7eae-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="c7eae-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7eae-110">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="c7eae-110">Prerequisites</span></span>  
 <span data-ttu-id="c7eae-111">Для выполнения данного пошагового руководства требуется:</span><span class="sxs-lookup"><span data-stu-id="c7eae-111">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="c7eae-112">Разрешения, необходимые для создания и выполнения проектов приложений Windows Forms на компьютере, где установлена среда Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="c7eae-112">Sufficient permissions to be able to create and run Windows Forms application projects on the computer where Visual Studio is installed.</span></span>  
  
## <a name="creating-a-control-that-has-a-serializable-collection"></a><span data-ttu-id="c7eae-113">Создание элемента управления с сериализуемой коллекцией</span><span class="sxs-lookup"><span data-stu-id="c7eae-113">Creating a Control That Has a Serializable Collection</span></span>  
 <span data-ttu-id="c7eae-114">Первым шагом является создание элемента управления с сериализуемой коллекцией как свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-114">The first step is to create a control that has a serializable collection as a property.</span></span> <span data-ttu-id="c7eae-115">Можно изменить содержимое этой коллекции с помощью **редактор коллекции**, к которому можно получить из **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="c7eae-115">You can edit the contents of this collection using the **Collection Editor**, which you can access from the **Properties** window.</span></span>  
  
#### <a name="to-create-a-control-with-a-serializable-collection"></a><span data-ttu-id="c7eae-116">Создание элемента управления с сериализуемой коллекцией</span><span class="sxs-lookup"><span data-stu-id="c7eae-116">To create a control with a serializable collection</span></span>  
  
1.  <span data-ttu-id="c7eae-117">Создайте проект библиотеки элементов управления Windows с именем `SerializationDemoControlLib`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-117">Create a Windows Control Library project called `SerializationDemoControlLib`.</span></span> <span data-ttu-id="c7eae-118">Дополнительные сведения см. в разделе [шаблон библиотеки элементов управления Windows](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span><span class="sxs-lookup"><span data-stu-id="c7eae-118">For more information, see [Windows Control Library Template](http://msdn.microsoft.com/library/722f4e2d-1310-4ed5-8f33-593337ab66b4).</span></span>  
  
2.  <span data-ttu-id="c7eae-119">Переименуйте `UserControl1` для `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-119">Rename `UserControl1` to `SerializationDemoControl`.</span></span> <span data-ttu-id="c7eae-120">Дополнительные сведения см. в разделе [как: переименовать идентификаторы](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span><span class="sxs-lookup"><span data-stu-id="c7eae-120">For more information, see [How to: Rename Identifiers](http://msdn.microsoft.com/library/2430f732-2b70-4516-8cf6-a7bb71cc9724).</span></span>  
  
3.  <span data-ttu-id="c7eae-121">В **свойства** задайте значение <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> свойства `10`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-121">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Padding.All%2A?displayProperty=nameWithType> property to `10`.</span></span>  
  
4.  <span data-ttu-id="c7eae-122">Место <xref:System.Windows.Forms.TextBox> управления `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-122">Place a <xref:System.Windows.Forms.TextBox> control in the `SerializationDemoControl`.</span></span>  
  
5.  <span data-ttu-id="c7eae-123">Выберите элемент управления <xref:System.Windows.Forms.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="c7eae-123">Select the <xref:System.Windows.Forms.TextBox> control.</span></span> <span data-ttu-id="c7eae-124">В **свойства** задайте следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="c7eae-124">In the **Properties** window, set the following properties.</span></span>  
  
    |<span data-ttu-id="c7eae-125">Свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-125">Property</span></span>|<span data-ttu-id="c7eae-126">Измените на</span><span class="sxs-lookup"><span data-stu-id="c7eae-126">Change to</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="c7eae-127">**Multiline**</span><span class="sxs-lookup"><span data-stu-id="c7eae-127">**Multiline**</span></span>|`true`|  
    |<span data-ttu-id="c7eae-128">**Закрепление**</span><span class="sxs-lookup"><span data-stu-id="c7eae-128">**Dock**</span></span>|<xref:System.Windows.Forms.DockStyle.Fill>|  
    |<span data-ttu-id="c7eae-129">**ScrollBars**</span><span class="sxs-lookup"><span data-stu-id="c7eae-129">**ScrollBars**</span></span>|<xref:System.Windows.Forms.ScrollBars.Vertical>|  
    |<span data-ttu-id="c7eae-130">**ReadOnly**</span><span class="sxs-lookup"><span data-stu-id="c7eae-130">**ReadOnly**</span></span>|`true`|  
  
6.  <span data-ttu-id="c7eae-131">В **редактор кода**, объявите поле строкового массива с именем `stringsValue` в `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-131">In the **Code Editor**, declare a string array field named `stringsValue` in `SerializationDemoControl`.</span></span>  
  
     [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#4)]
     [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#4)]
     [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#4)]  
  
7.  <span data-ttu-id="c7eae-132">Определение `Strings` свойство `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-132">Define the `Strings` property on the `SerializationDemoControl`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7eae-133"><xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> Значение используется для включения сериализации коллекции.</span><span class="sxs-lookup"><span data-stu-id="c7eae-133">The <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute.Content> value is used to enable serialization of the collection.</span></span>  
  
 [!code-cpp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/cpp/form1.cpp#5)]
 [!code-csharp[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/CS/form1.cs#5)]
 [!code-vb[System.ComponentModel.DesignerSerializationVisibilityAttribute#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.DesignerSerializationVisibilityAttribute/VB/form1.vb#5)]  
  
1.  <span data-ttu-id="c7eae-134">Нажмите клавишу F5, чтобы собрать проект и запустить элемент управления в **тестовом контейнере элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-134">Press F5 to build the project and run your control in the **UserControl Test Container**.</span></span>  
  
2.  <span data-ttu-id="c7eae-135">Найти `Strings` свойство в <xref:System.Windows.Forms.PropertyGrid> из **тестовый контейнер пользовательских элементов управления**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-135">Find the `Strings` property in the <xref:System.Windows.Forms.PropertyGrid> of the **UserControl Test Container**.</span></span> <span data-ttu-id="c7eae-136">Нажмите кнопку `Strings` свойства, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-136">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
3.  <span data-ttu-id="c7eae-137">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-137">Enter several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="c7eae-138">Разделите их, нажав клавишу ВВОД в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-138">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="c7eae-139">Нажмите кнопку **ОК** завершении ввода строки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-139">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7eae-140">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-140">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
## <a name="serializing-a-collection-property"></a><span data-ttu-id="c7eae-141">Сериализация свойства коллекции</span><span class="sxs-lookup"><span data-stu-id="c7eae-141">Serializing a Collection Property</span></span>  
 <span data-ttu-id="c7eae-142">Для проверки сериализации элемента управления, будет разместить его в форме и изменить содержимое коллекции с **редактор коллекции**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-142">To test the serialization behavior of your control, you will place it on a form and change the contents of the collection with the **Collection Editor**.</span></span> <span data-ttu-id="c7eae-143">Вы увидите состояния сериализации, просмотрев служит файл конструктора, в который **конструктор Windows Forms** выдает код.</span><span class="sxs-lookup"><span data-stu-id="c7eae-143">You can see the serialized collection state by looking at a special designer file, into which the **Windows Forms Designer** emits code.</span></span>  
  
#### <a name="to-serialize-a-collection"></a><span data-ttu-id="c7eae-144">Для сериализации коллекции</span><span class="sxs-lookup"><span data-stu-id="c7eae-144">To serialize a collection</span></span>  
  
1.  <span data-ttu-id="c7eae-145">Добавьте в решение проект приложения Windows.</span><span class="sxs-lookup"><span data-stu-id="c7eae-145">Add a Windows Application project to the solution.</span></span> <span data-ttu-id="c7eae-146">Задайте для проекта имя `SerializationDemoControlTest`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-146">Name the project `SerializationDemoControlTest`.</span></span>  
  
2.  <span data-ttu-id="c7eae-147">В **элементов**, найти вкладка с именем **SerializationDemoControlLib компонентов**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-147">In the **Toolbox**, find the tab named **SerializationDemoControlLib Components**.</span></span> <span data-ttu-id="c7eae-148">На этой вкладке вы найдете `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-148">In this tab, you will find the `SerializationDemoControl`.</span></span> <span data-ttu-id="c7eae-149">Дополнительные сведения см. в разделе [Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span><span class="sxs-lookup"><span data-stu-id="c7eae-149">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
3.  <span data-ttu-id="c7eae-150">Место `SerializationDemoControl` в форме.</span><span class="sxs-lookup"><span data-stu-id="c7eae-150">Place a `SerializationDemoControl` on your form.</span></span>  
  
4.  <span data-ttu-id="c7eae-151">Найти `Strings` свойство в **свойства** окна.</span><span class="sxs-lookup"><span data-stu-id="c7eae-151">Find the `Strings` property in the **Properties** window.</span></span> <span data-ttu-id="c7eae-152">Нажмите кнопку `Strings` свойства, нажмите кнопку с многоточием (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) кнопку, чтобы открыть **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-152">Click the `Strings` property, then click the ellipsis (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button to open the **String Collection Editor**.</span></span>  
  
5.  <span data-ttu-id="c7eae-153">Введите несколько строк в **редактор коллекции строк**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-153">Type several strings in the **String Collection Editor**.</span></span> <span data-ttu-id="c7eae-154">Разделите их, нажав клавишу ВВОД в конце каждой строки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-154">Separate them by pressing the ENTER key at the end of each string.</span></span> <span data-ttu-id="c7eae-155">Нажмите кнопку **ОК** завершении ввода строки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-155">Click **OK** when you are finished entering strings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7eae-156">Строки отображаются в <xref:System.Windows.Forms.TextBox> из `SerializationDemoControl`.</span><span class="sxs-lookup"><span data-stu-id="c7eae-156">The strings you typed appear in the <xref:System.Windows.Forms.TextBox> of the `SerializationDemoControl`.</span></span>  
  
1.  <span data-ttu-id="c7eae-157">В **обозревателе решений** нажмите кнопку **Показать все файлы**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-157">In **Solution Explorer**, click the **Show All Files** button.</span></span>  
  
2.  <span data-ttu-id="c7eae-158">Откройте **Form1** узла.</span><span class="sxs-lookup"><span data-stu-id="c7eae-158">Open the **Form1** node.</span></span> <span data-ttu-id="c7eae-159">Ниже это файл с именем **Form1.Designer.cs** или **Form1.Designer.vb**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-159">Beneath it is a file called **Form1.Designer.cs** or **Form1.Designer.vb**.</span></span> <span data-ttu-id="c7eae-160">Это файл, в который **конструктор Windows Forms** выдает код, представляющий состояние вашей формы и ее дочерних элементов управления во время разработки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-160">This is the file into which the **Windows Forms Designer** emits code representing the design-time state of your form and its child controls.</span></span> <span data-ttu-id="c7eae-161">Откройте этот файл в **редакторе кода**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-161">Open this file in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="c7eae-162">Откройте область, называемую **код, автоматически созданный конструктором форм Windows** и найдите раздел **serializationDemoControl1**.</span><span class="sxs-lookup"><span data-stu-id="c7eae-162">Open the region called **Windows Form Designer generated code** and find the section labeled **serializationDemoControl1**.</span></span> <span data-ttu-id="c7eae-163">Под этой надписью находится код, представляющий сериализованное состояние элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c7eae-163">Beneath this label is the code representing the serialized state of your control.</span></span> <span data-ttu-id="c7eae-164">Строки, введенного в шаге 5, отображаются в назначении `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-164">The strings you typed in step 5 appear in an assignment to the `Strings` property.</span></span> <span data-ttu-id="c7eae-165">В следующих примерах кода в C# и Visual Basic, Показать код, аналогичный тому, что будет при вводе строки «red», «оранжевый» и «желтый».</span><span class="sxs-lookup"><span data-stu-id="c7eae-165">The following code examples in C# and Visual Basic, show code similar to what you will see if you typed the strings "red", "orange", and "yellow".</span></span>  
  
    ```csharp  
    this.serializationDemoControl1.Strings = new string[] {  
            "red",  
            "orange",  
            "yellow"};  
    ```  
    
    ```vb  
    Me.serializationDemoControl1.Strings = New String() {"red", "orange", "yellow"}  
    ```
  
4.  <span data-ttu-id="c7eae-166">В **редактор кода**, измените значение <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> на `Strings` свойства <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span><span class="sxs-lookup"><span data-stu-id="c7eae-166">In the **Code Editor**, change the value of the <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute> on the `Strings` property to <xref:System.ComponentModel.DesignerSerializationVisibility.Hidden>.</span></span>  
  
    ```csharp  
    [DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)]  
    ```  
    ```vb  
    <DesignerSerializationVisibility(DesignerSerializationVisibility.Hidden)> _  
    ```  
  
5. <span data-ttu-id="c7eae-167">Пересоберите решение и повторите шаги 3 и 4.</span><span class="sxs-lookup"><span data-stu-id="c7eae-167">Rebuild the solution and repeat steps 3 and 4.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7eae-168">В этом случае **конструктор Windows Forms** не выдает назначения `Strings` свойство.</span><span class="sxs-lookup"><span data-stu-id="c7eae-168">In this case, the **Windows Forms Designer** emits no assignment to the `Strings` property.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7eae-169">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="c7eae-169">Next Steps</span></span>  
 <span data-ttu-id="c7eae-170">Если известно, как выполнять сериализацию коллекции стандартных типов, рассмотрите возможность более глубокий уровень интеграции пользовательских элементов управления в среду разработки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-170">Once you know how to serialize a collection of standard types, consider integrating your custom controls more deeply into the design-time environment.</span></span> <span data-ttu-id="c7eae-171">Следующие разделы описывают для улучшения интеграции пользовательских элементов управления во время разработки.</span><span class="sxs-lookup"><span data-stu-id="c7eae-171">The following topics describe how to enhance the design-time integration of your custom controls:</span></span>  
  
-   [<span data-ttu-id="c7eae-172">Архитектура времени разработки</span><span class="sxs-lookup"><span data-stu-id="c7eae-172">Design-Time Architecture</span></span>](http://msdn.microsoft.com/library/4881917b-628f-4689-b872-472e4f8a4e3a)  
  
-   [<span data-ttu-id="c7eae-173">Атрибуты в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c7eae-173">Attributes in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)  
  
-   [<span data-ttu-id="c7eae-174">Общие сведения о сериализации конструктора</span><span class="sxs-lookup"><span data-stu-id="c7eae-174">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
  
-   [<span data-ttu-id="c7eae-175">Пошаговое руководство. Создание элемента управления Windows Forms, в котором используются преимущества функций Visual Studio, применяемых во время разработки</span><span class="sxs-lookup"><span data-stu-id="c7eae-175">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](../../../../docs/framework/winforms/controls/creating-a-wf-control-design-time-features.md)  
  
## <a name="see-also"></a><span data-ttu-id="c7eae-176">См. также</span><span class="sxs-lookup"><span data-stu-id="c7eae-176">See Also</span></span>  
 <xref:System.ComponentModel.DesignerSerializationVisibilityAttribute>  
 [<span data-ttu-id="c7eae-177">Общие сведения о сериализации конструктора</span><span class="sxs-lookup"><span data-stu-id="c7eae-177">Designer Serialization Overview</span></span>](http://msdn.microsoft.com/library/c342635a-aa5f-4281-915b-b013738af15a)  
 [<span data-ttu-id="c7eae-178">Как: сериализация коллекций стандартных типов с использованием атрибута DesignerSerializationVisibilityAttribute</span><span class="sxs-lookup"><span data-stu-id="c7eae-178">How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute</span></span>](http://msdn.microsoft.com/library/7829fcdd-8205-405f-8231-a1282a9835c9)  
 [<span data-ttu-id="c7eae-179">Пошаговое руководство. Автоматическое заполнение панели элементов пользовательскими компонентами</span><span class="sxs-lookup"><span data-stu-id="c7eae-179">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
