---
title: Практическое руководство. Вставка элемента в текст программными средствами
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Text Animation sample [WPF]
- elements [WPF], inserting into text
- inserting elements into text [WPF]
- TextPointer objects [WPF]
- text [WPF], inserting elements
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
ms.openlocfilehash: 8eaf0c6a1e3ad3c64800f8611aba555110aa4c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-insert-an-element-into-text-programmatically"></a><span data-ttu-id="3b942-102">Практическое руководство. Вставка элемента в текст программными средствами</span><span class="sxs-lookup"><span data-stu-id="3b942-102">How to: Insert an Element Into Text Programmatically</span></span>
<span data-ttu-id="3b942-103">В следующем примере показано, как использовать два <xref:System.Windows.Documents.TextPointer> объектов, чтобы указать диапазон, в тексте, чтобы применить <xref:System.Windows.Documents.Span> элемента.</span><span class="sxs-lookup"><span data-stu-id="3b942-103">The following example shows how to use two <xref:System.Windows.Documents.TextPointer> objects to specify a range within text to apply a <xref:System.Windows.Documents.Span> element to.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b942-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3b942-104">Example</span></span>  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 <span data-ttu-id="3b942-105">На рисунке ниже представлен результат выполнения этого примера.</span><span class="sxs-lookup"><span data-stu-id="3b942-105">The illustration below shows what this example looks like.</span></span>  
  
 <span data-ttu-id="3b942-106">![Элемент Span, применяемый к диапазону текста ](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span><span class="sxs-lookup"><span data-stu-id="3b942-106">![A Span element applied to a range of text](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow_InsertElementIntoTextProgrammatically")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b942-107">См. также</span><span class="sxs-lookup"><span data-stu-id="3b942-107">See Also</span></span>  
 [<span data-ttu-id="3b942-108">Общие сведения о документе нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="3b942-108">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)
