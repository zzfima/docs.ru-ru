---
title: "Стили и шаблоны элемента RadioButton"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], RadioButton
- RadioButton [WPF], styles and templates
- ControlTemplate [WPF], RadioButton
- states [WPF], RadioButton
- templates [WPF], RadioButton
- parts [WPF], RadioButton
ms.assetid: 9acf93f7-dd2f-4010-8ce0-1edd81c52ae2
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 384a587fe01fb69ff5d377f2aa34d03ff110880d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="radiobutton-styles-and-templates"></a><span data-ttu-id="3598c-102">Стили и шаблоны элемента RadioButton</span><span class="sxs-lookup"><span data-stu-id="3598c-102">RadioButton Styles and Templates</span></span>
<span data-ttu-id="3598c-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.RadioButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3598c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.RadioButton> control.</span></span> <span data-ttu-id="3598c-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3598c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="3598c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="3598c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="radiobutton-parts"></a><span data-ttu-id="3598c-106">Элементы RadioButton</span><span class="sxs-lookup"><span data-stu-id="3598c-106">RadioButton Parts</span></span>  
 <span data-ttu-id="3598c-107"><xref:System.Windows.Controls.RadioButton> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="3598c-107">The <xref:System.Windows.Controls.RadioButton> control does not have any named parts.</span></span>  
  
## <a name="radiobutton-states"></a><span data-ttu-id="3598c-108">Состояния RadioButton</span><span class="sxs-lookup"><span data-stu-id="3598c-108">RadioButton States</span></span>  
 <span data-ttu-id="3598c-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.RadioButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3598c-109">The following table lists the visual states for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
|<span data-ttu-id="3598c-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="3598c-110">VisualState Name</span></span>|<span data-ttu-id="3598c-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="3598c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="3598c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="3598c-112">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="3598c-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="3598c-113">Normal</span></span>|<span data-ttu-id="3598c-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3598c-114">CommonStates</span></span>|<span data-ttu-id="3598c-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3598c-115">The default state.</span></span>|  
|<span data-ttu-id="3598c-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="3598c-116">MouseOver</span></span>|<span data-ttu-id="3598c-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3598c-117">CommonStates</span></span>|<span data-ttu-id="3598c-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="3598c-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="3598c-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="3598c-119">Pressed</span></span>|<span data-ttu-id="3598c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3598c-120">CommonStates</span></span>|<span data-ttu-id="3598c-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="3598c-121">The control is pressed.</span></span>|  
|<span data-ttu-id="3598c-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="3598c-122">Disabled</span></span>|<span data-ttu-id="3598c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="3598c-123">CommonStates</span></span>|<span data-ttu-id="3598c-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="3598c-124">The control is disabled.</span></span>|  
|<span data-ttu-id="3598c-125">Focused</span><span class="sxs-lookup"><span data-stu-id="3598c-125">Focused</span></span>|<span data-ttu-id="3598c-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3598c-126">FocusStates</span></span>|<span data-ttu-id="3598c-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3598c-127">The control has focus.</span></span>|  
|<span data-ttu-id="3598c-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="3598c-128">Unfocused</span></span>|<span data-ttu-id="3598c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="3598c-129">FocusStates</span></span>|<span data-ttu-id="3598c-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="3598c-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="3598c-131">Помечено</span><span class="sxs-lookup"><span data-stu-id="3598c-131">Checked</span></span>|<span data-ttu-id="3598c-132">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3598c-132">CheckStates</span></span>|<span data-ttu-id="3598c-133">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `true`.</span><span class="sxs-lookup"><span data-stu-id="3598c-133"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `true`.</span></span>|  
|<span data-ttu-id="3598c-134">флажок снят</span><span class="sxs-lookup"><span data-stu-id="3598c-134">Unchecked</span></span>|<span data-ttu-id="3598c-135">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3598c-135">CheckStates</span></span>|<span data-ttu-id="3598c-136">Свойство <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> имеет значение `false`.</span><span class="sxs-lookup"><span data-stu-id="3598c-136"><xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `false`.</span></span>|  
|<span data-ttu-id="3598c-137">Неопределенный</span><span class="sxs-lookup"><span data-stu-id="3598c-137">Indeterminate</span></span>|<span data-ttu-id="3598c-138">CheckStates</span><span class="sxs-lookup"><span data-stu-id="3598c-138">CheckStates</span></span>|<span data-ttu-id="3598c-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A>— `true`, и <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> — `null`.</span><span class="sxs-lookup"><span data-stu-id="3598c-139"><xref:System.Windows.Controls.Primitives.ToggleButton.IsThreeState%2A> is `true`, and <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> is `null`.</span></span>|  
|<span data-ttu-id="3598c-140">Valid</span><span class="sxs-lookup"><span data-stu-id="3598c-140">Valid</span></span>|<span data-ttu-id="3598c-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3598c-141">ValidationStates</span></span>|<span data-ttu-id="3598c-142">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="3598c-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="3598c-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="3598c-143">InvalidFocused</span></span>|<span data-ttu-id="3598c-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3598c-144">ValidationStates</span></span>|<span data-ttu-id="3598c-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3598c-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="3598c-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="3598c-146">InvalidUnfocused</span></span>|<span data-ttu-id="3598c-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="3598c-147">ValidationStates</span></span>|<span data-ttu-id="3598c-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="3598c-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="radiobutton-controltemplate-example"></a><span data-ttu-id="3598c-149">Пример шаблона элемента управления RadioButton</span><span class="sxs-lookup"><span data-stu-id="3598c-149">RadioButton ControlTemplate Example</span></span>  
 <span data-ttu-id="3598c-150">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.RadioButton> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3598c-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.RadioButton> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#RadioButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/radiobutton.xaml#radiobutton)]  
  
 <span data-ttu-id="3598c-151">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="3598c-151">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="3598c-152">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="3598c-152">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3598c-153">См. также</span><span class="sxs-lookup"><span data-stu-id="3598c-153">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="3598c-154">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="3598c-154">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="3598c-155">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="3598c-155">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="3598c-156">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="3598c-156">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="3598c-157">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="3598c-157">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
