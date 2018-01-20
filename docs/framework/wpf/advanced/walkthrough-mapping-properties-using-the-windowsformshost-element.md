---
title: "Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- WindowsFormsHost element property mapping [WPF]
ms.assetid: 74809167-bf8e-48b7-a2e7-b4ea08bc7d8c
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eaab6b7724a1e6145dfce3998ccf75904df01802
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-mapping-properties-using-the-windowsformshost-element"></a><span data-ttu-id="08c74-102">Пошаговое руководство: сопоставление свойств с помощью элемента WindowsFormsHost</span><span class="sxs-lookup"><span data-stu-id="08c74-102">Walkthrough: Mapping Properties Using the WindowsFormsHost Element</span></span>
<span data-ttu-id="08c74-103">В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> свойство для сопоставления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="08c74-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A> property to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
 <span data-ttu-id="08c74-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="08c74-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="08c74-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="08c74-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="08c74-106">Определение макета приложения.</span><span class="sxs-lookup"><span data-stu-id="08c74-106">Defining the application layout.</span></span>  
  
-   <span data-ttu-id="08c74-107">Определение нового сопоставления свойства.</span><span class="sxs-lookup"><span data-stu-id="08c74-107">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="08c74-108">Удаление сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08c74-108">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="08c74-109">Замена сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08c74-109">Replacing a default property mapping.</span></span>  
  
