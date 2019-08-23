---
title: Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 00a0f19803967f02795e3eade767786eecc1f4dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966545"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a>Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms
Иногда бывает полезно изучить каждый узел в элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> , чтобы выполнить некоторые вычисления по значениям узла. Выполнить эту операции можно с помощью рекурсивной процедуры (рекурсивного метода в C# и C++), которая перебирает каждый узел в каждой коллекции дерева.  
  
 Каждый <xref:System.Windows.Forms.TreeNode> объект в представлении в виде дерева имеет свойства, которые можно использовать для навигации по древовидному <xref:System.Windows.Forms.TreeNode.FirstNode%2A>представлению <xref:System.Windows.Forms.TreeNode.NextNode%2A>: <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.Parent%2A>, и. Значением <xref:System.Windows.Forms.TreeNode.Parent%2A> свойства является родительский узел текущего узла. Дочерние узлы текущего узла, если таковые имеются, перечислены в его <xref:System.Windows.Forms.TreeNode.Nodes%2A> свойстве. Сам элемент управления <xref:System.Windows.Forms.TreeView.TopNode%2A> имеет свойство, которое является корневым узлом всего представления в виде дерева. <xref:System.Windows.Forms.TreeView>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a>Перебор всех узлов элемента управления в представлении в виде дерева  
  
1. Создайте рекурсивную процедуру (рекурсивный метод в C# и C++) для проверки каждого узла.  
  
2. Вызовите процедуру.  
  
     В следующем примере показано, как вывести <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeNode.Text%2A> свойство каждого объекта:  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a>См. также

- [Элемент управления TreeView](treeview-control-windows-forms.md)
- [Рекурсивные процедуры](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
