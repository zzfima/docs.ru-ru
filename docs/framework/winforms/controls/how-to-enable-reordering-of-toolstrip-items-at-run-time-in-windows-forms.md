---
title: Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения
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
ms.openlocfilehash: 44b52bf997819f090569d08eb395d8af18f61370
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745485"
---
# <a name="how-to-enable-reordering-of-toolstrip-items-at-run-time-in-windows-forms"></a>Практическое руководство. Разрешение переупорядочения элементов ToolStrip во время выполнения в Windows Forms
Вы можете разрешить пользователю изменять порядок элементов управления <xref:System.Windows.Forms.ToolStripItem> на <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-enable-toolstripitem-rearrangement-at-run-time"></a>Включение перестановки элементов ToolStripItem во время выполнения  
  
- Установите свойство <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> в значение `true`. По умолчанию <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A> `false`.  
  
     Во время выполнения пользователь удерживает нажатой клавишу ALT и левую кнопку мыши для перетаскивания <xref:System.Windows.Forms.ToolStripItem> в другое место на <xref:System.Windows.Forms.ToolStrip>.  
  
    ```vb  
    toolStrip1.AllowItemReorder = True  
    ```  
  
    ```csharp  
    toolStrip1.AllowItemReorder = true;  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
