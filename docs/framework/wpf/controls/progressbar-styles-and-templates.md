---
title: Стили и шаблоны элемента ProgressBar
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
ms.openlocfilehash: 7041a5497355a806894b0a0e0363fffde134aadb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377255"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="18ca5-102">Стили и шаблоны элемента ProgressBar</span><span class="sxs-lookup"><span data-stu-id="18ca5-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="18ca5-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18ca5-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="18ca5-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18ca5-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="18ca5-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="18ca5-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="18ca5-106">Части элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="18ca5-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="18ca5-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18ca5-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="18ca5-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="18ca5-108">Part</span></span>|<span data-ttu-id="18ca5-109">Тип</span><span class="sxs-lookup"><span data-stu-id="18ca5-109">Type</span></span>|<span data-ttu-id="18ca5-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="18ca5-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="18ca5-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="18ca5-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18ca5-112">Объект, который показывает ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="18ca5-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="18ca5-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="18ca5-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18ca5-114">Объект, определяющий путь индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="18ca5-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="18ca5-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="18ca5-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="18ca5-116">Объект, оформляющий индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="18ca5-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="18ca5-117">Состояния элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="18ca5-117">ProgressBar States</span></span>  
 <span data-ttu-id="18ca5-118">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18ca5-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="18ca5-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="18ca5-119">VisualState Name</span></span>|<span data-ttu-id="18ca5-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="18ca5-120">VisualStateGroup Name</span></span>|<span data-ttu-id="18ca5-121">Описание:</span><span class="sxs-lookup"><span data-stu-id="18ca5-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="18ca5-122">Определенный</span><span class="sxs-lookup"><span data-stu-id="18ca5-122">Determinate</span></span>|<span data-ttu-id="18ca5-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18ca5-123">CommonStates</span></span>|<span data-ttu-id="18ca5-124"><xref:System.Windows.Controls.ProgressBar> сообщает о ходе выполнения на основе <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="18ca5-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="18ca5-125">Неопределенное</span><span class="sxs-lookup"><span data-stu-id="18ca5-125">Indeterminate</span></span>|<span data-ttu-id="18ca5-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="18ca5-126">CommonStates</span></span>|<span data-ttu-id="18ca5-127"><xref:System.Windows.Controls.ProgressBar> показывает общий ход выполнения с повторяющийся шаблон.</span><span class="sxs-lookup"><span data-stu-id="18ca5-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="18ca5-128">Valid</span><span class="sxs-lookup"><span data-stu-id="18ca5-128">Valid</span></span>|<span data-ttu-id="18ca5-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18ca5-129">ValidationStates</span></span>|<span data-ttu-id="18ca5-130">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="18ca5-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="18ca5-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="18ca5-131">InvalidFocused</span></span>|<span data-ttu-id="18ca5-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18ca5-132">ValidationStates</span></span>|<span data-ttu-id="18ca5-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="18ca5-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="18ca5-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="18ca5-134">InvalidUnfocused</span></span>|<span data-ttu-id="18ca5-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="18ca5-135">ValidationStates</span></span>|<span data-ttu-id="18ca5-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="18ca5-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="18ca5-137">Пример шаблона элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="18ca5-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="18ca5-138">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="18ca5-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="18ca5-139">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="18ca5-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="18ca5-140">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="18ca5-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ca5-141">См. также</span><span class="sxs-lookup"><span data-stu-id="18ca5-141">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="18ca5-142">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="18ca5-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="18ca5-143">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="18ca5-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="18ca5-144">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="18ca5-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="18ca5-145">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="18ca5-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
