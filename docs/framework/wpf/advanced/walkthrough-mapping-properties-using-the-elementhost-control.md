---
title: Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mapping properties [WPF]
- ElementHost control [WPF], mapping properties
ms.assetid: bccd6e0d-2272-4924-9107-ff8ed58b88aa
ms.openlocfilehash: b5af1f45a0d01761358e83c890544ec1a11836e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-mapping-properties-using-the-elementhost-control"></a><span data-ttu-id="4f96f-102">Пошаговое руководство. Сопоставление свойств с помощью элемента управления ElementHost</span><span class="sxs-lookup"><span data-stu-id="4f96f-102">Walkthrough: Mapping Properties Using the ElementHost Control</span></span>
<span data-ttu-id="4f96f-103">В этом пошаговом руководстве показано, как использовать <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> свойство для сопоставления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства соответствующим свойствам размещенных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] элемента.</span><span class="sxs-lookup"><span data-stu-id="4f96f-103">This walkthrough shows you how to use the <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A> property to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding properties on a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element.</span></span>  
  
 <span data-ttu-id="4f96f-104">В данном пошаговом руководстве представлены следующие задачи.</span><span class="sxs-lookup"><span data-stu-id="4f96f-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="4f96f-105">Создание проекта.</span><span class="sxs-lookup"><span data-stu-id="4f96f-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="4f96f-106">Определение нового сопоставления свойства.</span><span class="sxs-lookup"><span data-stu-id="4f96f-106">Defining a new property mapping.</span></span>  
  
-   <span data-ttu-id="4f96f-107">Удаление сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f96f-107">Removing a default property mapping.</span></span>  
  
