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
ms.openlocfilehash: 8c7fd54931fad060a5d78e4c47c2cfce2767025a
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355250"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Практическое руководство. Извлечение текстового содержимого из элемента управления RichTextBox
В этом примере показано, как извлечь содержимое <xref:System.Windows.Controls.RichTextBox> как обычный текст.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] коде описывается элемент <xref:System.Windows.Controls.RichTextBox> элемента управления с простым содержимым.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Пример  
 Следующий код реализует метод, который принимает <xref:System.Windows.Controls.RichTextBox> как аргумент и возвращает строку, представляющую текстовое содержимое <xref:System.Windows.Controls.RichTextBox>.  
  
 Создает новый метод <xref:System.Windows.Documents.TextRange> из содержимого <xref:System.Windows.Controls.RichTextBox>, с использованием <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> чтобы обозначить диапазон содержимого для извлечения.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> и <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> свойства каждого возвращают <xref:System.Windows.Documents.TextPointer>эти данные доступны в основном FlowDocument, представляющий содержимое <xref:System.Windows.Controls.RichTextBox>.  <xref:System.Windows.Documents.TextRange> Предоставляет текстовое свойство, которое возвращает часть обычного текста <xref:System.Windows.Documents.TextRange> как строка.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о RichTextBox](richtextbox-overview.md)
- [Общие сведения о TextBox](textbox-overview.md)
