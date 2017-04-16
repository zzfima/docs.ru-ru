---
title: "Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms | Microsoft Docs"
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
  - "узлы дерева в элементе управления TreeView, перебор"
  - "TreeView - элемент управления [Windows Forms], перебор узлов"
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms
Время от времени рекомендуется проверять каждый узел в элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> для выполнения некоторых вычислений для значений узлов.  Эта операция может быть выполнена с помощью рекурсивной процедуры \(рекурсивного метода в C\# и C\+\+\), в ходе которой просматривается каждый узел в каждой коллекции дерева.  
  
 Каждый объект <xref:System.Windows.Forms.TreeNode>, представленный в дереве просмотра, имеет свойства <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A> и <xref:System.Windows.Forms.TreeNode.Parent%2A>, которые можно использовать для перемещения по дереву.  Свойство <xref:System.Windows.Forms.TreeNode.Parent%2A> определяет родительский узел текущего узла.  Если у текущего узла есть дочерние узлы, они указаны в его свойстве <xref:System.Windows.Forms.TreeNode.Nodes%2A>.  У самого элемента управления <xref:System.Windows.Forms.TreeView> имеется свойство <xref:System.Windows.Forms.TreeView.TopNode%2A>, определяющее корневой узел для всего дерева.  
  
### Итерация всех узлов элемента управления TreeView  
  
1.  Создайте рекурсивную процедуру \(в C\# и C\+\+ — рекурсивный метод\) для проверки каждого узла.  
  
2.  Вызовите эту процедуру.  
  
     В следующем примере показано, как вывести на печать значение свойства <xref:System.Windows.Forms.TreeNode.Text%2A> каждого объекта <xref:System.Windows.Forms.TreeNode>:  
  
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
  
## См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Рекурсивные процедуры](../Topic/Recursive%20Procedures%20\(Visual%20Basic\).md)