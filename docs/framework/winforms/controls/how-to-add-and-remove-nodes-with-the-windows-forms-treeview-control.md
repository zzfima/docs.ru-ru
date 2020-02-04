---
title: Добавление и удаление узлов с помощью элемента управления TreeView
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
ms.openlocfilehash: 02b3a7286798c6f2a6426e09c8fc6c18b74a6bf0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731961"
---
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a>Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms
Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления хранит узлы верхнего уровня в его <xref:System.Windows.Forms.TreeView.Nodes%2A> коллекции. Каждый <xref:System.Windows.Forms.TreeNode> также имеет собственную коллекцию <xref:System.Windows.Forms.TreeNode.Nodes%2A> для хранения своих дочерних узлов. Оба свойства коллекции имеют тип <xref:System.Windows.Forms.TreeNodeCollection>, который предоставляет стандартные элементы коллекции, позволяющие добавлять, удалять и переупорядочивать узлы на одном уровне иерархии узлов.  
  
### <a name="to-add-nodes-programmatically"></a>Добавление узлов программным способом  
  
1. Используйте метод <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> свойства <xref:System.Windows.Forms.TreeView.Nodes%2A> иерархического представления.  
  
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
  
### <a name="to-remove-nodes-programmatically"></a>Удаление узлов программным способом  
  
1. Используйте метод <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> свойства <xref:System.Windows.Forms.TreeView.Nodes%2A> иерархического представления для удаления одного узла или метода <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> для очистки всех узлов.  
  
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
