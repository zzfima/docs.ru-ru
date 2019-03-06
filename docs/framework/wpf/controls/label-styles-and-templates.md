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
ms.openlocfilehash: e77c27546f4575fb6fae1081ec5a64e904721586
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377538"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="a7ad3-102">Стили и шаблоны элемента Label</span><span class="sxs-lookup"><span data-stu-id="a7ad3-102">Label Styles and Templates</span></span>
<span data-ttu-id="a7ad3-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="a7ad3-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a7ad3-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a7ad3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="a7ad3-106">Метка части</span><span class="sxs-lookup"><span data-stu-id="a7ad3-106">Label Parts</span></span>  
 <span data-ttu-id="a7ad3-107"><xref:System.Windows.Controls.Label> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="a7ad3-108">Метка состояния</span><span class="sxs-lookup"><span data-stu-id="a7ad3-108">Label States</span></span>  
 <span data-ttu-id="a7ad3-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="a7ad3-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="a7ad3-110">VisualState Name</span></span>|<span data-ttu-id="a7ad3-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a7ad3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="a7ad3-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="a7ad3-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a7ad3-113">Valid</span><span class="sxs-lookup"><span data-stu-id="a7ad3-113">Valid</span></span>|<span data-ttu-id="a7ad3-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a7ad3-114">ValidationStates</span></span>|<span data-ttu-id="a7ad3-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a7ad3-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a7ad3-116">InvalidFocused</span></span>|<span data-ttu-id="a7ad3-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a7ad3-117">ValidationStates</span></span>|<span data-ttu-id="a7ad3-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a7ad3-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a7ad3-119">InvalidUnfocused</span></span>|<span data-ttu-id="a7ad3-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a7ad3-120">ValidationStates</span></span>|<span data-ttu-id="a7ad3-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="a7ad3-122">Пример шаблона элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="a7ad3-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="a7ad3-123">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="a7ad3-124"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a7ad3-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a7ad3-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a7ad3-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7ad3-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a7ad3-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a7ad3-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="a7ad3-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a7ad3-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="a7ad3-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a7ad3-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="a7ad3-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="a7ad3-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a7ad3-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
