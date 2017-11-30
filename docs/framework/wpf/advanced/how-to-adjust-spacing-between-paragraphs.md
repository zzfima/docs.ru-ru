---
title: "Практическое руководство. Изменение интервалов между абзацами"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1936426b44ed667d03e4881e66a081d5097a2880
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a><span data-ttu-id="59a57-102">Практическое руководство. Изменение интервалов между абзацами</span><span class="sxs-lookup"><span data-stu-id="59a57-102">How to: Adjust Spacing Between Paragraphs</span></span>
<span data-ttu-id="59a57-103">В этом примере показано, как Настройка или устранение интервалов между абзацами в содержимом нефиксированного формата.</span><span class="sxs-lookup"><span data-stu-id="59a57-103">This example shows how to adjust or eliminate spacing between paragraphs in flow content.</span></span>  
  
 <span data-ttu-id="59a57-104">В содержимом нефиксированного формата дополнительное пространство, возникающее между абзацами является результатом поля этих абзацев. Таким образом интервала между абзацами можно управлять, настраивая размеры полей этих абзацев.</span><span class="sxs-lookup"><span data-stu-id="59a57-104">In flow content, extra space that appears between paragraphs is the result of margins set on these paragraphs; thus, the spacing between paragraphs can be controlled by adjusting the margins on those paragraphs.</span></span>  <span data-ttu-id="59a57-105">Чтобы полностью убрать дополнительное расстояние между двумя абзацами, установите поля для абзацев в **0**.</span><span class="sxs-lookup"><span data-stu-id="59a57-105">To eliminate extra spacing between two paragraphs altogether, set the margins for the paragraphs to **0**.</span></span>  <span data-ttu-id="59a57-106">Для достижения одинакового интервала между абзацами во всем <xref:System.Windows.Documents.FlowDocument>, использовать для задания одинакового значения поля для всех абзацев в стилях <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="59a57-106">To achieve uniform spacing between paragraphs throughout an entire <xref:System.Windows.Documents.FlowDocument>, use styling to set a uniform margin value for all paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 <span data-ttu-id="59a57-107">Это важно отметить, что поля для двух соседних абзацев будет «свернуть» большее из двух полей, а не вдвое.</span><span class="sxs-lookup"><span data-stu-id="59a57-107">It is important to note that the margins for two adjacent paragraphs will "collapse" to the larger of the two margins, rather than doubling up.</span></span> <span data-ttu-id="59a57-108">Таким образом Если два соседних абзаца имеют поля 20 пикселей и 40 пикселей соответственно, результирующий интервал между абзацами будет 40 пикселей, большее из двух значений полей.</span><span class="sxs-lookup"><span data-stu-id="59a57-108">So, if two adjacent paragraphs have margins of 20 pixels and 40 pixels respectively, the resulting space between the paragraphs is 40 pixels, the larger of the two margin values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59a57-109">Пример</span><span class="sxs-lookup"><span data-stu-id="59a57-109">Example</span></span>  
 <span data-ttu-id="59a57-110">В следующем примере используется стили, чтобы задать поля для всех <xref:System.Windows.Documents.Paragraph> элементов в <xref:System.Windows.Documents.FlowDocument> для **0**, которая эффективно удаляет дополнительное расстояние между абзацами в <xref:System.Windows.Documents.FlowDocument>.</span><span class="sxs-lookup"><span data-stu-id="59a57-110">The following example uses styling to set the margin for all <xref:System.Windows.Documents.Paragraph> elements in a <xref:System.Windows.Documents.FlowDocument> to **0**, which effectively eliminates extra spacing between paragraphs in the <xref:System.Windows.Documents.FlowDocument>.</span></span>  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
