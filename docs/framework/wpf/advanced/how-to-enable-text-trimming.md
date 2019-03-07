---
title: Практическое руководство. Включение обрезки текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474151"
---
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="ab600-102">Практическое руководство. Включение обрезки текста</span><span class="sxs-lookup"><span data-stu-id="ab600-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="ab600-103">В этом примере демонстрируется использование и влияние значений, доступных в <xref:System.Windows.TextTrimming> перечисления.</span><span class="sxs-lookup"><span data-stu-id="ab600-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="ab600-104">Пример</span><span class="sxs-lookup"><span data-stu-id="ab600-104">Example</span></span>

<span data-ttu-id="ab600-105">В следующем примере определяется <xref:System.Windows.Controls.TextBlock> элемент с <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> набором атрибутов.</span><span class="sxs-lookup"><span data-stu-id="ab600-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="ab600-106">Установка соответствующего <xref:System.Windows.TextTrimming> ниже показано свойство в коде.</span><span class="sxs-lookup"><span data-stu-id="ab600-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="ab600-107">Существует в настоящее время три параметра обрезки текста: **CharacterEllipsis**, **WordEllipsis**, и **None**.</span><span class="sxs-lookup"><span data-stu-id="ab600-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="ab600-108">Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> присваивается **CharacterEllipsis**, текст обрезается и продолжается многоточием после символа, ближайшего к краю обрезки.</span><span class="sxs-lookup"><span data-stu-id="ab600-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="ab600-109">Эта настройка позволяет обрезать текст максимально близко к границе обрезки, однако иногда частично обрезаются слова.</span><span class="sxs-lookup"><span data-stu-id="ab600-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="ab600-110">На следующем рисунке показано влияние этой настройки на <xref:System.Windows.Controls.TextBlock> аналогичную определенным выше.</span><span class="sxs-lookup"><span data-stu-id="ab600-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="ab600-111">![Пример: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="ab600-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="ab600-112">Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> присваивается **WordEllipsis**, текст обрезается и продолжается многоточием в конце первого полного слова, ближайшего к краю обрезки.</span><span class="sxs-lookup"><span data-stu-id="ab600-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="ab600-113">Этот параметр не будет отображаться частично обрезанные слова, но не текст обрезается так близко к краю обрезки, как **CharacterEllipsis** параметр.</span><span class="sxs-lookup"><span data-stu-id="ab600-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="ab600-114">На следующем рисунке показано влияние этой настройки на <xref:System.Windows.Controls.TextBlock> определенный выше.</span><span class="sxs-lookup"><span data-stu-id="ab600-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="ab600-115">![Пример: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="ab600-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="ab600-116">Когда <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> присваивается **None**, обрезка текста не выполняется.</span><span class="sxs-lookup"><span data-stu-id="ab600-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="ab600-117">В этом случае текст просто обрезается по границе родительского контейнера текста.</span><span class="sxs-lookup"><span data-stu-id="ab600-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="ab600-118">На следующем рисунке показано влияние этой настройки на <xref:System.Windows.Controls.TextBlock> аналогичную определенным выше.</span><span class="sxs-lookup"><span data-stu-id="ab600-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="ab600-119">![Пример: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="ab600-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
