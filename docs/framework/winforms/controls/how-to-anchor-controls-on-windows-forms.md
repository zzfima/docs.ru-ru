---
title: Практическое руководство. Привязка элементов управления в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
ms.openlocfilehash: b48761bda2baad4f7d1e6db9b41d73d6d54bc081
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211276"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Практическое руководство. Привязка элементов управления в формах Windows Forms

При создании формы, в которой пользователь может сделать во время выполнения, элементы управления в форме следует изменить размер и местоположение. Чтобы изменить размер элементов управления, динамически с формой, можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> элементов управления Windows Forms. <xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет положение прикрепления для элемента управления. Когда элемент управления привязан к форме и изменении размера формы, элемент управления поддерживает расстояние между элементом управления и положениями прикрепления. Например, если у вас есть <xref:System.Windows.Forms.TextBox> элемент управления, привязанный к левой, правой и верхней границе формы, при изменении размера формы, <xref:System.Windows.Forms.TextBox> изменении размера элемента управления по горизонтали таким образом, чтобы сохранить такое же расстояние от правой и левой сторон формы. Кроме того элемент управления размещается по вертикали, чтобы она будет находиться всегда такое же расстояние от нижнего края формы. Если элемент управления не привязан и изменении размера формы, изменяется положение элемента управления относительно соответствующих краев формы.

<xref:System.Windows.Forms.Control.Anchor%2A> Свойство взаимодействует с <xref:System.Windows.Forms.Control.AutoSize%2A> свойство. Дополнительные сведения см. в разделе [Общие](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Привязка элемента управления в форме

1. В Visual Studio выберите элемент управления, который нужно закрепить.

    > [!NOTE]
    > Можно прикрепить несколько элементов одновременно, удерживая нажатой клавишу CTRL, щелкнув каждый элемент управления, чтобы выбрать его и следуйте оставшуюся часть этой процедуры.

2. В **свойства** окно, щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойство.

     Отображается редактор, показывающий крест.

3. Чтобы задать привязки, щелкните сверху, слева, справа или нижней части крестика.

     Элементы управления, привязанный к верхней и левой по умолчанию.

4. Чтобы очистить стороны элемента управления, который был прикреплен, щелкните соответствующую часть крестика.

5. Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> щелкните редактор свойств <xref:System.Windows.Forms.Control.Anchor%2A> снова имя свойства.

При отображении формы во время выполнения, оставаясь на одинаковом расстоянии от края формы размера элемента управления. Расстояние от прикрепленного края всегда остается как расстояние определено, если элемент управления находится в конструкторе Windows Forms.

> [!NOTE]
> Определенные элементы управления, такие как <xref:System.Windows.Forms.ComboBox> управления, ограничение для их высоту. Привязка элемента управления в нижней части формы или контейнера не может принудительно требовать элементе управления превышает предельное значение высоты.

Наследуемые элементы управления должны быть `Protected` могла быть прикреплены. Чтобы изменить уровень доступа для элемента управления, установите его `Modifiers` свойство в **свойства** окна.

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Упорядочение элементов управления в формах Windows Forms](arranging-controls-on-windows-forms.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Закрепление элементов управления в формах Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пошаговое руководство: Упорядочение элементов управления в Windows Forms, с помощью элемента управления TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Создание структуры Windows Forms элементов управления с помощью свойств Padding, Margins и свойство AutoSize](windows-forms-controls-padding-autosize.md)
