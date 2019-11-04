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
ms.openlocfilehash: 9b16f2d99295a28725255361b0be3ef7f4245fd2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459301"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Практическое руководство. Установка текстового содержимого для элемента управления TextBox

В этом примере показано, как использовать свойство <xref:System.Windows.Controls.TextBox.Text%2A> для задания начального текстового содержимого элемента управления <xref:System.Windows.Controls.TextBox>.

> [!NOTE]
> Несмотря на то, что [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ная версия примера может использовать теги `<TextBox.Text>` по отношению к тексту <xref:System.Windows.Controls.TextBox> для каждой кнопки, это необязательно, так как <xref:System.Windows.Controls.TextBox> применяет атрибут <xref:System.Windows.Markup.ContentPropertyAttribute> к свойству <xref:System.Windows.Controls.TextBox.Text%2A>. Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Пример

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Пример

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>См. также

- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
