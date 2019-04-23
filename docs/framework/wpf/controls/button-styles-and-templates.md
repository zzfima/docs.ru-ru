---
title: Стили и шаблоны элемента Button
ms.date: 03/30/2017
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
ms.openlocfilehash: ec64c7c2051b12cba01135054a90e54864b7386a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116341"
---
# <a name="button-styles-and-templates"></a><span data-ttu-id="0eb85-102">Стили и шаблоны элемента Button</span><span class="sxs-lookup"><span data-stu-id="0eb85-102">Button Styles and Templates</span></span>
<span data-ttu-id="0eb85-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0eb85-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Button> control.</span></span> <span data-ttu-id="0eb85-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0eb85-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="0eb85-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="0eb85-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="button-parts"></a><span data-ttu-id="0eb85-106">Кнопка частей</span><span class="sxs-lookup"><span data-stu-id="0eb85-106">Button Parts</span></span>  
 <span data-ttu-id="0eb85-107"><xref:System.Windows.Controls.Button> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="0eb85-107">The <xref:System.Windows.Controls.Button> control does not have any named parts.</span></span>  
  
## <a name="button-states"></a><span data-ttu-id="0eb85-108">Состояния кнопок</span><span class="sxs-lookup"><span data-stu-id="0eb85-108">Button States</span></span>  
 <span data-ttu-id="0eb85-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0eb85-109">The following table lists the visual states for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
|<span data-ttu-id="0eb85-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="0eb85-110">VisualState Name</span></span>|<span data-ttu-id="0eb85-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="0eb85-111">VisualStateGroup Name</span></span>|<span data-ttu-id="0eb85-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0eb85-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="0eb85-113">Норм.</span><span class="sxs-lookup"><span data-stu-id="0eb85-113">Normal</span></span>|<span data-ttu-id="0eb85-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-114">CommonStates</span></span>|<span data-ttu-id="0eb85-115">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0eb85-115">The default state.</span></span>|  
|<span data-ttu-id="0eb85-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="0eb85-116">MouseOver</span></span>|<span data-ttu-id="0eb85-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-117">CommonStates</span></span>|<span data-ttu-id="0eb85-118">Указатель мыши расположен в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="0eb85-118">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="0eb85-119">Нажато</span><span class="sxs-lookup"><span data-stu-id="0eb85-119">Pressed</span></span>|<span data-ttu-id="0eb85-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-120">CommonStates</span></span>|<span data-ttu-id="0eb85-121">Элемент управления нажат.</span><span class="sxs-lookup"><span data-stu-id="0eb85-121">The control is pressed.</span></span>|  
|<span data-ttu-id="0eb85-122">Отключено</span><span class="sxs-lookup"><span data-stu-id="0eb85-122">Disabled</span></span>|<span data-ttu-id="0eb85-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-123">CommonStates</span></span>|<span data-ttu-id="0eb85-124">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="0eb85-124">The control is disabled.</span></span>|  
|<span data-ttu-id="0eb85-125">Focused</span><span class="sxs-lookup"><span data-stu-id="0eb85-125">Focused</span></span>|<span data-ttu-id="0eb85-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-126">FocusStates</span></span>|<span data-ttu-id="0eb85-127">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="0eb85-127">The control has focus.</span></span>|  
|<span data-ttu-id="0eb85-128">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="0eb85-128">Unfocused</span></span>|<span data-ttu-id="0eb85-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-129">FocusStates</span></span>|<span data-ttu-id="0eb85-130">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="0eb85-130">The control does not have focus.</span></span>|  
|<span data-ttu-id="0eb85-131">Valid</span><span class="sxs-lookup"><span data-stu-id="0eb85-131">Valid</span></span>|<span data-ttu-id="0eb85-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-132">ValidationStates</span></span>|<span data-ttu-id="0eb85-133">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="0eb85-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="0eb85-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="0eb85-134">InvalidFocused</span></span>|<span data-ttu-id="0eb85-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-135">ValidationStates</span></span>|<span data-ttu-id="0eb85-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` и элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="0eb85-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control has focus.</span></span>|  
|<span data-ttu-id="0eb85-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="0eb85-137">InvalidUnfocused</span></span>|<span data-ttu-id="0eb85-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="0eb85-138">ValidationStates</span></span>|<span data-ttu-id="0eb85-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` и элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="0eb85-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` and the control does not have focus.</span></span>|  
  
## <a name="button-controltemplate-example"></a><span data-ttu-id="0eb85-140">Пример шаблона элемента управления кнопки</span><span class="sxs-lookup"><span data-stu-id="0eb85-140">Button ControlTemplate Example</span></span>  
 <span data-ttu-id="0eb85-141">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Button> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0eb85-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Button> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Button](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
 <span data-ttu-id="0eb85-142">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0eb85-142">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="0eb85-143">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="0eb85-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eb85-144">См. также</span><span class="sxs-lookup"><span data-stu-id="0eb85-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="0eb85-145">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="0eb85-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="0eb85-146">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="0eb85-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="0eb85-147">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="0eb85-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="0eb85-148">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="0eb85-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
