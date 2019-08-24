---
title: Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- text [Windows Forms], drawing in combo boxes
- examples [Windows Forms], ComboBox control
- combo boxes [Windows Forms], drawing text
- ComboBox control [Windows Forms], examples [C#]
- ComboBox control [Windows Forms], drawing custom text
ms.assetid: ce39b9ea-e626-49fe-bd5a-f567f6d157df
ms.openlocfilehash: acc5ee47536772d98fcfe98849335933c24a41d7
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70015904"
---
# <a name="how-to-create-variable-sized-text-in-a-combobox-control"></a>Практическое руководство. Индивидуальное форматирование строк, отображаемых в элементе управления ComboBox
В этом примере демонстрируется пользовательское рисование текста <xref:System.Windows.Forms.ComboBox> в элементе управления. Если элемент соответствует определенным критериям, он рисуется на более крупном шрифте и становится красным.

## <a name="example"></a>Пример

```vb
Private Sub ComboBox1_MeasureItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.MeasureItemEventArgs) Handles ComboBox1.MeasureItem
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)
    Dim siText As SizeF

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), _
lFont)
    Else
        siText = e.Graphics.MeasureString(ComboBox1.Items().Item(e.Index), bFont)
    End If

    e.ItemHeight = siText.Height
    e.ItemWidth = siText.Width
End Sub

Private Sub ComboBox1_DrawItem(ByVal sender As Object, ByVal e As _
System.Windows.Forms.DrawItemEventArgs) Handles ComboBox1.DrawItem
    Dim g As Graphics = e.Graphics
    Dim bFont As New Font("Arial", 8, FontStyle.Bold)
    Dim lFont As New Font("Arial", 12, FontStyle.Bold)

    If ComboBox1.Items().Item(e.Index) = "Two" Then
        g.DrawString(ComboBox1.Items.Item(e.Index), lfont, Brushes.Red, _
e.Bounds.X, e.Bounds.Y)
    Else
        g.DrawString(ComboBox1.Items.Item(e.Index), bFont, Brushes.Black, e.Bounds.X, e.Bounds.Y)
    End If
End Sub
```

## <a name="compiling-the-code"></a>Компиляция кода
 Для этого примера требуются:

- Форма Windows Forms.

- Элемент управления с именем `ListBox1` с тремя элементами в свойстве.<xref:System.Windows.Forms.ComboBox.Items%2A> <xref:System.Windows.Forms.ComboBox> В этом примере три элемента имеют имя `"One", Two", and Three"`. Свойство объекта `ComboBox1` должно иметь значение <xref:System.Windows.Forms.DrawMode.OwnerDrawVariable>. <xref:System.Windows.Forms.ComboBox.DrawMode%2A>

    > [!NOTE]
    > Этот метод также применим к <xref:System.Windows.Forms.ListBox> элементу управления — вы можете <xref:System.Windows.Forms.ListBox> заменить для <xref:System.Windows.Forms.ComboBox>.

- Ссылки на пространства имен <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.ComboBox.DrawItem>
- <xref:System.Windows.Forms.DrawItemEventArgs>
- <xref:System.Windows.Forms.ComboBox.MeasureItem>
- [Элементы управления со встроенной поддержкой рисования владельцем](controls-with-built-in-owner-drawing-support.md)
- [Элемент управления ListBox](listbox-control-windows-forms.md)
- [Элемент управления ComboBox](combobox-control-windows-forms.md)
