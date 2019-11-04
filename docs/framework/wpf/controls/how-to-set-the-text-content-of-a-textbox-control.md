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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="0d4b8-102">Практическое руководство. Установка текстового содержимого для элемента управления TextBox</span><span class="sxs-lookup"><span data-stu-id="0d4b8-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="0d4b8-103">В этом примере показано, как использовать свойство <xref:System.Windows.Controls.TextBox.Text%2A> для задания начального текстового содержимого элемента управления <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="0d4b8-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="0d4b8-104">Несмотря на то, что [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]ная версия примера может использовать теги `<TextBox.Text>` по отношению к тексту <xref:System.Windows.Controls.TextBox> для каждой кнопки, это необязательно, так как <xref:System.Windows.Controls.TextBox> применяет атрибут <xref:System.Windows.Markup.ContentPropertyAttribute> к свойству <xref:System.Windows.Controls.TextBox.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="0d4b8-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="0d4b8-105">Дополнительные сведения см. в разделе [Общие сведения о XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="0d4b8-105">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="0d4b8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="0d4b8-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="0d4b8-107">Пример</span><span class="sxs-lookup"><span data-stu-id="0d4b8-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="0d4b8-108">См. также</span><span class="sxs-lookup"><span data-stu-id="0d4b8-108">See also</span></span>

- [<span data-ttu-id="0d4b8-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="0d4b8-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="0d4b8-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="0d4b8-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
