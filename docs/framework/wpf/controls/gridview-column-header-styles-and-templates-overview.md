---
title: "Общие сведения о стилях заголовков столбцов GridView и шаблонах"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- column headers [WPF], customizing
- ListView controls [WPF], GridView column header styles
- controls [WPF], ListView
- headers [WPF], customizing
- GridView view mode [WPF], customizing column headers
ms.assetid: 74835674-a39e-4ab5-9418-ad7f6ab7b956
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 996d6d5f531a866d4fc80acc3848cdf264901032
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="gridview-column-header-styles-and-templates-overview"></a><span data-ttu-id="1a5bf-102">Общие сведения о стилях заголовков столбцов GridView и шаблонах</span><span class="sxs-lookup"><span data-stu-id="1a5bf-102">GridView Column Header Styles and Templates Overview</span></span>
<span data-ttu-id="1a5bf-103">В этом обзоре описывается порядок приоритета для свойств, которые позволяют настроить заголовок столбца в <xref:System.Windows.Controls.GridView> режим просмотра для <xref:System.Windows.Controls.ListView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-103">This overview discusses the order of precedence for properties that you use to customize a column header in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="customizing-a-column-header-in-a-gridview"></a><span data-ttu-id="1a5bf-104">Настройка заголовка столбца в элементе управления GridView</span><span class="sxs-lookup"><span data-stu-id="1a5bf-104">Customizing a Column Header in a GridView</span></span>  
 <span data-ttu-id="1a5bf-105">Свойства, определяющие содержимое, макет и стиль заголовка столбца в <xref:System.Windows.Controls.GridView> находятся на множество связанных классов.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-105">The properties that define the content, layout, and style of a column header in a <xref:System.Windows.Controls.GridView> are found on many related classes.</span></span> <span data-ttu-id="1a5bf-106">Некоторые из этих свойств имеют сходные или тому же.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-106">Some of these properties have functionality that is similar or the same.</span></span>  
  
 <span data-ttu-id="1a5bf-107">Строки в таблице ниже показаны группы свойств, которые выполняют ту же функцию.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-107">The rows in the following table show groups of properties that perform the same function.</span></span> <span data-ttu-id="1a5bf-108">Эти свойства можно использовать для настройки заголовков столбцов в <xref:System.Windows.Controls.GridView>.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-108">You can use these properties to customize the column headers in a <xref:System.Windows.Controls.GridView>.</span></span> <span data-ttu-id="1a5bf-109">Порядок приоритетов для связанных свойств — справа налево, где свойство в крайнем правом столбце имеет наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-109">The order of precedence for related properties is from right to left where the property in the farthest right column has the highest precedence.</span></span> <span data-ttu-id="1a5bf-110">Например если <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> устанавливается на <xref:System.Windows.Controls.GridViewColumnHeader> объекта и <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> набор для соответствующей <xref:System.Windows.Controls.GridViewColumn>, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> имеет более высокий приоритет.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-110">For example, if a <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> is set on the <xref:System.Windows.Controls.GridViewColumnHeader> object and the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> is set on the associated <xref:System.Windows.Controls.GridViewColumn>, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> takes precedence.</span></span> <span data-ttu-id="1a5bf-111">В этом сценарии <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> не делает ничего.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-111">In this scenario, the <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A> has no effect.</span></span>  
  
 <span data-ttu-id="1a5bf-112">**Связанные свойства для заголовков столбцов в элементе управления GridView**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-112">**Related properties for column headers in a GridView**</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1a5bf-113">**Классы**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-113">**Classes**</span></span>|<xref:System.Windows.Controls.GridView>|<xref:System.Windows.Controls.GridViewColumn>|<xref:System.Windows.Controls.GridViewColumnHeader>|  
|<span data-ttu-id="1a5bf-114">**Свойства контекстного меню**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-114">**Context Menu Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContextMenu%2A>|<span data-ttu-id="1a5bf-115">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="1a5bf-115">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ContextMenu%2A>|  
|<span data-ttu-id="1a5bf-116">**ToolTip**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-116">**ToolTip**</span></span><br /><br /> <span data-ttu-id="1a5bf-117">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-117">**Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderToolTip%2A>|<span data-ttu-id="1a5bf-118">Неприменимо</span><span class="sxs-lookup"><span data-stu-id="1a5bf-118">Not applicable</span></span>|<xref:System.Windows.FrameworkElement.ToolTip%2A>|  
|<span data-ttu-id="1a5bf-119">**Шаблон заголовка**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-119">**Header Template**</span></span><br /><br /> <span data-ttu-id="1a5bf-120">**Свойства**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-120">**Properties**</span></span>|<span data-ttu-id="1a5bf-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="1a5bf-121"><xref:System.Windows.Controls.GridView.ColumnHeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridView.ColumnHeaderTemplateSelector%2A>|<span data-ttu-id="1a5bf-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="1a5bf-122"><xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.GridViewColumn.HeaderTemplateSelector%2A>|<span data-ttu-id="1a5bf-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span><span class="sxs-lookup"><span data-stu-id="1a5bf-123"><xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> <sup>1</sup>/</span></span><br /><br /> <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A>|  
|<span data-ttu-id="1a5bf-124">**Свойства стиля**</span><span class="sxs-lookup"><span data-stu-id="1a5bf-124">**Style Properties**</span></span>|<xref:System.Windows.Controls.GridView.ColumnHeaderContainerStyle%2A>|<xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A>|<xref:System.Windows.FrameworkElement.Style%2A>|  
  
 <span data-ttu-id="1a5bf-125"><sup>1</sup>для **свойств шаблона заголовка**, если значение шаблона и свойства селектор шаблона, имеет приоритет свойства шаблона.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-125"><sup>1</sup>For **Header Template Properties**, if you set both the template and template selector properties, the template property takes precedence.</span></span> <span data-ttu-id="1a5bf-126">Например, если заданы оба <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> и <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> свойства, <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> имеет приоритет.</span><span class="sxs-lookup"><span data-stu-id="1a5bf-126">For example, if you set both the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> and <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> properties, the <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> property takes precedence.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a5bf-127">См. также</span><span class="sxs-lookup"><span data-stu-id="1a5bf-127">See Also</span></span>  
 [<span data-ttu-id="1a5bf-128">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="1a5bf-128">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="1a5bf-129">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="1a5bf-129">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="1a5bf-130">Общие сведения о GridView</span><span class="sxs-lookup"><span data-stu-id="1a5bf-130">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
