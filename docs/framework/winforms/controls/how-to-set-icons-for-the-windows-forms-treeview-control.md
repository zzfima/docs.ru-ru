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
ms.openlocfilehash: 451f9ab2b35ad1fbbe9401dacbc8aab44e302701
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909808"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms может отображать значки рядом с каждым узлом. Значки располагаются непосредственно слева от текста узла. Для отображения этих значков необходимо связать древовидное представление с <xref:System.Windows.Forms.ImageList> элементом управления. Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции: Добавление или удаление изображений с помощью компонента](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)Windows Forms ImageList.  
  
> [!NOTE]
> Ошибка в Microsoft .NET Framework версии 1,1 предотвращает отображение изображений на <xref:System.Windows.Forms.TreeView> узлах при вызове <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>приложения. Чтобы обойти эту ошибку, вызовите <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> `Main` метод непосредственно после вызова <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>метода. Эта ошибка исправлена в .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Отображение изображений в представлении в виде дерева  
  
1. Задайте для <xref:System.Windows.Forms.TreeView.ImageList%2A> свойства <xref:System.Windows.Forms.ImageList> элемента управления существующий элемент управления, который вы хотите использовать. <xref:System.Windows.Forms.TreeView>  
  
     Эти свойства можно задать в конструкторе с помощью окно свойств или в коде.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2. Задайте свойства узла <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> . Свойство определяет изображение, отображаемое для обычных и развернутых состояний узла, <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> а свойство определяет изображение, отображаемое для выбранного состояния узла. <xref:System.Windows.Forms.TreeNode.ImageIndex%2A>  
  
     Эти свойства можно задать в коде или в редакторе TreeNode. Чтобы открыть редактор TreeNode, нажмите кнопку с многоточием ( ![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со <xref:System.Windows.Forms.TreeView.Nodes%2A> свойством в окно свойств.  
  
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

- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление узлов с помощью элемента управления Windows Forms TreeView](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор всех узлов элемента управления Windows Forms TreeView](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определение того, какой узел TreeView был выбран](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских сведений в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
