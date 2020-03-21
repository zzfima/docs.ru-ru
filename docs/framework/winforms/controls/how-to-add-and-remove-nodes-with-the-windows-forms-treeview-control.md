---
title: Добавить и удалить узлы с помощью управления TreeView
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
ms.openlocfilehash: f1e74e6d2f827167c32a6955b3010b59cb2f85b8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142216"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms
Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms хранит узлы <xref:System.Windows.Forms.TreeView.Nodes%2A> верхнего уровня в своей коллекции. Каждый из <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeNode.Nodes%2A> них также имеет свою собственную коллекцию для хранения своих детских узлов. Оба свойства коллекции <xref:System.Windows.Forms.TreeNodeCollection>имеют тип, который обеспечивает стандартные члены коллекции, которые позволяют добавлять, удалять и перестраивать узлы на одном уровне иерархии узлов.  
  
### <a name="to-add-nodes-programmatically"></a>Добавление узлов программно  
  
1. Используйте <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> метод свойства представления <xref:System.Windows.Forms.TreeView.Nodes%2A> дерева.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Удаление узлов программно  
  
1. Используйте <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> метод свойства представления <xref:System.Windows.Forms.TreeView.Nodes%2A> дерева, чтобы удалить один <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> узлы, или метод для очистки всех узлов.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
