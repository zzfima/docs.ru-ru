---
title: Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], node icons
- ImageList component [Windows Forms], adding images
- icons [Windows Forms], setting for TreeView control
- tree nodes in TreeView control [Windows Forms], icons
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
ms.openlocfilehash: b732aa510be22f3cbdc5197574f1e2a825c35df4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
Windows Forms <xref:System.Windows.Forms.TreeView> элемент управления может отображать значки рядом с каждым узлом. Значки располагаются непосредственно слева от текста узла. Чтобы отобразить эти значки, необходимо связать дерево с <xref:System.Windows.Forms.ImageList> элемента управления. Дополнительные сведения о списках изображений см. в разделе [компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [как: Добавление и удаление изображений с помощью компонента ImageList в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Ошибка в Microsoft .NET Framework версии 1.1 предотвращающим изображения на <xref:System.Windows.Forms.TreeView> узлов, когда приложение вызывает метод <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Чтобы обойти эту ошибку, вызовите <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> в ваш `Main` метод сразу после вызова <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Эта ошибка исправлена в [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### <a name="to-display-images-in-a-tree-view"></a>Для отображения изображений в виде дерева  
  
1.  Задать <xref:System.Windows.Forms.TreeView> элемента управления <xref:System.Windows.Forms.TreeView.ImageList%2A> свойства для существующего <xref:System.Windows.Forms.ImageList> управления вы хотите использовать.  
  
     Эти свойства можно задать в конструкторе с помощью окна «Свойства» или в коде.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Узел набора <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> свойства. <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> Свойство определяет рисунок, отображаемый для обычного и развернутого состояний узла и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> определяет рисунок, отображаемый для выделенного узла.  
  
     Эти свойства могут быть заданы в коде или в редакторе узлов дерева. Чтобы открыть редактор узлов дерева, нажмите кнопку с многоточием ( ![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с <xref:System.Windows.Forms.TreeView.Nodes%2A> свойства в окне «Свойства».  
  
    ```vb  
    ' (Assumes that ImageList1 contains at least two images and  
    ' the TreeView control contains a selected image.)  
    TreeView1.SelectedNode.ImageIndex = 0  
    TreeView1.SelectedNode.SelectedImageIndex = 1  
    ```  
  
    ```csharp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1.SelectedNode.ImageIndex = 0;  
    treeView1.SelectedNode.SelectedImageIndex = 1;  
    ```  
  
    ```cpp  
    // (Assumes that imageList1 contains at least two images and  
    // the TreeView control contains a selected image.)  
    treeView1->SelectedNode->ImageIndex = 0;  
    treeView1->SelectedNode->SelectedImageIndex = 1;  
    ```  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)  
 [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)  
 [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)  
 [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)  
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
