---
title: Международные шрифты в формах и элементах управления
ms.date: 03/30/2017
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
dev_langs:
- csharp
- vb
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
ms.openlocfilehash: 59dde6bb384d644321a8ff5674d735f8e6d36fd0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743517"
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Международные шрифты в Windows Forms и элементы управления

В международных приложениях рекомендуемым методом выбора шрифтов является использование отката шрифта везде, где это возможно. Откат шрифта означает, что система определяет, к какому скрипту относится этот символ.

## <a name="using-font-fallback"></a>Использование отката шрифта

Чтобы воспользоваться этой функцией, не устанавливайте свойство <xref:System.Drawing.Font> для формы или любого другого элемента. Приложение будет автоматически использовать системный шрифт по умолчанию, который отличается от локализованного языка операционной системы на другой. При запуске приложения система автоматически предоставит правильный шрифт для языка и региональных параметров, выбранных в операционной системе.

Существует исключение в правиле «не задавать шрифт», которое предназначено для изменения стиля шрифта. Это может быть важно для приложения, в котором пользователь нажимает кнопку, чтобы текст в текстовом поле отображался полужирным шрифтом. Для этого необходимо написать функцию, чтобы изменить стиль шрифта текстового поля на полужирный, исходя из того, что имеет шрифт формы. Важно вызывать эту функцию в двух местах: в обработчике событий <xref:System.Windows.Forms.Control.Click> кнопки и в обработчике событий <xref:System.Windows.Forms.Control.FontChanged>. Если функция вызывается только в обработчике событий <xref:System.Windows.Forms.Control.Click>, а другой фрагмент кода изменяет семейство шрифтов всей формы, текстовое поле не изменяется в остальной части формы.

```vb
Private Sub MakeBold()
   ' Change the TextBox to a bold version of the form font
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)
End Sub

Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click
   ' Clicking this button makes the TextBox bold
   MakeBold()
End Sub

Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged
   ' If the TextBox is already bold and the form's font changes,
   ' change the TextBox to a bold version of the new form font
   If (TextBox1.Font.Style = FontStyle.Bold) Then
      MakeBold()
   End If
End Sub
```

```csharp
private void button1_Click(object sender, System.EventArgs e)
{
   // Clicking this button makes the TextBox bold
   MakeBold();
}

private void MakeBold()
{
   // Change the TextBox to a bold version of the form's font
   textBox1.Font = new Font(this.Font, FontStyle.Bold);
}

private void Form1_FontChanged(object sender, System.EventArgs e)
{
   // If the TextBox is already bold and the form's font changes,
   // change the TextBox to a bold version of the new form font
   if (textBox1.Font.Style == FontStyle.Bold)
   {
      MakeBold();
   }
}
```

Однако при локализации приложения полужирный шрифт может плохо отображаться для определенных языков. Если это важно, Локализаторы должны иметь возможность переключения шрифта с полужирного на обычный текст. Так как локализаторы обычно не являются разработчиками и не имеют доступа к исходному коду только для файлов ресурсов, этот параметр необходимо задать в файлах ресурсов. Для этого задайте для свойства <xref:System.Drawing.Font.Bold%2A> значение `true`. Это приводит к записанию параметра Font в файлы ресурсов, где локализаторы могут редактировать их. Затем вы пишете код после метода `InitializeComponent` для сброса шрифта в зависимости от шрифта формы, но с использованием стиля шрифта, указанного в файле ресурсов.

```vb
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)
```

```csharp
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);
```
  
## <a name="see-also"></a>См. также:

- [Работами со шрифтами и текстом](using-fonts-and-text.md)
