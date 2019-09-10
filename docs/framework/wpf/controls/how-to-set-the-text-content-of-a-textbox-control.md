---
title: Практическое руководство. Установка текстового содержимого для элемента управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856109"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Практическое руководство. Установка текстового содержимого для элемента управления TextBox

В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.Text%2A> свойство для задания начального текстового содержимого <xref:System.Windows.Controls.TextBox> элемента управления.

> [!NOTE]
> Несмотря на [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] то, что в версии примера можно `<TextBox.Text>` использовать теги вокруг <xref:System.Windows.Controls.TextBox> текста <xref:System.Windows.Controls.TextBox> содержимого каждой кнопки, <xref:System.Windows.Markup.ContentPropertyAttribute> это <xref:System.Windows.Controls.TextBox.Text%2A> необязательно, так как применяет атрибут к свойству. . Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../advanced/xaml-overview-wpf.md).

## <a name="example"></a>Пример

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Пример

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>См. также

- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
