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
ms.openlocfilehash: f30a0abb3e4252737e513b531b8d5f49a0d47f0b
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458442"
---
# <a name="scrollbar-styles-and-templates"></a><span data-ttu-id="0c416-102">Стили и шаблоны элемента ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0c416-102">ScrollBar Styles and Templates</span></span>
<span data-ttu-id="0c416-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0c416-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span> <span data-ttu-id="0c416-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0c416-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0c416-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0c416-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="scrollbar-parts"></a><span data-ttu-id="0c416-106">Элементы полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="0c416-106">ScrollBar Parts</span></span>  
 <span data-ttu-id="0c416-107">В следующей таблице перечислены именованные части для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0c416-107">The following table lists the named parts for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0c416-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="0c416-108">Part</span></span>|<span data-ttu-id="0c416-109">Type</span><span class="sxs-lookup"><span data-stu-id="0c416-109">Type</span></span>|<span data-ttu-id="0c416-110">Описание</span><span class="sxs-lookup"><span data-stu-id="0c416-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0c416-111">PART_Track</span><span class="sxs-lookup"><span data-stu-id="0c416-111">PART_Track</span></span>|<xref:System.Windows.Controls.Primitives.Track>|<span data-ttu-id="0c416-112">Контейнер для элемента, указывающий расположение <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0c416-112">The container for the element that indicates the position of the <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>|  
  
## <a name="scrollbar-states"></a><span data-ttu-id="0c416-113">Состояния полосы прокрутки</span><span class="sxs-lookup"><span data-stu-id="0c416-113">ScrollBar States</span></span>  
 <span data-ttu-id="0c416-114">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0c416-114">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
|<span data-ttu-id="0c416-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="0c416-115">VisualState Name</span></span>|<span data-ttu-id="0c416-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0c416-116">VisualStateGroup Name</span></span>|<span data-ttu-id="0c416-117">Описание</span><span class="sxs-lookup"><span data-stu-id="0c416-117">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="0c416-118">Норм.</span><span class="sxs-lookup"><span data-stu-id="0c416-118">Normal</span></span>|<span data-ttu-id="0c416-119">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0c416-119">CommonStates</span></span>|<span data-ttu-id="0c416-120">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0c416-120">The default state.</span></span>|  
|<span data-ttu-id="0c416-121">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0c416-121">MouseOver</span></span>|<span data-ttu-id="0c416-122">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0c416-122">CommonStates</span></span>|<span data-ttu-id="0c416-123">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="0c416-123">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0c416-124">Отключено.</span><span class="sxs-lookup"><span data-stu-id="0c416-124">Disabled</span></span>|<span data-ttu-id="0c416-125">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0c416-125">CommonStates</span></span>|<span data-ttu-id="0c416-126">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="0c416-126">The control is disabled.</span></span>|  
|<span data-ttu-id="0c416-127">Valid</span><span class="sxs-lookup"><span data-stu-id="0c416-127">Valid</span></span>|<span data-ttu-id="0c416-128">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c416-128">ValidationStates</span></span>|<span data-ttu-id="0c416-129">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="0c416-129">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0c416-130">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0c416-130">InvalidFocused</span></span>|<span data-ttu-id="0c416-131">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c416-131">ValidationStates</span></span>|<span data-ttu-id="0c416-132"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="0c416-132">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="0c416-133">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0c416-133">InvalidUnfocused</span></span>|<span data-ttu-id="0c416-134">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0c416-134">ValidationStates</span></span>|<span data-ttu-id="0c416-135"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `true`, а элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="0c416-135">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="scrollbar-controltemplate-example"></a><span data-ttu-id="0c416-136">Пример элемента ControlTemplate для элемента управления ScrollBar</span><span class="sxs-lookup"><span data-stu-id="0c416-136">ScrollBar ControlTemplate Example</span></span>  
 <span data-ttu-id="0c416-137">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Primitives.ScrollBar>.</span><span class="sxs-lookup"><span data-stu-id="0c416-137">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.ScrollBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ScrollBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#scrollbar)]  
  
 <span data-ttu-id="0c416-138">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0c416-138">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0c416-139">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0c416-139">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c416-140">См. также</span><span class="sxs-lookup"><span data-stu-id="0c416-140">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0c416-141">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="0c416-141">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0c416-142">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="0c416-142">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0c416-143">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="0c416-143">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="0c416-144">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0c416-144">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
