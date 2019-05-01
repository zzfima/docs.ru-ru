---
title: Практическое руководство. Использование элементов потокового содержимого
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: df591304736adf1725b2b4235149bd426fe15216
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052356"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="47b41-102">Практическое руководство. Использование элементов потокового содержимого</span><span class="sxs-lookup"><span data-stu-id="47b41-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="47b41-103">В приведенном ниже примере показано декларативное использование различных элементов с содержимым нефиксированного формата и связанных атрибутов.</span><span class="sxs-lookup"><span data-stu-id="47b41-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="47b41-104">Демонстрируемые элементы и атрибуты включают в себя:</span><span class="sxs-lookup"><span data-stu-id="47b41-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="47b41-105">Элемент <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="47b41-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="47b41-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> Атрибут</span><span class="sxs-lookup"><span data-stu-id="47b41-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="47b41-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> Атрибут</span><span class="sxs-lookup"><span data-stu-id="47b41-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="47b41-108">Элемент <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="47b41-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="47b41-109">Элемент <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="47b41-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="47b41-110">Элемент <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="47b41-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="47b41-111">Элемент <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="47b41-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="47b41-112">Элемент <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="47b41-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="47b41-113">Элемент <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="47b41-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="47b41-114">Элемент <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="47b41-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="47b41-115">Элемент <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="47b41-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="47b41-116"><xref:System.Windows.Documents.Typography.Variants%2A> атрибут (надстрочный и подстрочный)</span><span class="sxs-lookup"><span data-stu-id="47b41-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="47b41-117">Элемент <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="47b41-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="47b41-118">Пример</span><span class="sxs-lookup"><span data-stu-id="47b41-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
