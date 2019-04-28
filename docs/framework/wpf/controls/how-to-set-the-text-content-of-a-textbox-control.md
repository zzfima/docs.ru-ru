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
ms.openlocfilehash: da91e27b804d649f5b8010bc9d7c074425be26f6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024148"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="865a5-102">Практическое руководство. Установка текстового содержимого для элемента управления TextBox</span><span class="sxs-lookup"><span data-stu-id="865a5-102">How to: Set the Text Content of a TextBox Control</span></span>
<span data-ttu-id="865a5-103">В этом примере показано, как использовать <xref:System.Windows.Controls.TextBox.Text%2A> свойство для задания начального текстового содержимого элемента <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="865a5-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
 <span data-ttu-id="865a5-104">**Примечание** несмотря на то что [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] использовать версию примера `<TextBox.Text>` теги вокруг текста каждой кнопки <xref:System.Windows.Controls.TextBox> содержимого, нет необходимости поскольку <xref:System.Windows.Controls.TextBox> применяется <xref:System.Windows.Markup.ContentPropertyAttribute> для атрибута <xref:System.Windows.Controls.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="865a5-104">**Note** Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="865a5-105">Дополнительные сведения см. в разделе [Обзор XAML (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="865a5-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="865a5-106">Пример</span><span class="sxs-lookup"><span data-stu-id="865a5-106">Example</span></span>  
 [!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]  
  
## <a name="example"></a><span data-ttu-id="865a5-107">Пример</span><span class="sxs-lookup"><span data-stu-id="865a5-107">Example</span></span>  
 [!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
 [!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]  
  
## <a name="see-also"></a><span data-ttu-id="865a5-108">См. также</span><span class="sxs-lookup"><span data-stu-id="865a5-108">See also</span></span>

- [<span data-ttu-id="865a5-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="865a5-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="865a5-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="865a5-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
