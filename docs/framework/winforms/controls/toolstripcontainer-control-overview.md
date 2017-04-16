---
title: "Общие сведения об элементе управления ToolStripContainer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ToolStripContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "панели инструментов [Windows Forms], встроенное нависание"
  - "ToolStripContainer - элемент управления [Windows Forms], сведения об элементе управления ToolStripContainer"
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Общие сведения об элементе управления ToolStripContainer
Элемент управления <xref:System.Windows.Forms.ToolStripContainer> содержит панели в левой, правой, верхней и нижней частях формы, служащие для расположения и обеспечения нависания элементов управления <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> и <xref:System.Windows.Forms.StatusStrip>.  Если несколько элементов управления <xref:System.Windows.Forms.ToolStrip> помещаются в левую или правую панель <xref:System.Windows.Forms.ToolStripContainer>, они располагаются по вертикали.  Если же они помещаются в верхнюю или нижнюю панель <xref:System.Windows.Forms.ToolStripContainer>, они будут располагаться по вертикали.  Для расположения на форме традиционных элементов управления может использоваться центральная панель <xref:System.Windows.Forms.ToolStripContentPanel> элемента управления <xref:System.Windows.Forms.ToolStripContainer>.  
  
 Любые элементы управления <xref:System.Windows.Forms.ToolStripContainer> можно выделять и удалять на этапе разработки.  Каждая панель элемента управления <xref:System.Windows.Forms.ToolStripContainer> может расширяться и сворачиваться, и его размеры изменяются в соответствии с содержащимися в нем элементами управления.  
  
### Важные компоненты элемента управления ToolStripContainer  
  
|Имя|Описание|  
|---------|--------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Получает нижнюю панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Получает или задает значение, показывающее, видна ли нижняя панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Получает левую панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Получает или задает значение, показывающее, видна ли левая панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Получает правую панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Получает или задает значение, показывающее, видна ли правая панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Получает верхнюю панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Получает или задает значение, показывающее, видна ли верхняя панель элемента управления <xref:System.Windows.Forms.ToolStripContainer>.|  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripContainer>   
 <xref:System.Windows.Forms.ToolStripContentPanel>