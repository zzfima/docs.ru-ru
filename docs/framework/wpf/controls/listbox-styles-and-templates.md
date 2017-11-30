---
title: "Стили и шаблоны элемента ListBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], ListBox
- templates [WPF], ListBox
- states [WPF], ListBox
- ControlTemplate [WPF], ListBox
- parts [WPF], ListBox
- ListBox [WPF], styles and templates
ms.assetid: fc5764cb-c27b-495b-88d4-d969a8213ccb
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: df974b2f6f89c3b62c5039be9cde144d9ef62d14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="listbox-styles-and-templates"></a><span data-ttu-id="6c964-102">Стили и шаблоны элемента ListBox</span><span class="sxs-lookup"><span data-stu-id="6c964-102">ListBox Styles and Templates</span></span>
<span data-ttu-id="6c964-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ListBox> control.</span></span> <span data-ttu-id="6c964-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="6c964-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="6c964-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="listbox-parts"></a><span data-ttu-id="6c964-106">Части ListBox</span><span class="sxs-lookup"><span data-stu-id="6c964-106">ListBox Parts</span></span>  
 <span data-ttu-id="6c964-107"><xref:System.Windows.Controls.ListBox> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="6c964-107">The <xref:System.Windows.Controls.ListBox> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="6c964-108">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ListBox>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="6c964-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ListBox>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="6c964-109">( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.ListBox>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="6c964-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ListBox>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="6c964-110">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="6c964-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="listbox-states"></a><span data-ttu-id="6c964-111">Состояния ListBox</span><span class="sxs-lookup"><span data-stu-id="6c964-111">ListBox States</span></span>  
 <span data-ttu-id="6c964-112">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-112">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="6c964-113">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="6c964-113">VisualState Name</span></span>|<span data-ttu-id="6c964-114">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6c964-114">VisualStateGroup Name</span></span>|<span data-ttu-id="6c964-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6c964-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6c964-116">Valid</span><span class="sxs-lookup"><span data-stu-id="6c964-116">Valid</span></span>|<span data-ttu-id="6c964-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-117">ValidationStates</span></span>|<span data-ttu-id="6c964-118">Элемент управления является допустимым.</span><span class="sxs-lookup"><span data-stu-id="6c964-118">The control is valid.</span></span>|  
|<span data-ttu-id="6c964-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6c964-119">InvalidFocused</span></span>|<span data-ttu-id="6c964-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-120">ValidationStates</span></span>|<span data-ttu-id="6c964-121">Элемент управления не является допустимым и имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6c964-121">The control is not valid and has focus.</span></span>|  
|<span data-ttu-id="6c964-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6c964-122">InvalidUnfocused</span></span>|<span data-ttu-id="6c964-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-123">ValidationStates</span></span>|<span data-ttu-id="6c964-124">Элемент управления не является допустимым и не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6c964-124">The control is not valid and does not have focus.</span></span>|  
  
## <a name="listboxitem-parts"></a><span data-ttu-id="6c964-125">Части ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="6c964-125">ListBoxItem Parts</span></span>  
 <span data-ttu-id="6c964-126"><xref:System.Windows.Controls.ListBoxItem> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="6c964-126">The <xref:System.Windows.Controls.ListBoxItem> control does not have any named parts.</span></span>  
  
## <a name="listboxitem-states"></a><span data-ttu-id="6c964-127">Состояния ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="6c964-127">ListBoxItem States</span></span>  
 <span data-ttu-id="6c964-128">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ListBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-128">The following table lists the visual states for the <xref:System.Windows.Controls.ListBox> control.</span></span>  
  
