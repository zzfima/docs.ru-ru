---
title: Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 7951a545fd8cbd0ae30907922551216161171a8d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
<xref:System.Windows.Forms.ToolStrip> Управления полностью поддерживает возможности макета, такие как изменение размера, расстояние между <xref:System.Windows.Forms.ToolStripItem> элементов управления относительно друг друга, размещение элементов управления в <xref:System.Windows.Forms.ToolStrip>и интервалы между элементами управления <xref:System.Windows.Forms.ToolStrip>.  
  
 Так как значение по умолчанию <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойство `true`, элементов управления изменяются автоматически, если не задать <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Чтобы вручную указать значения на элемент ToolStripItem  
  
1.  Задать <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойства `false` для связанного элемента управления.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2.  Задать <xref:System.Windows.Forms.ToolStripItem.Size%2A> нужным образом для связанного свойства <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Чтобы задать интервал ToolStripItem  
  
1.  Вставьте нужные значения в пикселях <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойств связанного элемента управления.  
  
     Значения <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства задайте интервал между элементом и соседними элементами в следующем порядке: слева, сверху, справа и нижней.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Чтобы выровнять ToolStripItem правую сторону элемента управления ToolStrip  
  
1.  Задать <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойства <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления. По умолчанию <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> равно <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, что элементы управления выравниваются по левому краю <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Чтобы упорядочить элементы ToolStrip на панели инструментов  
  
-   Задать <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> значение из свойства <xref:System.Windows.Forms.ToolStripLayoutStyle> нужного.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.Control.Layout>  
 <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>  
 <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>  
 <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Placement%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
