---
title: "Практическое руководство. Включение проверки орфографии в элементе управления редактирования текста"
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
- spellchecking [WPF]
- real-time spellchecking
- TextBox control [WPF], real-time spellchecking
- spelling checker [WPF]
- checking spelling [WPF]
ms.assetid: 6f953d2b-67e8-4012-84ce-53c0e958da47
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e70bbe3b4d3656001af23108b2f76b40d2887318
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-spell-checking-in-a-text-editing-control"></a><span data-ttu-id="a2acf-102">Практическое руководство. Включение проверки орфографии в элементе управления редактирования текста</span><span class="sxs-lookup"><span data-stu-id="a2acf-102">How to: Enable Spell Checking in a Text Editing Control</span></span>
<span data-ttu-id="a2acf-103">В следующем примере показано, как включить проверку правописания в реальном времени <xref:System.Windows.Controls.TextBox> с помощью <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> свойство <xref:System.Windows.Controls.SpellCheck> класса.</span><span class="sxs-lookup"><span data-stu-id="a2acf-103">The following example shows how to enable real-time spell checking in a <xref:System.Windows.Controls.TextBox> by using the <xref:System.Windows.Controls.SpellCheck.IsEnabled%2A> property of the <xref:System.Windows.Controls.SpellCheck> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2acf-104">Пример</span><span class="sxs-lookup"><span data-stu-id="a2acf-104">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellCheckExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/spellcheckexample.xaml#spellcheckexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/CSharp/SpellCheckExample.cs#spellcheckcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_procedural_snip#SpellCheckCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_procedural_snip/visualbasic/spellcheckexample.vb#spellcheckcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="a2acf-105">См. также</span><span class="sxs-lookup"><span data-stu-id="a2acf-105">See Also</span></span>  
 [<span data-ttu-id="a2acf-106">Использование проверки орфографии с помощью контекстного меню</span><span class="sxs-lookup"><span data-stu-id="a2acf-106">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="a2acf-107">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="a2acf-107">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="a2acf-108">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="a2acf-108">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
