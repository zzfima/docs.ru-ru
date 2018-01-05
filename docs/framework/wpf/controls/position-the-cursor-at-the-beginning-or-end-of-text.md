---
title: "Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox"
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
- positioning cursor [WPF]
- TextBox control [WPF], positioning cursor
- cursor [WPF], positioning
ms.assetid: c771a0b8-c6b4-4240-aecd-a21d0ba51a2e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df30adf232ad782999d8bdf52b1946f84785f98d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a><span data-ttu-id="c68bd-102">Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="c68bd-102">How to: Position the Cursor at the Beginning or End of Text in a TextBox Control</span></span>
<span data-ttu-id="c68bd-103">В этом примере показано, как для позиционирования курсора в начале или конце текстовое содержимое <xref:System.Windows.Controls.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c68bd-103">This example shows how to position the cursor at the beginning or end of the text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c68bd-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c68bd-104">Example</span></span>  
 <span data-ttu-id="c68bd-105">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] код описывает <xref:System.Windows.Controls.TextBox> управления и присваивает ему имя.</span><span class="sxs-lookup"><span data-stu-id="c68bd-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] code describes a <xref:System.Windows.Controls.TextBox> control and assigns it a Name.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a><span data-ttu-id="c68bd-106">Пример</span><span class="sxs-lookup"><span data-stu-id="c68bd-106">Example</span></span>  
 <span data-ttu-id="c68bd-107">Для позиционирования курсора в начало содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию 0 и длину, равную 0.</span><span class="sxs-lookup"><span data-stu-id="c68bd-107">To position the cursor at the beginning of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position of 0, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a><span data-ttu-id="c68bd-108">Пример</span><span class="sxs-lookup"><span data-stu-id="c68bd-108">Example</span></span>  
 <span data-ttu-id="c68bd-109">Для позиционирования курсора в конце содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию равной длины текстового содержимого и длину, равную 0.</span><span class="sxs-lookup"><span data-stu-id="c68bd-109">To position the cursor at the end of the contents of a <xref:System.Windows.Controls.TextBox> control, call the <xref:System.Windows.Controls.TextBox.Select%2A> method and specify the selection start position equal to the  length of the text content, and a selection length of 0.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a><span data-ttu-id="c68bd-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c68bd-110">See Also</span></span>  
 [<span data-ttu-id="c68bd-111">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="c68bd-111">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="c68bd-112">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c68bd-112">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
