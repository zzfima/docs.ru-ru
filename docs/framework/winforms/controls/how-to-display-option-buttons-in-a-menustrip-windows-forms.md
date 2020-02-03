---
title: Практическое руководство. Отображение переключателей в элементе управления MenuStrip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: f3010e71396ce562e9dbdefd4b75b36f3a81ffb3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735522"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a>Практическое руководство. Отображение переключателей в элементе управления MenuStrip (Windows Forms)

Переключатели, также называемые переключателями, аналогичны флажкам, за исключением того, что пользователи могут выбирать только один из них за раз. Несмотря на то, что по умолчанию класс <xref:System.Windows.Forms.ToolStripMenuItem> не обеспечивает поведение переключателя, класс предоставляет поведение флажка, которое можно настроить для реализации поведения переключателей для пунктов меню в элементе управления <xref:System.Windows.Forms.MenuStrip>.

Если свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> элемента меню `true`, пользователи могут щелкнуть элемент, чтобы включить или отключить отображение галочки. Свойство <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> указывает текущее состояние элемента. Чтобы реализовать базовое поведение переключателя, необходимо убедиться, что при выборе элемента свойству <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> для ранее выбранного элемента задается значение `false`.

В следующих процедурах описывается реализация этой и дополнительной функциональности в классе, который наследует класс <xref:System.Windows.Forms.ToolStripMenuItem>. Класс `ToolStripRadioButtonMenuItem` переопределяет элементы, такие как <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> и <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, чтобы обеспечить поведение выбора и внешний вид переключателей. Кроме того, этот класс переопределяет свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>, чтобы параметры в подменю были отключены, если не выбран родительский элемент.

## <a name="to-implement-option-button-selection-behavior"></a>Реализация поведения при выборе переключателя

1. Инициализируйте свойство <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A>, чтобы `true`, чтобы включить выбор элементов.

     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]

2. Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A>, чтобы очистить выбор ранее выбранного элемента при выборе нового элемента.

     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]

3. Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A>, чтобы убедиться, что щелчок элемента, который уже был выбран, не очистит выбор.

     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]

## <a name="to-modify-the-appearance-of-the-option-button-items"></a>Изменение внешнего вида элементов переключателя

1. Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A>, чтобы заменить флажок по умолчанию на переключатель с помощью класса <xref:System.Windows.Forms.RadioButtonRenderer>.

     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]

2. Переопределите методы <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>и <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> для отслеживания состояния мыши и убедитесь, что метод <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> рисует правильное состояние переключателя.

     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]

## <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a>Отключение параметров в подменю, если родительский элемент не выбран

1. Переопределите свойство <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>, чтобы элемент был отключен, если у него есть родительский элемент с <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> значением `true` и <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> значением `false`.

     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]

2. Переопределите метод <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A>, чтобы подписаться на событие <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента.

     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]

3. В обработчике для события <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> родительского элемента делает недействительным элемент для обновления отображения с новым включенным состоянием.

     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]

## <a name="example"></a>Пример

В следующем примере кода представлен полный `ToolStripRadioButtonMenuItem` класс, класс <xref:System.Windows.Forms.Form> и класс `Program`, демонстрирующие поведение переключателя.

[!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
[!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]

## <a name="compiling-the-code"></a>Компиляция кода

Для этого примера требуются:

- ссылки на сборки System, System.Drawing и System.Windows.Forms.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [Элемент управления MenuStrip](menustrip-control-windows-forms.md)
- [Практическое руководство. Реализация пользовательского класса, производного от ToolStripRenderer](how-to-implement-a-custom-toolstriprenderer.md)
