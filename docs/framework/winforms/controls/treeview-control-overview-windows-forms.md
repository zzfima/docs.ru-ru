---
title: Общие сведения об элементе управления TreeView (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- TreeView
helpviewer_keywords:
- TreeView control [Windows Forms], about TreeView control
ms.assetid: 0ece823a-9508-478a-bbdb-7d7c3bae51d5
ms.openlocfilehash: 6326f8976e20b5b72e1b6690ab323c8581411156
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="treeview-control-overview-windows-forms"></a>Общие сведения об элементе управления TreeView (Windows Forms)
С помощью элемента управления <xref:System.Windows.Forms.TreeView> Windows Forms пользователям можно показывать иерархию узлов аналогично отображению файлов и папок на левой панели проводника операционной системы Windows. Каждый узел дерева может содержать другие узлы, называемые *дочерние узлы*. Родительские узлы (т. е. содержащие дочерние узлы) можно показывать как в развернутом, так и в свернутом виде. В представлении в виде дерева рядом с узлами можно также показывать флажки, если присвоить свойству <xref:System.Windows.Forms.TreeView.CheckBoxes%2A> этого дерева значение `true`. Вы можете выделять узлы и отменять их выделение программными средствами, задавая для свойства <xref:System.Windows.Forms.TreeNode.Checked%2A> узла значение `true` или `false`.  
  
## <a name="key-properties"></a>Ключевые свойства  
 Ключевые свойства элемента управления <xref:System.Windows.Forms.TreeView> — это <xref:System.Windows.Forms.TreeView.Nodes%2A> и <xref:System.Windows.Forms.TreeView.SelectedNode%2A>. Свойство <xref:System.Windows.Forms.TreeView.Nodes%2A> содержит список узлов верхнего уровня в представлении дерева. Свойство <xref:System.Windows.Forms.TreeView.SelectedNode%2A> определяет выделенный в данный момент узел. Рядом с узлами могут отображаться значки. Элемент управления использует изображения из элемента <xref:System.Windows.Forms.ImageList>, указанного в свойстве <xref:System.Windows.Forms.TreeView.ImageList%2A> дерева. Свойство <xref:System.Windows.Forms.TreeView.ImageIndex%2A> задает изображение по умолчанию для узлов в представлении дерева. Дополнительные сведения о выводе изображений см. в разделе [как: определение значков для элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md). При использовании [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)] вы получаете доступ к большой библиотеке стандартных изображений, которые можно использовать с элементом управления <xref:System.Windows.Forms.TreeView>.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.TreeView>  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)  
 [Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)  
 [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
