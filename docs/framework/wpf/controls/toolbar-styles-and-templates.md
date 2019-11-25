---
title: Стили и шаблоны элемента ToolBar
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], ToolBar
- styles [WPF], ToolBar
- ControlTemplate [WPF], ToolBar
- parts [WPF], ToolBar
- ToolBar [WPF], styles and templates
- templates [WPF], ToolBar
ms.assetid: bd875f46-4690-46f5-81e0-f11a9822484f
ms.openlocfilehash: a984311234386cb205d5db35f18a743ca535ff05
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283659"
---
# <a name="toolbar-styles-and-templates"></a><span data-ttu-id="dae0b-102">Стили и шаблоны элемента ToolBar</span><span class="sxs-lookup"><span data-stu-id="dae0b-102">ToolBar Styles and Templates</span></span>
<span data-ttu-id="dae0b-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolBar> control.</span></span> <span data-ttu-id="dae0b-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="dae0b-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="dae0b-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="dae0b-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="toolbar-parts"></a><span data-ttu-id="dae0b-106">Части панели инструментов</span><span class="sxs-lookup"><span data-stu-id="dae0b-106">ToolBar Parts</span></span>  
 <span data-ttu-id="dae0b-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-107">The following table lists the named parts for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="dae0b-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="dae0b-108">Part</span></span>|<span data-ttu-id="dae0b-109">Type</span><span class="sxs-lookup"><span data-stu-id="dae0b-109">Type</span></span>|<span data-ttu-id="dae0b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="dae0b-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="dae0b-111">PART_ToolBarPanel</span><span class="sxs-lookup"><span data-stu-id="dae0b-111">PART_ToolBarPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarPanel>|<span data-ttu-id="dae0b-112">Объект, содержащий элементы управления в <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-112">The object that contains the controls on the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
|<span data-ttu-id="dae0b-113">PART_ToolBarOverflowPanel</span><span class="sxs-lookup"><span data-stu-id="dae0b-113">PART_ToolBarOverflowPanel</span></span>|<xref:System.Windows.Controls.Primitives.ToolBarOverflowPanel>|<span data-ttu-id="dae0b-114">Объект, содержащий элементы управления, которые находятся в области переполнения <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-114">The object that contains the controls that are in the overflow area of the <xref:System.Windows.Controls.ToolBar>.</span></span>|  
  
 <span data-ttu-id="dae0b-115">При создании <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ToolBar>шаблон может содержать <xref:System.Windows.Controls.ItemsPresenter> в пределах <xref:System.Windows.Controls.ScrollViewer>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-115">When you create a <xref:System.Windows.Controls.ControlTemplate> for a <xref:System.Windows.Controls.ToolBar>, your template might contain an <xref:System.Windows.Controls.ItemsPresenter> within a <xref:System.Windows.Controls.ScrollViewer>.</span></span> <span data-ttu-id="dae0b-116">(<xref:System.Windows.Controls.ItemsPresenter> отображает каждый элемент в <xref:System.Windows.Controls.ToolBar>; <xref:System.Windows.Controls.ScrollViewer> включает прокрутку в элементе управления).</span><span class="sxs-lookup"><span data-stu-id="dae0b-116">(The <xref:System.Windows.Controls.ItemsPresenter> displays each item in the <xref:System.Windows.Controls.ToolBar>; the <xref:System.Windows.Controls.ScrollViewer> enables scrolling within the control).</span></span>  <span data-ttu-id="dae0b-117">Если <xref:System.Windows.Controls.ItemsPresenter> не является прямым дочерним элементом <xref:System.Windows.Controls.ScrollViewer>, необходимо присвоить <xref:System.Windows.Controls.ItemsPresenter> имя, `ItemsPresenter`.</span><span class="sxs-lookup"><span data-stu-id="dae0b-117">If the <xref:System.Windows.Controls.ItemsPresenter> is not the direct child of the <xref:System.Windows.Controls.ScrollViewer>, you must give the <xref:System.Windows.Controls.ItemsPresenter> the name, `ItemsPresenter`.</span></span>  
  
## <a name="toolbar-states"></a><span data-ttu-id="dae0b-118">Состояния панелей инструментов</span><span class="sxs-lookup"><span data-stu-id="dae0b-118">ToolBar States</span></span>  
 <span data-ttu-id="dae0b-119">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-119">The following table lists the visual states for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
|<span data-ttu-id="dae0b-120">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="dae0b-120">VisualState Name</span></span>|<span data-ttu-id="dae0b-121">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="dae0b-121">VisualStateGroup Name</span></span>|<span data-ttu-id="dae0b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="dae0b-122">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="dae0b-123">Valid</span><span class="sxs-lookup"><span data-stu-id="dae0b-123">Valid</span></span>|<span data-ttu-id="dae0b-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dae0b-124">ValidationStates</span></span>|<span data-ttu-id="dae0b-125">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="dae0b-125">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="dae0b-126">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="dae0b-126">InvalidFocused</span></span>|<span data-ttu-id="dae0b-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dae0b-127">ValidationStates</span></span>|<span data-ttu-id="dae0b-128">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="dae0b-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="dae0b-129">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="dae0b-129">InvalidUnfocused</span></span>|<span data-ttu-id="dae0b-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="dae0b-130">ValidationStates</span></span>|<span data-ttu-id="dae0b-131">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="dae0b-131">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="toolbar-controltemplate-example"></a><span data-ttu-id="dae0b-132">Пример панели инструментов ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="dae0b-132">ToolBar ControlTemplate Example</span></span>  
 <span data-ttu-id="dae0b-133">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ToolBar>.</span><span class="sxs-lookup"><span data-stu-id="dae0b-133">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/toolbar.xaml#toolbar)]  
  
 <span data-ttu-id="dae0b-134">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="dae0b-134">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="dae0b-135">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="dae0b-135">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dae0b-136">См. также</span><span class="sxs-lookup"><span data-stu-id="dae0b-136">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="dae0b-137">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="dae0b-137">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="dae0b-138">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="dae0b-138">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="dae0b-139">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="dae0b-139">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="dae0b-140">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="dae0b-140">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
