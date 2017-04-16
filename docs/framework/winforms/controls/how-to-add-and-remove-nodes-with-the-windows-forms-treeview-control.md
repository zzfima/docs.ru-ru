---
title: "Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms | Microsoft Docs"
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
  - "примеры [Windows Forms], TreeView - элемент управления"
  - "узлы дерева в элементе управления TreeView"
  - "TreeView - элемент управления [Windows Forms], добавление узлов"
  - "TreeView - элемент управления [Windows Forms], удаление узлов"
ms.assetid: de1b82db-4905-449a-9f59-af271a6b6673
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms
В элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> хранятся узлы верхнего уровня в коллекции <xref:System.Windows.Forms.TreeView.Nodes%2A>.  Каждый элемент <xref:System.Windows.Forms.TreeNode> также имеет собственную коллекцию <xref:System.Windows.Forms.TreeNode.Nodes%2A> для хранения дочерних узлов.  Оба свойства коллекции имеют тип <xref:System.Windows.Forms.TreeNodeCollection>, обеспечивающий стандартные элементы коллекции с возможностью добавления, удаления и переупорядочения узлов на одном уровне иерархии узла.  
  
### Чтобы добавить узел программными средствами  
  
1.  Используйте метод <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> свойства древовидного представления <xref:System.Windows.Forms.TreeView.Nodes%2A>.  
  
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
  
### Чтобы удалить узел программными средствами  
  
1.  Воспользуйтесь методом <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> свойства <xref:System.Windows.Forms.TreeView.Nodes%2A> данного дерева для удаления одиночного узла или методом <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> для очистки всех узлов.  
  
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
  
## См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)