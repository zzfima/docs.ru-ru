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
ms.openlocfilehash: 474cda0abc6a18c015836c749c78f4d33aa5abd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187476"
---
# <a name="groupbox-styles-and-templates"></a><span data-ttu-id="90d12-102">Стили и шаблоны элемента GroupBox</span><span class="sxs-lookup"><span data-stu-id="90d12-102">GroupBox Styles and Templates</span></span>
<a name="introduction"></a><span data-ttu-id="90d12-103">Эта тема описывает стили и <xref:System.Windows.Controls.GroupBox> шаблоны для управления.</span><span class="sxs-lookup"><span data-stu-id="90d12-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.GroupBox> control.</span></span> <span data-ttu-id="90d12-104">Вы можете изменить <xref:System.Windows.Controls.ControlTemplate> значение по умолчанию, чтобы придать элементу управления уникальный внешний вид.</span><span class="sxs-lookup"><span data-stu-id="90d12-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="90d12-105">Для получения дополнительной информации [см.](../../../desktop-wpf/themes/how-to-create-apply-template.md)</span><span class="sxs-lookup"><span data-stu-id="90d12-105">For more information, see [Create a template for a control](../../../desktop-wpf/themes/how-to-create-apply-template.md).</span></span>  
  
<a name="groupbox_parts"></a>
## <a name="groupbox-parts"></a><span data-ttu-id="90d12-106">Части GroupBox</span><span class="sxs-lookup"><span data-stu-id="90d12-106">GroupBox Parts</span></span>  
 <span data-ttu-id="90d12-107">Элемент <xref:System.Windows.Controls.GroupBox> управления не имеет никаких названных частей.</span><span class="sxs-lookup"><span data-stu-id="90d12-107">The <xref:System.Windows.Controls.GroupBox> control does not have any named parts.</span></span>  
  
<a name="groupbox_states"></a>
## <a name="groupbox-states"></a><span data-ttu-id="90d12-108">Государства GroupBox</span><span class="sxs-lookup"><span data-stu-id="90d12-108">GroupBox States</span></span>  
 <span data-ttu-id="90d12-109">В следующей таблице перечислены <xref:System.Windows.Controls.GroupBox> визуальные состояния для управления.</span><span class="sxs-lookup"><span data-stu-id="90d12-109">The following table lists the visual states for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
|<span data-ttu-id="90d12-110">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="90d12-110">VisualState Name</span></span>|<span data-ttu-id="90d12-111">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="90d12-111">VisualStateGroup Name</span></span>|<span data-ttu-id="90d12-112">Описание</span><span class="sxs-lookup"><span data-stu-id="90d12-112">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="90d12-113">Допустимо</span><span class="sxs-lookup"><span data-stu-id="90d12-113">Valid</span></span>|<span data-ttu-id="90d12-114">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90d12-114">ValidationStates</span></span>|<span data-ttu-id="90d12-115">Элемент управления <xref:System.Windows.Controls.Validation> использует класс, а <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `false`прилагаемое свойство находится под контролем.</span><span class="sxs-lookup"><span data-stu-id="90d12-115">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="90d12-116">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="90d12-116">InvalidFocused</span></span>|<span data-ttu-id="90d12-117">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90d12-117">ValidationStates</span></span>|<span data-ttu-id="90d12-118">Прилагаемое <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> `true` свойство имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="90d12-118">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="90d12-119">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="90d12-119">InvalidUnfocused</span></span>|<span data-ttu-id="90d12-120">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="90d12-120">ValidationStates</span></span>|<span data-ttu-id="90d12-121">Прикрепленное <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> свойство `true` имеет элемент управления не имеет фокуса.</span><span class="sxs-lookup"><span data-stu-id="90d12-121">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
<a name="groupbox_controltemplate_example"></a>
## <a name="groupbox-controltemplate-example"></a><span data-ttu-id="90d12-122">Пример Управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="90d12-122">GroupBox ControlTemplate Example</span></span>  
 <span data-ttu-id="90d12-123">В следующем примере показано, <xref:System.Windows.Controls.GroupBox> как определить <xref:System.Windows.Controls.ControlTemplate> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="90d12-123">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.GroupBox> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#GroupBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/groupbox.xaml#groupbox)]  
  
 <span data-ttu-id="90d12-124">Используется <xref:System.Windows.Controls.ControlTemplate> один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="90d12-124">The <xref:System.Windows.Controls.ControlTemplate> uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="90d12-125">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="90d12-125">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d12-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="90d12-126">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="90d12-127">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="90d12-127">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="90d12-128">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="90d12-128">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="90d12-129">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="90d12-129">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="90d12-130">Создание шаблона для управления</span><span class="sxs-lookup"><span data-stu-id="90d12-130">Create a template for a control</span></span>](../../../desktop-wpf/themes/how-to-create-apply-template.md)
