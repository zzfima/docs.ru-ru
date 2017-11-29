---
title: "Общие сведения об элементе управления ToolStripContainer"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ToolStripContainer
helpviewer_keywords:
- toolbars [Windows Forms], built-in rafting
- ToolStripContainer control [Windows Forms], about ToolStripContainer control
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4abc783961177a55cdb81cefd21ed2d7aefb0620
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="toolstripcontainer-control-overview"></a><span data-ttu-id="a7aa5-102">Общие сведения об элементе управления ToolStripContainer</span><span class="sxs-lookup"><span data-stu-id="a7aa5-102">ToolStripContainer Control Overview</span></span>
<span data-ttu-id="a7aa5-103">Объект <xref:System.Windows.Forms.ToolStripContainer> содержит панели на левой, правой, верхней и нижней сторонах для размещения и нависания <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, и <xref:System.Windows.Forms.StatusStrip> элементов управления.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-103">A <xref:System.Windows.Forms.ToolStripContainer> has panels on its left, right, top, and bottom sides for positioning and rafting <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, and <xref:System.Windows.Forms.StatusStrip> controls.</span></span> <span data-ttu-id="a7aa5-104">Несколько элементов управления <xref:System.Windows.Forms.ToolStrip> располагаются по вертикали, если поместить их в левый или правый контейнер <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-104">Multiple <xref:System.Windows.Forms.ToolStrip> controls stack vertically if you put them in the left or right <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="a7aa5-105">Они располагаются по горизонтали, если поместить их в верхний или нижний контейнер <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-105">They stack horizontally if you put them in the top or bottom <xref:System.Windows.Forms.ToolStripContainer>.</span></span> <span data-ttu-id="a7aa5-106">Для размещения традиционных элементов управления в форме может использоваться центральная панель <xref:System.Windows.Forms.ToolStripContentPanel> из контейнера <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-106">You can use the central <xref:System.Windows.Forms.ToolStripContentPanel> of the <xref:System.Windows.Forms.ToolStripContainer> to position traditional controls on the form.</span></span>  
  
 <span data-ttu-id="a7aa5-107">Все элементы управления <xref:System.Windows.Forms.ToolStripContainer> непосредственно доступны для выбора во время разработки и могут быть удалены.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-107">Any or all <xref:System.Windows.Forms.ToolStripContainer> controls are directly selectable at design time and can be deleted.</span></span> <span data-ttu-id="a7aa5-108">Каждая панель элемента <xref:System.Windows.Forms.ToolStripContainer> может расширяться и сворачиваться и изменять размеры элементов управления, которые он содержит.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-108">Each panel of a <xref:System.Windows.Forms.ToolStripContainer> is expandable and collapsible, and resizes with the controls that it contains.</span></span>  
  
### <a name="important-toolstripcontainer-members"></a><span data-ttu-id="a7aa5-109">ToolStripContainer важные члены</span><span class="sxs-lookup"><span data-stu-id="a7aa5-109">Important ToolStripContainer Members</span></span>  
  
|<span data-ttu-id="a7aa5-110">Имя</span><span class="sxs-lookup"><span data-stu-id="a7aa5-110">Name</span></span>|<span data-ttu-id="a7aa5-111">Описание</span><span class="sxs-lookup"><span data-stu-id="a7aa5-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|<span data-ttu-id="a7aa5-112">Возвращает на нижней панели <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-112">Gets the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|<span data-ttu-id="a7aa5-113">Возвращает или задает значение, указывающее, является ли на нижней панели <xref:System.Windows.Forms.ToolStripContainer> является видимым.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-113">Gets or sets a value indicating whether the bottom panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|<span data-ttu-id="a7aa5-114">На левой панели возвращает <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-114">Gets the left panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|<span data-ttu-id="a7aa5-115">Возвращает или задает значение, указывающее, является ли на левой панели <xref:System.Windows.Forms.ToolStripContainer> является видимым.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-115">Gets or sets a value indicating whether the left panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|<span data-ttu-id="a7aa5-116">Возвращает правая панель <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-116">Gets the right panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|<span data-ttu-id="a7aa5-117">Возвращает или задает значение, указывающее, является ли правая панель <xref:System.Windows.Forms.ToolStripContainer> является видимым.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-117">Gets or sets a value indicating whether the right panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|<span data-ttu-id="a7aa5-118">Возвращает верхняя панель <xref:System.Windows.Forms.ToolStripContainer>.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-118">Gets the top panel of the <xref:System.Windows.Forms.ToolStripContainer>.</span></span>|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|<span data-ttu-id="a7aa5-119">Возвращает или задает значение, указывающее, является ли верхняя панель <xref:System.Windows.Forms.ToolStripContainer> является видимым.</span><span class="sxs-lookup"><span data-stu-id="a7aa5-119">Gets or sets a value indicating whether the top panel of the <xref:System.Windows.Forms.ToolStripContainer> is visible.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a7aa5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="a7aa5-120">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
