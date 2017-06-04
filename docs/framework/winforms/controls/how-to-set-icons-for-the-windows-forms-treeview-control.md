---
title: "Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "примеры [Windows Forms], TreeView - элемент управления"
  - "значки, настройки элемента управления TreeView"
  - "ImageList - компонент [Windows Forms], добавление изображений"
  - "узлы дерева в элементе управления TreeView, значки"
  - "TreeView - элемент управления [Windows Forms], значки узлов"
ms.assetid: c14ddcc0-e5a6-4c21-a2d5-6799fd491781
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Практическое руководство. Определение значков для элемента управления TreeView в Windows Forms
В элементе управления Windows Forms <xref:System.Windows.Forms.TreeView> рядом с каждым узлом может отображаться значок.  Значки располагаются непосредственно слева от текстового обозначения узла.  Чтобы отобразить эти значки, необходимо связать дерево с элементом управления <xref:System.Windows.Forms.ImageList>.  Дополнительные сведения о списках рисунков см. в разделах [Компонент ImageList](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) и [Практическое руководство. Добавление и удаление изображений, выводимых с помощью компонента ImageList, в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).  
  
> [!NOTE]
>  Ошибка в пакете Microsoft .NET Framework версии 1.1 не позволяет отображаться рисункам в узлах <xref:System.Windows.Forms.TreeView>, если приложение вызывает <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>.  Для устранения ошибки следует сразу после вызова <xref:System.Windows.Forms.Application.EnableVisualStyles%2A> вызвать <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> в методе `Main` Эта ошибка устранена в [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
### Чтобы отобразить рисунки в дереве  
  
1.  В свойстве <xref:System.Windows.Forms.TreeView.ImageList%2A> элемента управления <xref:System.Windows.Forms.TreeView> укажите существующий элемент управления <xref:System.Windows.Forms.ImageList>, который необходимо использовать.  
  
     Эти свойства можно задать в окне "Свойства" конструктора или в коде.  
  
    ```vb  
    TreeView1.ImageList = ImageList1  
  
    ```  
  
    ```csharp  
    treeView1.ImageList = imageList1;  
  
    ```  
  
    ```cpp  
    treeView1->ImageList = imageList1;  
    ```  
  
2.  Установите свойства <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> и <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> узла.  Свойство <xref:System.Windows.Forms.TreeNode.ImageIndex%2A> определяет рисунок, отображаемый для обычного и развернутого состояний узла, а свойство <xref:System.Windows.Forms.TreeNode.SelectedImageIndex%2A> определяет рисунок, отображаемый для выделенного узла.  
  
     Эти свойства могут быть заданы в коде или в окне редактора узлов дерева.  Чтобы открыть редактор узлов дерева, нажмите кнопку с многоточием \(![Снимок экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\), расположенную рядом со свойством <xref:System.Windows.Forms.TreeView.Nodes%2A> в окне "Свойства"  
  
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
  
## См. также  
 [Общие сведения об элементе управления TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)   
 [Практическое руководство. Перебор узлов элемента управления TreeView в Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Практическое руководство. Определение того, какой узел элемента управления TreeView был выбран щелчком мыши](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView \(Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)