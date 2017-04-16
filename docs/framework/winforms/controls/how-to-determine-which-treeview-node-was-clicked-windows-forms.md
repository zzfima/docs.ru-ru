---
title: "Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TreeNode"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], TreeView - элемент управления"
  - "узлы дерева в элементе управления TreeView, определение выбранного узла"
  - "TreeView - элемент управления [Windows Forms], определение выбранного узла"
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)
Одной из типичных задач, выполняемых при работе с элементом управления Windows Forms <xref:System.Windows.Forms.TreeView>, является определение узла, выбранного щелчком мыши, и выбор соответствующего ответного действия.  
  
### Чтобы определить, какой узел элемента управления TreeView был выбран щелчком мыши  
  
1.  Используйте объект <xref:System.EventArgs> для получения ссылки для объекта узла, выбранного щелчком мыши.  
  
2.  Определите, какой узел был выбран щелчком мыши, путем проверки класса <xref:System.Windows.Forms.TreeViewEventArgs>, в котором содержатся данные, связанные с этим событием.  
  
    ```vb  
    Private Sub TreeView1_AfterSelect(ByVal sender As System.Object, _  
    ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       ' Determine by checking the Node property of the TreeViewEventArgs.  
       MessageBox.Show(e.Node.Text)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,   
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       // Determine by checking the Text property.  
       MessageBox.Show(e.Node.Text);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          // Determine by checking the Text property.  
          MessageBox::Show(e->Node->Text);  
       }  
    ```  
  
    > [!NOTE]
    >  Можно также использовать объект <xref:System.Windows.Forms.MouseEventArgs> события <xref:System.Windows.Forms.Control.MouseDown> или <xref:System.Windows.Forms.Control.MouseUp> для получения значений координат <xref:System.Drawing.Point.X%2A> и <xref:System.Drawing.Point.Y%2A> объекта <xref:System.Drawing.Point> — точки, в которой пользователь щелкнул мышью.  Затем используйте метод <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> элемента управления <xref:System.Windows.Forms.TreeView>, чтобы определить, какой узел был выбран щелчком мыши.  
  
## См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)