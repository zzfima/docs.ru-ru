---
title: "Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора | Microsoft Docs"
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
  - "контекстные меню, присоединение к TreeNodes"
  - "TreeNode, присоединение к контекстному меню с помощью конструктора"
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Прикрепление контекстного меню к элементу управления TreeNode с помощью конструктора
Элемент управления Windows Forms <xref:System.Windows.Forms.TreeView> отображает иерархию узлов аналогично функции отображения файлов и папок в левой области окна проводника Windows.  Настроив свойство <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>, можно дать пользователям возможность выполнять контекстно\-зависимые операции при нажатии правой кнопкой мыши элемента управления <xref:System.Windows.Forms.TreeView>.  Путем сопоставления компонента <xref:System.Windows.Forms.ContextMenuStrip> с отдельными элементами <xref:System.Windows.Forms.TreeNode> можно добавить к элементам управления <xref:System.Windows.Forms.TreeView> контекстное меню нужного уровня.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих настроек или выпуска.  Чтобы изменить параметры, в меню **Сервис** выберите команду **Импорт и экспорт параметров**.  Дополнительные сведения см. в разделе [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ru-ru/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Чтобы сопоставить контекстное меню элементу TreeNode в процессе разработки, выполните следующие действия:  
  
1.  Добавьте к форме элемент управления <xref:System.Windows.Forms.TreeView>, затем добавьте к <xref:System.Windows.Forms.TreeView> необходимые узлы.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Добавьте к форме компонент <xref:System.Windows.Forms.ContextMenuStrip>, затем добавьте к контекстному меню пункты меню, соответствующие операциям на уровне узлов, которые должны быть доступны во время выполнения.  Дополнительные сведения см. в разделе [Практическое руководство. Добавление элементов меню в элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Повторно откройте диалоговое окно **TreeNodeEditor** для элемента управления <xref:System.Windows.Forms.TreeView>, выберите узел, который необходимо изменить, и установите для его свойства <xref:System.Windows.Forms.ContextMenuStrip> добавленное контекстное меню.  
  
4.  После установки свойства контекстное меню будет отображаться в ответ на нажатие правой кнопки мыши на данном узле.  
  
     Кроме того, необходимо написать код для обработки событий <xref:System.Windows.Forms.ToolStripItem.Click> для этих пунктов меню.  
  
## См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Элемент управления ContextMenuStrip](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)