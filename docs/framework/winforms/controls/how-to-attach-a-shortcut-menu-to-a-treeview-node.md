---
title: "Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shortcut menus [Windows Forms], adding to TreeView controls
- TreeView control [Windows Forms], adding shortcut menus
- tree nodes in TreeView control [Windows Forms], shortcut menus
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d3814e95ad2d91157181682984fc9b53254ba813
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-attach-a-shortcut-menu-to-a-treeview-node"></a>Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView
Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления выводит на экран иерархию узлов аналогично отображения файлов и папок в левой области окна проводника. Установив <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> свойства, можно предоставить контекстно-зависимые операции для пользователя при их правой кнопкой мыши <xref:System.Windows.Forms.TreeView> элемента управления. Связав <xref:System.Windows.Forms.ContextMenuStrip> компонента с отдельными <xref:System.Windows.Forms.TreeNode> элементы, можно добавить настраиваемый уровень функциональности контекстное меню для вашего <xref:System.Windows.Forms.TreeView> элементов управления.  
  
### <a name="to-associate-a-shortcut-menu-with-a-treenode-programmatically"></a>Чтобы связать контекстное меню с TreeNode программным способом  
  
1.  Создать экземпляр <xref:System.Windows.Forms.TreeView> управления с соответствующими параметрами свойств, создайте корневой <xref:System.Windows.Forms.TreeNode>, а затем добавьте вложенные узлы.  
  
2.  Создать экземпляр <xref:System.Windows.Forms.ContextMenuStrip> компонента, а затем добавьте <xref:System.Windows.Forms.ToolStripMenuItem> для каждой операции, которую нужно сделать доступными во время выполнения.  
  
3.  Задать <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> свойства соответствующего <xref:System.Windows.Forms.TreeNode> в контекстное меню создания.  
  
4.  Если это свойство имеет значение, в контекстном меню отображается при щелчке правой кнопкой мыши узел.  
  
 В следующем примере кода создается простой <xref:System.Windows.Forms.TreeView> и <xref:System.Windows.Forms.ContextMenuStrip> связанную с корневым <xref:System.Windows.Forms.TreeNode> из <xref:System.Windows.Forms.TreeView>. Необходимо будет подставить те пункты меню, которые соответствуют <xref:System.Windows.Forms.TreeView> вы разрабатываете. Кроме того, необходимо написать код для обработки <xref:System.Windows.Forms.ToolStripItem.Click> событий для этих пунктов меню.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
