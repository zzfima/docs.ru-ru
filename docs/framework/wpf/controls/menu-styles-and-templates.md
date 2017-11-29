---
title: "Стили и шаблоны элемента Menu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- styles [WPF], Menu
- ControlTemplate [WPF], Menu
- Menu [WPF], styles and templates
- states [WPF], Menu
- templates [WPF], Menu
- parts [WPF], Menu
ms.assetid: b89da183-9b87-42c6-ac53-731a42c7b09e
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e007ae09e57353446feb13b3693e62c985f522d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="menu-styles-and-templates"></a><span data-ttu-id="61c39-102">Стили и шаблоны элемента Menu</span><span class="sxs-lookup"><span data-stu-id="61c39-102">Menu Styles and Templates</span></span>
<span data-ttu-id="61c39-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Menu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Menu> control.</span></span> <span data-ttu-id="61c39-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="61c39-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="61c39-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="menu-parts"></a><span data-ttu-id="61c39-106">Элементы меню</span><span class="sxs-lookup"><span data-stu-id="61c39-106">Menu Parts</span></span>  
 <span data-ttu-id="61c39-107"><xref:System.Windows.Controls.Menu> Управления не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="61c39-107">The <xref:System.Windows.Controls.Menu> control does not have any named parts.</span></span>  
  
 <span data-ttu-id="61c39-108">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Menu>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="61c39-108">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.Menu>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="61c39-109">( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.Menu>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="61c39-109">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.Menu>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="61c39-110">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="61c39-110">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menu-states"></a><span data-ttu-id="61c39-111">Состояния меню</span><span class="sxs-lookup"><span data-stu-id="61c39-111">Menu States</span></span>  
 <span data-ttu-id="61c39-112">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Menu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-112">The following table lists the visual states for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="61c39-113">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="61c39-113">VisualState Name</span></span>|<span data-ttu-id="61c39-114">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="61c39-114">VisualStateGroup Name</span></span>|<span data-ttu-id="61c39-115">Описание</span><span class="sxs-lookup"><span data-stu-id="61c39-115">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61c39-116">Valid</span><span class="sxs-lookup"><span data-stu-id="61c39-116">Valid</span></span>|<span data-ttu-id="61c39-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-117">ValidationStates</span></span>|<span data-ttu-id="61c39-118">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="61c39-118">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="61c39-119">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="61c39-119">InvalidFocused</span></span>|<span data-ttu-id="61c39-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-120">ValidationStates</span></span>|<span data-ttu-id="61c39-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="61c39-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="61c39-122">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="61c39-122">InvalidUnfocused</span></span>|<span data-ttu-id="61c39-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-123">ValidationStates</span></span>|<span data-ttu-id="61c39-124"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="61c39-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menuitem-parts"></a><span data-ttu-id="61c39-125">MenuItem частей</span><span class="sxs-lookup"><span data-stu-id="61c39-125">MenuItem Parts</span></span>  
 <span data-ttu-id="61c39-126">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Menu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-126">The following table lists the named parts for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
|<span data-ttu-id="61c39-127">Отделение</span><span class="sxs-lookup"><span data-stu-id="61c39-127">Part</span></span>|<span data-ttu-id="61c39-128">Тип</span><span class="sxs-lookup"><span data-stu-id="61c39-128">Type</span></span>|<span data-ttu-id="61c39-129">Описание</span><span class="sxs-lookup"><span data-stu-id="61c39-129">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61c39-130">PART_Popup</span><span class="sxs-lookup"><span data-stu-id="61c39-130">PART_Popup</span></span>|<xref:System.Windows.Controls.Primitives.Popup>|<span data-ttu-id="61c39-131">Область подменю.</span><span class="sxs-lookup"><span data-stu-id="61c39-131">The area for the submenu.</span></span>|  
  
 <span data-ttu-id="61c39-132">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.MenuItem>, шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="61c39-132">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.MenuItem>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="61c39-133">( <xref:System.Windows.Controls.ItemsPresenter> Отображает каждый элемент в <xref:System.Windows.Controls.MenuItem>; <xref:System.Windows.Controls.ScrollViewer> разрешает прокрутку в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="61c39-133">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.MenuItem>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="61c39-134">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым потомком <xref:System.Windows.Controls.ScrollViewer>, вы должны предоставить <xref:System.Windows.Controls.ItemsPresenter> имя `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="61c39-134">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="menuitem-states"></a><span data-ttu-id="61c39-135">MenuItem состояний</span><span class="sxs-lookup"><span data-stu-id="61c39-135">MenuItem States</span></span>  
 <span data-ttu-id="61c39-136">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.MenuItem> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-136">The following table lists the visual states for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
|<span data-ttu-id="61c39-137">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="61c39-137">VisualState Name</span></span>|<span data-ttu-id="61c39-138">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="61c39-138">VisualStateGroup Name</span></span>|<span data-ttu-id="61c39-139">Описание</span><span class="sxs-lookup"><span data-stu-id="61c39-139">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="61c39-140">Valid</span><span class="sxs-lookup"><span data-stu-id="61c39-140">Valid</span></span>|<span data-ttu-id="61c39-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-141">ValidationStates</span></span>|<span data-ttu-id="61c39-142">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="61c39-142">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="61c39-143">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="61c39-143">InvalidFocused</span></span>|<span data-ttu-id="61c39-144">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-144">ValidationStates</span></span>|<span data-ttu-id="61c39-145"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="61c39-145">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="61c39-146">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="61c39-146">InvalidUnfocused</span></span>|<span data-ttu-id="61c39-147">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="61c39-147">ValidationStates</span></span>|<span data-ttu-id="61c39-148"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="61c39-148">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="menu-and-menuitem-controltemplate-example"></a><span data-ttu-id="61c39-149">Меню и пример шаблона элемента управления MenuItem</span><span class="sxs-lookup"><span data-stu-id="61c39-149">Menu and MenuItem ControlTemplate Example</span></span>  
 <span data-ttu-id="61c39-150">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Menu> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-150">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Menu> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Menu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menu)]  
  
 <span data-ttu-id="61c39-151">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.MenuItem> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="61c39-151">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.MenuItem> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuItem](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuitem)]  
  
 <span data-ttu-id="61c39-152">В следующем примере определяется `MenuScrollViewer`, который используется в предыдущем примере.</span><span class="sxs-lookup"><span data-stu-id="61c39-152">The following example defines the `MenuScrollViewer`, which is used in the previous example.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#MenuScrollViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/menu.xaml#menuscrollviewer)]  
  
 <span data-ttu-id="61c39-153"><xref:System.Windows.Controls.ControlTemplate> Примерах используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="61c39-153">The <xref:System.Windows.Controls.ControlTemplate> examples use one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="61c39-154">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="61c39-154">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c39-155">См. также</span><span class="sxs-lookup"><span data-stu-id="61c39-155">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="61c39-156">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="61c39-156">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="61c39-157">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="61c39-157">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="61c39-158">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="61c39-158">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="61c39-159">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="61c39-159">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
