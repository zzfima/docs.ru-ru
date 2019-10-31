---
title: 'Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
ms.openlocfilehash: c8a83dd3f7327d00979431ca7fa801ff642a4eef
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197798"
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="44269-102">Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="44269-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>

<span data-ttu-id="44269-103">В этом пошаговом руководстве показано, как использовать свойство <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>, чтобы сопоставлять свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] с соответствующими свойствами размещенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44269-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

<span data-ttu-id="44269-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="44269-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="44269-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="44269-105">Creating the project.</span></span>

- <span data-ttu-id="44269-106">Определение макета приложения.</span><span class="sxs-lookup"><span data-stu-id="44269-106">Defining the application layout.</span></span>

- <span data-ttu-id="44269-107">Определение нового сопоставления свойства.</span><span class="sxs-lookup"><span data-stu-id="44269-107">Defining a new property mapping.</span></span>

- <span data-ttu-id="44269-108">Удаление сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44269-108">Removing a default property mapping.</span></span>

- <span data-ttu-id="44269-109">Замена сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44269-109">Replacing a default property mapping.</span></span>

- <span data-ttu-id="44269-110">Расширение сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44269-110">Extending a default property mapping.</span></span>

<span data-ttu-id="44269-111">Полный листинг кода задач, показанных в этом пошаговом руководстве, см. в разделе [сопоставление свойств с помощью примера элемента WindowsFormsHost](https://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="44269-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](https://go.microsoft.com/fwlink/?LinkID=160019).</span></span>

<span data-ttu-id="44269-112">По завершении вы сможете сопоставлять [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства с соответствующими свойствами размещенного элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44269-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="44269-113">Необходимые компоненты</span><span class="sxs-lookup"><span data-stu-id="44269-113">Prerequisites</span></span>

<span data-ttu-id="44269-114">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="44269-114">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="44269-115">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="44269-115">Visual Studio 2017</span></span>

## <a name="create-and-set-up-the-project"></a><span data-ttu-id="44269-116">Создание и Настройка проекта</span><span class="sxs-lookup"><span data-stu-id="44269-116">Create and set up the project</span></span>

1. <span data-ttu-id="44269-117">Создайте проект **приложения WPF** с именем `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="44269-117">Create a **WPF App** project named `PropertyMappingWithWfhSample`.</span></span>

2. <span data-ttu-id="44269-118">В **Обозреватель решений**добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration. dll.</span><span class="sxs-lookup"><span data-stu-id="44269-118">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="44269-119">В **Обозреватель решений**добавьте ссылки на сборки System. Drawing и System. Windows. Forms.</span><span class="sxs-lookup"><span data-stu-id="44269-119">In **Solution Explorer**, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="defining-the-application-layout"></a><span data-ttu-id="44269-120">Определение макета приложения</span><span class="sxs-lookup"><span data-stu-id="44269-120">Defining the Application Layout</span></span>

<span data-ttu-id="44269-121">Приложение на основе [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]использует элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения элемента управления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44269-121">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>

### <a name="to-define-the-application-layout"></a><span data-ttu-id="44269-122">Определение макета приложения</span><span class="sxs-lookup"><span data-stu-id="44269-122">To define the application layout</span></span>

1. <span data-ttu-id="44269-123">Откройте Window1. XAML в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44269-123">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="44269-124">Замените существующий код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="44269-124">Replace the existing code with the following code.</span></span>

     [!code-xaml[PropertyMappingWithWfhSample#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]

3. <span data-ttu-id="44269-125">Откройте файл Window1.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="44269-125">Open Window1.xaml.cs in the Code Editor.</span></span>

4. <span data-ttu-id="44269-126">В верхней части файла импортируйте указанные ниже пространства имен.</span><span class="sxs-lookup"><span data-stu-id="44269-126">At the top of the file, import the following namespaces.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#20](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]

## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="44269-127">Определение нового сопоставления свойства</span><span class="sxs-lookup"><span data-stu-id="44269-127">Defining a New Property Mapping</span></span>

<span data-ttu-id="44269-128">Элемент <xref:System.Windows.Forms.Integration.WindowsFormsHost> предоставляет несколько сопоставлений свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44269-128">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="44269-129">Новое сопоставление свойств добавляется путем вызова метода <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="44269-129">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="44269-130">Определение нового сопоставления свойства</span><span class="sxs-lookup"><span data-stu-id="44269-130">To define a new property mapping</span></span>

- <span data-ttu-id="44269-131">Скопируйте следующий код в определение класса `Window1`.</span><span class="sxs-lookup"><span data-stu-id="44269-131">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]

     <span data-ttu-id="44269-132">Метод `AddClipMapping` добавляет новое сопоставление для свойства <xref:System.Windows.UIElement.Clip%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-132">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>

     <span data-ttu-id="44269-133">Метод `OnClipChange` преобразует свойство <xref:System.Windows.UIElement.Clip%2A> в свойство [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-133">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>

     <span data-ttu-id="44269-134">Метод `Window1_SizeChanged` обрабатывает событие <xref:System.Windows.FrameworkElement.SizeChanged> окна и изменяет размер вырезанной области в соответствии с окном приложения.</span><span class="sxs-lookup"><span data-stu-id="44269-134">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>

## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="44269-135">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-135">Removing a Default Property Mapping</span></span>

<span data-ttu-id="44269-136">Удалите сопоставление свойств по умолчанию, вызвав метод <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="44269-136">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="44269-137">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-137">To remove a default property mapping</span></span>

- <span data-ttu-id="44269-138">Скопируйте следующий код в определение класса `Window1`.</span><span class="sxs-lookup"><span data-stu-id="44269-138">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#13](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]

     <span data-ttu-id="44269-139">Метод `RemoveCursorMapping` удаляет сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.Cursor%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-139">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>

## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="44269-140">Замена сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-140">Replacing a Default Property Mapping</span></span>

<span data-ttu-id="44269-141">Замените сопоставление свойства по умолчанию, удалив сопоставление по умолчанию и вызвав метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> для <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost>.</span><span class="sxs-lookup"><span data-stu-id="44269-141">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>

### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="44269-142">Замена сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-142">To replace a default property mapping</span></span>

- <span data-ttu-id="44269-143">Скопируйте следующий код в определение класса `Window1`.</span><span class="sxs-lookup"><span data-stu-id="44269-143">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#12](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]

     <span data-ttu-id="44269-144">Метод `ReplaceFlowDirectionMapping` заменяет сопоставление по умолчанию для свойства <xref:System.Windows.FrameworkElement.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-144">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>

     <span data-ttu-id="44269-145">Метод `OnFlowDirectionChange` преобразует свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> в свойство [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-145">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>

     <span data-ttu-id="44269-146">Метод `cb_CheckedChanged` обрабатывает событие <xref:System.Windows.Forms.CheckBox.CheckedChanged> в элементе управления <xref:System.Windows.Forms.CheckBox>.</span><span class="sxs-lookup"><span data-stu-id="44269-146">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="44269-147">Он назначает свойство <xref:System.Windows.FrameworkElement.FlowDirection%2A> на основе значения свойства <xref:System.Windows.Forms.CheckBox.CheckState%2A></span><span class="sxs-lookup"><span data-stu-id="44269-147">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>

## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="44269-148">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-148">Extending a Default Property Mapping</span></span>

<span data-ttu-id="44269-149">Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="44269-149">You can use a default property mapping and also extend it with your own mapping.</span></span>

### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="44269-150">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="44269-150">To extend a default property mapping</span></span>

- <span data-ttu-id="44269-151">Скопируйте следующий код в определение класса `Window1`.</span><span class="sxs-lookup"><span data-stu-id="44269-151">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]

     <span data-ttu-id="44269-152">Метод `ExtendBackgroundMapping` добавляет настраиваемый транслятор свойств к существующему сопоставлению свойств <xref:System.Windows.Controls.Control.Background%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-152">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>

     <span data-ttu-id="44269-153">Метод `OnBackgroundChange` присваивает конкретному изображению свойство <xref:System.Windows.Forms.Control.BackgroundImage%2A> размещаемого элемента управления.</span><span class="sxs-lookup"><span data-stu-id="44269-153">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="44269-154">Метод `OnBackgroundChange` вызывается после применения сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="44269-154">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>

## <a name="initializing-your-property-mappings"></a><span data-ttu-id="44269-155">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="44269-155">Initializing Your Property Mappings</span></span>

<span data-ttu-id="44269-156">Настройте сопоставления свойств, вызвав ранее описанные методы в обработчике событий <xref:System.Windows.FrameworkElement.Loaded>.</span><span class="sxs-lookup"><span data-stu-id="44269-156">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>

### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="44269-157">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="44269-157">To initialize your property mappings</span></span>

1. <span data-ttu-id="44269-158">Скопируйте следующий код в определение класса `Window1`.</span><span class="sxs-lookup"><span data-stu-id="44269-158">Copy the following code into the definition for the `Window1` class.</span></span>

     [!code-csharp[PropertyMappingWithWfhSample#11](~/samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]

     <span data-ttu-id="44269-159">Метод `WindowLoaded` обрабатывает событие <xref:System.Windows.FrameworkElement.Loaded> и выполняет следующую инициализацию.</span><span class="sxs-lookup"><span data-stu-id="44269-159">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>

    - <span data-ttu-id="44269-160">Создает элемент управления <xref:System.Windows.Forms.CheckBox> [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="44269-160">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>

    - <span data-ttu-id="44269-161">Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.</span><span class="sxs-lookup"><span data-stu-id="44269-161">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>

    - <span data-ttu-id="44269-162">Присваивает начальные значения сопоставленным свойствам.</span><span class="sxs-lookup"><span data-stu-id="44269-162">Assigns initial values to the mapped properties.</span></span>

2. <span data-ttu-id="44269-163">Нажмите клавишу **F5**, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="44269-163">Press **F5** to build and run the application.</span></span> <span data-ttu-id="44269-164">Установите флажок, чтобы увидеть результат сопоставления <xref:System.Windows.FrameworkElement.FlowDirection%2A>.</span><span class="sxs-lookup"><span data-stu-id="44269-164">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="44269-165">При установке флажка меняется ориентация макета по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="44269-165">When you click the check box, the layout reverses its left-right orientation.</span></span>

## <a name="see-also"></a><span data-ttu-id="44269-166">См. также</span><span class="sxs-lookup"><span data-stu-id="44269-166">See also</span></span>

- <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="44269-167">Сопоставление свойств Windows Forms и WPF</span><span class="sxs-lookup"><span data-stu-id="44269-167">Windows Forms and WPF Property Mapping</span></span>](windows-forms-and-wpf-property-mapping.md)
- [<span data-ttu-id="44269-168">Проектирование XAML в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="44269-168">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [<span data-ttu-id="44269-169">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="44269-169">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
