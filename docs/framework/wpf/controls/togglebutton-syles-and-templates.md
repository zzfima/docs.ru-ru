---
title: "Стили и шаблоны элемента ToggleButton"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], ToggleButton
- ToggleButton [WPF], styles and templates
- ControlTemplate [WPF], ToggleButton
- styles [WPF], ToggleButton
- templates [WPF], ToggleButton
- parts [WPF], ToggleButton
ms.assetid: 54f23f30-4bcb-4f09-8ce4-376a13a255a1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5c143717b691e79771fbaa55724d9d9748259e3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="togglebutton-syles-and-templates"></a><span data-ttu-id="d0629-102">Стили и шаблоны элемента ToggleButton</span><span class="sxs-lookup"><span data-stu-id="d0629-102">ToggleButton Syles and Templates</span></span>
<span data-ttu-id="d0629-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0629-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span> <span data-ttu-id="d0629-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0629-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d0629-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d0629-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="togglebutton-parts"></a><span data-ttu-id="d0629-106">Элемент управления ToggleButton частей</span><span class="sxs-lookup"><span data-stu-id="d0629-106">ToggleButton Parts</span></span>  
 <span data-ttu-id="d0629-107"><xref:System.Windows.Controls.Primitives.ToggleButton> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="d0629-107">The <xref:System.Windows.Controls.Primitives.ToggleButton> control does not have any named parts.</span></span>  
  
## <a name="togglebutton-states"></a><span data-ttu-id="d0629-108">Элемент управления ToggleButton состояний</span><span class="sxs-lookup"><span data-stu-id="d0629-108">ToggleButton States</span></span>  
 <span data-ttu-id="d0629-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0629-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
|<span data-ttu-id="d0629-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d0629-110">VisualState Name</span></span>|<span data-ttu-id="d0629-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d0629-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d0629-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="d0629-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d0629-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="d0629-113">Normal</span></span>|<span data-ttu-id="d0629-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d0629-114">CommonStates</span></span>|<span data-ttu-id="d0629-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0629-115">The default state.</span></span>|  
|<span data-ttu-id="d0629-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="d0629-116">MouseOver</span></span>|<span data-ttu-id="d0629-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d0629-117">CommonStates</span></span>|<span data-ttu-id="d0629-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="d0629-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="d0629-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="d0629-119">Pressed</span></span>|<span data-ttu-id="d0629-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d0629-120">CommonStates</span></span>|<span data-ttu-id="d0629-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="d0629-121">The control is pressed.</span></span>|  
|<span data-ttu-id="d0629-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="d0629-122">Disabled</span></span>|<span data-ttu-id="d0629-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="d0629-123">CommonStates</span></span>|<span data-ttu-id="d0629-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="d0629-124">The control is disabled.</span></span>|  
|<span data-ttu-id="d0629-125">Focused</span><span class="sxs-lookup"><span data-stu-id="d0629-125">Focused</span></span>|<span data-ttu-id="d0629-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d0629-126">FocusStates</span></span>|<span data-ttu-id="d0629-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d0629-127">The control has focus.</span></span>|  
|<span data-ttu-id="d0629-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="d0629-128">Unfocused</span></span>|<span data-ttu-id="d0629-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="d0629-129">FocusStates</span></span>|<span data-ttu-id="d0629-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d0629-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="d0629-131">Помечено</span><span class="sxs-lookup"><span data-stu-id="d0629-131">Checked</span></span>|<span data-ttu-id="d0629-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d0629-132">CheckStates</span></span>|<span data-ttu-id="d0629-133">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="d0629-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="d0629-134">флажок снят</span><span class="sxs-lookup"><span data-stu-id="d0629-134">Unchecked</span></span>|<span data-ttu-id="d0629-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d0629-135">CheckStates</span></span>|<span data-ttu-id="d0629-136">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="d0629-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="d0629-137">Неопределенный</span><span class="sxs-lookup"><span data-stu-id="d0629-137">Indeterminate</span></span>|<span data-ttu-id="d0629-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="d0629-138">CheckStates</span></span>|<span data-ttu-id="d0629-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>— `true`, и <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> — `null`.</span><span class="sxs-lookup"><span data-stu-id="d0629-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="d0629-140">Valid</span><span class="sxs-lookup"><span data-stu-id="d0629-140">Valid</span></span>|<span data-ttu-id="d0629-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d0629-141">ValidationStates</span></span>|<span data-ttu-id="d0629-142">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="d0629-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d0629-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d0629-143">InvalidFocused</span></span>|<span data-ttu-id="d0629-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d0629-144">ValidationStates</span></span>|<span data-ttu-id="d0629-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d0629-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d0629-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d0629-146">InvalidUnfocused</span></span>|<span data-ttu-id="d0629-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d0629-147">ValidationStates</span></span>|<span data-ttu-id="d0629-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d0629-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d0629-149">Если в шаблоне элемента управления не существует неопределенного визуального состояния, неограниченное визуальное состояние будет использоваться как визуальное состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d0629-149">If the Indeterminate visual state does not exist in your control template, then the Unchecked visual state will be used as default visual state.</span></span>  
  
## <a name="togglebutton-controltemplate-example"></a><span data-ttu-id="d0629-150">Пример шаблона элемента управления ToggleButton</span><span class="sxs-lookup"><span data-stu-id="d0629-150">ToggleButton ControlTemplate Example</span></span>  
 <span data-ttu-id="d0629-151">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.ToggleButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d0629-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ToggleButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToggleButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/combobox.xaml#togglebutton)]  
  
 <span data-ttu-id="d0629-152">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d0629-152">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d0629-153">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="d0629-153">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0629-154">См. также</span><span class="sxs-lookup"><span data-stu-id="d0629-154">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d0629-155">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d0629-155">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d0629-156">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d0629-156">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d0629-157">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d0629-157">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d0629-158">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d0629-158">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
