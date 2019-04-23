---
title: Стили и шаблоны элемента StatusBar
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], StatusBar
- styles [WPF], StatusBar
- templates [WPF], StatusBar
- states [WPF], StatusBar
- parts [WPF], StatusBar
- StatusBar [WPF], styles and templates
ms.assetid: 9f5e1c25-81eb-4756-a0ac-d9e1fbe33ee2
ms.openlocfilehash: 64b5b66f7f32ea31b51b4da990ceede4078c27cf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59177727"
---
# <a name="statusbar-styles-and-templates"></a><span data-ttu-id="257a5-102">Стили и шаблоны элемента StatusBar</span><span class="sxs-lookup"><span data-stu-id="257a5-102">StatusBar Styles and Templates</span></span>
<span data-ttu-id="257a5-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="257a5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span> <span data-ttu-id="257a5-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="257a5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="257a5-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="257a5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="statusbar-parts"></a><span data-ttu-id="257a5-106">StatusBar частей</span><span class="sxs-lookup"><span data-stu-id="257a5-106">StatusBar Parts</span></span>  
 <span data-ttu-id="257a5-107"><xref:System.Windows.Controls.Primitives.StatusBar> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="257a5-107">The <xref:System.Windows.Controls.Primitives.StatusBar> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="257a5-108">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="257a5-108">StatusBar States</span></span>  
 <span data-ttu-id="257a5-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="257a5-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
|<span data-ttu-id="257a5-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="257a5-110">VisualState Name</span></span>|<span data-ttu-id="257a5-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="257a5-111">VisualStateGroup Name</span></span>|<span data-ttu-id="257a5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="257a5-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="257a5-113">Valid</span><span class="sxs-lookup"><span data-stu-id="257a5-113">Valid</span></span>|<span data-ttu-id="257a5-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-114">ValidationStates</span></span>|<span data-ttu-id="257a5-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="257a5-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="257a5-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="257a5-116">InvalidFocused</span></span>|<span data-ttu-id="257a5-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-117">ValidationStates</span></span>|<span data-ttu-id="257a5-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="257a5-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="257a5-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="257a5-119">InvalidUnfocused</span></span>|<span data-ttu-id="257a5-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-120">ValidationStates</span></span>|<span data-ttu-id="257a5-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="257a5-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbaritem-parts"></a><span data-ttu-id="257a5-122">Элемент управления StatusBarItem частей</span><span class="sxs-lookup"><span data-stu-id="257a5-122">StatusBarItem Parts</span></span>  
 <span data-ttu-id="257a5-123"><xref:System.Windows.Controls.Primitives.StatusBarItem> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="257a5-123">The <xref:System.Windows.Controls.Primitives.StatusBarItem> control does not have any named parts.</span></span>  
  
## <a name="statusbar-states"></a><span data-ttu-id="257a5-124">Состояния StatusBar</span><span class="sxs-lookup"><span data-stu-id="257a5-124">StatusBar States</span></span>  
 <span data-ttu-id="257a5-125">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.StatusBarItem> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="257a5-125">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.StatusBarItem> control.</span></span>  
  
|<span data-ttu-id="257a5-126">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="257a5-126">VisualState Name</span></span>|<span data-ttu-id="257a5-127">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="257a5-127">VisualStateGroup Name</span></span>|<span data-ttu-id="257a5-128">Описание</span><span class="sxs-lookup"><span data-stu-id="257a5-128">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="257a5-129">Valid</span><span class="sxs-lookup"><span data-stu-id="257a5-129">Valid</span></span>|<span data-ttu-id="257a5-130">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-130">ValidationStates</span></span>|<span data-ttu-id="257a5-131">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="257a5-131">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="257a5-132">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="257a5-132">InvalidFocused</span></span>|<span data-ttu-id="257a5-133">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-133">ValidationStates</span></span>|<span data-ttu-id="257a5-134"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="257a5-134">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="257a5-135">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="257a5-135">InvalidUnfocused</span></span>|<span data-ttu-id="257a5-136">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="257a5-136">ValidationStates</span></span>|<span data-ttu-id="257a5-137"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="257a5-137">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="statusbar-controltemplate-example"></a><span data-ttu-id="257a5-138">Пример шаблона элемента управления StatusBar</span><span class="sxs-lookup"><span data-stu-id="257a5-138">StatusBar ControlTemplate Example</span></span>  
 <span data-ttu-id="257a5-139">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.StatusBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="257a5-139">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.StatusBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#StatusBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/statusbar.xaml#statusbar)]  
  
 <span data-ttu-id="257a5-140"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="257a5-140">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="257a5-141">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="257a5-141">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257a5-142">См. также</span><span class="sxs-lookup"><span data-stu-id="257a5-142">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="257a5-143">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="257a5-143">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="257a5-144">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="257a5-144">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="257a5-145">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="257a5-145">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="257a5-146">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="257a5-146">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
