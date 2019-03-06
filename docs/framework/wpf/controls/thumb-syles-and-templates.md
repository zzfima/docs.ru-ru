---
title: Стили и шаблоны элемента Thumb
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Thumb
- styles [WPF], Thumb
- templates [WPF], Thumb
- Thumb [WPF], styles and templates
- ControlTemplate [WPF], Thumb
- parts [WPF], Thumb
ms.assetid: 86a49235-62d9-414e-923e-53126e3f930a
ms.openlocfilehash: ffeec38cef04f49afc114a1946d88621063d700a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367639"
---
# <a name="thumb-syles-and-templates"></a><span data-ttu-id="e6cb9-102">Стили и шаблоны элемента Thumb</span><span class="sxs-lookup"><span data-stu-id="e6cb9-102">Thumb Syles and Templates</span></span>
<span data-ttu-id="e6cb9-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span> <span data-ttu-id="e6cb9-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="e6cb9-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="e6cb9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="thumb-parts"></a><span data-ttu-id="e6cb9-106">Бегунок частей</span><span class="sxs-lookup"><span data-stu-id="e6cb9-106">Thumb Parts</span></span>  
 <span data-ttu-id="e6cb9-107"><xref:System.Windows.Controls.Primitives.Thumb> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-107">The <xref:System.Windows.Controls.Primitives.Thumb> control does not have any named parts.</span></span>  
  
## <a name="thumb-states"></a><span data-ttu-id="e6cb9-108">Бегунок состояний</span><span class="sxs-lookup"><span data-stu-id="e6cb9-108">Thumb States</span></span>  
 <span data-ttu-id="e6cb9-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
|<span data-ttu-id="e6cb9-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="e6cb9-110">VisualState Name</span></span>|<span data-ttu-id="e6cb9-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="e6cb9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="e6cb9-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="e6cb9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="e6cb9-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-113">Normal</span></span>|<span data-ttu-id="e6cb9-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-114">CommonStates</span></span>|<span data-ttu-id="e6cb9-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-115">The default state.</span></span>|  
|<span data-ttu-id="e6cb9-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="e6cb9-116">MouseOver</span></span>|<span data-ttu-id="e6cb9-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-117">CommonStates</span></span>|<span data-ttu-id="e6cb9-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="e6cb9-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="e6cb9-119">Pressed</span></span>|<span data-ttu-id="e6cb9-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-120">CommonStates</span></span>|<span data-ttu-id="e6cb9-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-121">The control is pressed.</span></span>|  
|<span data-ttu-id="e6cb9-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="e6cb9-122">Disabled</span></span>|<span data-ttu-id="e6cb9-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-123">CommonStates</span></span>|<span data-ttu-id="e6cb9-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-124">The control is disabled.</span></span>|  
|<span data-ttu-id="e6cb9-125">Focused</span><span class="sxs-lookup"><span data-stu-id="e6cb9-125">Focused</span></span>|<span data-ttu-id="e6cb9-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-126">FocusStates</span></span>|<span data-ttu-id="e6cb9-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-127">The control has focus.</span></span>|  
|<span data-ttu-id="e6cb9-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="e6cb9-128">Unfocused</span></span>|<span data-ttu-id="e6cb9-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-129">FocusStates</span></span>|<span data-ttu-id="e6cb9-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="e6cb9-131">Valid</span><span class="sxs-lookup"><span data-stu-id="e6cb9-131">Valid</span></span>|<span data-ttu-id="e6cb9-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-132">ValidationStates</span></span>|<span data-ttu-id="e6cb9-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="e6cb9-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="e6cb9-134">InvalidFocused</span></span>|<span data-ttu-id="e6cb9-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-135">ValidationStates</span></span>|<span data-ttu-id="e6cb9-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="e6cb9-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="e6cb9-137">InvalidUnfocused</span></span>|<span data-ttu-id="e6cb9-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="e6cb9-138">ValidationStates</span></span>|<span data-ttu-id="e6cb9-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="thumb-controltemplate-example"></a><span data-ttu-id="e6cb9-140">Пример шаблона элемента управления Thumb</span><span class="sxs-lookup"><span data-stu-id="e6cb9-140">Thumb ControlTemplate Example</span></span>  
 <span data-ttu-id="e6cb9-141">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Primitives.Thumb> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.Thumb> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/slider.xaml#thumb)]  
  
 <span data-ttu-id="e6cb9-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e6cb9-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="e6cb9-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="e6cb9-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6cb9-144">См. также</span><span class="sxs-lookup"><span data-stu-id="e6cb9-144">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="e6cb9-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="e6cb9-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="e6cb9-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="e6cb9-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="e6cb9-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="e6cb9-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="e6cb9-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="e6cb9-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
