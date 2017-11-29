---
title: "Стили и шаблоны элемента CheckBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], CheckBox
- templates [WPF], CheckBox
- parts [WPF], CheckBox
- ControlTemplate [WPF], CheckBox
- CheckBox [WPF], styles and templates
- styles [WPF], CheckBox
ms.assetid: bfdaec96-d101-4d3d-864d-c27e6b621d03
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9c901d710e96cd111104b9fef2219b157377adc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="checkbox-styles-and-templates"></a><span data-ttu-id="ba634-102">Стили и шаблоны элемента CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba634-102">CheckBox Styles and Templates</span></span>
<span data-ttu-id="ba634-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.CheckBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba634-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.CheckBox> control.</span></span> <span data-ttu-id="ba634-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba634-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ba634-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ba634-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="checkbox-parts"></a><span data-ttu-id="ba634-106">Флажок частей</span><span class="sxs-lookup"><span data-stu-id="ba634-106">CheckBox Parts</span></span>  
 <span data-ttu-id="ba634-107"><xref:System.Windows.Controls.CheckBox> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="ba634-107">The <xref:System.Windows.Controls.CheckBox> control does not have any named parts.</span></span>  
  
## <a name="checkbox-states"></a><span data-ttu-id="ba634-108">Состояния CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba634-108">CheckBox States</span></span>  
 <span data-ttu-id="ba634-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.CheckBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba634-109">The following table lists the visual states for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
|<span data-ttu-id="ba634-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="ba634-110">VisualState Name</span></span>|<span data-ttu-id="ba634-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ba634-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ba634-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ba634-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="ba634-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="ba634-113">Normal</span></span>|<span data-ttu-id="ba634-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-114">CommonStates</span></span>|<span data-ttu-id="ba634-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ba634-115">The default state.</span></span>|  
|<span data-ttu-id="ba634-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="ba634-116">MouseOver</span></span>|<span data-ttu-id="ba634-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-117">CommonStates</span></span>|<span data-ttu-id="ba634-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="ba634-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="ba634-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="ba634-119">Pressed</span></span>|<span data-ttu-id="ba634-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-120">CommonStates</span></span>|<span data-ttu-id="ba634-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="ba634-121">The control is pressed.</span></span>|  
|<span data-ttu-id="ba634-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="ba634-122">Disabled</span></span>|<span data-ttu-id="ba634-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="ba634-123">CommonStates</span></span>|<span data-ttu-id="ba634-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="ba634-124">The control is disabled.</span></span>|  
|<span data-ttu-id="ba634-125">Focused</span><span class="sxs-lookup"><span data-stu-id="ba634-125">Focused</span></span>|<span data-ttu-id="ba634-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba634-126">FocusStates</span></span>|<span data-ttu-id="ba634-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ba634-127">The control has focus.</span></span>|  
|<span data-ttu-id="ba634-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="ba634-128">Unfocused</span></span>|<span data-ttu-id="ba634-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="ba634-129">FocusStates</span></span>|<span data-ttu-id="ba634-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="ba634-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="ba634-131">Помечено</span><span class="sxs-lookup"><span data-stu-id="ba634-131">Checked</span></span>|<span data-ttu-id="ba634-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ba634-132">CheckStates</span></span>|<span data-ttu-id="ba634-133">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="ba634-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="ba634-134">флажок снят</span><span class="sxs-lookup"><span data-stu-id="ba634-134">Unchecked</span></span>|<span data-ttu-id="ba634-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ba634-135">CheckStates</span></span>|<span data-ttu-id="ba634-136">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="ba634-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="ba634-137">Неопределенный</span><span class="sxs-lookup"><span data-stu-id="ba634-137">Indeterminate</span></span>|<span data-ttu-id="ba634-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="ba634-138">CheckStates</span></span>|<span data-ttu-id="ba634-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>— `true`, и <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> — `null`.</span><span class="sxs-lookup"><span data-stu-id="ba634-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="ba634-140">Valid</span><span class="sxs-lookup"><span data-stu-id="ba634-140">Valid</span></span>|<span data-ttu-id="ba634-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-141">ValidationStates</span></span>|<span data-ttu-id="ba634-142">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="ba634-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ba634-143">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ba634-143">InvalidUnfocused</span></span>|<span data-ttu-id="ba634-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-144">ValidationStates</span></span>|<span data-ttu-id="ba634-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ba634-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ba634-146">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ba634-146">InvalidFocused</span></span>|<span data-ttu-id="ba634-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ba634-147">ValidationStates</span></span>|<span data-ttu-id="ba634-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ba634-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="checkbox-controltemplate-example"></a><span data-ttu-id="ba634-149">Пример шаблона элемента управления CheckBox</span><span class="sxs-lookup"><span data-stu-id="ba634-149">CheckBox ControlTemplate Example</span></span>  
 <span data-ttu-id="ba634-150">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.CheckBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ba634-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.CheckBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#CheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/checkbox.xaml#checkbox)]  
  
 <span data-ttu-id="ba634-151">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ba634-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ba634-152">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="ba634-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba634-153">См. также</span><span class="sxs-lookup"><span data-stu-id="ba634-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="ba634-154">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="ba634-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="ba634-155">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="ba634-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="ba634-156">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="ba634-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="ba634-157">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ba634-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
