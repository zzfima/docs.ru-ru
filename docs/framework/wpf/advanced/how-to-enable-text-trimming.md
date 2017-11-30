---
title: "Практическое руководство. Включение обрезки текста"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimmng text
- trimmng text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e8f0f24bb6271e63dc50bd063aedfd8185711e7a
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="f6a7a-102">Практическое руководство. Включение обрезки текста</span><span class="sxs-lookup"><span data-stu-id="f6a7a-102">How to: Enable Text Trimming</span></span>
<span data-ttu-id="f6a7a-103">В этом примере демонстрируется использование и влияние значений, доступных в <xref:System.Windows.TextTrimming> перечисления.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6a7a-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f6a7a-104">Example</span></span>  
 <span data-ttu-id="f6a7a-105">В следующем примере определяется <xref:System.Windows.Controls.TextBlock> элемент с <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> набором атрибутов.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>  
  
 [!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]  
  
## <a name="example"></a><span data-ttu-id="f6a7a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f6a7a-106">Example</span></span>  
 <span data-ttu-id="f6a7a-107">Установив соответствующие <xref:System.Windows.TextTrimming> свойства в коде показана ниже.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-107">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>  
  
 [!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
 [!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]  
  
 <span data-ttu-id="f6a7a-108">В настоящее время три значения для усечения текста: **CharacterEllipsis**, **WordEllipsis**, и **нет**.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-108">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>  
  
 <span data-ttu-id="f6a7a-109">Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **CharacterEllipsis**, текст обрезается и продолжается многоточием после символа, ближайшего к краю обрезки.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-109">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="f6a7a-110">Эта настройка позволяет обрезать текст максимально близко к границе обрезки, однако иногда частично обрезаются слова.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-110">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="f6a7a-111">На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> аналогично указанному выше.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-111">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="f6a7a-112">![Пример: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="f6a7a-112">![Example: TextTrimming.CharacterEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-character.png "TextTrimming_Character")</span></span>  
  
 <span data-ttu-id="f6a7a-113">Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **WordEllipsis**, текст обрезается и продолжается многоточием в конце первого полного слова, ближайшего к краю обрезки.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-113">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="f6a7a-114">Этот параметр не будут отображаться частично обрезанные слова, но не текст обрезается так близко к краю обрезки, как **CharacterEllipsis** параметр.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-114">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="f6a7a-115">На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> описанный выше.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-115">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>  
  
 <span data-ttu-id="f6a7a-116">![Пример: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="f6a7a-116">![Example: TextTrimming.WordEllipsis](../../../../docs/framework/wpf/advanced/media/texttrimming-word.png "TextTrimming_Word")</span></span>  
  
 <span data-ttu-id="f6a7a-117">При <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> равно **нет**, то обрезка текста не выполняется.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-117">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="f6a7a-118">В этом случае текст просто обрезается по границе родительского контейнера текста.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-118">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="f6a7a-119">На следующем рисунке показано влияние этого параметра на <xref:System.Windows.Controls.TextBlock> аналогично указанному выше.</span><span class="sxs-lookup"><span data-stu-id="f6a7a-119">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>  
  
 <span data-ttu-id="f6a7a-120">![Пример: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="f6a7a-120">![Example: TextTrimming.None](../../../../docs/framework/wpf/advanced/media/texttrimming-none.png "TextTrimming_None")</span></span>
