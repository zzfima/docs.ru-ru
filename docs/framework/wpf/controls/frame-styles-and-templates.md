---
title: Стили и шаблоны элемента Frame
ms.date: 03/30/2017
helpviewer_keywords:
- parts [WPF], Frame
- templates [WPF], Frame
- ControlTemplate [WPF], Frame
- Frame [WPF], styles and templates
- states [WPF], Frame
- styles [WPF], Frame
ms.assetid: a01c32e2-c951-46a0-a82f-2614ca241f0b
ms.openlocfilehash: 6b084cfa31efebe2456871a99cd810741aa26609
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61912214"
---
# <a name="frame-styles-and-templates"></a><span data-ttu-id="d8433-102">Стили и шаблоны элемента Frame</span><span class="sxs-lookup"><span data-stu-id="d8433-102">Frame Styles and Templates</span></span>
<span data-ttu-id="d8433-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8433-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Frame> control.</span></span> <span data-ttu-id="d8433-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8433-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d8433-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d8433-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="frame-parts"></a><span data-ttu-id="d8433-106">Части фрейма</span><span class="sxs-lookup"><span data-stu-id="d8433-106">Frame Parts</span></span>  
 <span data-ttu-id="d8433-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8433-107">The following table lists the named parts for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="d8433-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="d8433-108">Part</span></span>|<span data-ttu-id="d8433-109">Тип</span><span class="sxs-lookup"><span data-stu-id="d8433-109">Type</span></span>|<span data-ttu-id="d8433-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d8433-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d8433-111">PART_FrameCP</span><span class="sxs-lookup"><span data-stu-id="d8433-111">PART_FrameCP</span></span>|<xref:System.Windows.Controls.ContentPresenter>|<span data-ttu-id="d8433-112">Область содержимого.</span><span class="sxs-lookup"><span data-stu-id="d8433-112">The content area.</span></span>|  
  
## <a name="frame-states"></a><span data-ttu-id="d8433-113">Состояния кадра</span><span class="sxs-lookup"><span data-stu-id="d8433-113">Frame States</span></span>  
 <span data-ttu-id="d8433-114">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8433-114">The following table lists the visual states for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
|<span data-ttu-id="d8433-115">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d8433-115">VisualState Name</span></span>|<span data-ttu-id="d8433-116">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d8433-116">VisualStateGroup Name</span></span>|<span data-ttu-id="d8433-117">Описание</span><span class="sxs-lookup"><span data-stu-id="d8433-117">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d8433-118">Valid</span><span class="sxs-lookup"><span data-stu-id="d8433-118">Valid</span></span>|<span data-ttu-id="d8433-119">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8433-119">ValidationStates</span></span>|<span data-ttu-id="d8433-120">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="d8433-120">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d8433-121">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d8433-121">InvalidFocused</span></span>|<span data-ttu-id="d8433-122">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8433-122">ValidationStates</span></span>|<span data-ttu-id="d8433-123"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d8433-123">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d8433-124">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d8433-124">InvalidUnfocused</span></span>|<span data-ttu-id="d8433-125">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d8433-125">ValidationStates</span></span>|<span data-ttu-id="d8433-126"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d8433-126">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="frame-controltemplate-example"></a><span data-ttu-id="d8433-127">Пример создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d8433-127">Frame ControlTemplate Example</span></span>  
 <span data-ttu-id="d8433-128">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.Frame> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d8433-128">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Frame> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Frame](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/frame.xaml#frame)]  
  
 <span data-ttu-id="d8433-129">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d8433-129">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d8433-130">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d8433-130">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8433-131">См. также</span><span class="sxs-lookup"><span data-stu-id="d8433-131">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d8433-132">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d8433-132">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d8433-133">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d8433-133">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d8433-134">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d8433-134">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="d8433-135">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d8433-135">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