-   <span data-ttu-id="08c74-110">Расширение сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08c74-110">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="08c74-111">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [сопоставление свойств с помощью образец элемента WindowsFormsHost](http://go.microsoft.com/fwlink/?LinkID=160019).</span><span class="sxs-lookup"><span data-stu-id="08c74-111">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the WindowsFormsHost Element Sample](http://go.microsoft.com/fwlink/?LinkID=160019).</span></span>  
  
 <span data-ttu-id="08c74-112">Когда вы закончите, можно для сопоставления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="08c74-112">When you are finished, you will be able to map [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="08c74-113">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="08c74-113">Prerequisites</span></span>  
 <span data-ttu-id="08c74-114">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="08c74-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="08c74-115">.</span><span class="sxs-lookup"><span data-stu-id="08c74-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="08c74-116">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="08c74-116">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="08c74-117">Создание и настройка проекта</span><span class="sxs-lookup"><span data-stu-id="08c74-117">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="08c74-118">Создание проекта приложения WPF с именем `PropertyMappingWithWfhSample`.</span><span class="sxs-lookup"><span data-stu-id="08c74-118">Create a WPF Application project named `PropertyMappingWithWfhSample`.</span></span>  
  
2.  <span data-ttu-id="08c74-119">В обозревателе решений добавьте ссылку на сборку WindowsFormsIntegration, которая называется WindowsFormsIntegration.dll.</span><span class="sxs-lookup"><span data-stu-id="08c74-119">In Solution Explorer, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="08c74-120">В обозревателе решений добавьте ссылки на сборки System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="08c74-120">In Solution Explorer, add references to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="defining-the-application-layout"></a><span data-ttu-id="08c74-121">Определение макета приложения</span><span class="sxs-lookup"><span data-stu-id="08c74-121">Defining the Application Layout</span></span>  
 <span data-ttu-id="08c74-122">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-На основе приложения использует <xref:System.Windows.Forms.Integration.WindowsFormsHost> для размещения элемента [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] элемента управления.</span><span class="sxs-lookup"><span data-stu-id="08c74-122">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element to host a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-define-the-application-layout"></a><span data-ttu-id="08c74-123">Определение макета приложения</span><span class="sxs-lookup"><span data-stu-id="08c74-123">To define the application layout</span></span>  
  
1.  <span data-ttu-id="08c74-124">Откройте файл Window1.xaml в [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="08c74-124">Open Window1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>  
  
2.  <span data-ttu-id="08c74-125">Замените существующий код следующим кодом:</span><span class="sxs-lookup"><span data-stu-id="08c74-125">Replace the existing code with the following code.</span></span>  
  
     [!code-xaml[PropertyMappingWithWfhSample#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml#1)]  
  
3.  <span data-ttu-id="08c74-126">Откройте файл Window1.xaml.cs в редакторе кода.</span><span class="sxs-lookup"><span data-stu-id="08c74-126">Open Window1.xaml.cs in the Code Editor.</span></span>  
  
4.  <span data-ttu-id="08c74-127">В верхней части файла импортируйте указанные ниже пространства имен.</span><span class="sxs-lookup"><span data-stu-id="08c74-127">At the top of the file, import the following namespaces.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#20)]
     [!code-vb[PropertyMappingWithWfhSample#20](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#20)]  
  
## <a name="defining-a-new-property-mapping"></a><span data-ttu-id="08c74-128">Определение нового сопоставления свойства</span><span class="sxs-lookup"><span data-stu-id="08c74-128">Defining a New Property Mapping</span></span>  
 <span data-ttu-id="08c74-129"><xref:System.Windows.Forms.Integration.WindowsFormsHost> Элемент предоставляет несколько по умолчанию сопоставления свойств.</span><span class="sxs-lookup"><span data-stu-id="08c74-129">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element provides several default property mappings.</span></span> <span data-ttu-id="08c74-130">Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c74-130">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-a-new-property-mapping"></a><span data-ttu-id="08c74-131">Определение нового сопоставления свойства</span><span class="sxs-lookup"><span data-stu-id="08c74-131">To define a new property mapping</span></span>  
  
-   <span data-ttu-id="08c74-132">Скопируйте следующий код в определение `Window1` класса.</span><span class="sxs-lookup"><span data-stu-id="08c74-132">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#14)]
     [!code-vb[PropertyMappingWithWfhSample#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#14)]  
  
     <span data-ttu-id="08c74-133">`AddClipMapping` Метод добавляет новое сопоставление для <xref:System.Windows.UIElement.Clip%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="08c74-133">The `AddClipMapping` method adds a new mapping for the <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="08c74-134">`OnClipChange` Метод переводит <xref:System.Windows.UIElement.Clip%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.Region%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="08c74-134">The `OnClipChange` method translates the <xref:System.Windows.UIElement.Clip%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="08c74-135">`Window1_SizeChanged` Метод обрабатывает окна <xref:System.Windows.FrameworkElement.SizeChanged> событий и размеров области отсечения по размеру окна приложения.</span><span class="sxs-lookup"><span data-stu-id="08c74-135">The `Window1_SizeChanged` method handles the window's <xref:System.Windows.FrameworkElement.SizeChanged> event and sizes the clipping region to fit the application window.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="08c74-136">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-136">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="08c74-137">Удалить сопоставление свойства по умолчанию путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c74-137">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="08c74-138">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-138">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="08c74-139">Скопируйте следующий код в определение `Window1` класса.</span><span class="sxs-lookup"><span data-stu-id="08c74-139">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#13)]
     [!code-vb[PropertyMappingWithWfhSample#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#13)]  
  
     <span data-ttu-id="08c74-140">`RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.Cursor%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="08c74-140">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.FrameworkElement.Cursor%2A> property.</span></span>  
  
## <a name="replacing-a-default-property-mapping"></a><span data-ttu-id="08c74-141">Замена сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-141">Replacing a Default Property Mapping</span></span>  
 <span data-ttu-id="08c74-142">Замените сопоставление свойства по умолчанию, удалив сопоставление по умолчанию и вызывая метод <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.WindowsFormsHost> элемента <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="08c74-142">Replace a default property mapping by removing the default mapping and calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-replace-a-default-property-mapping"></a><span data-ttu-id="08c74-143">Замена сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-143">To replace a default property mapping</span></span>  
  
-   <span data-ttu-id="08c74-144">Скопируйте следующий код в определение `Window1` класса.</span><span class="sxs-lookup"><span data-stu-id="08c74-144">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#12)]
     [!code-vb[PropertyMappingWithWfhSample#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#12)]  
  
     <span data-ttu-id="08c74-145">`ReplaceFlowDirectionMapping` Метод заменяет сопоставление по умолчанию для <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="08c74-145">The `ReplaceFlowDirectionMapping` method replaces the default mapping for the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property.</span></span>  
  
     <span data-ttu-id="08c74-146">`OnFlowDirectionChange` Метод переводит <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Control.RightToLeft%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="08c74-146">The `OnFlowDirectionChange` method translates the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Control.RightToLeft%2A> property.</span></span>  
  
     <span data-ttu-id="08c74-147">`cb_CheckedChanged` Метод обрабатывает <xref:System.Windows.Forms.CheckBox.CheckedChanged> события <xref:System.Windows.Forms.CheckBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="08c74-147">The `cb_CheckedChanged` method handles the <xref:System.Windows.Forms.CheckBox.CheckedChanged> event on the <xref:System.Windows.Forms.CheckBox> control.</span></span> <span data-ttu-id="08c74-148">Он назначает <xref:System.Windows.FrameworkElement.FlowDirection%2A> свойства на основе значения <xref:System.Windows.Forms.CheckBox.CheckState%2A> свойство</span><span class="sxs-lookup"><span data-stu-id="08c74-148">It assigns the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property based on the value of the <xref:System.Windows.Forms.CheckBox.CheckState%2A> property</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="08c74-149">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-149">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="08c74-150">Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="08c74-150">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="08c74-151">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="08c74-151">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="08c74-152">Скопируйте следующий код в определение `Window1` класса.</span><span class="sxs-lookup"><span data-stu-id="08c74-152">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#15)]
     [!code-vb[PropertyMappingWithWfhSample#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#15)]  
  
     <span data-ttu-id="08c74-153">`ExtendBackgroundMapping` Метод добавляет пользовательский преобразователь свойств для существующего <xref:System.Windows.Controls.Control.Background%2A> сопоставление свойств.</span><span class="sxs-lookup"><span data-stu-id="08c74-153">The `ExtendBackgroundMapping` method adds a custom property translator to the existing <xref:System.Windows.Controls.Control.Background%2A> property mapping.</span></span>  
  
     <span data-ttu-id="08c74-154">`OnBackgroundChange` Метод назначает конкретный образ размещенного элемента управления <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="08c74-154">The `OnBackgroundChange` method assigns a specific image to the hosted control's <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span> <span data-ttu-id="08c74-155">`OnBackgroundChange` Метод вызывается после применения сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="08c74-155">The `OnBackgroundChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="08c74-156">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="08c74-156">Initializing Your Property Mappings</span></span>  
 <span data-ttu-id="08c74-157">Настройка сопоставления свойств путем вызова описанных ранее методов <xref:System.Windows.FrameworkElement.Loaded> обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="08c74-157">Set up your property mappings by calling the previously described methods in the <xref:System.Windows.FrameworkElement.Loaded> event handler.</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="08c74-158">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="08c74-158">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="08c74-159">Скопируйте следующий код в определение `Window1` класса.</span><span class="sxs-lookup"><span data-stu-id="08c74-159">Copy the following code into the definition for the `Window1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithWfhSample#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithWfhSample/CSharp/PropertyMappingWithWfh/Window1.xaml.cs#11)]
     [!code-vb[PropertyMappingWithWfhSample#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithWfhSample/VisualBasic/PropertyMappingWithWfh/Window1.xaml.vb#11)]  
  
     <span data-ttu-id="08c74-160">`WindowLoaded` Метод обрабатывает <xref:System.Windows.FrameworkElement.Loaded> событие и выполняет следующую инициализацию.</span><span class="sxs-lookup"><span data-stu-id="08c74-160">The `WindowLoaded` method handles the <xref:System.Windows.FrameworkElement.Loaded> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="08c74-161">Создает [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.CheckBox> управления.</span><span class="sxs-lookup"><span data-stu-id="08c74-161">Creates a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.CheckBox> control.</span></span>  
  
    -   <span data-ttu-id="08c74-162">Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.</span><span class="sxs-lookup"><span data-stu-id="08c74-162">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="08c74-163">Присваивает начальные значения сопоставленным свойствам.</span><span class="sxs-lookup"><span data-stu-id="08c74-163">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="08c74-164">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="08c74-164">Press F5 to build and run the application.</span></span> <span data-ttu-id="08c74-165">Щелкните флажок, чтобы увидеть эффект <xref:System.Windows.FrameworkElement.FlowDirection%2A> сопоставления.</span><span class="sxs-lookup"><span data-stu-id="08c74-165">Click the check box to see the effect of the <xref:System.Windows.FrameworkElement.FlowDirection%2A> mapping.</span></span> <span data-ttu-id="08c74-166">При установке флажка меняется ориентация макета по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="08c74-166">When you click the check box, the layout reverses its left-right orientation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c74-167">См. также</span><span class="sxs-lookup"><span data-stu-id="08c74-167">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="08c74-168">Сопоставление свойств Windows Forms и WPF</span><span class="sxs-lookup"><span data-stu-id="08c74-168">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="08c74-169">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="08c74-169">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="08c74-170">Пошаговое руководство. Размещение элемента управления Windows Forms в приложении WPF</span><span class="sxs-lookup"><span data-stu-id="08c74-170">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)
