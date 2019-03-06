---
title: Практическое руководство. Использование элементов размещения содержимого
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: df591304736adf1725b2b4235149bd426fe15216
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57368116"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="f70dc-102">Практическое руководство. Использование элементов размещения содержимого</span><span class="sxs-lookup"><span data-stu-id="f70dc-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="f70dc-103">В приведенном ниже примере показано декларативное использование различных элементов с содержимым нефиксированного формата и связанных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f70dc-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="f70dc-104">Демонстрируемые элементы и атрибуты включают в себя:</span><span class="sxs-lookup"><span data-stu-id="f70dc-104">Elements and attributes demonstrated include:</span></span>  
  
-   <span data-ttu-id="f70dc-105"><xref:System.Windows.Documents.Bold> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
-   <span data-ttu-id="f70dc-106">Атрибут <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="f70dc-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
-   <span data-ttu-id="f70dc-107">Атрибут <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="f70dc-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
-   <span data-ttu-id="f70dc-108"><xref:System.Windows.Documents.Italic> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
-   <span data-ttu-id="f70dc-109"><xref:System.Windows.Documents.LineBreak> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
-   <span data-ttu-id="f70dc-110"><xref:System.Windows.Documents.List> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-110"><xref:System.Windows.Documents.List> element</span></span>  
  
-   <span data-ttu-id="f70dc-111"><xref:System.Windows.Documents.ListItem> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
-   <span data-ttu-id="f70dc-112"><xref:System.Windows.Documents.Paragraph> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
-   <span data-ttu-id="f70dc-113"><xref:System.Windows.Documents.Run> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
-   <span data-ttu-id="f70dc-114"><xref:System.Windows.Documents.Section> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
-   <span data-ttu-id="f70dc-115"><xref:System.Windows.Documents.Span> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
-   <span data-ttu-id="f70dc-116"><xref:System.Windows.Documents.Typography.Variants%2A> атрибут (надстрочный и подстрочный)</span><span class="sxs-lookup"><span data-stu-id="f70dc-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
-   <span data-ttu-id="f70dc-117"><xref:System.Windows.Documents.Underline> - элемент</span><span class="sxs-lookup"><span data-stu-id="f70dc-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="f70dc-118">Пример</span><span class="sxs-lookup"><span data-stu-id="f70dc-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
