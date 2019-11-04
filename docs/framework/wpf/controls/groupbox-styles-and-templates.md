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
ms.openlocfilehash: 0835c106ffbda86bca8e01bc61adebfc1ab0c2cb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459641"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="d4de9-102">Стили и шаблоны элемента GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4de9-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="d4de9-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d4de9-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="d4de9-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d4de9-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d4de9-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d4de9-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="d4de9-106">Части GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4de9-106">GroupBox Parts</span></span>  
 <span data-ttu-id="d4de9-107">Элемент управления <xref:System.Windows.Controls.GroupBox> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="d4de9-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="d4de9-108">Состояния GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4de9-108">GroupBox States</span></span>  
 <span data-ttu-id="d4de9-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d4de9-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="d4de9-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d4de9-110">VisualState Name</span></span>|<span data-ttu-id="d4de9-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d4de9-111">VisualStateGroup Name</span></span>|<span data-ttu-id="d4de9-112">Описание</span><span class="sxs-lookup"><span data-stu-id="d4de9-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d4de9-113">Valid</span><span class="sxs-lookup"><span data-stu-id="d4de9-113">Valid</span></span>|<span data-ttu-id="d4de9-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d4de9-114">ValidationStates</span></span>|<span data-ttu-id="d4de9-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="d4de9-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d4de9-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d4de9-116">InvalidFocused</span></span>|<span data-ttu-id="d4de9-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d4de9-117">ValidationStates</span></span>|<span data-ttu-id="d4de9-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d4de9-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d4de9-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d4de9-119">InvalidUnfocused</span></span>|<span data-ttu-id="d4de9-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d4de9-120">ValidationStates</span></span>|<span data-ttu-id="d4de9-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="d4de9-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="d4de9-122">Пример объекта ControlTemplate для GroupBox</span><span class="sxs-lookup"><span data-stu-id="d4de9-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="d4de9-123">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="d4de9-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="d4de9-124"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d4de9-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d4de9-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="d4de9-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4de9-126">См. также</span><span class="sxs-lookup"><span data-stu-id="d4de9-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="d4de9-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d4de9-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="d4de9-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d4de9-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="d4de9-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d4de9-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="d4de9-130">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d4de9-130">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)
