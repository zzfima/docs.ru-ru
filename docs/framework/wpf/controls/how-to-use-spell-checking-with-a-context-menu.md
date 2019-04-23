---
title: Практическое руководство. Использование проверки орфографии с помощью контекстного меню
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 72b24c386eb99140c9c2729688994b81f92e1a6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192983"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="340db-102">Практическое руководство. Использование проверки орфографии с помощью контекстного меню</span><span class="sxs-lookup"><span data-stu-id="340db-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="340db-103">По умолчанию при включении орфографии в элементе управления редактирования, такие как <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.RichTextBox>, можно выбрать варианты правописания в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="340db-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="340db-104">Например, если пользователи неправильно написанное слово, щелкните правой кнопкой мыши, они получают набор вариантов правописания или возможность **пропустить все**.</span><span class="sxs-lookup"><span data-stu-id="340db-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="340db-105">Тем не менее при переопределении отобразится контекстное меню по умолчанию с собственного пользовательского контекстного меню, эта функция теряется, и вам нужно написать код, чтобы включить средство проверки орфографии в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="340db-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="340db-106">В следующем примере показано, как включить эту функцию для <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="340db-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="340db-107">Пример</span><span class="sxs-lookup"><span data-stu-id="340db-107">Example</span></span>  
 <span data-ttu-id="340db-108">В следующем примере показан [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , создающий <xref:System.Windows.Controls.TextBox> с некоторые события, которые используются для реализации контекстного меню.</span><span class="sxs-lookup"><span data-stu-id="340db-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="340db-109">Пример</span><span class="sxs-lookup"><span data-stu-id="340db-109">Example</span></span>  
 <span data-ttu-id="340db-110">Следующий пример показывает код, который реализует в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="340db-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="340db-111">Код, используемый для этого с помощью <xref:System.Windows.Controls.RichTextBox> похож.</span><span class="sxs-lookup"><span data-stu-id="340db-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="340db-112">Основное различие состоит в параметр, передаваемый `GetSpellingError` метод.</span><span class="sxs-lookup"><span data-stu-id="340db-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="340db-113">Для <xref:System.Windows.Controls.TextBox>, передайте целочисленный индекс положения курсора:</span><span class="sxs-lookup"><span data-stu-id="340db-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="340db-114">Для <xref:System.Windows.Controls.RichTextBox>, передайте <xref:System.Windows.Documents.TextPointer> , указывающий положение курсора:</span><span class="sxs-lookup"><span data-stu-id="340db-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="340db-115">См. также</span><span class="sxs-lookup"><span data-stu-id="340db-115">See also</span></span>

- [<span data-ttu-id="340db-116">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="340db-116">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="340db-117">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="340db-117">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="340db-118">Включение проверки орфографии в элементе управления редактирования текста</span><span class="sxs-lookup"><span data-stu-id="340db-118">Enable Spell Checking in a Text Editing Control</span></span>](how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="340db-119">Использование пользовательского контекстного меню с элементом TextBox</span><span class="sxs-lookup"><span data-stu-id="340db-119">Use a Custom Context Menu with a TextBox</span></span>](how-to-use-a-custom-context-menu-with-a-textbox.md)
