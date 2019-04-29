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
ms.openlocfilehash: f948cf2b4f4cd2a4cb73b0cd5fc754240c850b83
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61770530"
---
# <a name="progressbar-styles-and-templates"></a><span data-ttu-id="a232e-102">Стили и шаблоны элемента ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a232e-102">ProgressBar Styles and Templates</span></span>
<span data-ttu-id="a232e-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a232e-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.ProgressBar> control.</span></span> <span data-ttu-id="a232e-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a232e-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="a232e-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="a232e-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="progressbar-parts"></a><span data-ttu-id="a232e-106">Части элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a232e-106">ProgressBar Parts</span></span>  
 <span data-ttu-id="a232e-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a232e-107">The following table lists the named parts for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="a232e-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="a232e-108">Part</span></span>|<span data-ttu-id="a232e-109">Тип</span><span class="sxs-lookup"><span data-stu-id="a232e-109">Type</span></span>|<span data-ttu-id="a232e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="a232e-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="a232e-111">PART_Indicator</span><span class="sxs-lookup"><span data-stu-id="a232e-111">PART_Indicator</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a232e-112">Объект, который показывает ход выполнения.</span><span class="sxs-lookup"><span data-stu-id="a232e-112">The object that indicates progress.</span></span>|  
|<span data-ttu-id="a232e-113">PART_Track</span><span class="sxs-lookup"><span data-stu-id="a232e-113">PART_Track</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a232e-114">Объект, определяющий путь индикатора хода выполнения.</span><span class="sxs-lookup"><span data-stu-id="a232e-114">The object that defines the path of the progress indicator.</span></span>|  
|<span data-ttu-id="a232e-115">PART_GlowRect</span><span class="sxs-lookup"><span data-stu-id="a232e-115">PART_GlowRect</span></span>|<xref:System.Windows.FrameworkElement>|<span data-ttu-id="a232e-116">Объект, оформляющий индикатор выполнения.</span><span class="sxs-lookup"><span data-stu-id="a232e-116">An object that embellishes the progress bar.</span></span>|  
  
## <a name="progressbar-states"></a><span data-ttu-id="a232e-117">Состояния элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a232e-117">ProgressBar States</span></span>  
 <span data-ttu-id="a232e-118">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a232e-118">The following table lists the visual states for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
|<span data-ttu-id="a232e-119">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="a232e-119">VisualState Name</span></span>|<span data-ttu-id="a232e-120">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="a232e-120">VisualStateGroup Name</span></span>|<span data-ttu-id="a232e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="a232e-121">Description</span></span>|  
|----------------------|---------------------------|-----------------|  
|<span data-ttu-id="a232e-122">Определенный</span><span class="sxs-lookup"><span data-stu-id="a232e-122">Determinate</span></span>|<span data-ttu-id="a232e-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a232e-123">CommonStates</span></span>|<span data-ttu-id="a232e-124"><xref:System.Windows.Controls.ProgressBar> сообщает о ходе выполнения на основе <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="a232e-124"><xref:System.Windows.Controls.ProgressBar> reports progress based on the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property.</span></span>|  
|<span data-ttu-id="a232e-125">Неопределенное</span><span class="sxs-lookup"><span data-stu-id="a232e-125">Indeterminate</span></span>|<span data-ttu-id="a232e-126">CommonStates</span><span class="sxs-lookup"><span data-stu-id="a232e-126">CommonStates</span></span>|<span data-ttu-id="a232e-127"><xref:System.Windows.Controls.ProgressBar> показывает общий ход выполнения с повторяющийся шаблон.</span><span class="sxs-lookup"><span data-stu-id="a232e-127"><xref:System.Windows.Controls.ProgressBar> reports generic progress with a repeating pattern.</span></span>|  
|<span data-ttu-id="a232e-128">Valid</span><span class="sxs-lookup"><span data-stu-id="a232e-128">Valid</span></span>|<span data-ttu-id="a232e-129">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a232e-129">ValidationStates</span></span>|<span data-ttu-id="a232e-130">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="a232e-130">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="a232e-131">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="a232e-131">InvalidFocused</span></span>|<span data-ttu-id="a232e-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a232e-132">ValidationStates</span></span>|<span data-ttu-id="a232e-133"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="a232e-133">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="a232e-134">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="a232e-134">InvalidUnfocused</span></span>|<span data-ttu-id="a232e-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="a232e-135">ValidationStates</span></span>|<span data-ttu-id="a232e-136"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="a232e-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="progressbar-controltemplate-example"></a><span data-ttu-id="a232e-137">Пример шаблона элемента управления ProgressBar</span><span class="sxs-lookup"><span data-stu-id="a232e-137">ProgressBar ControlTemplate Example</span></span>  
 <span data-ttu-id="a232e-138">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.ProgressBar> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="a232e-138">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.ProgressBar> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 <span data-ttu-id="a232e-139">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="a232e-139">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="a232e-140">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="a232e-140">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a232e-141">См. также</span><span class="sxs-lookup"><span data-stu-id="a232e-141">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="a232e-142">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="a232e-142">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="a232e-143">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="a232e-143">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="a232e-144">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="a232e-144">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="a232e-145">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="a232e-145">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
