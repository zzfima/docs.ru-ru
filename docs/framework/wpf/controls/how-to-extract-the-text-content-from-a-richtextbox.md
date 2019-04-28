---
title: Практическое руководство. Извлечение текстового содержимого из элемента управления RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: 220da59ec893528c99014e9ec95fb185c461b291
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001706"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="393e2-102">Практическое руководство. Извлечение текстового содержимого из элемента управления RichTextBox</span><span class="sxs-lookup"><span data-stu-id="393e2-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="393e2-103">В этом примере показано, как извлечь содержимое <xref:System.Windows.Controls.RichTextBox> как обычный текст.</span><span class="sxs-lookup"><span data-stu-id="393e2-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="393e2-104">Пример</span><span class="sxs-lookup"><span data-stu-id="393e2-104">Example</span></span>  
 <span data-ttu-id="393e2-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] коде описывается элемент <xref:System.Windows.Controls.RichTextBox> элемента управления с простым содержимым.</span><span class="sxs-lookup"><span data-stu-id="393e2-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="393e2-106">Пример</span><span class="sxs-lookup"><span data-stu-id="393e2-106">Example</span></span>  
 <span data-ttu-id="393e2-107">Следующий код реализует метод, который принимает <xref:System.Windows.Controls.RichTextBox> как аргумент и возвращает строку, представляющую текстовое содержимое <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="393e2-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="393e2-108">Создает новый метод <xref:System.Windows.Documents.TextRange> из содержимого <xref:System.Windows.Controls.RichTextBox>, с использованием <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> чтобы обозначить диапазон содержимого для извлечения.</span><span class="sxs-lookup"><span data-stu-id="393e2-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="393e2-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> свойства каждого возвращают <xref:System.Windows.Documents.TextPointer>эти данные доступны в основном FlowDocument, представляющий содержимое <xref:System.Windows.Controls.RichTextBox>.</span><span class="sxs-lookup"><span data-stu-id="393e2-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="393e2-110"><xref:System.Windows.Documents.TextRange> Предоставляет текстовое свойство, которое возвращает часть обычного текста <xref:System.Windows.Documents.TextRange> как строка.</span><span class="sxs-lookup"><span data-stu-id="393e2-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="393e2-111">См. также</span><span class="sxs-lookup"><span data-stu-id="393e2-111">See also</span></span>

- [<span data-ttu-id="393e2-112">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="393e2-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="393e2-113">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="393e2-113">TextBox Overview</span></span>](textbox-overview.md)
