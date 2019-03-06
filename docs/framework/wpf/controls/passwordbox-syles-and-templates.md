---
title: Стили и шаблоны элемента PasswordBox
ms.date: 03/30/2017
helpviewer_keywords:
- styles [WPF], PasswordBox
- templates [WPF], PasswordBox
- ControlTemplate [WPF], PasswordBox
- states [WPF], PasswordBox
- PasswordBox [WPF], styles and templates
- parts [WPF], PasswordBox
ms.assetid: deb52107-959f-4a60-b303-d21a0a933060
ms.openlocfilehash: ddc0a2a01b78a01e8f90c26df9b91521ebfa9bf5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377733"
---
# <a name="passwordbox-syles-and-templates"></a><span data-ttu-id="7d09c-102">Стили и шаблоны элемента PasswordBox</span><span class="sxs-lookup"><span data-stu-id="7d09c-102">PasswordBox Syles and Templates</span></span>
<span data-ttu-id="7d09c-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.PasswordBox> control.</span></span> <span data-ttu-id="7d09c-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="7d09c-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="7d09c-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="passwordbox-parts"></a><span data-ttu-id="7d09c-106">Части PasswordBox</span><span class="sxs-lookup"><span data-stu-id="7d09c-106">PasswordBox Parts</span></span>  
 <span data-ttu-id="7d09c-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-107">The following table lists the named parts for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="7d09c-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="7d09c-108">Part</span></span>|<span data-ttu-id="7d09c-109">Тип</span><span class="sxs-lookup"><span data-stu-id="7d09c-109">Type</span></span>|<span data-ttu-id="7d09c-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="7d09c-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7d09c-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="7d09c-111">PART_ContentHost</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="7d09c-112">Визуальный элемент, который может содержать <xref:System.Windows.FrameworkElement>.</span><span class="sxs-lookup"><span data-stu-id="7d09c-112">A visual element that can contain a <xref:System.Windows.FrameworkElement>.</span></span> <span data-ttu-id="7d09c-113">Текст <xref:System.Windows.Controls.PasswordBox> отображается в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="7d09c-113">The text of the <xref:System.Windows.Controls.PasswordBox> is displayed in this element.</span></span>|  
  
## <a name="passwordbox-states"></a><span data-ttu-id="7d09c-114">Состояния PasswordBox</span><span class="sxs-lookup"><span data-stu-id="7d09c-114">PasswordBox States</span></span>  
 <span data-ttu-id="7d09c-115">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-115">The following table lists the visual states for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
|<span data-ttu-id="7d09c-116">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="7d09c-116">VisualState Name</span></span>|<span data-ttu-id="7d09c-117">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="7d09c-117">VisualStateGroup Name</span></span>|<span data-ttu-id="7d09c-118">Описание</span><span class="sxs-lookup"><span data-stu-id="7d09c-118">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="7d09c-119">Норм.</span><span class="sxs-lookup"><span data-stu-id="7d09c-119">Normal</span></span>|<span data-ttu-id="7d09c-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-120">CommonStates</span></span>|<span data-ttu-id="7d09c-121">Состояние по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7d09c-121">The default state.</span></span>|  
|<span data-ttu-id="7d09c-122">MouseOver</span><span class="sxs-lookup"><span data-stu-id="7d09c-122">MouseOver</span></span>|<span data-ttu-id="7d09c-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-123">CommonStates</span></span>|<span data-ttu-id="7d09c-124">Указатель мыши расположен над элементом управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-124">The mouse pointer is positioned over the control.</span></span>|  
|<span data-ttu-id="7d09c-125">Отключено</span><span class="sxs-lookup"><span data-stu-id="7d09c-125">Disabled</span></span>|<span data-ttu-id="7d09c-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-126">CommonStates</span></span>|<span data-ttu-id="7d09c-127">Элемент управления отключен.</span><span class="sxs-lookup"><span data-stu-id="7d09c-127">The control is disabled.</span></span>|  
|<span data-ttu-id="7d09c-128">Focused</span><span class="sxs-lookup"><span data-stu-id="7d09c-128">Focused</span></span>|<span data-ttu-id="7d09c-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-129">FocusStates</span></span>|<span data-ttu-id="7d09c-130">Элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="7d09c-130">The control has focus.</span></span>|  
|<span data-ttu-id="7d09c-131">Без фокуса ввода</span><span class="sxs-lookup"><span data-stu-id="7d09c-131">Unfocused</span></span>|<span data-ttu-id="7d09c-132">FocusStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-132">FocusStates</span></span>|<span data-ttu-id="7d09c-133">Элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="7d09c-133">The control does not have focus.</span></span>|  
|<span data-ttu-id="7d09c-134">Valid</span><span class="sxs-lookup"><span data-stu-id="7d09c-134">Valid</span></span>|<span data-ttu-id="7d09c-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-135">ValidationStates</span></span>|<span data-ttu-id="7d09c-136">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="7d09c-136">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="7d09c-137">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="7d09c-137">InvalidFocused</span></span>|<span data-ttu-id="7d09c-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-138">ValidationStates</span></span>|<span data-ttu-id="7d09c-139"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="7d09c-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="7d09c-140">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="7d09c-140">InvalidUnfocused</span></span>|<span data-ttu-id="7d09c-141">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="7d09c-141">ValidationStates</span></span>|<span data-ttu-id="7d09c-142"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="7d09c-142">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="passwordbox-controltemplate-example"></a><span data-ttu-id="7d09c-143">Пример шаблона элемента управления PasswordBox</span><span class="sxs-lookup"><span data-stu-id="7d09c-143">PasswordBox ControlTemplate Example</span></span>  
 <span data-ttu-id="7d09c-144">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.PasswordBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="7d09c-144">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.PasswordBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#PasswordBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/textbox.xaml#passwordbox)]  
  
 <span data-ttu-id="7d09c-145">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="7d09c-145">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="7d09c-146">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="7d09c-146">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d09c-147">См. также</span><span class="sxs-lookup"><span data-stu-id="7d09c-147">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="7d09c-148">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="7d09c-148">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="7d09c-149">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="7d09c-149">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="7d09c-150">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="7d09c-150">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="7d09c-151">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="7d09c-151">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
