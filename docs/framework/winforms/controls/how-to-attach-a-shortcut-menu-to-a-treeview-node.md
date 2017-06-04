---
title: "Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView | Microsoft Docs"
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
  - "контекстные меню, добавление к элементам управления TreeView"
  - "узлы дерева в элементе управления TreeView, контекстные меню"
  - "TreeView - элемент управления [Windows Forms], добавление контекстного меню"
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView
Элемент управления Windows Forms <xref:System.Windows.Forms.TreeView> отображает иерархию узлов аналогично функции отображения файлов и папок в левой области окна проводника Windows.  Настроив свойство <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>, можно дать пользователям возможность выполнять контекстно\-зависимые операции при нажатии правой кнопкой мыши элемента управления <xref:System.Windows.Forms.TreeView>.  Путем сопоставления компонента <xref:System.Windows.Forms.ContextMenuStrip> с отдельными элементами <xref:System.Windows.Forms.TreeNode> можно добавить к элементам управления <xref:System.Windows.Forms.TreeView> контекстное меню нужного уровня.  
  
### Чтобы сопоставить контекстное меню элементу TreeNode программно, выполните следующие действия:  
  
1.  Создайте элемент управления <xref:System.Windows.Forms.TreeView> с соответствующими параметрами свойств, создайте корневой <xref:System.Windows.Forms.TreeNode> и добавьте подузлы.  
  
2.  Создайте компонент <xref:System.Windows.Forms.ContextMenuStrip>, а затем добавьте <xref:System.Windows.Forms.ToolStripMenuItem> для каждой операции, которая должна быть доступна во время выполнения.  
  
3.  Присвойте свойству <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> соответствующего <xref:System.Windows.Forms.TreeNode> создаваемое контекстное меню.  
  
4.  После установки свойства контекстное меню будет отображаться в ответ на нажатие правой кнопки мыши на данном узле.  
  
 Следующий пример кода создает базовый <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ContextMenuStrip>, связанный с корневым <xref:System.Windows.Forms.TreeNode> элемента управления <xref:System.Windows.Forms.TreeView>.  В нее необходимо будет подставить те пункты меню, которые требуются для разрабатываемого <xref:System.Windows.Forms.TreeView>.  Кроме того, необходимо написать код для обработки событий <xref:System.Windows.Forms.ToolStripItem.Click> для этих пунктов меню.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)