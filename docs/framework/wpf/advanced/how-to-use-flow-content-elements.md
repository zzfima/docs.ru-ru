---
title: "Практическое руководство. Использование содержимого нефиксированного формата"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c1350a380e97631ac290e57de64fec696535fecc
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="10212-102">Практическое руководство. Использование содержимого нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="10212-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="10212-103">В приведенном ниже примере показано декларативное использование различных элементов с содержимым нефиксированного формата и связанных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="10212-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="10212-104">Демонстрируемые элементы и атрибуты включают в себя:</span><span class="sxs-lookup"><span data-stu-id="10212-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="10212-105"><xref:System.Windows.Documents.Bold> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="10212-106">Атрибут <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="10212-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="10212-107">Атрибут <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="10212-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="10212-108"><xref:System.Windows.Documents.Italic> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="10212-109"><xref:System.Windows.Documents.LineBreak> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="10212-110"><xref:System.Windows.Documents.List> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="10212-111"><xref:System.Windows.Documents.ListItem> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="10212-112"><xref:System.Windows.Documents.Paragraph> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="10212-113"><xref:System.Windows.Documents.Run> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="10212-114"><xref:System.Windows.Documents.Section> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="10212-115"><xref:System.Windows.Documents.Span> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="10212-116"><xref:System.Windows.Documents.Typography.Variants%2A>атрибут (верхний и нижний индекс)</span><span class="sxs-lookup"><span data-stu-id="10212-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="10212-117"><xref:System.Windows.Documents.Underline> - элемент</span><span class="sxs-lookup"><span data-stu-id="10212-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="10212-118">Пример</span><span class="sxs-lookup"><span data-stu-id="10212-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
