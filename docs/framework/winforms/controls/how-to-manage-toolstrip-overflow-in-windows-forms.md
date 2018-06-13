---
title: Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], managing overflow
- toolbars [Windows Forms], managing overflow
- examples [Windows Forms], toolbars
- CanOverflow property
ms.assetid: fa10e0ad-4cbf-4c0d-9082-359c2f855d4e
ms.openlocfilehash: 32bbc06320f0dc7f096a4b9021bebfbefedaf8f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33534896"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms
Если все элементы на <xref:System.Windows.Forms.ToolStrip> управления не помещаются в отведенное место, можно разрешить возможность переполнения для <xref:System.Windows.Forms.ToolStrip> и определить поведение о конкретных <xref:System.Windows.Forms.ToolStripItem>s.  
  
 При добавлении <xref:System.Windows.Forms.ToolStripItem>, которые требуют больше места, чем должно быть <xref:System.Windows.Forms.ToolStrip> получает текущий размер формы, <xref:System.Windows.Forms.ToolStripOverflowButton> автоматически отображается на <xref:System.Windows.Forms.ToolStrip>. <xref:System.Windows.Forms.ToolStripOverflowButton> Появляется, и поддержкой переполнения элементы перемещаются в меню переполнения раскрывающегося списка. Это позволяет настроить и определять их приоритеты как ваш <xref:System.Windows.Forms.ToolStrip> элементы соответствии с изменением размеров формы. Можно также изменить внешний вид элементов, переносимых в меню переполнения с помощью <xref:System.Windows.Forms.ToolStripItem.Placement%2A> и <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> свойства и <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> событий. Увеличение размеров формы во время разработки или во время выполнения более <xref:System.Windows.Forms.ToolStripItem>s могут отображаться в главной <xref:System.Windows.Forms.ToolStrip> и <xref:System.Windows.Forms.ToolStripOverflowButton> может даже исчезнуть до уменьшения размера формы.  
  
### <a name="to-enable-overflow-on-a-toolstrip-control"></a>Включение переполнения для элемента управления ToolStrip  
  
-   Убедитесь, что <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> не задано значение `false` для <xref:System.Windows.Forms.ToolStrip>. Значение по умолчанию — `True`.  
  
     При <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> — `True` (по умолчанию), <xref:System.Windows.Forms.ToolStripItem> отправляется в меню переполнения раскрывающегося списка при содержимое <xref:System.Windows.Forms.ToolStripItem> превышает ширину горизонтального <xref:System.Windows.Forms.ToolStrip> или высоту вертикального <xref:System.Windows.Forms.ToolStrip>.  
  
### <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Чтобы указать поведение при переполнении отдельного элемента ToolStripItem  
  
-   Задать <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> свойство <xref:System.Windows.Forms.ToolStripItem> нужное значение. Возможные значения — `Always`, `Never`, и `AsNeeded`. Defaultis `AsNeeded`.  
  
    ```vb  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never  
    ```  
  
    ```csharp  
    toolStripTextBox1.Overflow = _  
    System.Windows.Forms.ToolStripItemOverflow.Never;  
    ```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripOverflowButton>  
 <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>  
 <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>  
 [Общие сведения об элементе управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-overview-windows-forms.md)  
 [Архитектура элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md)  
 [Технологии, положенные в основу работы элемента управления ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md)
