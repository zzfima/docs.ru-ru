---
title: Как выполнить Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], examples
- examples [Windows Forms], toolbars
- toolbars [Windows Forms], rearranging controls
- ToolStrip control [Windows Forms], reordering items
ms.assetid: 8480b69a-379f-4dc2-8dcf-365ed93692b2
ms.openlocfilehash: 0b3662a700d897607780e8d5032c498faff97753
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577023"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Как выполнить Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms
Вы можете включить пользователя для изменения порядка <xref:System.Windows.Forms.ToolStripItem> элементов управления в <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Для включения элементов ToolStripItem во время выполнения  
  
-   Задайте для свойства <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> значение `true`. По умолчанию <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> является `false`.  
  
     Во время выполнения пользователь удерживает клавишу ALT и левую кнопку мыши для перетаскивания <xref:System.Windows.Forms.ToolStripItem> в другое расположение на <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
