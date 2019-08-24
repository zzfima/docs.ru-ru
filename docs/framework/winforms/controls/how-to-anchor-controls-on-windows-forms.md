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
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 94fa6fe90e5583a3bfecf376af59d53f6d8528af
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987501"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Практическое руководство. Привязка элементов управления к Windows Forms

Если вы разрабатываете форму, размер которой может изменить пользователь во время выполнения, элементы управления в форме должны изменить его размер и правильно изменить расположение. Для динамического изменения размера элементов управления с помощью формы можно использовать <xref:System.Windows.Forms.Control.Anchor%2A> свойство элементов управления Windows Forms. <xref:System.Windows.Forms.Control.Anchor%2A> Свойство определяет точку привязки для элемента управления. Когда элемент управления привязан к форме и изменяется размер формы, элемент управления сохраняет расстояние между элементом управления и положением привязки. Например, если имеется <xref:System.Windows.Forms.TextBox> элемент управления, привязанный к левому, правому и нижнему краю формы при изменении размера формы, то <xref:System.Windows.Forms.TextBox> элемент управления изменяет свой размер по горизонтали таким образом, чтобы он удерживает то же расстояние от правой и левой сторон формы. Кроме того, элемент управления располагается по вертикали, чтобы его положение всегда совпадало с нижним ребром формы. Если элемент управления не привязан и размеры формы изменяются, изменяется расположение элемента управления относительно границ формы.

Свойство взаимодействует со <xref:System.Windows.Forms.Control.AutoSize%2A>свойством. <xref:System.Windows.Forms.Control.Anchor%2A> Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Привязка элемента управления к форме

1. В Visual Studio выберите элемент управления, который необходимо привязать.

    > [!NOTE]
    > Можно закрепить несколько элементов управления одновременно, нажав клавишу CTRL, щелкнув каждый из них, а затем выполнив оставшуюся часть этой процедуры.

2. В окне **Свойства** щелкните стрелку справа от <xref:System.Windows.Forms.Control.Anchor%2A> свойства.

     Откроется редактор, в котором отображается крестик.

3. Чтобы задать привязку, щелкните верхнюю, левую, правую или нижнюю часть крестика.

     По умолчанию элементы управления привязаны к верхнему и левому краю.

4. Чтобы очистить сторону привязанного элемента управления, щелкните точку пересечения.

5. Чтобы закрыть <xref:System.Windows.Forms.Control.Anchor%2A> редактор свойств, еще раз <xref:System.Windows.Forms.Control.Anchor%2A> щелкните имя свойства.

Когда форма отображается во время выполнения, размер элемента управления изменяется так, чтобы оставаться расположенными на том же расстоянии от края формы. Расстояние от привязанного периметра всегда остается таким же, как и расстояние, определенное при размещении элемента управления в конструктор Windows Forms.

> [!NOTE]
> Некоторые элементы управления, такие как <xref:System.Windows.Forms.ComboBox> элемент управления, имеют ограничение по высоте. Привязка элемента управления к нижней части его формы или контейнера не может привести к превышению предельной высоты элемента управления.

Наследуемые элементы `Protected` управления должны быть доступны для привязки. Чтобы изменить уровень доступа элемента управления, задайте его `Modifiers` свойство в окне **Свойства** .

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Закреплять элементы управления на Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пошаговое руководство: Упорядочивание элементов управления в Windows Forms с помощью TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство: Разметка элементов управления Windows Forms с заполнением, полями и свойством AutoSize](windows-forms-controls-padding-autosize.md)
