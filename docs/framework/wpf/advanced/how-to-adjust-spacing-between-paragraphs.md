---
title: Практическое руководство. Настройка интервалов между абзацами
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367483"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="8220b-102">Практическое руководство. Настройка интервалов между абзацами</span><span class="sxs-lookup"><span data-stu-id="8220b-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="8220b-103">В этом примере показано, как Настройка или устранение интервалов между абзацами в содержимом нефиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="8220b-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="8220b-104">В содержимом нефиксированного формата дополнительное пространство между абзацами является результатом поля этих абзацев. Таким образом интервалов между абзацами можно управлять с помощью полей этих абзацев.</span><span class="sxs-lookup"><span data-stu-id="8220b-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="8220b-105">Чтобы полностью убрать дополнительное расстояние между двумя абзацами, установите поля для абзаца для **0**.</span><span class="sxs-lookup"><span data-stu-id="8220b-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="8220b-106">Для достижения одинакового интервала между абзацами во всем <xref:System.Windows.Documents.FlowDocument>, используйте стилизацию для установки одинакового значения поля для всех абзацев в <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8220b-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="8220b-107">Важно отметить, что поля для двух соседних абзацев будет «свернуть» большее из двух полей, а не вдвое.</span><span class="sxs-lookup"><span data-stu-id="8220b-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="8220b-108">Поэтому, если два соседних абзаца имеют поля 20 пикселей и 40 пикселей соответственно, полученное в результате пространство между абзацами 40 пикселей, большее из двух значений полей.</span><span class="sxs-lookup"><span data-stu-id="8220b-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8220b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="8220b-109">Example</span></span>  
 <span data-ttu-id="8220b-110">В следующем примере используется стиль, чтобы задать поля для всех <xref:System.Windows.Documents.Paragraph> элементов в <xref:System.Windows.Documents.FlowDocument> для **0**, что эффективно устраняет дополнительный интервал между абзацами в <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="8220b-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