|<span data-ttu-id="6c964-129">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="6c964-129">VisualState Name</span></span>|<span data-ttu-id="6c964-130">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="6c964-130">VisualStateGroup Name</span></span>|<span data-ttu-id="6c964-131">Описание</span><span class="sxs-lookup"><span data-stu-id="6c964-131">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="6c964-132">Норм.</span><span class="sxs-lookup"><span data-stu-id="6c964-132">Normal</span></span>|<span data-ttu-id="6c964-133">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6c964-133">CommonStates</span></span>|<span data-ttu-id="6c964-134">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6c964-134">The default state.</span></span>|  
|<span data-ttu-id="6c964-135">MouseOver</span><span class="sxs-lookup"><span data-stu-id="6c964-135">MouseOver</span></span>|<span data-ttu-id="6c964-136">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6c964-136">CommonStates</span></span>|<span data-ttu-id="6c964-137">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-137">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="6c964-138">Отключено</span><span class="sxs-lookup"><span data-stu-id="6c964-138">Disabled</span></span>|<span data-ttu-id="6c964-139">CommonStates</span><span class="sxs-lookup"><span data-stu-id="6c964-139">CommonStates</span></span>|<span data-ttu-id="6c964-140">Элемент отключен.</span><span class="sxs-lookup"><span data-stu-id="6c964-140">The item is disabled.</span></span>|  
|<span data-ttu-id="6c964-141">Focused</span><span class="sxs-lookup"><span data-stu-id="6c964-141">Focused</span></span>|<span data-ttu-id="6c964-142">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6c964-142">FocusStates</span></span>|<span data-ttu-id="6c964-143">Элемент имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6c964-143">The item has focus.</span></span>|  
|<span data-ttu-id="6c964-144">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="6c964-144">Unfocused</span></span>|<span data-ttu-id="6c964-145">FocusStates</span><span class="sxs-lookup"><span data-stu-id="6c964-145">FocusStates</span></span>|<span data-ttu-id="6c964-146">Элемент не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6c964-146">The item does not have focus.</span></span>|  
|<span data-ttu-id="6c964-147">Unselected</span><span class="sxs-lookup"><span data-stu-id="6c964-147">Unselected</span></span>|<span data-ttu-id="6c964-148">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6c964-148">SelectionStates</span></span>|<span data-ttu-id="6c964-149">Элемент не выбран.</span><span class="sxs-lookup"><span data-stu-id="6c964-149">The item is not selected.</span></span>|  
|<span data-ttu-id="6c964-150">Selected</span><span class="sxs-lookup"><span data-stu-id="6c964-150">Selected</span></span>|<span data-ttu-id="6c964-151">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6c964-151">SelectionStates</span></span>|<span data-ttu-id="6c964-152">Этот элемент сейчас выбран.</span><span class="sxs-lookup"><span data-stu-id="6c964-152">The item is currentlyplate selected.</span></span>|  
|<span data-ttu-id="6c964-153">SelectedUnfocused</span><span class="sxs-lookup"><span data-stu-id="6c964-153">SelectedUnfocused</span></span>|<span data-ttu-id="6c964-154">SelectionStates</span><span class="sxs-lookup"><span data-stu-id="6c964-154">SelectionStates</span></span>|<span data-ttu-id="6c964-155">Элемент выбран, но не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="6c964-155">The item is selected, but does not have focus.</span></span>|  
|<span data-ttu-id="6c964-156">Valid</span><span class="sxs-lookup"><span data-stu-id="6c964-156">Valid</span></span>|<span data-ttu-id="6c964-157">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-157">ValidationStates</span></span>|<span data-ttu-id="6c964-158">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="6c964-158">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="6c964-159">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="6c964-159">InvalidFocused</span></span>|<span data-ttu-id="6c964-160">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-160">ValidationStates</span></span>|<span data-ttu-id="6c964-161"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6c964-161">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="6c964-162">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="6c964-162">InvalidUnfocused</span></span>|<span data-ttu-id="6c964-163">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="6c964-163">ValidationStates</span></span>|<span data-ttu-id="6c964-164"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="6c964-164">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="listbox-controltemplate-example"></a><span data-ttu-id="6c964-165">Пример шаблона элемента управления ControlTemplate для ListBox</span><span class="sxs-lookup"><span data-stu-id="6c964-165">ListBox ControlTemplate Example</span></span>  
 <span data-ttu-id="6c964-166">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ListBox> и <xref:System.Windows.Controls.ListBoxItem> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="6c964-166">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ListBox> and <xref:System.Windows.Controls.ListBoxItem> controls.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ListBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/listbox.xaml#listbox)]  
  
 <span data-ttu-id="6c964-167">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="6c964-167">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="6c964-168">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="6c964-168">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c964-169">См. также</span><span class="sxs-lookup"><span data-stu-id="6c964-169">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="6c964-170">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="6c964-170">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="6c964-171">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="6c964-171">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="6c964-172">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="6c964-172">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="6c964-173">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="6c964-173">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
