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
# <a name="how-to-determine-which-treeview-node-was-clicked-windows-forms"></a><span data-ttu-id="c22d6-102">Практическое руководство. Определение узла TreeView, выбранного щелчком мыши (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c22d6-102">How to: Determine Which TreeView Node Was Clicked (Windows Forms)</span></span>
<span data-ttu-id="c22d6-103">При работе с <xref:System.Windows.Forms.TreeView> управлением Windows Forms общая задача состоит в том, чтобы определить, какой узла нажал, и ответить соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="c22d6-103">When working with the Windows Forms <xref:System.Windows.Forms.TreeView> control, a common task is to determine which node was clicked, and respond appropriately.</span></span>  
  
### <a name="to-determine-which-treeview-node-was-clicked"></a><span data-ttu-id="c22d6-104">Чтобы определить, какой узла TreeView был нажат</span><span class="sxs-lookup"><span data-stu-id="c22d6-104">To determine which TreeView node was clicked</span></span>  
  
1. <span data-ttu-id="c22d6-105">Используйте <xref:System.EventArgs> объект, чтобы вернуть ссылку на объект нажатого узла.</span><span class="sxs-lookup"><span data-stu-id="c22d6-105">Use the <xref:System.EventArgs> object to return a reference to the clicked node object.</span></span>  
  
2. <span data-ttu-id="c22d6-106">Определите, какой узла <xref:System.Windows.Forms.TreeViewEventArgs> нажался, проверив класс, содержащий данные, связанные с событием.</span><span class="sxs-lookup"><span data-stu-id="c22d6-106">Determine which node was clicked by checking the <xref:System.Windows.Forms.TreeViewEventArgs> class, which contains data related to the event.</span></span>  
  
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
    > <span data-ttu-id="c22d6-107">В качестве альтернативы можно <xref:System.Windows.Forms.MouseEventArgs> использовать <xref:System.Windows.Forms.Control.MouseDown> событие <xref:System.Windows.Forms.Control.MouseUp> для получения <xref:System.Drawing.Point.X%2A> <xref:System.Drawing.Point.Y%2A> и координации <xref:System.Drawing.Point> значений того, где произошел клик.</span><span class="sxs-lookup"><span data-stu-id="c22d6-107">As an alternative, you can use the <xref:System.Windows.Forms.MouseEventArgs> of the <xref:System.Windows.Forms.Control.MouseDown> or <xref:System.Windows.Forms.Control.MouseUp> event to get the <xref:System.Drawing.Point.X%2A> and <xref:System.Drawing.Point.Y%2A> coordinate values of the <xref:System.Drawing.Point> where the click occurred.</span></span> <span data-ttu-id="c22d6-108">Затем используйте <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> метод управления, чтобы определить, какой узла был нажат.</span><span class="sxs-lookup"><span data-stu-id="c22d6-108">Then, use the <xref:System.Windows.Forms.TreeView> control's <xref:System.Windows.Forms.TreeView.GetNodeAt%2A> method to determine which node was clicked.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22d6-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c22d6-109">See also</span></span>

- [<span data-ttu-id="c22d6-110">Элемент управления TreeView</span><span class="sxs-lookup"><span data-stu-id="c22d6-110">TreeView Control</span></span>](treeview-control-windows-forms.md)
