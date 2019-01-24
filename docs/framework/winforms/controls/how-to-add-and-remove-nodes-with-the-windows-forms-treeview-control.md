---
title: Как выполнить Добавление и удаление узлов с помощью элемента управления TreeView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], removing nodes
- tree nodes in TreeView control
- TreeView control [Windows Forms], adding nodes
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
ms.openlocfilehash: 30dbe55711d92ea1fdbbbfd147a65b27d0dc9a50
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54711513"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Как выполнить Добавление и удаление узлов с помощью элемента управления TreeView в Windows Forms
Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления сохраняет узлы верхнего уровня в его <xref:System.Windows.Forms.TreeView.Nodes%2A> коллекции. Каждый <xref:System.Windows.Forms.TreeNode> также имеет свой собственный <xref:System.Windows.Forms.TreeNode.Nodes%2A> коллекцию для хранения дочерних узлов. Оба свойства коллекции имеют тип <xref:System.Windows.Forms.TreeNodeCollection>, который предоставляет стандартные элементы коллекции, которые позволяют добавлять, удалять и изменения порядка узлов на одном уровне иерархии узла.  
  
### <a name="to-add-nodes-programmatically"></a>Чтобы добавить узлы программным способом  
  
1.  Используйте <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> метод представления дерева <xref:System.Windows.Forms.TreeView.Nodes%2A> свойство.  
  
    ```vb  
    ' Adds new node as a child node of the currently selected node.  
    Dim newNode As TreeNode = New TreeNode("Text for new node")  
    TreeView1.SelectedNode.Nodes.Add(newNode)  
    ```  
  
    ```csharp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode newNode = new TreeNode("Text for new node");  
    treeView1.SelectedNode.Nodes.Add(newNode);  
    ```  
  
    ```cpp  
    // Adds new node as a child node of the currently selected node.  
    TreeNode ^ newNode = new TreeNode("Text for new node");  
    treeView1->SelectedNode->Nodes->Add(newNode);  
    ```  
  
### <a name="to-remove-nodes-programmatically"></a>Для удаления узлов программным способом  
  
1.  Используйте <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> метод представления дерева <xref:System.Windows.Forms.TreeView.Nodes%2A> свойство, чтобы удалить только один узел, или <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> метод, чтобы удалить все узлы.  
  
    ```vb  
    ' Removes currently selected node, or root if nothing is selected.  
    TreeView1.Nodes.Remove(TreeView1.SelectedNode)  
    ' Clears all nodes.  
    TreeView1.Nodes.Clear()  
    ```  
  
    ```csharp  
    // Removes currently selected node, or root if nothing   
    // is selected.  
    treeView1.Nodes.Remove(treeView1.SelectedNode);  
    // Clears all nodes.  
    TreeView1.Nodes.Clear();  
    ```  
  
    ```cpp  
    // Removes currently selected node, or root if nothing  
    // is selected.  
    treeView1->Nodes->Remove(treeView1->SelectedNode);  
    // Clears all nodes.  
    treeView1->Nodes->Clear();  
    ```  
  
## <a name="see-also"></a>См. также
- [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
- [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)
- [Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определить, какой узел элемента управления TreeView была нажата](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или элемент управления ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
