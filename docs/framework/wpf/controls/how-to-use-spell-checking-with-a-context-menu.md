---
title: Практическое руководство. Использование проверки орфографии при помощи контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 966e3adbcb57c30a55d606f6d6b8b51523ee30ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33553771"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="ada8b-102">Практическое руководство. Использование проверки орфографии при помощи контекстного меню</span><span class="sxs-lookup"><span data-stu-id="ada8b-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="ada8b-103">По умолчанию при включении проверка орфографии в элементе управления редактирования, например <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>, можно выбрать варианты проверки орфографии в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="ada8b-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="ada8b-104">Например, если пользователи неправильно написанное слово, щелкните правой кнопкой мыши, они получают набор замен или параметр, чтобы **пропустить все**.</span><span class="sxs-lookup"><span data-stu-id="ada8b-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="ada8b-105">Однако при переопределении контекстное меню по умолчанию с собственного пользовательского контекстного меню, эта функциональная возможность теряется и необходимо написать код, чтобы включить средство проверки орфографии в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="ada8b-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="ada8b-106">В следующем примере показано, как включить ее на <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="ada8b-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ada8b-107">Пример</span><span class="sxs-lookup"><span data-stu-id="ada8b-107">Example</span></span>  
 <span data-ttu-id="ada8b-108">В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , создающего <xref:System.Windows.Controls.TextBox> с несколькими событиями, которые используются для реализации контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="ada8b-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="ada8b-109">Пример</span><span class="sxs-lookup"><span data-stu-id="ada8b-109">Example</span></span>  
 <span data-ttu-id="ada8b-110">В примере показан код, который реализует в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="ada8b-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="ada8b-111">Код, используемый для этого с <xref:System.Windows.Controls.RichTextBox> аналогично.</span><span class="sxs-lookup"><span data-stu-id="ada8b-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="ada8b-112">Основное отличие состоит в параметр, передаваемый `GetSpellingError` метод.</span><span class="sxs-lookup"><span data-stu-id="ada8b-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="ada8b-113">Для <xref:System.Windows.Controls.TextBox>, передайте целочисленный индекс положения курсора:</span><span class="sxs-lookup"><span data-stu-id="ada8b-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="ada8b-114">Для <xref:System.Windows.Controls.RichTextBox>, передайте <xref:System.Windows.Documents.TextPointer> , указывающий положение курсора:</span><span class="sxs-lookup"><span data-stu-id="ada8b-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="ada8b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ada8b-115">See Also</span></span>  
 [<span data-ttu-id="ada8b-116">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="ada8b-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="ada8b-117">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ada8b-117">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [<span data-ttu-id="ada8b-118">Включение проверки орфографии в элементе управления редактирования текста</span><span class="sxs-lookup"><span data-stu-id="ada8b-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)  
 [<span data-ttu-id="ada8b-119">Использование пользовательского контекстного меню с элементом TextBox</span><span class="sxs-lookup"><span data-stu-id="ada8b-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
