---
title: Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
ms.openlocfilehash: 7a0e2b69bbec0eb03d40bee2c8e2d4bc9c3558f9
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742016"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)
При работе с элементом управления <xref:System.Windows.Forms.TreeView> Windows Forms, распространенной задачей является определение того, какой узел был выбран, и ответ соответствующим образом.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Определение того, какой узел TreeView был выбран  
  
1. Используйте объект <xref:System.EventArgs>, чтобы получить ссылку на объект узла, который щелкнули.  
  
2. Определите, какой узел был выбран, проверив класс <xref:System.Windows.Forms.TreeViewEventArgs>, который содержит данные, связанные с событием.  
  
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
    > В качестве альтернативы можно использовать <xref:System.Windows.Forms.MouseEventArgs> события <xref:System.Windows.Forms.Control.MouseDown> или <xref:System.Windows.Forms.Control.MouseUp> для получения <xref:System.Drawing.Point.X%2A> и <xref:System.Drawing.Point.Y%2A> значений координат <xref:System.Drawing.Point>, в которых произошло нажатие. Затем используйте метод <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> элемента управления <xref:System.Windows.Forms.TreeView>, чтобы определить, какой узел был выбран.  
  
## <a name="see-also"></a>См. также:

- [Элемент управления TreeView](treeview-control-windows-forms.md)
