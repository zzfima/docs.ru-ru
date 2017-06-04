---
title: "Практическое руководство. Использование элементов управления ToolStripPanel при создании форм MDI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MDI - интерфейс, использование элементов управления ToolStripPanel [Windows Forms]"
  - "панели инструментов [Windows Forms], использование для MDI"
  - "ToolStripPanel - элемент управления [Windows Forms], использование для MDI"
ms.assetid: d6b884fc-0846-465f-83c3-5dc0fe93b00f
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Использование элементов управления ToolStripPanel при создании форм MDI
<xref:System.Windows.Forms.ToolStripPanel> обеспечивает гибкость для приложений многодокументного интерфейса \(MDI\) с помощью метода <xref:System.Windows.Forms.ToolStripPanel.Join%2A>.  
  
## Пример  
 В примере кода ниже показано использование элементов управления <xref:System.Windows.Forms.ToolStripPanel> с формой MDI.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#10)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#10)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Design, System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## См. также  
 <xref:System.Windows.Forms.ToolStripPanel>   
 [Практическое руководство. Присоединение ToolStrip к ToolStripPanel](../../../../docs/framework/winforms/controls/how-to-join-toolstrippanels.md)