---
title: Стили и шаблоны элемента Label
ms.date: 03/30/2017
helpviewer_keywords:
- templates [WPF], Label
- parts [WPF], Label
- ControlTemplate [WPF], Label
- styles [WPF], Label
- Label [WPF], styles and templates
- states [WPF], Label
ms.assetid: c1d5359a-8e4a-4925-ab3e-e92bf6694859
ms.openlocfilehash: c3bf4dc629bbb3e4ea21862c6893b001749f4649
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459399"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="ef513-102">Стили и шаблоны элемента Label</span><span class="sxs-lookup"><span data-stu-id="ef513-102">Label Styles and Templates</span></span>
<span data-ttu-id="ef513-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef513-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="ef513-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="ef513-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="ef513-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="ef513-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="ef513-106">Элементы меток</span><span class="sxs-lookup"><span data-stu-id="ef513-106">Label Parts</span></span>  
 <span data-ttu-id="ef513-107">Элемент управления <xref:System.Windows.Controls.Label> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="ef513-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="ef513-108">Состояния меток</span><span class="sxs-lookup"><span data-stu-id="ef513-108">Label States</span></span>  
 <span data-ttu-id="ef513-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef513-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="ef513-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="ef513-110">VisualState Name</span></span>|<span data-ttu-id="ef513-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="ef513-111">VisualStateGroup Name</span></span>|<span data-ttu-id="ef513-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ef513-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="ef513-113">Valid</span><span class="sxs-lookup"><span data-stu-id="ef513-113">Valid</span></span>|<span data-ttu-id="ef513-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef513-114">ValidationStates</span></span>|<span data-ttu-id="ef513-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="ef513-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="ef513-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="ef513-116">InvalidFocused</span></span>|<span data-ttu-id="ef513-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef513-117">ValidationStates</span></span>|<span data-ttu-id="ef513-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="ef513-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="ef513-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="ef513-119">InvalidUnfocused</span></span>|<span data-ttu-id="ef513-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="ef513-120">ValidationStates</span></span>|<span data-ttu-id="ef513-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="ef513-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="ef513-122">Пример создания ControlTemplate для метки</span><span class="sxs-lookup"><span data-stu-id="ef513-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="ef513-123">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="ef513-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="ef513-124"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="ef513-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="ef513-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="ef513-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef513-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ef513-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ef513-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="ef513-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="ef513-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="ef513-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="ef513-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="ef513-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="ef513-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="ef513-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
