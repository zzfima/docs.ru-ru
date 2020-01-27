---
title: Руководство. Изменение расстояния и выравнивания элементов ToolStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 805fbac5fe33071006f29692d503e5c57eacd765
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746560"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
Элемент управления <xref:System.Windows.Forms.ToolStrip> полностью поддерживает функции макета, такие как изменение размера, расстояния от <xref:System.Windows.Forms.ToolStripItem> элементов управления относительно друг друга, размещение элементов управления в <xref:System.Windows.Forms.ToolStrip>и расстояния от элементов управления относительно <xref:System.Windows.Forms.ToolStrip>.  
  
 Так как значение свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> по умолчанию равно `true`, размер элементов управления изменяется автоматически, если только для свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> не установлено значение `false`.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Ручное изменение размера элемента ToolStripItem  
  
1. Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> значение `false` для связанного элемента управления.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Задайте свойство <xref:System.Windows.Forms.ToolStripItem.Size%2A> для связанного <xref:System.Windows.Forms.ToolStripItem>.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Задание расстояния для элемента ToolStripItem  
  
1. Вставьте нужные значения (в пикселях) в свойство <xref:System.Windows.Forms.ToolStripItem.Margin%2A> связанного элемента управления.  
  
     Значения свойства <xref:System.Windows.Forms.ToolStripItem.Margin%2A> задают интервал между элементом и соседними элементами в следующем порядке: слева, сверху, справа и снизу.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding   
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Выровняйте ToolStripItem с правой стороны ToolStrip  
  
1. Задайте для свойства <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> значение <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления. По умолчанию <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> имеет значение <xref:System.Windows.Forms.ToolStripItemAlignment.Left>, которое выровняйте элементы управления по левой стороне <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =   
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Упорядочивание элементов ToolStrip на ToolStrip  
  
- Присвойте свойству <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> нужное значение <xref:System.Windows.Forms.ToolStripLayoutStyle>.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =   
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.Control.Layout>
- <xref:System.Windows.Forms.ToolStrip.LayoutCompleted>
- <xref:System.Windows.Forms.ToolStrip.LayoutSettings%2A>
- <xref:System.Windows.Forms.ToolStripItem.TextImageRelation%2A>
- <xref:System.Windows.Forms.ToolStripItem.Placement%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
