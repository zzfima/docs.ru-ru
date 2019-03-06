---
title: Практическое руководство. Изменение оформления текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- setting Typography attributes [WPF]
- Typography attribute [WPF], setting
ms.assetid: 19a3b49b-60a2-4c11-a786-e26b4c965588
ms.openlocfilehash: eeed93f62802a942915511db060c0e6c029579e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365790"
---
# <a name="how-to-alter-the-typography-of-text"></a><span data-ttu-id="4b30f-102">Практическое руководство. Изменение оформления текста</span><span class="sxs-lookup"><span data-stu-id="4b30f-102">How-to: Alter the Typography of Text</span></span>
<span data-ttu-id="4b30f-103">В следующем примере показано, как задать <xref:System.Windows.Documents.TextElement.Typography%2A> атрибут, с помощью <xref:System.Windows.Documents.Paragraph> качестве элемента примера.</span><span class="sxs-lookup"><span data-stu-id="4b30f-103">The following example shows how to set the <xref:System.Windows.Documents.TextElement.Typography%2A> attribute, using <xref:System.Windows.Documents.Paragraph> as the example element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b30f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="4b30f-104">Example</span></span>  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 <span data-ttu-id="4b30f-105">На следующем рисунке показана отрисовка этого примера.</span><span class="sxs-lookup"><span data-stu-id="4b30f-105">The following figure shows how this example renders.</span></span>  
  
 <span data-ttu-id="4b30f-106">![Снимок экрана: Текст с измененной типографией](./media/textelement-typog.png "TextElement_Typog")</span><span class="sxs-lookup"><span data-stu-id="4b30f-106">![Screenshot: Text with altered typography](./media/textelement-typog.png "TextElement_Typog")</span></span>  
  
 <span data-ttu-id="4b30f-107">Напротив, на следующем рисунке показано, как отрисовывается аналогичный пример с типографскими характеристиками по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4b30f-107">In contrast, the following figure shows how a similar example with default typographic properties renders.</span></span>  
  
 <span data-ttu-id="4b30f-108">![Снимок экрана: Текст с измененной типографией](./media/textelement-typog-default.png "TextElement_Typog_Default")</span><span class="sxs-lookup"><span data-stu-id="4b30f-108">![Screenshot: Text with altered typography](./media/textelement-typog-default.png "TextElement_Typog_Default")</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b30f-109">Пример</span><span class="sxs-lookup"><span data-stu-id="4b30f-109">Example</span></span>  
 <span data-ttu-id="4b30f-110">В следующем примере показано, как задать <xref:System.Windows.Controls.TextBox.Typography%2A> свойства программным способом.</span><span class="sxs-lookup"><span data-stu-id="4b30f-110">The following example shows how to set the <xref:System.Windows.Controls.TextBox.Typography%2A> property programmatically.</span></span>  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](~/samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
## <a name="see-also"></a><span data-ttu-id="4b30f-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4b30f-111">See also</span></span>
- [<span data-ttu-id="4b30f-112">Общие сведения о документах нефиксированного формата</span><span class="sxs-lookup"><span data-stu-id="4b30f-112">Flow Document Overview</span></span>](flow-document-overview.md)