-   <span data-ttu-id="4f96f-108">Расширение сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f96f-108">Extending a default property mapping.</span></span>  
  
 <span data-ttu-id="4f96f-109">Полный пример кода для задач, приведенных в этом пошаговом руководстве, см. [сопоставление свойств с помощью пример элемента управления ElementHost](http://go.microsoft.com/fwlink/?LinkID=160018).</span><span class="sxs-lookup"><span data-stu-id="4f96f-109">For a complete code listing of the tasks illustrated in this walkthrough, see [Mapping Properties Using the ElementHost Control Sample](http://go.microsoft.com/fwlink/?LinkID=160018).</span></span>  
  
 <span data-ttu-id="4f96f-110">Когда вы закончите, можно для сопоставления [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] свойства соответствующее [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойства элемента.</span><span class="sxs-lookup"><span data-stu-id="4f96f-110">When you are finished, you will be able to map [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] properties to corresponding [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] properties on a hosted element.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4f96f-111">Предварительные требования</span><span class="sxs-lookup"><span data-stu-id="4f96f-111">Prerequisites</span></span>  
 <span data-ttu-id="4f96f-112">Ниже приведены компоненты, необходимые для выполнения данного пошагового руководства.</span><span class="sxs-lookup"><span data-stu-id="4f96f-112">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="4f96f-113">.</span><span class="sxs-lookup"><span data-stu-id="4f96f-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="4f96f-114">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4f96f-114">Creating the Project</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="4f96f-115">Создание проекта</span><span class="sxs-lookup"><span data-stu-id="4f96f-115">To create the project</span></span>  
  
1.  <span data-ttu-id="4f96f-116">Создание [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] проект приложения с именем `PropertyMappingWithElementHost`.</span><span class="sxs-lookup"><span data-stu-id="4f96f-116">Create a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project named `PropertyMappingWithElementHost`.</span></span> <span data-ttu-id="4f96f-117">Дополнительные сведения см. в разделе [Практическое руководство. Создание проекта приложения WPF](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span><span class="sxs-lookup"><span data-stu-id="4f96f-117">For more information, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="4f96f-118">В обозревателе решений добавьте ссылки на следующие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сборки.</span><span class="sxs-lookup"><span data-stu-id="4f96f-118">In Solution Explorer, add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies.</span></span>  
  
    -   <span data-ttu-id="4f96f-119">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="4f96f-119">PresentationCore</span></span>  
  
    -   <span data-ttu-id="4f96f-120">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="4f96f-120">PresentationFramework</span></span>  
  
    -   <span data-ttu-id="4f96f-121">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="4f96f-121">WindowsBase</span></span>  
  
    -   <span data-ttu-id="4f96f-122">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="4f96f-122">WindowsFormsIntegration</span></span>  
  
3.  <span data-ttu-id="4f96f-123">Скопируйте следующий код в верхнюю часть `Form1` файл кода.</span><span class="sxs-lookup"><span data-stu-id="4f96f-123">Copy the following code into the top of the `Form1` code file.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#10)]
     [!code-vb[PropertyMappingWithElementHost#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#10)]  
  
4.  <span data-ttu-id="4f96f-124">Откройте `Form1` в конструкторе Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4f96f-124">Open `Form1` in the Windows Forms Designer.</span></span> <span data-ttu-id="4f96f-125">Дважды щелкните форму, чтобы добавить обработчик событий для <xref:System.Windows.Forms.Form.Load> события.</span><span class="sxs-lookup"><span data-stu-id="4f96f-125">Double-click the form to add an event handler for the <xref:System.Windows.Forms.Form.Load> event.</span></span>  
  
5.  <span data-ttu-id="4f96f-126">Вернитесь к конструктору Windows Forms и добавьте обработчик событий для формы <xref:System.Windows.Forms.Control.Resize> событий.</span><span class="sxs-lookup"><span data-stu-id="4f96f-126">Return to the Windows Forms Designer and add an event handler for the form's <xref:System.Windows.Forms.Control.Resize> event.</span></span> <span data-ttu-id="4f96f-127">Дополнительные сведения см. в разделе [как: создание событий обработчики с помощью конструктора](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span><span class="sxs-lookup"><span data-stu-id="4f96f-127">For more information, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
6.  <span data-ttu-id="4f96f-128">Объявите <xref:System.Windows.Forms.Integration.ElementHost> в `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-128">Declare an <xref:System.Windows.Forms.Integration.ElementHost> field in the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#16)]
     [!code-vb[PropertyMappingWithElementHost#16](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#16)]  
  
## <a name="defining-new-property-mappings"></a><span data-ttu-id="4f96f-129">Определение новых сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="4f96f-129">Defining New Property Mappings</span></span>  
 <span data-ttu-id="4f96f-130"><xref:System.Windows.Forms.Integration.ElementHost> Управления предоставляет несколько по умолчанию сопоставления свойств.</span><span class="sxs-lookup"><span data-stu-id="4f96f-130">The <xref:System.Windows.Forms.Integration.ElementHost> control provides several default property mappings.</span></span> <span data-ttu-id="4f96f-131">Добавить новое сопоставление свойства путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f96f-131">You add a new property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Add%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-define-new-property-mappings"></a><span data-ttu-id="4f96f-132">Для определения новых сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="4f96f-132">To define new property mappings</span></span>  
  
1.  <span data-ttu-id="4f96f-133">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-133">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#12)]
     [!code-vb[PropertyMappingWithElementHost#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#12)]  
  
     <span data-ttu-id="4f96f-134">`AddMarginMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Margin%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="4f96f-134">The `AddMarginMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Margin%2A> property.</span></span>  
  
     <span data-ttu-id="4f96f-135">`OnMarginChange` Метод переводит <xref:System.Windows.Forms.Control.Margin%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4f96f-135">The `OnMarginChange` method translates the <xref:System.Windows.Forms.Control.Margin%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement.Margin%2A> property.</span></span>  
  
2.  <span data-ttu-id="4f96f-136">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-136">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#14)]
     [!code-vb[PropertyMappingWithElementHost#14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#14)]  
  
     <span data-ttu-id="4f96f-137">`AddRegionMapping` Метод добавляет новое сопоставление для <xref:System.Windows.Forms.Control.Region%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="4f96f-137">The `AddRegionMapping` method adds a new mapping for the <xref:System.Windows.Forms.Control.Region%2A> property.</span></span>  
  
     <span data-ttu-id="4f96f-138">`OnRegionChange` Метод переводит <xref:System.Windows.Forms.Control.Region%2A> свойства [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4f96f-138">The `OnRegionChange` method translates the <xref:System.Windows.Forms.Control.Region%2A> property to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.UIElement.Clip%2A> property.</span></span>  
  
     <span data-ttu-id="4f96f-139">`Form1_Resize` Метод обрабатывает формы <xref:System.Windows.Forms.Control.Resize> событий и размеров области отсечения для соответствия размещаемому элементу.</span><span class="sxs-lookup"><span data-stu-id="4f96f-139">The `Form1_Resize` method handles the form's <xref:System.Windows.Forms.Control.Resize> event and sizes the clipping region to fit the hosted element.</span></span>  
  
## <a name="removing-a-default-property-mapping"></a><span data-ttu-id="4f96f-140">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f96f-140">Removing a Default Property Mapping</span></span>  
 <span data-ttu-id="4f96f-141">Удалить сопоставление свойства по умолчанию путем вызова <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> метод <xref:System.Windows.Forms.Integration.ElementHost> элемента управления <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f96f-141">Remove a default property mapping by calling the <xref:System.Windows.Forms.Integration.PropertyMap.Remove%2A> method on the <xref:System.Windows.Forms.Integration.ElementHost> control's <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A>.</span></span>  
  
#### <a name="to-remove-a-default-property-mapping"></a><span data-ttu-id="4f96f-142">Удаление сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f96f-142">To remove a default property mapping</span></span>  
  
-   <span data-ttu-id="4f96f-143">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-143">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#13)]
     [!code-vb[PropertyMappingWithElementHost#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#13)]  
  
     <span data-ttu-id="4f96f-144">`RemoveCursorMapping` Метод удаляет сопоставление по умолчанию для <xref:System.Windows.Forms.Control.Cursor%2A> свойства.</span><span class="sxs-lookup"><span data-stu-id="4f96f-144">The `RemoveCursorMapping` method deletes the default mapping for the <xref:System.Windows.Forms.Control.Cursor%2A> property.</span></span>  
  
## <a name="extending-a-default-property-mapping"></a><span data-ttu-id="4f96f-145">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f96f-145">Extending a Default Property Mapping</span></span>  
 <span data-ttu-id="4f96f-146">Вы можете использовать сопоставление свойства по умолчанию, а также расширить его с помощью собственного сопоставления.</span><span class="sxs-lookup"><span data-stu-id="4f96f-146">You can use a default property mapping and also extend it with your own mapping.</span></span>  
  
#### <a name="to-extend-a-default-property-mapping"></a><span data-ttu-id="4f96f-147">Расширение сопоставления свойства по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4f96f-147">To extend a default property mapping</span></span>  
  
-   <span data-ttu-id="4f96f-148">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-148">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#15)]
     [!code-vb[PropertyMappingWithElementHost#15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#15)]  
  
     <span data-ttu-id="4f96f-149">`ExtendBackColorMapping` Метод добавляет пользовательский преобразователь свойств для существующего <xref:System.Windows.Forms.Control.BackColor%2A> сопоставление свойств.</span><span class="sxs-lookup"><span data-stu-id="4f96f-149">The `ExtendBackColorMapping` method adds a custom property translator to the existing <xref:System.Windows.Forms.Control.BackColor%2A> property mapping.</span></span>  
  
     <span data-ttu-id="4f96f-150">`OnBackColorChange` Метод назначает конкретный образ размещенного элемента управления <xref:System.Windows.Controls.Control.Background%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="4f96f-150">The `OnBackColorChange` method assigns a specific image to the hosted control's <xref:System.Windows.Controls.Control.Background%2A> property.</span></span> <span data-ttu-id="4f96f-151">`OnBackColorChange` Метод вызывается после применения сопоставления свойства по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4f96f-151">The `OnBackColorChange` method is called after the default property mapping is applied.</span></span>  
  
## <a name="initializing-your-property-mappings"></a><span data-ttu-id="4f96f-152">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="4f96f-152">Initializing Your Property Mappings</span></span>  
  
#### <a name="to-initialize-your-property-mappings"></a><span data-ttu-id="4f96f-153">Инициализация сопоставлений свойств</span><span class="sxs-lookup"><span data-stu-id="4f96f-153">To initialize your property mappings</span></span>  
  
1.  <span data-ttu-id="4f96f-154">Скопируйте следующий код в определение `Form1` класса.</span><span class="sxs-lookup"><span data-stu-id="4f96f-154">Copy the following code into the definition for the `Form1` class.</span></span>  
  
     [!code-csharp[PropertyMappingWithElementHost#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertyMappingWithElementHost/CSharp/PropertyMappingWithElementHost/Form1.cs#11)]
     [!code-vb[PropertyMappingWithElementHost#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertyMappingWithElementHost/VisualBasic/PropertyMappingWithElementHost/Form1.vb#11)]  
  
     <span data-ttu-id="4f96f-155">`Form1_Load` Метод обрабатывает <xref:System.Windows.Forms.Form.Load> событие и выполняет следующую инициализацию.</span><span class="sxs-lookup"><span data-stu-id="4f96f-155">The `Form1_Load` method handles the <xref:System.Windows.Forms.Form.Load> event and performs the following initialization.</span></span>  
  
    -   <span data-ttu-id="4f96f-156">Создает [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> элемента.</span><span class="sxs-lookup"><span data-stu-id="4f96f-156">Creates a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Button> element.</span></span>  
  
    -   <span data-ttu-id="4f96f-157">Вызывает методы, ранее определенные в руководстве, для настройки сопоставлений свойств.</span><span class="sxs-lookup"><span data-stu-id="4f96f-157">Calls the methods you defined earlier in the walkthrough to set up the property mappings.</span></span>  
  
    -   <span data-ttu-id="4f96f-158">Присваивает начальные значения сопоставленным свойствам.</span><span class="sxs-lookup"><span data-stu-id="4f96f-158">Assigns initial values to the mapped properties.</span></span>  
  
2.  <span data-ttu-id="4f96f-159">Нажмите клавишу F5, чтобы выполнить сборку приложения и запустить его.</span><span class="sxs-lookup"><span data-stu-id="4f96f-159">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f96f-160">См. также</span><span class="sxs-lookup"><span data-stu-id="4f96f-160">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost.PropertyMap%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="4f96f-161">Сопоставление свойств Windows Forms и WPF</span><span class="sxs-lookup"><span data-stu-id="4f96f-161">Windows Forms and WPF Property Mapping</span></span>](../../../../docs/framework/wpf/advanced/windows-forms-and-wpf-property-mapping.md)  
 [<span data-ttu-id="4f96f-162">Конструктор WPF</span><span class="sxs-lookup"><span data-stu-id="4f96f-162">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="4f96f-163">Пошаговое руководство. Размещение составного элемента управления WPF в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4f96f-163">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
