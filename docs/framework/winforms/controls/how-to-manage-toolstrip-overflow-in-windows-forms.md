---
title: Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip
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
ms.openlocfilehash: 52cc02e626bee2d2457355028ecddc17e462d8fa
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736143"
---
# <a name="how-to-manage-toolstrip-overflow-in-windows-forms"></a>Практическое руководство. Определение действий, выполняемых в случае переполнения элемента управления ToolStrip, в Windows Forms

Если все элементы элемента управления <xref:System.Windows.Forms.ToolStrip> не помещаются в выделенном пространстве, можно включить функцию переполнения на <xref:System.Windows.Forms.ToolStrip> и определить поведение переполнения конкретных <xref:System.Windows.Forms.ToolStripItem>.

При добавлении <xref:System.Windows.Forms.ToolStripItem>s, требующих больше пространства, чем выделено <xref:System.Windows.Forms.ToolStrip> с учетом текущего размера формы, <xref:System.Windows.Forms.ToolStripOverflowButton> автоматически появляется на <xref:System.Windows.Forms.ToolStrip>. Появится <xref:System.Windows.Forms.ToolStripOverflowButton>, а элементы с поддержкой переполнения будут перемещены в раскрывающееся меню переполнения. Это позволяет настраивать и определять приоритеты, определяющие правильную настройку <xref:System.Windows.Forms.ToolStrip> элементов на различные размеры форм. Можно также изменить внешний вид элементов, попадающие в переполнение, с помощью свойств <xref:System.Windows.Forms.ToolStripItem.Placement%2A> и <xref:System.Windows.Forms.ToolStripOverflow.DisplayedItems%2A?displayProperty=nameWithType> и <xref:System.Windows.Forms.ToolStrip.LayoutCompleted> события. При увеличении формы во время разработки или во время выполнения на главном <xref:System.Windows.Forms.ToolStrip> может отображаться больше <xref:System.Windows.Forms.ToolStripItem>, а <xref:System.Windows.Forms.ToolStripOverflowButton> может даже исчезнуть до тех пор, пока не будет уменьшен размер формы.

## <a name="to-enable-overflow-on-a-toolstrip-control"></a>Включение переполнения для элемента управления ToolStrip

- Убедитесь, что для свойства <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> не задано значение `false` для <xref:System.Windows.Forms.ToolStrip>. Значение по умолчанию — `True`.

     Если <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A> имеет `True` (значение по умолчанию), <xref:System.Windows.Forms.ToolStripItem> передается в раскрывающееся меню переполнения, если содержимое <xref:System.Windows.Forms.ToolStripItem> превышает ширину горизонтального <xref:System.Windows.Forms.ToolStrip> или высоты вертикального <xref:System.Windows.Forms.ToolStrip>.

## <a name="to-specify-overflow-behavior-of-a-specific-toolstripitem"></a>Указание поведения определенного элемента ToolStripItem в случае переполнения

- Присвойте свойству <xref:System.Windows.Forms.ToolStripItem.Overflow%2A> <xref:System.Windows.Forms.ToolStripItem> нужное значение. Возможные варианты: `Always`, `Never`и `AsNeeded`. Значение по умолчанию — `AsNeeded`.

    ```vb
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never
    ```

    ```csharp
    toolStripTextBox1.Overflow = _
    System.Windows.Forms.ToolStripItemOverflow.Never;
    ```

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripOverflowButton>
- <xref:System.Windows.Forms.ToolStripItem.Overflow%2A>
- <xref:System.Windows.Forms.ToolStrip.CanOverflow%2A>
- [Общие сведения об элементе управления ToolStrip](toolstrip-control-overview-windows-forms.md)
- [Архитектура элемента управления ToolStrip](toolstrip-control-architecture.md)
- [Технологии, положенные в основу работы элемента управления ToolStrip](toolstrip-technology-summary.md)
