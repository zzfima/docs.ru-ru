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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="039e6-102">Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="039e6-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="039e6-103">При работе с элементом управления <xref:System.Windows.Forms.TreeView> Windows Forms, распространенной задачей является определение того, какой узел был выбран, и ответ соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="039e6-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="039e6-104">Определение того, какой узел TreeView был выбран</span><span class="sxs-lookup"><span data-stu-id="039e6-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="039e6-105">Используйте объект <xref:System.EventArgs>, чтобы получить ссылку на объект узла, который щелкнули.</span><span class="sxs-lookup"><span data-stu-id="039e6-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="039e6-106">Определите, какой узел был выбран, проверив класс <xref:System.Windows.Forms.TreeViewEventArgs>, который содержит данные, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="039e6-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="039e6-107">В качестве альтернативы можно использовать <xref:System.Windows.Forms.MouseEventArgs> события <xref:System.Windows.Forms.Control.MouseDown> или <xref:System.Windows.Forms.Control.MouseUp> для получения <xref:System.Drawing.Point.X%2A> и <xref:System.Drawing.Point.Y%2A> значений координат <xref:System.Drawing.Point>, в которых произошло нажатие.</span><span class="sxs-lookup"><span data-stu-id="039e6-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="039e6-108">Затем используйте метод <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> элемента управления <xref:System.Windows.Forms.TreeView>, чтобы определить, какой узел был выбран.</span><span class="sxs-lookup"><span data-stu-id="039e6-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="039e6-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="039e6-109">See also</span></span>

- [<span data-ttu-id="039e6-110">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="039e6-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
