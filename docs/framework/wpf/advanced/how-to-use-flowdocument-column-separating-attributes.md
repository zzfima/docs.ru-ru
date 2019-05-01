---
title: Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 27491b21da587fa198061ba52d8daed5d3f28de3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032043"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
В этом примере показано, как использовать функции разделения столбцов <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Documents.FlowDocument>и задает <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты.  <xref:System.Windows.Documents.FlowDocument> Содержит один абзац содержимого образца.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 На следующем рисунке показаны последствия <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты на отображаемый <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Снимок экрана: внутренний столбец документа FlowDocument атрибута.](./media/how-to-use-flowdocument-column-separating-attributes/flowdocument-intra-column.png)
