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
# <a name="how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control"></a><span data-ttu-id="e0e26-102">Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0e26-102">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>
<span data-ttu-id="e0e26-103">Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms хранит узлы <xref:System.Windows.Forms.TreeView.Nodes%2A> верхнего уровня в своей коллекции.</span><span class="sxs-lookup"><span data-stu-id="e0e26-103">The Windows Forms <xref:System.Windows.Forms.TreeView> control stores the top-level nodes in its <xref:System.Windows.Forms.TreeView.Nodes%2A> collection.</span></span> <span data-ttu-id="e0e26-104">Каждый из <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeNode.Nodes%2A> них также имеет свою собственную коллекцию для хранения своих детских узлов.</span><span class="sxs-lookup"><span data-stu-id="e0e26-104">Each <xref:System.Windows.Forms.TreeNode> also has its own <xref:System.Windows.Forms.TreeNode.Nodes%2A> collection to store its child nodes.</span></span> <span data-ttu-id="e0e26-105">Оба свойства коллекции <xref:System.Windows.Forms.TreeNodeCollection>имеют тип, который обеспечивает стандартные члены коллекции, которые позволяют добавлять, удалять и перестраивать узлы на одном уровне иерархии узлов.</span><span class="sxs-lookup"><span data-stu-id="e0e26-105">Both collection properties are of type <xref:System.Windows.Forms.TreeNodeCollection>, which provides standard collection members that enable you to add, remove, and rearrange the nodes at a single level of the node hierarchy.</span></span>  
  
### <a name="to-add-nodes-programmatically"></a><span data-ttu-id="e0e26-106">Добавление узлов программно</span><span class="sxs-lookup"><span data-stu-id="e0e26-106">To add nodes programmatically</span></span>  
  
1. <span data-ttu-id="e0e26-107">Используйте <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> метод свойства представления <xref:System.Windows.Forms.TreeView.Nodes%2A> дерева.</span><span class="sxs-lookup"><span data-stu-id="e0e26-107">Use the <xref:System.Windows.Forms.TreeNodeCollection.Add%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property.</span></span>  
  
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
  
### <a name="to-remove-nodes-programmatically"></a><span data-ttu-id="e0e26-108">Удаление узлов программно</span><span class="sxs-lookup"><span data-stu-id="e0e26-108">To remove nodes programmatically</span></span>  
  
1. <span data-ttu-id="e0e26-109">Используйте <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> метод свойства представления <xref:System.Windows.Forms.TreeView.Nodes%2A> дерева, чтобы удалить один <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> узлы, или метод для очистки всех узлов.</span><span class="sxs-lookup"><span data-stu-id="e0e26-109">Use the <xref:System.Windows.Forms.TreeNodeCollection.Remove%2A> method of the tree view's <xref:System.Windows.Forms.TreeView.Nodes%2A> property to remove a single node, or the <xref:System.Windows.Forms.TreeNodeCollection.Clear%2A> method to clear all nodes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e0e26-110">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e0e26-110">See also</span></span>

- [<span data-ttu-id="e0e26-111">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="e0e26-111">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="e0e26-112">Общие сведения об элементе управления TreeView</span><span class="sxs-lookup"><span data-stu-id="e0e26-112">TreeView Control Overview</span></span>](treeview-control-overview-windows-forms.md)
- [<span data-ttu-id="e0e26-113">Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0e26-113">How to: Set Icons for the Windows Forms TreeView Control</span></span>](how-to-set-icons-for-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="e0e26-114">Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0e26-114">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [<span data-ttu-id="e0e26-115">Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши</span><span class="sxs-lookup"><span data-stu-id="e0e26-115">How to: Determine Which TreeView Node Was Clicked</span></span>](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [<span data-ttu-id="e0e26-116">Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e0e26-116">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)
