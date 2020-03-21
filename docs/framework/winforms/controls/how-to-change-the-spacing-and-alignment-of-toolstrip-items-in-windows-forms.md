---
title: 'Как: Изменить интервал и выравнивание элементов ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], aligning items
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], aligning items
ms.assetid: cd483466-0f49-43df-addf-e2b5fcd64027
ms.openlocfilehash: 550ac1660a077e8d766a01bfa8d102c07f0fbfeb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182230"
---
# <a name="how-to-change-the-spacing-and-alignment-of-toolstrip-items-in-windows-forms"></a>Практическое руководство. Изменение расстояния между элементами и способа их выравнивания для элемента управления ToolStrip в Windows Forms
Элемент <xref:System.Windows.Forms.ToolStrip> управления полностью поддерживает функции компоновки, такие как размер, расстояние <xref:System.Windows.Forms.ToolStripItem> <xref:System.Windows.Forms.ToolStrip>элементов управления относительно друг друга, <xref:System.Windows.Forms.ToolStrip>расположение элементов управления на , и расстояние элементов управления по отношению к .  
  
 Поскольку <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> значение свойства по `true`умолчанию является, элементы <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> управления `false`размерируются автоматически, если вы не установите свойство.  
  
### <a name="to-manually-size-a-toolstripitem"></a>Вручную размер ToolStripItem  
  
1. Установите <xref:System.Windows.Forms.ToolStripItem.AutoSize%2A> свойство `false` для связанного элемента управления.  
  
    ```vb  
    ToolStripButton1.AutoSize = False  
    ```  
  
    ```csharp  
    toolStripButton1.AutoSize = false;  
    ```  
  
2. Установите <xref:System.Windows.Forms.ToolStripItem.Size%2A> свойство так, как <xref:System.Windows.Forms.ToolStripItem>вы хотите для связанных.  
  
### <a name="to-set-the-spacing-of-a-toolstripitem"></a>Установить интервал ы от ToolStripItem  
  
1. Вставьте желаемые значения в пиксели в свойство <xref:System.Windows.Forms.ToolStripItem.Margin%2A> связанного элемента управления.  
  
     Значения <xref:System.Windows.Forms.ToolStripItem.Margin%2A> свойства указывают расстояние между элементом и соседними элементами в этом порядке: левый, верхний, правый и нижний.  
  
    ```vb  
    ToolStripTextBox1.Margin = New System.Windows.Forms.Padding _  
        (3, 0, 3, 0)  
    ```  
  
    ```csharp  
    toolStripTextBox1.Margin = new System.Windows.Forms.Padding
        (3, 0, 3, 0);  
    ```  
  
### <a name="to-align-a-toolstripitem-to-the-right-side-of-the-toolstrip"></a>Для выравнивания ToolStripItem в правую сторону ToolStrip  
  
1. Установите <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> свойство <xref:System.Windows.Forms.ToolStripItemAlignment.Right> для связанного элемента управления. По умолчанию, <xref:System.Windows.Forms.ToolStripItem.Alignment%2A> <xref:System.Windows.Forms.ToolStripItemAlignment.Left>устанавливается, который выравнивает элементы <xref:System.Windows.Forms.ToolStrip>управления в левую сторону .  
  
    ```vb  
    ToolStripSplitButton1.Alignment = _  
        System.Windows.Forms.ToolStripItemAlignment.Right  
    ```  
  
    ```csharp  
    toolStripSplitButton1.Alignment =
        System.Windows.Forms.ToolStripItemAlignment.Right;  
    ```  
  
### <a name="to-arrange-toolstrip-items-on-the-toolstrip"></a>Для организации элементов ToolStrip на ToolStrip  
  
- Установите <xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A> свойство на <xref:System.Windows.Forms.ToolStripLayoutStyle> стоимость, что вы хотите.  
  
    ```vb  
    ToolStripDropDown1.LayoutStyle = _  
        System.Windows.Forms.ToolStripLayoutStyle.Flow  
    ```  
  
    ```csharp  
    toolStripDropDown1.LayoutStyle =
        System.Windows.Forms.ToolStripLayoutStyle.Flow;  
    ```  
  
## <a name="see-also"></a>См. также раздел

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
