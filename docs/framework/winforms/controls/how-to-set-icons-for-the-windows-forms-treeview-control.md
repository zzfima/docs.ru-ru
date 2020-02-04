---
title: Задание значков для элемента управления TreeView
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
ms.openlocfilehash: e3d7fc35c6d9f70822cdd0b69dd12f3d469f4ffa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76737262"
---
# <a name="how-to-set-icons-for-the-windows-forms-treeview-control"></a>Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
Элемент управления <xref:System.Windows.Forms.TreeView> Windows Forms может отображать значки рядом с каждым узлом. Значки располагаются непосредственно слева от текста узла. Для отображения этих значков необходимо связать представление в виде дерева с элементом управления <xref:System.Windows.Forms.ImageList>. Дополнительные сведения о списках изображений см. в разделе [ImageList Component](imagelist-component-windows-forms.md) и [инструкции по добавлению или удалению изображений с помощью компонента Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
> Ошибка в Microsoft .NET Framework версии 1,1 не приводит к появлению изображений на <xref:System.Windows.Forms.TreeView> узлах, когда приложение вызывает <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>. Чтобы обойти эту ошибку, вызовите <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> в методе `Main` сразу же после вызова <xref:System.Windows.Forms.Application.EnableVisualStyles%2A>. Эта ошибка исправлена в .NET Framework 2,0.  
  
### <a name="to-display-images-in-a-tree-view"></a>Отображение изображений в представлении в виде дерева  
  
1. Задайте для свойства <xref:System.Windows.Forms.TreeView.ImageList%2A> элемента управления <xref:System.Windows.Forms.TreeView> существующий элемент управления <xref:System.Windows.Forms.ImageList>, который вы хотите использовать.  
  
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
  
2. Задайте свойства <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> узла. Свойство <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> определяет изображение, отображаемое для обычных и развернутых состояний узла, а свойство <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> определяет изображение, отображаемое для выбранного состояния узла.  
  
     Эти свойства можно задать в коде или в редакторе TreeNode. Чтобы открыть редактор узлов дерева, нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.TreeView.Nodes%2A> в окно свойств.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об элементе управления TreeView](treeview-control-overview-windows-forms.md)
- [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)
- [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](how-to-determine-which-treeview-node-was-clicked-windows-forms.md)
- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
