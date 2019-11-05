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
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 15f12cb0d389344351c4ddf97ee9db37882de460
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459678"
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>Как привязать элементы управления к Windows Forms

Если вы разрабатываете форму, размер которой может изменить пользователь во время выполнения, элементы управления в форме должны изменить его размер и правильно изменить расположение. Для динамического изменения размера элементов управления с помощью формы можно использовать свойство <xref:System.Windows.Forms.Control.Anchor%2A> элементов управления Windows Forms. Свойство <xref:System.Windows.Forms.Control.Anchor%2A> определяет точку привязки для элемента управления. Когда элемент управления привязан к форме и изменяется размер формы, элемент управления сохраняет расстояние между элементом управления и положением привязки. Например, если имеется элемент управления <xref:System.Windows.Forms.TextBox>, привязанный к левому, правому и нижнему краю формы при изменении размера формы, элемент управления <xref:System.Windows.Forms.TextBox> изменяет размер по горизонтали таким образом, чтобы он удерживает то же расстояние от правой и левой сторон формы. Кроме того, элемент управления располагается по вертикали, чтобы его положение всегда совпадало с нижним ребром формы. Если элемент управления не привязан и размеры формы изменяются, изменяется расположение элемента управления относительно границ формы.

Свойство <xref:System.Windows.Forms.Control.Anchor%2A> взаимодействует со свойством <xref:System.Windows.Forms.Control.AutoSize%2A>. Дополнительные сведения см. в разделе [Общие сведения о свойстве AutoSize](autosize-property-overview.md).

## <a name="anchor-a-control-on-a-form"></a>Привязка элемента управления к форме

1. В Visual Studio выберите элемент управления, который необходимо привязать.

    > [!NOTE]
    > Можно закрепить несколько элементов управления одновременно, нажав клавишу CTRL, щелкнув каждый из них, а затем выполнив оставшуюся часть этой процедуры.

2. В окне **Свойства** щелкните стрелку справа от свойства <xref:System.Windows.Forms.Control.Anchor%2A>.

     Откроется редактор, в котором отображается крестик.

3. Чтобы задать привязку, щелкните верхнюю, левую, правую или нижнюю часть крестика.

     По умолчанию элементы управления привязаны к верхнему и левому краю.

4. Чтобы очистить сторону привязанного элемента управления, щелкните точку пересечения.

5. Чтобы закрыть редактор свойств <xref:System.Windows.Forms.Control.Anchor%2A>, снова щелкните имя свойства <xref:System.Windows.Forms.Control.Anchor%2A>.

Когда форма отображается во время выполнения, размер элемента управления изменяется так, чтобы оставаться расположенными на том же расстоянии от края формы. Расстояние от привязанного периметра всегда остается таким же, как и расстояние, определенное при размещении элемента управления в конструктор Windows Forms.

> [!NOTE]
> Некоторые элементы управления, такие как элемент управления <xref:System.Windows.Forms.ComboBox>, имеют ограничения по высоте. Привязка элемента управления к нижней части его формы или контейнера не может привести к превышению предельной высоты элемента управления.

Наследуемые элементы управления должны быть `Protected` для привязки. Чтобы изменить уровень доступа элемента управления, задайте его свойство `Modifiers` в окне **Свойства** .

## <a name="see-also"></a>См. также

- [Элементы управления Windows Forms](index.md)
- [Свойство AutoSize](autosize-property-overview.md)
- [Практическое руководство. Закрепление элементов управления в формах Windows Forms](how-to-dock-controls-on-windows-forms.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Пошаговое руководство. Упорядочение элементов управления в формах Windows Forms с помощью элемента TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [Пошаговое руководство. Создание структуры элементов управления Windows Forms с помощью свойств Padding, Margins и AutoSize](windows-forms-controls-padding-autosize.md)
