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
ms.openlocfilehash: e5befffc86f26176da4accfc01239a08d4978713
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283768"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="cb917-102">Стили и шаблоны элемента GroupBox</span><span class="sxs-lookup"><span data-stu-id="cb917-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="cb917-103">В этом разделе описываются стили и шаблоны для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="cb917-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="cb917-104">Можно изменить <xref:System.Windows.Controls.ControlTemplate> по умолчанию, чтобы обеспечить уникальность внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="cb917-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="cb917-105">Дополнительные сведения см. в разделе [Создание шаблона для элемента управления](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span><span class="sxs-lookup"><span data-stu-id="cb917-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>   
## <a name="groupbox-parts"></a><span data-ttu-id="cb917-106">Части GroupBox</span><span class="sxs-lookup"><span data-stu-id="cb917-106">GroupBox Parts</span></span>  
 <span data-ttu-id="cb917-107">Элемент управления <xref:System.Windows.Controls.GroupBox> не имеет именованных частей.</span><span class="sxs-lookup"><span data-stu-id="cb917-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>   
## <a name="groupbox-states"></a><span data-ttu-id="cb917-108">Состояния GroupBox</span><span class="sxs-lookup"><span data-stu-id="cb917-108">GroupBox States</span></span>  
 <span data-ttu-id="cb917-109">В следующей таблице перечислены визуальные состояния для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="cb917-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="cb917-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="cb917-110">VisualState Name</span></span>|<span data-ttu-id="cb917-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="cb917-111">VisualStateGroup Name</span></span>|<span data-ttu-id="cb917-112">Описание</span><span class="sxs-lookup"><span data-stu-id="cb917-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="cb917-113">Valid</span><span class="sxs-lookup"><span data-stu-id="cb917-113">Valid</span></span>|<span data-ttu-id="cb917-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cb917-114">ValidationStates</span></span>|<span data-ttu-id="cb917-115">Элемент управления использует класс <xref:System.Windows.Controls.Validation>, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> присоединенным свойством является `false`.</span><span class="sxs-lookup"><span data-stu-id="cb917-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="cb917-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="cb917-116">InvalidFocused</span></span>|<span data-ttu-id="cb917-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cb917-117">ValidationStates</span></span>|<span data-ttu-id="cb917-118">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="cb917-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="cb917-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="cb917-119">InvalidUnfocused</span></span>|<span data-ttu-id="cb917-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="cb917-120">ValidationStates</span></span>|<span data-ttu-id="cb917-121">Присоединенное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство имеет `true` элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="cb917-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>   
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="cb917-122">Пример объекта ControlTemplate для GroupBox</span><span class="sxs-lookup"><span data-stu-id="cb917-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="cb917-123">В следующем примере показано, как определить <xref:System.Windows.Controls.ControlTemplate> для элемента управления <xref:System.Windows.Controls.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="cb917-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="cb917-124"><xref:System.Windows.Controls.ControlTemplate> использует один или несколько следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="cb917-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="cb917-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="cb917-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb917-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cb917-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="cb917-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="cb917-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="cb917-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="cb917-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="cb917-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="cb917-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="cb917-130">Создание шаблона для элемента управления</span><span class="sxs-lookup"><span data-stu-id="cb917-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
