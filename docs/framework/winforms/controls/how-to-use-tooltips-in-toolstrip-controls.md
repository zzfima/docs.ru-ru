---
title: "Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip | Microsoft Docs"
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
  - "панели инструментов [Windows Forms], добавление всплывающих подсказок"
  - "ToolStrip - элемент управления [Windows Forms], добавление всплывающих подсказок"
  - "всплывающие подсказки [Windows Forms], добавление"
ms.assetid: c5d86024-a7c5-44ee-8b3f-2daf53d80d3e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Практическое руководство. Использование всплывающих подсказок в элементах управления ToolStrip
Подсказку <xref:System.Windows.Forms.ToolTip> можно отобразить для необходимого элемента управления <xref:System.Windows.Forms.ToolStrip>, присвоив свойству <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> элемента управления значение `true`.  
  
### Отображение всплывающей подсказки  
  
-   Задайте для свойства <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> элемента управления значение `true`.  
  
     Значением по умолчанию для <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A?displayProperty=fullName> является `true`, а для <xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A?displayProperty=fullName> и <xref:System.Windows.Forms.StatusStrip.ShowItemToolTips%2A?displayProperty=fullName> – `false`.  
  
### Использование свойства ToolTipText для текста подсказки элемента управления ToolStripButton  
  
1.  Присвойте свойству <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A> кнопки значение `true`.  
  
2.  Присвойте свойству <xref:System.Windows.Forms.ToolStripButton.AutoToolTip%2A?displayProperty=fullName> кнопки значение `false`.  
  
     Свойство `AutoToolTip` по умолчанию имеет значение `true` для <xref:System.Windows.Forms.ToolStripButton>, <xref:System.Windows.Forms.ToolStripDropDownButton> и <xref:System.Windows.Forms.ToolStripSplitButton>.  
  
     <xref:System.Windows.Forms.ToolStripButton> используйте свое свойство `Text` для текста <xref:System.Windows.Forms.ToolTip> по умолчанию.  Используйте эту процедуру для отображения пользовательского текста в <xref:System.Windows.Forms.ToolStripButton> <xref:System.Windows.Forms.ToolTip>.  
  
> [!NOTE]
>  Если <xref:System.Windows.Forms.ToolStripItemDisplayStyle> присвоить значение <xref:System.Windows.Forms.ToolStripItemDisplayStyle> или <xref:System.Windows.Forms.ToolStripItemDisplayStyle>, текст на кнопке отображаться не будет, но подсказка будет показана.  
  
## См. также  
 <xref:System.Windows.Forms.ToolStrip.ShowItemToolTips%2A>   
 <xref:System.Windows.Forms.ToolStripButton>   
 <xref:System.Windows.Forms.ToolStripDropDownButton>   
 <xref:System.Windows.Forms.ToolStripSplitButton>   
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)