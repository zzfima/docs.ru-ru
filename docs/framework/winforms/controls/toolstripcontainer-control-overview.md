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
# <a name="toolstripcontainer-control-overview"></a>Общие сведения об элементе управления ToolStripContainer
Объект <xref:System.Windows.Forms.ToolStripContainer> содержит панели на левой, правой, верхней и нижней сторонах для размещения и нависания <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, и <xref:System.Windows.Forms.StatusStrip> элементов управления. Несколько элементов управления <xref:System.Windows.Forms.ToolStrip> располагаются по вертикали, если поместить их в левый или правый контейнер <xref:System.Windows.Forms.ToolStripContainer>. Они располагаются по горизонтали, если поместить их в верхний или нижний контейнер <xref:System.Windows.Forms.ToolStripContainer>. Для размещения традиционных элементов управления в форме может использоваться центральная панель <xref:System.Windows.Forms.ToolStripContentPanel> из контейнера <xref:System.Windows.Forms.ToolStripContainer>.  
  
 Все элементы управления <xref:System.Windows.Forms.ToolStripContainer> непосредственно доступны для выбора во время разработки и могут быть удалены. Каждая панель элемента <xref:System.Windows.Forms.ToolStripContainer> может расширяться и сворачиваться и изменять размеры элементов управления, которые он содержит.  
  
### <a name="important-toolstripcontainer-members"></a>ToolStripContainer важные члены  
  
|Имя|Описание|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Возвращает на нижней панели <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Возвращает или задает значение, указывающее, является ли на нижней панели <xref:System.Windows.Forms.ToolStripContainer> является видимым.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|На левой панели возвращает <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Возвращает или задает значение, указывающее, является ли на левой панели <xref:System.Windows.Forms.ToolStripContainer> является видимым.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Возвращает правая панель <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Возвращает или задает значение, указывающее, является ли правая панель <xref:System.Windows.Forms.ToolStripContainer> является видимым.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Возвращает верхняя панель <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Возвращает или задает значение, указывающее, является ли верхняя панель <xref:System.Windows.Forms.ToolStripContainer> является видимым.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStripContainer>  
 <xref:System.Windows.Forms.ToolStripContentPanel>
