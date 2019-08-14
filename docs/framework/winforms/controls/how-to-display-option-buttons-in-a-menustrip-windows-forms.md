---
title: Практическое руководство. Отображение кнопок параметров в MenuStrip (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 94d683369edd6583ad8b01c2ce3f393567a5ed75
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2019
ms.locfileid: "68971926"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Практическое руководство. Отображение кнопок параметров в MenuStrip (Windows Forms)

Переключатели, также называемые переключателями, аналогичны флажкам, за исключением того, что пользователи могут выбирать только один из них за раз. Хотя по умолчанию <xref:System.Windows.Forms.ToolStripMenuItem> класс не обеспечивает поведение переключателя, класс предоставляет поведение флажка, которое можно настроить для реализации поведения переключателей для пунктов меню <xref:System.Windows.Forms.MenuStrip> в элементе управления.

Если свойство пункта меню имеет `true`значение, пользователи могут щелкнуть элемент, чтобы включить или отключить отображение галочки. <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Свойство указывает текущее состояние элемента. Чтобы реализовать базовое поведение переключателя, необходимо убедиться, что при выборе элемента <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> свойству для ранее выбранного `false`элемента задается значение.

В следующих процедурах описывается реализация этой и дополнительной функциональности в классе, который наследует <xref:System.Windows.Forms.ToolStripMenuItem> класс. Класс переопределяет элементы, такие <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> как <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> и, для обеспечения поведения выбора и внешнего вида переключателей. `ToolStripRadioButtonMenuItem` Кроме того, этот класс переопределяет <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство таким образом, чтобы параметры в подменю были отключены, если не выбран родительский элемент.

## <a name="to-implement-option-button-selection-behavior"></a>Реализация поведения при выборе переключателя

1. `true` Инициализируйте <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> свойство, чтобы включить выбор элементов.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Переопределите <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> метод, чтобы очистить выбор выбранного ранее элемента при выборе нового элемента.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Переопределите <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> метод, чтобы убедиться, что щелчок элемента, который уже был выбран, не очистит выбор.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Изменение внешнего вида элементов переключателя

1. Переопределите <xref:System.Windows.Forms.RadioButtonRenderer> метод, чтобы заменить флажок по умолчанию на переключатель с помощью класса. <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A> Переопределите<xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>методы ,,<xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> и для отслеживания состояния мыши и убедитесь, что методрисуетправильноесостояниепереключателя.<xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Отключение параметров в подменю, если родительский элемент не выбран

1. `false` <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> `true` <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Переопределите свойствотакимобразом,чтобыэлементбылотключен,еслиунегоестьродительскийэлементсозначениемизначением.<xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Переопределите <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> метод, чтобы подписаться на событие родительского элемента. <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. В обработчике события родительского элемента <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> делает недействительным элемент для обновления экрана с новым включенным состоянием.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Пример

Следующий пример кода предоставляет полный `ToolStripRadioButtonMenuItem` класс, <xref:System.Windows.Forms.Form> класс и `Program` класс для демонстрации поведения переключателя.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылки на сборки System, System.Drawing и System.Windows.Forms.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
- [Практическое руководство. Реализация пользовательского ToolStripRenderer](how-to-implement-a-custom-toolstriprenderer.md)
