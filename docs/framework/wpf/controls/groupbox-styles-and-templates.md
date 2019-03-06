---
title: Стили и шаблоны элемента GroupBox
ms.date: 03/30/2017
helpviewer_keywords:
- ControlTemplate [WPF], GroupBox
- parts [WPF], GroupBox
- GroupBox [WPF], styles and templates
- states [WPF], GroupBox
- styles [WPF], GroupBox
- templates [WPF], GroupBox
ms.assetid: 33df7037-0a1b-476f-b9d0-41566a777699
ms.openlocfilehash: 26a935b40ede80aad533c7951f667afa37c57477
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368968"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="efb8a-102">Стили и шаблоны элемента GroupBox</span><span class="sxs-lookup"><span data-stu-id="efb8a-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a> <span data-ttu-id="efb8a-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="efb8a-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="efb8a-104">Вы можете изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> предоставить уникальный внешний вид элемента управления.</span><span class="sxs-lookup"><span data-stu-id="efb8a-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="efb8a-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="efb8a-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="efb8a-106">GroupBox частей</span><span class="sxs-lookup"><span data-stu-id="efb8a-106">GroupBox Parts</span></span>  
 <span data-ttu-id="efb8a-107"><xref:System.Windows.Controls.GroupBox> Управления не имеет частей с именами.</span><span class="sxs-lookup"><span data-stu-id="efb8a-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="efb8a-108">GroupBox состояний</span><span class="sxs-lookup"><span data-stu-id="efb8a-108">GroupBox States</span></span>  
 <span data-ttu-id="efb8a-109">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="efb8a-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="efb8a-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="efb8a-110">VisualState Name</span></span>|<span data-ttu-id="efb8a-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="efb8a-111">VisualStateGroup Name</span></span>|<span data-ttu-id="efb8a-112">Описание:</span><span class="sxs-lookup"><span data-stu-id="efb8a-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="efb8a-113">Valid</span><span class="sxs-lookup"><span data-stu-id="efb8a-113">Valid</span></span>|<span data-ttu-id="efb8a-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="efb8a-114">ValidationStates</span></span>|<span data-ttu-id="efb8a-115">Элемент управления использует <xref:System.Windows.Controls.Validation> класс и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="efb8a-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="efb8a-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="efb8a-116">InvalidFocused</span></span>|<span data-ttu-id="efb8a-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="efb8a-117">ValidationStates</span></span>|<span data-ttu-id="efb8a-118"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="efb8a-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="efb8a-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="efb8a-119">InvalidUnfocused</span></span>|<span data-ttu-id="efb8a-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="efb8a-120">ValidationStates</span></span>|<span data-ttu-id="efb8a-121"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Присоединенное свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="efb8a-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="efb8a-122">Пример шаблона элемента управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="efb8a-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="efb8a-123">В следующем примере показано определение <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.GroupBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="efb8a-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="efb8a-124"><xref:System.Windows.Controls.ControlTemplate> Использует один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="efb8a-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="efb8a-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="efb8a-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb8a-126">См. также</span><span class="sxs-lookup"><span data-stu-id="efb8a-126">See also</span></span>
- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="efb8a-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="efb8a-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="efb8a-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="efb8a-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="efb8a-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="efb8a-129">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="efb8a-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="efb8a-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
