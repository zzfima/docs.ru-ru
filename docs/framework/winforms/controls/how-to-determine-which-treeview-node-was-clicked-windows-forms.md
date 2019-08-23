---
title: Практическое руководство. Определение того, какой узел TreeView был выбран (Windows Forms)
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
ms.openlocfilehash: ab93158daf987e2f19516b8fb3abf80bfe79a12c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967334"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Практическое руководство. Определение того, какой узел TreeView был выбран (Windows Forms)
При работе с элементом управления <xref:System.Windows.Forms.TreeView> Windows Forms распространенной задачей является определение того, какой узел был выбран, и ответ соответствующим образом.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Определение того, какой узел TreeView был выбран  
  
1. <xref:System.EventArgs> Используйте объект для возврата ссылки на объект узла, который щелкнули.  
  
2. Определите, какой узел был выбран, путем проверки <xref:System.Windows.Forms.TreeViewEventArgs> класса, который содержит данные, связанные с событием.  
  
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
    > В качестве альтернативы можно использовать <xref:System.Windows.Forms.MouseEventArgs> <xref:System.Windows.Forms.Control.MouseDown> событие <xref:System.Drawing.Point.X%2A> или <xref:System.Windows.Forms.Control.MouseUp> для получения значений и <xref:System.Drawing.Point.Y%2A> координат, в <xref:System.Drawing.Point> которых произошло нажатие. Затем используйте <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> метод элемента управления, чтобы определить, какой узел был выбран.  
  
## <a name="see-also"></a>См. также

- [Элемент управления TreeView](treeview-control-windows-forms.md)
