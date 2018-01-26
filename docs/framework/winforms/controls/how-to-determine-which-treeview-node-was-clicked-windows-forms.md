---
title: "Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: TreeNode
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- tree nodes in TreeView control [Windows Forms], determining node clicked
- TreeView control [Windows Forms], determining node clicked
ms.assetid: 06a4a191-d918-42af-9f49-956c93eff261
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2671d2790b3c5e476513cd5932d4684838aeceb6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a>Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)
При работе с Windows Forms <xref:System.Windows.Forms.TreeView> является управление, общие задачи для определения узла, выбранного щелчком мыши и реагировать соответствующим образом.  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a>Чтобы определить, какой узел элемента управления TreeView, выбранного щелчком мыши  
  
1.  Используйте <xref:System.EventArgs> объект для получения ссылки для объекта выделенного узла.  
  
2.  Определить, какой из узлов была нажата, установив <xref:System.Windows.Forms.TreeViewEventArgs> класс, который содержит данные, связанные с событием.  
  
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
    >  В качестве альтернативы можно использовать <xref:System.Windows.Forms.MouseEventArgs> из <xref:System.Windows.Forms.Control.MouseDown> или <xref:System.Windows.Forms.Control.MouseUp> событий для получения <xref:System.Drawing.Point.X%2A> и <xref:System.Drawing.Point.Y%2A> координировать значения <xref:System.Drawing.Point> места щелчка. Затем с помощью <xref:System.Windows.Forms.TreeView> элемента управления <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> метод, чтобы определить, какой из узлов выполнен щелчок.  
  
## <a name="see-also"></a>См. также  
 [Элемент управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)
