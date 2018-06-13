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
# <a name="how-to-position-the-cursor-at-the-beginning-or-end-of-text-in-a-textbox-control"></a>Практическое руководство. Позиционирование курсора в начало или конец текста в элементе управления TextBox
В этом примере показано, как для позиционирования курсора в начале или конце текстовое содержимое <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] код описывает <xref:System.Windows.Controls.TextBox> управления и присваивает ему имя.  
  
 [!code-xaml[TextBox_MiscCode#_MoveCursorXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_movecursorxaml)]  
  
## <a name="example"></a>Пример  
 Для позиционирования курсора в начало содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию 0 и длину, равную 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortostart)]
 [!code-vb[TextBox_MiscCode#_CursorToStart](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortostart)]  
  
## <a name="example"></a>Пример  
 Для позиционирования курсора в конце содержимого <xref:System.Windows.Controls.TextBox> управления, вызовите метод <xref:System.Windows.Controls.TextBox.Select%2A> метод и укажите начальную позицию равной длины текстового содержимого и длину, равную 0.  
  
 [!code-csharp[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_cursortoend)]
 [!code-vb[TextBox_MiscCode#_CursorToEnd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_cursortoend)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
