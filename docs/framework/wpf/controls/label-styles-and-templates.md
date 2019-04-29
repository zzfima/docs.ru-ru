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
ms.openlocfilehash: d2bb348fc9c0348fd8093452e022df7ab4e0b3f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696253"
---
# <a name="label-styles-and-templates"></a><span data-ttu-id="7f33c-102">Стили и шаблоны элемента Label</span><span class="sxs-lookup"><span data-stu-id="7f33c-102">Label Styles and Templates</span></span>
<span data-ttu-id="7f33c-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f33c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Label> control.</span></span> <span data-ttu-id="7f33c-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f33c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7f33c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="7f33c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="label-parts"></a><span data-ttu-id="7f33c-106">Метка части</span><span class="sxs-lookup"><span data-stu-id="7f33c-106">Label Parts</span></span>  
 <span data-ttu-id="7f33c-107"><xref:System.Windows.Controls.Label> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="7f33c-107">The <xref:System.Windows.Controls.Label> control does not have any named parts.</span></span>  
  
## <a name="label-states"></a><span data-ttu-id="7f33c-108">Метка состояния</span><span class="sxs-lookup"><span data-stu-id="7f33c-108">Label States</span></span>  
 <span data-ttu-id="7f33c-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f33c-109">The following table lists the visual states for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
|<span data-ttu-id="7f33c-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="7f33c-110">VisualState Name</span></span>|<span data-ttu-id="7f33c-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="7f33c-111">VisualStateGroup Name</span></span>|<span data-ttu-id="7f33c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="7f33c-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7f33c-113">Valid</span><span class="sxs-lookup"><span data-stu-id="7f33c-113">Valid</span></span>|<span data-ttu-id="7f33c-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f33c-114">ValidationStates</span></span>|<span data-ttu-id="7f33c-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="7f33c-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7f33c-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7f33c-116">InvalidFocused</span></span>|<span data-ttu-id="7f33c-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f33c-117">ValidationStates</span></span>|<span data-ttu-id="7f33c-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="7f33c-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7f33c-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7f33c-119">InvalidUnfocused</span></span>|<span data-ttu-id="7f33c-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7f33c-120">ValidationStates</span></span>|<span data-ttu-id="7f33c-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="7f33c-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="label-controltemplate-example"></a><span data-ttu-id="7f33c-122">Пример шаблона элемента управления Label</span><span class="sxs-lookup"><span data-stu-id="7f33c-122">Label ControlTemplate Example</span></span>  
 <span data-ttu-id="7f33c-123">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Label> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7f33c-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Label> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Label](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/label.xaml#label)]  
  
 <span data-ttu-id="7f33c-124"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7f33c-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7f33c-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="7f33c-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f33c-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7f33c-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7f33c-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="7f33c-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7f33c-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="7f33c-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7f33c-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="7f33c-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="7f33c-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7f33c-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
