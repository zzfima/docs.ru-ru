---
title: Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
ms.date: 03/30/2017
helpviewer_keywords:
- FlowDocument column-separating attributes
- column-separating attributes
- documents [WPF], FlowDocument column-separating attributes
ms.assetid: c7a822f8-aeca-45bd-a258-2852ff28005c
ms.openlocfilehash: 8693c8973442a5c6e65e64c5c66194c11bbff119
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363791"
---
# <a name="how-to-use-flowdocument-column-separating-attributes"></a>Практическое руководство. Использование атрибутов разделения столбцов FlowDocument
В этом примере показано, как использовать функции разделения столбцов <xref:System.Windows.Documents.FlowDocument>.  
  
## <a name="example"></a>Пример  
 В следующем примере определяется <xref:System.Windows.Documents.FlowDocument>и задает <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты.  <xref:System.Windows.Documents.FlowDocument> Содержит один абзац содержимого образца.  
  
 [!code-xaml[FlowDocumentSnippets#_FlowDocumentColumnStuffXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml#_flowdocumentcolumnstuffxaml)]  
  
 На следующем рисунке показаны последствия <xref:System.Windows.Documents.FlowDocument.ColumnGap%2A>, <xref:System.Windows.Documents.FlowDocument.ColumnRuleBrush%2A>, и <xref:System.Windows.Documents.FlowDocument.ColumnRuleWidth%2A> атрибуты на отображаемый <xref:System.Windows.Documents.FlowDocument>.  
  
 ![Снимок экрана: Столбец документа FlowDocument](./media/flowdocumentintracolumn.png "FlowDocumentIntraColumn")
