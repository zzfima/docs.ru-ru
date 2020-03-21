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
ms.openlocfilehash: d960eaae2aa479e0be74e9a5e4fdbfec8ff411c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182180"
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)
При работе с <xref:System.Windows.Forms.TreeView> управлением Windows Forms общая задача состоит в том, чтобы определить, какой узла нажал, и ответить соответствующим образом.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Чтобы определить, какой узла TreeView был нажат  
  
1. Используйте <xref:System.EventArgs> объект, чтобы вернуть ссылку на объект нажатого узла.  
  
2. Определите, какой узла <xref:System.Windows.Forms.TreeViewEventArgs> нажался, проверив класс, содержащий данные, связанные с событием.  
  
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
    > В качестве альтернативы можно <xref:System.Windows.Forms.MouseEventArgs> использовать <xref:System.Windows.Forms.Control.MouseDown> событие <xref:System.Windows.Forms.Control.MouseUp> для получения <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> и координации <xref:System.Drawing.Point> значений того, где произошел клик. Затем используйте <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> метод управления, чтобы определить, какой узла был нажат.  
  
## <a name="see-also"></a>См. также раздел

- [Элемент управления TreeView](treeview-control-windows-forms.md)
