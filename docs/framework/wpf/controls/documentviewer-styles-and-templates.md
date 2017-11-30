---
title: "Стили и шаблоны элемента DocumentViewer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- templates [WPF], DocumentViewer
- DocumentViewer [WPF], styles and templates
- states [WPF], DocumentViewer
- ControlTemplate [WPF], DocumentViewer
- parts [WPF], DocumentViewer
- styles [WPF], DocumentViewer
ms.assetid: 6bd4ff8f-ea6a-4084-ac58-e7a67446ce1c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7027fbee6a35b9219e65c9964db9a038e942f14e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="documentviewer-styles-and-templates"></a><span data-ttu-id="d94c7-102">Стили и шаблоны элемента DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="d94c7-102">DocumentViewer Styles and Templates</span></span>
<span data-ttu-id="d94c7-103">В этом разделе описываются стили и шаблоны для <xref:System.Windows.Controls.DocumentViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d94c7-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span> <span data-ttu-id="d94c7-104">Можно изменить значение по умолчанию <xref:System.Windows.Controls.ControlTemplate> для предоставления уникального внешнего вида элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d94c7-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="d94c7-105">Подробнее см. в разделе [Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="d94c7-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).</span></span>  
  
## <a name="documentviewer-parts"></a><span data-ttu-id="d94c7-106">Части DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="d94c7-106">DocumentViewer Parts</span></span>  
 <span data-ttu-id="d94c7-107">В следующей таблице перечислены именованные части <xref:System.Windows.Controls.DocumentViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d94c7-107">The following table lists the named parts for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="d94c7-108">Отделение</span><span class="sxs-lookup"><span data-stu-id="d94c7-108">Part</span></span>|<span data-ttu-id="d94c7-109">Тип</span><span class="sxs-lookup"><span data-stu-id="d94c7-109">Type</span></span>|<span data-ttu-id="d94c7-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d94c7-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d94c7-111">PART_ContentHost</span><span class="sxs-lookup"><span data-stu-id="d94c7-111">PART_ContentHost</span></span>|<xref:System.Windows.Controls.ScrollViewer>|<span data-ttu-id="d94c7-112">Содержимое и область прокрутки.</span><span class="sxs-lookup"><span data-stu-id="d94c7-112">The content and scrolling area.</span></span>|  
|<span data-ttu-id="d94c7-113">PART_FindToolBarHost</span><span class="sxs-lookup"><span data-stu-id="d94c7-113">PART_FindToolBarHost</span></span>|<xref:System.Windows.Controls.ContentControl>|<span data-ttu-id="d94c7-114">Поле поиска в нижней по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d94c7-114">The search box, at the bottom by default.</span></span>|  
  
## <a name="documentviewer-states"></a><span data-ttu-id="d94c7-115">Состояния DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="d94c7-115">DocumentViewer States</span></span>  
 <span data-ttu-id="d94c7-116">В следующей таблице перечислены визуальные состояния <xref:System.Windows.Controls.DocumentViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d94c7-116">The following table lists the visual states for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
|<span data-ttu-id="d94c7-117">Имя VisualState</span><span class="sxs-lookup"><span data-stu-id="d94c7-117">VisualState Name</span></span>|<span data-ttu-id="d94c7-118">Имя VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="d94c7-118">VisualStateGroup Name</span></span>|<span data-ttu-id="d94c7-119">Описание</span><span class="sxs-lookup"><span data-stu-id="d94c7-119">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="d94c7-120">Valid</span><span class="sxs-lookup"><span data-stu-id="d94c7-120">Valid</span></span>|<span data-ttu-id="d94c7-121">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d94c7-121">ValidationStates</span></span>|<span data-ttu-id="d94c7-122">Элемент управления использует <xref:System.Windows.Controls.Validation> класса и <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> вложенное свойство `false`.</span><span class="sxs-lookup"><span data-stu-id="d94c7-122">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|  
|<span data-ttu-id="d94c7-123">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="d94c7-123">InvalidFocused</span></span>|<span data-ttu-id="d94c7-124">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d94c7-124">ValidationStates</span></span>|<span data-ttu-id="d94c7-125"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d94c7-125">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|  
|<span data-ttu-id="d94c7-126">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="d94c7-126">InvalidUnfocused</span></span>|<span data-ttu-id="d94c7-127">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="d94c7-127">ValidationStates</span></span>|<span data-ttu-id="d94c7-128"><xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Вложенное свойство `true` имеет элемент управления имеет фокус.</span><span class="sxs-lookup"><span data-stu-id="d94c7-128">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|  
  
## <a name="documentviewer-controltemplate-example"></a><span data-ttu-id="d94c7-129">Пример шаблона элемента управления DocumentViewer</span><span class="sxs-lookup"><span data-stu-id="d94c7-129">DocumentViewer ControlTemplate Example</span></span>  
 <span data-ttu-id="d94c7-130">В следующем примере показан способ определения <xref:System.Windows.Controls.ControlTemplate> для <xref:System.Windows.Controls.DocumentViewer> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d94c7-130">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.DocumentViewer> control.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#DocumentViewer](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/documentviewer.xaml#documentviewer)]  
  
 <span data-ttu-id="d94c7-131">В предыдущем примере используется один или несколько из следующих ресурсов.</span><span class="sxs-lookup"><span data-stu-id="d94c7-131">The preceding example uses one or more of the following resources.</span></span>  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 <span data-ttu-id="d94c7-132">Полный пример см. в разделе [Пример задания стиля с помощью ControlTemplates](http://go.microsoft.com/fwlink/?LinkID=160041).</span><span class="sxs-lookup"><span data-stu-id="d94c7-132">For the complete sample, see [Styling with ControlTemplates Sample](http://go.microsoft.com/fwlink/?LinkID=160041).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d94c7-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d94c7-133">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="d94c7-134">Стили и шаблоны элемента управления</span><span class="sxs-lookup"><span data-stu-id="d94c7-134">Control Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [<span data-ttu-id="d94c7-135">Настройка элементов управления</span><span class="sxs-lookup"><span data-stu-id="d94c7-135">Control Customization</span></span>](../../../../docs/framework/wpf/controls/control-customization.md)  
 [<span data-ttu-id="d94c7-136">Стилизация и использование шаблонов</span><span class="sxs-lookup"><span data-stu-id="d94c7-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="d94c7-137">Настройка внешнего вида существующего элемента управления путем создания объекта ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="d94c7-137">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
