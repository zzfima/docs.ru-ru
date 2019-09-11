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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="3612b-102">Практическое руководство. Установка текстового содержимого для элемента управления TextBox</span><span class="sxs-lookup"><span data-stu-id="3612b-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="3612b-103">В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.Text%2A> свойство для задания начального текстового содержимого <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3612b-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="3612b-104">Несмотря на [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] то, что в версии примера можно `<TextBox.Text>` использовать теги вокруг <xref:System.Windows.Controls.TextBox> текста <xref:System.Windows.Controls.TextBox> содержимого каждой кнопки, <xref:System.Windows.Markup.ContentPropertyAttribute> это <xref:System.Windows.Controls.TextBox.Text%2A> необязательно, так как применяет атрибут к свойству. .</span><span class="sxs-lookup"><span data-stu-id="3612b-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="3612b-105">Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="3612b-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="3612b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="3612b-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="3612b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3612b-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="3612b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="3612b-108">See also</span></span>

- [<span data-ttu-id="3612b-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="3612b-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="3612b-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="3612b-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
