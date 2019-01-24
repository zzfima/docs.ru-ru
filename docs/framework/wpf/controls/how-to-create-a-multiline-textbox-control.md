---
title: Как выполнить Создание элемента управления для многострочных элементов TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: ca1b499b2acdfd9fd2ff0f57f2b0c07d7da10789
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517829"
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="596a3-102">Как выполнить Создание элемента управления для многострочных элементов TextBox</span><span class="sxs-lookup"><span data-stu-id="596a3-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="596a3-103">В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемент управления, который будет автоматически расширяться, чтобы вместить несколько строк текста.</span><span class="sxs-lookup"><span data-stu-id="596a3-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="596a3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="596a3-104">Example</span></span>  
 <span data-ttu-id="596a3-105">Параметр <xref:System.Windows.Controls.TextBox.TextWrapping%2A> атрибут **Wrap** вызовет введенного текста программы-оболочки в новую строку при границе <xref:System.Windows.Controls.TextBox> будет достигнут элемент управления, автоматически расширяя <xref:System.Windows.Controls.TextBox> элемента управления, чтобы появилось место для строки, в том случае, если обязательно.</span><span class="sxs-lookup"><span data-stu-id="596a3-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="596a3-106">Установка <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибут **true** приводит к новой строке должен быть вставлен при нажатии клавиши ВВОД, автоматически расширяя <xref:System.Windows.Controls.TextBox> чтобы появилось место для новой строки, в том случае, при необходимости.</span><span class="sxs-lookup"><span data-stu-id="596a3-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="596a3-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Атрибут добавляет полосу прокрутки для <xref:System.Windows.Controls.TextBox>, так что содержимое <xref:System.Windows.Controls.TextBox> может прокручиваться до, если <xref:System.Windows.Controls.TextBox> превышает размеры рамки или окна, который его окружает.</span><span class="sxs-lookup"><span data-stu-id="596a3-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="596a3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="596a3-108">See also</span></span>
- <xref:System.Windows.TextWrapping>
- [<span data-ttu-id="596a3-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="596a3-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [<span data-ttu-id="596a3-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="596a3-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
