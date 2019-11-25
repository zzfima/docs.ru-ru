---
title: Стили и шаблоны элемента ScrollBar
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], ScrollBar
- ControlTemplate [WPF], ScrollBar
- states [WPF], ScrollBar
- ScrollBar [WPF], styles and templates
- templates [WPF], ScrollBar
- parts [WPF], ScrollBar
ms.assetid: 066ea45a-e27d-43b0-adfe-cce6934c22f5
ms.openlocfilehash: 7093a78555aefd73f9bb05c0a7b5fab6b66176fc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283415"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="e7ff3-102">Стили и шаблоны элемента ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e7ff3-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="e7ff3-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="e7ff3-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e7ff3-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="e7ff3-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="e7ff3-106">Элементы полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="e7ff3-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="e7ff3-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="e7ff3-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="e7ff3-108">Part</span></span>|<span data-ttu-id="e7ff3-109">Type</span><span class="sxs-lookup"><span data-stu-id="e7ff3-109">Type</span></span>|<span data-ttu-id="e7ff3-110">Описание</span><span class="sxs-lookup"><span data-stu-id="e7ff3-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e7ff3-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="e7ff3-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="e7ff3-112">Контейнер для элемента, указывающий расположение <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="e7ff3-113">Состояния полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="e7ff3-113">ScrollBar States</span></span>  
 <span data-ttu-id="e7ff3-114">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="e7ff3-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e7ff3-115">VisualState Name</span></span>|<span data-ttu-id="e7ff3-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e7ff3-116">VisualStateGroup Name</span></span>|<span data-ttu-id="e7ff3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="e7ff3-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="e7ff3-118">Норм.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-118">Normal</span></span>|<span data-ttu-id="e7ff3-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-119">CommonStates</span></span>|<span data-ttu-id="e7ff3-120">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-120">The default state.</span></span>|  
|<span data-ttu-id="e7ff3-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e7ff3-121">MouseOver</span></span>|<span data-ttu-id="e7ff3-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-122">CommonStates</span></span>|<span data-ttu-id="e7ff3-123">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="e7ff3-124">Отключено.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-124">Disabled</span></span>|<span data-ttu-id="e7ff3-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-125">CommonStates</span></span>|<span data-ttu-id="e7ff3-126">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-126">The control is disabled.</span></span>|  
|<span data-ttu-id="e7ff3-127">Valid</span><span class="sxs-lookup"><span data-stu-id="e7ff3-127">Valid</span></span>|<span data-ttu-id="e7ff3-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-128">ValidationStates</span></span>|<span data-ttu-id="e7ff3-129">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e7ff3-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e7ff3-130">InvalidFocused</span></span>|<span data-ttu-id="e7ff3-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-131">ValidationStates</span></span>|<span data-ttu-id="e7ff3-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="e7ff3-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e7ff3-133">InvalidUnfocused</span></span>|<span data-ttu-id="e7ff3-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e7ff3-134">ValidationStates</span></span>|<span data-ttu-id="e7ff3-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="e7ff3-136">Пример элемента ControlTemplate для элемента управления ScrollBar</span><span class="sxs-lookup"><span data-stu-id="e7ff3-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="e7ff3-137">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="e7ff3-138">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e7ff3-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e7ff3-139">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e7ff3-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ff3-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e7ff3-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e7ff3-141">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e7ff3-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e7ff3-142">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e7ff3-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e7ff3-143">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e7ff3-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e7ff3-144">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="e7ff3-144">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
