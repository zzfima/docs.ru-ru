---
title: Стили и шаблоны элемента ToolTip
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ToolTip
- styles [WPF], ToolTip
- states [WPF], ToolTip
- ToolTip [WPF], styles and templates
- ControlTemplate [WPF], ToolTip
- templates [WPF], ToolTip
ms.assetid: 405fe385-4de9-49ee-a448-d8f4d1f740dd
ms.openlocfilehash: 626d0b4d49d653f820d1506f0aa09f06d26352c2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458643"
---
# <a name="tooltip-styles-and-templates"></a><span data-ttu-id="e507d-102">Стили и шаблоны элемента ToolTip</span><span class="sxs-lookup"><span data-stu-id="e507d-102">ToolTip Styles and Templates</span></span>
<span data-ttu-id="e507d-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="e507d-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ToolTip> control.</span></span> <span data-ttu-id="e507d-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e507d-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e507d-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e507d-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="tooltip-parts"></a><span data-ttu-id="e507d-106">Элементы подсказки</span><span class="sxs-lookup"><span data-stu-id="e507d-106">ToolTip Parts</span></span>  
 <span data-ttu-id="e507d-107">Элемент управления <xref:System.Windows.Controls.ToolTip> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="e507d-107">The <xref:System.Windows.Controls.ToolTip> control does not have any named parts.</span></span>  
  
## <a name="tooltip-states"></a><span data-ttu-id="e507d-108">Состояния подсказки</span><span class="sxs-lookup"><span data-stu-id="e507d-108">ToolTip States</span></span>  
 <span data-ttu-id="e507d-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="e507d-109">The following table lists the visual states for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
|<span data-ttu-id="e507d-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e507d-110">VisualState Name</span></span>|<span data-ttu-id="e507d-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e507d-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e507d-112">Описание</span><span class="sxs-lookup"><span data-stu-id="e507d-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e507d-113">Закрыто</span><span class="sxs-lookup"><span data-stu-id="e507d-113">Closed</span></span>|<span data-ttu-id="e507d-114">опенстатес</span><span class="sxs-lookup"><span data-stu-id="e507d-114">OpenStates</span></span>|<span data-ttu-id="e507d-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e507d-115">The default state.</span></span>|  
|<span data-ttu-id="e507d-116">Открыть</span><span class="sxs-lookup"><span data-stu-id="e507d-116">Open</span></span>|<span data-ttu-id="e507d-117">опенстатес</span><span class="sxs-lookup"><span data-stu-id="e507d-117">OpenStates</span></span>|<span data-ttu-id="e507d-118">Отображается <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="e507d-118">The <xref:System.Windows.Controls.ToolTip> is visible.</span></span>|  
|<span data-ttu-id="e507d-119">Valid</span><span class="sxs-lookup"><span data-stu-id="e507d-119">Valid</span></span>|<span data-ttu-id="e507d-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e507d-120">ValidationStates</span></span>|<span data-ttu-id="e507d-121">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="e507d-121">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e507d-122">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e507d-122">InvalidFocused</span></span>|<span data-ttu-id="e507d-123">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e507d-123">ValidationStates</span></span>|<span data-ttu-id="e507d-124">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e507d-124">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e507d-125">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e507d-125">InvalidUnfocused</span></span>|<span data-ttu-id="e507d-126">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e507d-126">ValidationStates</span></span>|<span data-ttu-id="e507d-127">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e507d-127">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="tooltip-controltemplate-example"></a><span data-ttu-id="e507d-128">Пример ControlTemplate в подсказке</span><span class="sxs-lookup"><span data-stu-id="e507d-128">ToolTip ControlTemplate Example</span></span>  
 <span data-ttu-id="e507d-129">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.ToolTip>.</span><span class="sxs-lookup"><span data-stu-id="e507d-129">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ToolTip> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ToolTip](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/tooltip.xaml#tooltip)]  
  
 <span data-ttu-id="e507d-130">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e507d-130">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e507d-131">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e507d-131">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e507d-132">См. также</span><span class="sxs-lookup"><span data-stu-id="e507d-132">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e507d-133">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e507d-133">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e507d-134">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e507d-134">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e507d-135">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e507d-135">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="e507d-136">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e507d-136">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
