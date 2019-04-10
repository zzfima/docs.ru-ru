---
title: Практическое руководство. Получение выделенного текста
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: b7f0b9ee02a7ace717787fc8eeb6e15649829a49
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224589"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="d6f87-102">Практическое руководство. Получение выделенного текста</span><span class="sxs-lookup"><span data-stu-id="d6f87-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="d6f87-103">В этом примере показан один из способов использования <xref:System.Windows.Controls.TextBox.SelectedText%2A> свойства, чтобы получить текст, который пользователь выбрал в <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d6f87-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6f87-104">Пример</span><span class="sxs-lookup"><span data-stu-id="d6f87-104">Example</span></span>  
 <span data-ttu-id="d6f87-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере показано определение <xref:System.Windows.Controls.TextBox> элемент управления, содержащий текст для выбора, и <xref:System.Windows.Controls.Button> элемента управления с указанным <xref:System.Windows.Controls.Button.OnClick%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="d6f87-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="d6f87-106">В этом примере кнопка со связанным <xref:System.Windows.Controls.Primitives.ButtonBase.Click> обработчик событий используется для получения выделенный текст.</span><span class="sxs-lookup"><span data-stu-id="d6f87-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="d6f87-107">Когда пользователь нажимает кнопку, <xref:System.Windows.Controls.Button.OnClick%2A> метод копирует любой выделенный текст в текстовом поле в строку.</span><span class="sxs-lookup"><span data-stu-id="d6f87-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="d6f87-108">Конкретной ситуации, по которым выделенный текст извлекается (нажатие кнопки), а также действие, выполняемое с выделенным (копирование выделенного текста в строку), можно легко изменить в соответствии с самых разнообразных сценариях.</span><span class="sxs-lookup"><span data-stu-id="d6f87-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="d6f87-109">Пример</span><span class="sxs-lookup"><span data-stu-id="d6f87-109">Example</span></span>  
 <span data-ttu-id="d6f87-110">Следующие C# показано в примере <xref:System.Windows.Controls.Button.OnClick%2A> обработчик событий для кнопки, определенных в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] в этом примере.</span><span class="sxs-lookup"><span data-stu-id="d6f87-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="d6f87-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d6f87-111">See also</span></span>

- [<span data-ttu-id="d6f87-112">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="d6f87-112">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="d6f87-113">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="d6f87-113">RichTextBox Overview</span></span>](richtextbox-overview.md)
