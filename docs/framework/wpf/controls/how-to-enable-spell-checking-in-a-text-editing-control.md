---
title: Практическое руководство. Включение проверки орфографии в элементе управления редактирования текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- spellchecking [WPF]
- real-time spellchecking
- TextBox control [WPF], real-time spellchecking
- spelling checker [WPF]
- checking spelling [WPF]
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
ms.openlocfilehash: 633ffe38503df743df355a8b476e7b254fcafffa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370683"
---
# <a name="how-to-enable-spell-checking-in-a-text-editing-control"></a><span data-ttu-id="875a5-102">Практическое руководство. Включение проверки орфографии в элементе управления редактирования текста</span><span class="sxs-lookup"><span data-stu-id="875a5-102">How to: Enable Spell Checking in a Text Editing Control</span></span>
<span data-ttu-id="875a5-103">В следующем примере демонстрируется включение проверки орфографии в режиме реального времени <xref:System.Windows.Controls.TextBox> с помощью <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> свойство <xref:System.Windows.Controls.SpellCheck> класса.</span><span class="sxs-lookup"><span data-stu-id="875a5-103">The following example shows how to enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> by using the <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> property of the <xref:System.Windows.Controls.SpellCheck> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="875a5-104">Пример</span><span class="sxs-lookup"><span data-stu-id="875a5-104">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="875a5-105">См. также</span><span class="sxs-lookup"><span data-stu-id="875a5-105">See also</span></span>
- [<span data-ttu-id="875a5-106">Использование проверки орфографии с помощью контекстного меню</span><span class="sxs-lookup"><span data-stu-id="875a5-106">Use Spell Checking with a Context Menu</span></span>](how-to-use-spell-checking-with-a-context-menu.md)
- [<span data-ttu-id="875a5-107">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="875a5-107">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="875a5-108">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="875a5-108">RichTextBox Overview</span></span>](richtextbox-overview.md)
