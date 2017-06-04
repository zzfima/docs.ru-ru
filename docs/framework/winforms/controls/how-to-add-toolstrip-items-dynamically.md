---
title: "Практическое руководство. Динамическое добавление элементов ToolStrip | Microsoft Docs"
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
  - "ContextMenuStrip - элемент управления [Windows Forms]"
  - "панели инструментов [Windows Forms], добавление элементов динамически"
  - "ToolStrip - элемент управления [Windows Forms]"
ms.assetid: 0e8dea56-5f46-408b-914d-7e360341a234
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Динамическое добавление элементов ToolStrip
Коллекцию пунктов меню элемента управления <xref:System.Windows.Forms.ToolStrip> можно динамически заполнять при открытии меню.  
  
## Пример  
 В примере кода ниже демонстрируется динамическое добавление элементов в элемент управления <xref:System.Windows.Forms.ContextMenuStrip>.  В примере также показано повторное использование <xref:System.Windows.Forms.ContextMenuStrip> для трех различных элементов управления в форме.  
  
 В примере обработчик событий <xref:System.Windows.Forms.ToolStripDropDown.Opening> заполняет коллекцию пунктов меню.  Обработчик событий <xref:System.Windows.Forms.ToolStripDropDown.Opening> анализирует свойства <xref:System.Windows.Forms.ContextMenuStrip.SourceControl%2A?displayProperty=fullName> и <xref:System.Windows.Forms.ToolStripItem.OwnerItem%2A?displayProperty=fullName> и добавляет элемент <xref:System.Windows.Forms.ToolStripItem>, описывающий исходный элемент управления.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#40)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#40)]  
  
## Компиляция кода  
 Для этого примера требуются:  
  
-   ссылки на сборки System.Drawing и System.Windows.Forms.  
  
 Информацию о выполнении сборки этого примера из командной строки для [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] или [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] можно найти в разделе [Построение из командной строки](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) или [Построение из командной строки с помощью csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  Вы можете выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], вставив код в новый проект.  
  
## См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)