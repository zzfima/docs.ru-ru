---
title: "Размещение элементов управления в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windws Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6244b21c2729df3bfe5899a4f4970f4b48030057
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="37983-102">Размещение элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37983-102">Layout in Windows Forms Controls</span></span>
<span data-ttu-id="37983-103">Точное расположение элементов управления на форме является важным для многих приложений.</span><span class="sxs-lookup"><span data-stu-id="37983-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="37983-104"><xref:System.Windows.Forms?displayProperty=nameWithType> Пространство имен предоставляет много инструментов для выполнения этой задачи.</span><span class="sxs-lookup"><span data-stu-id="37983-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37983-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="37983-105">In This Section</span></span>  
 [<span data-ttu-id="37983-106">Свойство AutoSize</span><span class="sxs-lookup"><span data-stu-id="37983-106">AutoSize Property Overview</span></span>](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 <span data-ttu-id="37983-107">Описывает <xref:System.Windows.Forms.Control.AutoSize%2A> свойство и его роли в макете.</span><span class="sxs-lookup"><span data-stu-id="37983-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>  
  
 [<span data-ttu-id="37983-108">Поля и заполнение в элементах управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37983-108">Margin and Padding in Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)  
 <span data-ttu-id="37983-109">Описывает <xref:System.Windows.Forms.Control.Margin%2A> и <xref:System.Windows.Forms.Control.Padding%2A> свойства и их роли в макете.</span><span class="sxs-lookup"><span data-stu-id="37983-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>  
  
 [<span data-ttu-id="37983-110">Практическое руководство. Выравнивание элементов управления по границам формы</span><span class="sxs-lookup"><span data-stu-id="37983-110">How to: Align a Control to the Edges of Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms.md)  
 <span data-ttu-id="37983-111">Демонстрирует использование <xref:System.Windows.Forms.Control.Dock%2A> свойство для выравнивания пользовательского элемента управления по краю занимаемой им формы.</span><span class="sxs-lookup"><span data-stu-id="37983-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>  
  
 [<span data-ttu-id="37983-112">Практическое руководство. Создание рамки вокруг элемента управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="37983-112">How to: Create a Border Around a Windows Forms Control Using Padding</span></span>](../../../../docs/framework/winforms/controls/how-to-create-a-border-around-a-windows-forms-control-using-padding.md)  
 <span data-ttu-id="37983-113">Демонстрирует использование <xref:System.Windows.Forms.Control.Padding%2A> свойств для структуры элемента управления.</span><span class="sxs-lookup"><span data-stu-id="37983-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>  
  
 [<span data-ttu-id="37983-114">Практическое руководство. Реализация пользовательского механизма размещения элементов управления в форме</span><span class="sxs-lookup"><span data-stu-id="37983-114">How to: Implement a Custom Layout Engine</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-custom-layout-engine.md)  
 <span data-ttu-id="37983-115">Демонстрируется реализация <xref:System.Windows.Forms.Layout.LayoutEngine> для упорядочивания элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="37983-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="37983-116">Ссылка</span><span class="sxs-lookup"><span data-stu-id="37983-116">Reference</span></span>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <span data-ttu-id="37983-117">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.TableLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="37983-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
 <xref:System.Windows.Forms.FlowLayoutPanel>  
 <span data-ttu-id="37983-118">Содержит справочную документацию по элементу управления <xref:System.Windows.Forms.FlowLayoutPanel>.</span><span class="sxs-lookup"><span data-stu-id="37983-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37983-119">См. также</span><span class="sxs-lookup"><span data-stu-id="37983-119">See Also</span></span>  
 [<span data-ttu-id="37983-120">Практическое руководство. Закрепление дочерних элементов управления в элементе управления FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="37983-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [<span data-ttu-id="37983-121">Практическое руководство. Привязка и закрепление дочерних элементов управления в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="37983-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="37983-122">Практическое руководство. Формирование макета формы Windows Forms с учетом будущей локализации</span><span class="sxs-lookup"><span data-stu-id="37983-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](../../../../docs/framework/winforms/controls/how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)  
 [<span data-ttu-id="37983-123">Автоматическое изменение размеров элемента управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="37983-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/autosize-behavior-in-the-tablelayoutpanel-control.md)
