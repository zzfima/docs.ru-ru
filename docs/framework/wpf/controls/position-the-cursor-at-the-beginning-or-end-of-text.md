---
title: Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
ms.openlocfilehash: 79ecf1d5dccee0dacef8e288c0c2e044334e65d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556043"
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="21c7b-102">Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="21c7b-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="21c7b-103">В этом примере показано, как для позиционирования курсора в начале или конце текстовое содержимое <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="21c7b-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21c7b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="21c7b-104">Example</span></span>  
 <span data-ttu-id="21c7b-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] код описывает <xref:System.Windows.Controls.TextBox> управления и присваивает ему имя.</span><span class="sxs-lookup"><span data-stu-id="21c7b-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="21c7b-106">Пример</span><span class="sxs-lookup"><span data-stu-id="21c7b-106">Example</span></span>  
 <span data-ttu-id="21c7b-107">Для позиционирования курсора в начало содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию 0 и длину, равную 0.</span><span class="sxs-lookup"><span data-stu-id="21c7b-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="21c7b-108">Пример</span><span class="sxs-lookup"><span data-stu-id="21c7b-108">Example</span></span>  
 <span data-ttu-id="21c7b-109">Для позиционирования курсора в конце содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию равной длины текстового содержимого и длину, равную 0.</span><span class="sxs-lookup"><span data-stu-id="21c7b-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="21c7b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="21c7b-110">See Also</span></span>  
 [<span data-ttu-id="21c7b-111">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="21c7b-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="21c7b-112">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="21c7b-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
