---
title: "Практическое руководство. Обработка события Opening компонента ContextMenuStrip | Microsoft Docs"
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
  - "контекстные меню, обработка событий"
  - "ContextMenuStrip - элемент управления [Windows Forms]"
  - "обработка событий, контекстные меню"
  - "контекстные меню, обработка событий"
  - "ToolStrip - элемент управления [Windows Forms]"
ms.assetid: b661b3dd-7815-4cc2-a1aa-a9a391ab3427
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Практическое руководство. Обработка события Opening компонента ContextMenuStrip
Можно настроить поведение элемента управления <xref:System.Windows.Forms.ContextMenuStrip> путем обработки события <xref:System.Windows.Forms.ToolStripDropDown.Opening>.  
  
## Пример  
 В следующем примере кода показана обработка события <xref:System.Windows.Forms.ToolStripDropDown.Opening>.  Обработчик событий динамически добавляет элементы к элементу управления <xref:System.Windows.Forms.ContextMenuStrip>.  Полный пример кода см. в разделе [Практическое руководство. Динамическое добавление элементов ToolStrip](../../../../docs/framework/winforms/controls/how-to-add-toolstrip-items-dynamically.md).  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#42)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#42)]  
  
 Чтобы предотвратить открытие меню, установите для свойства <xref:System.ComponentModel.CancelEventArgs.Cancel%2A?displayProperty=fullName> значение `true`.  
  
## См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.ComponentModel.CancelEventArgs.Cancel%2A>   
 <xref:System.Windows.Forms.ToolStripDropDown>   
 [Элемент управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)