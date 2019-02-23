---
title: Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: 29356f171506ece0fe35418f682681b19830d71c
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2019
ms.locfileid: "56746342"
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="8c9e7-102">Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost</span><span class="sxs-lookup"><span data-stu-id="8c9e7-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>

<span data-ttu-id="8c9e7-103">В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> свойства для сопоставления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойств с соответствующими свойствами вложенного [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемент.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>

<span data-ttu-id="8c9e7-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="8c9e7-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-105">Creating the project.</span></span>

-   <span data-ttu-id="8c9e7-106">Определение нового сопоставления свойства.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-106">Defining a new property mapping.</span></span>

-   <span data-ttu-id="8c9e7-107">Удаление сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-107">Removing a default property mapping.</span></span>

-   <span data-ttu-id="8c9e7-108">Расширение сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-108">Extending a default property mapping.</span></span>

<span data-ttu-id="8c9e7-109">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. в разделе [сопоставления свойств с помощью пример элемента управления ElementHost](https://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="8c9e7-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](https://go.microsoft.com/fwlink/?LinkID=160018).</span></span>

<span data-ttu-id="8c9e7-110">Когда вы закончите, можно сопоставить [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойств с соответствующими [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c9e7-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="8c9e7-111">Prerequisites</span></span>

<span data-ttu-id="8c9e7-112">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-112">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="8c9e7-113">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="8c9e7-113">Visual Studio 2017</span></span>

## <a name="creating-the-project"></a><span data-ttu-id="8c9e7-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="8c9e7-114">Creating the Project</span></span>

### <a name="to-create-the-project"></a><span data-ttu-id="8c9e7-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="8c9e7-115">To create the project</span></span>

1.  <span data-ttu-id="8c9e7-116">Создание **приложения Windows Forms** проект с именем `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-116">Create a **Windows Forms App** project named `PropertyMappingWithElementHost`.</span></span>

2.  <span data-ttu-id="8c9e7-117">В **обозревателе решений**, добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборок.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-117">In **Solution Explorer**, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>

    -   <span data-ttu-id="8c9e7-118">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="8c9e7-118">PresentationCore</span></span>

    -   <span data-ttu-id="8c9e7-119">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="8c9e7-119">PresentationFramework</span></span>

    -   <span data-ttu-id="8c9e7-120">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="8c9e7-120">WindowsBase</span></span>

    -   <span data-ttu-id="8c9e7-121">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="8c9e7-121">WindowsFormsIntegration</span></span>

3.  <span data-ttu-id="8c9e7-122">Скопируйте следующий код в верхнюю часть `Form1` файл кода.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-122">Copy the following code into the top of the `Form1` code file.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]

4.  <span data-ttu-id="8c9e7-123">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-123">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="8c9e7-124">Дважды щелкните форму, чтобы добавить обработчик событий для <xref:System.Windows.Forms.Form.Load> событий.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-124">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>

5.  <span data-ttu-id="8c9e7-125">Вернитесь к конструктору Windows Forms и добавьте обработчик событий для формы <xref:System.Windows.Forms.Control.Resize> событий.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-125">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="8c9e7-126">Дополнительные сведения см. в разделе [Как Создание обработчиков событий с помощью конструктора](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="8c9e7-126">For more information, see [How to: Create Event Handlers Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/zwwsdtbk(v=vs.100)).</span></span>

6.  <span data-ttu-id="8c9e7-127">Объявите <xref:System.Windows.Forms.Integration.ElementHost> в `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-127">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]

## <a name="defining-new-property-mappings"></a><span data-ttu-id="8c9e7-128">Определение новых сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="8c9e7-128">Defining New Property Mappings</span></span>

<span data-ttu-id="8c9e7-129"><xref:System.Windows.Forms.Integration.ElementHost> Элемент управления предоставляет несколько стандартных сопоставления свойств.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-129">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="8c9e7-130">Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-define-new-property-mappings"></a><span data-ttu-id="8c9e7-131">Для определения новых сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="8c9e7-131">To define new property mappings</span></span>

1.  <span data-ttu-id="8c9e7-132">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-132">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]

     <span data-ttu-id="8c9e7-133">`AddMarginMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Margin%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-133">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>

     <span data-ttu-id="8c9e7-134">`OnMarginChange` Метод преобразует <xref:System.Windows.Forms.Control.Margin%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-134">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>

2.  <span data-ttu-id="8c9e7-135">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-135">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]

     <span data-ttu-id="8c9e7-136">`AddRegionMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Region%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-136">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="8c9e7-137">`OnRegionChange` Метод преобразует <xref:System.Windows.Forms.Control.Region%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-137">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="8c9e7-138">`Form1_Resize` Метод обрабатывает формы <xref:System.Windows.Forms.Control.Resize> событий и размеров области отсечения в соответствии с размещаемый элемент.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-138">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="8c9e7-139">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c9e7-139">Removing a Default Property Mapping</span></span>

<span data-ttu-id="8c9e7-140">Удаление сопоставления свойства по умолчанию путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-140">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="8c9e7-141">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c9e7-141">To remove a default property mapping</span></span>

-   <span data-ttu-id="8c9e7-142">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-142">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]

     <span data-ttu-id="8c9e7-143">`RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.Forms.Control.Cursor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-143">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="8c9e7-144">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c9e7-144">Extending a Default Property Mapping</span></span>

<span data-ttu-id="8c9e7-145">Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-145">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="8c9e7-146">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="8c9e7-146">To extend a default property mapping</span></span>

-   <span data-ttu-id="8c9e7-147">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-147">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]

     <span data-ttu-id="8c9e7-148">`ExtendBackColorMapping` Метод добавляет пользовательский преобразователь свойств для существующего <xref:System.Windows.Forms.Control.BackColor%2A> сопоставление свойств.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-148">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>

     <span data-ttu-id="8c9e7-149">`OnBackColorChange` Метод присваивает определенное изображение для размещенного элемента управления <xref:System.Windows.Controls.Control.Background%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-149">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="8c9e7-150">`OnBackColorChange` Метод вызывается после применения сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-150">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>

## <a name="initialize-your-property-mappings"></a><span data-ttu-id="8c9e7-151">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="8c9e7-151">Initialize your property mappings</span></span>

1.  <span data-ttu-id="8c9e7-152">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-152">Copy the following code into the definition for the `Form1` class.</span></span>

     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]

     <span data-ttu-id="8c9e7-153">`Form1_Load` Метод обрабатывает <xref:System.Windows.Forms.Form.Load> событий и выполнения следующей инициализации.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-153">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>

    -   <span data-ttu-id="8c9e7-154">Создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> элемент.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-154">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>

    -   <span data-ttu-id="8c9e7-155">Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-155">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    -   <span data-ttu-id="8c9e7-156">Присваивает начальные значения сопоставленным свойствам.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-156">Assigns initial values to the mapped properties.</span></span>

2.  <span data-ttu-id="8c9e7-157">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="8c9e7-157">Press F5 to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c9e7-158">См. также</span><span class="sxs-lookup"><span data-stu-id="8c9e7-158">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="8c9e7-159">Сопоставление свойств Windows Forms и WPF</span><span class="sxs-lookup"><span data-stu-id="8c9e7-159">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="8c9e7-160">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="8c9e7-160">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="8c9e7-161">Пошаговое руководство: Размещение составного элемента управления WPF в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8c9e7-161">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)