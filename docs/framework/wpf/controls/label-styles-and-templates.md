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
ms.openlocfilehash: 35fcd9c15bf44d15a08c16d58847698c5ec6e574
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283504"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="46cf6-102">Стили и шаблоны элемента Label</span><span class="sxs-lookup"><span data-stu-id="46cf6-102">Label Styles and Templates</span></span>
<span data-ttu-id="46cf6-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="46cf6-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="46cf6-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="46cf6-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="46cf6-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="46cf6-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="46cf6-106">Элементы меток</span><span class="sxs-lookup"><span data-stu-id="46cf6-106">Label Parts</span></span>  
 <span data-ttu-id="46cf6-107">Элемент управления <xref:System.Windows.Controls.Label> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="46cf6-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="46cf6-108">Состояния меток</span><span class="sxs-lookup"><span data-stu-id="46cf6-108">Label States</span></span>  
 <span data-ttu-id="46cf6-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="46cf6-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="46cf6-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="46cf6-110">VisualState Name</span></span>|<span data-ttu-id="46cf6-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="46cf6-111">VisualStateGroup Name</span></span>|<span data-ttu-id="46cf6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="46cf6-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="46cf6-113">Valid</span><span class="sxs-lookup"><span data-stu-id="46cf6-113">Valid</span></span>|<span data-ttu-id="46cf6-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46cf6-114">ValidationStates</span></span>|<span data-ttu-id="46cf6-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="46cf6-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="46cf6-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="46cf6-116">InvalidFocused</span></span>|<span data-ttu-id="46cf6-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46cf6-117">ValidationStates</span></span>|<span data-ttu-id="46cf6-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="46cf6-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="46cf6-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="46cf6-119">InvalidUnfocused</span></span>|<span data-ttu-id="46cf6-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="46cf6-120">ValidationStates</span></span>|<span data-ttu-id="46cf6-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="46cf6-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="46cf6-122">Пример создания ControlTemplate для метки</span><span class="sxs-lookup"><span data-stu-id="46cf6-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="46cf6-123">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.Label>.</span><span class="sxs-lookup"><span data-stu-id="46cf6-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="46cf6-124"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="46cf6-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="46cf6-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="46cf6-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46cf6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="46cf6-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="46cf6-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="46cf6-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="46cf6-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="46cf6-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="46cf6-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="46cf6-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="46cf6-130">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="46cf6-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
