---
title: "Как создать элемент управления для нескольких TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2a6885a594e5fcd747f85dedf1afbd39ec644717
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-multiline-textbox-control"></a><span data-ttu-id="f333b-102">Как создать элемент управления для нескольких TextBox</span><span class="sxs-lookup"><span data-stu-id="f333b-102">How to: Create a Multiline TextBox Control</span></span>
<span data-ttu-id="f333b-103">В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемент управления, который будет автоматически расширяться, чтобы вместить несколько строк текста.</span><span class="sxs-lookup"><span data-stu-id="f333b-103">This example shows how to use [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.TextBox> control that will automatically expand to accommodate multiple lines of text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f333b-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f333b-104">Example</span></span>  
 <span data-ttu-id="f333b-105">Параметр <xref:System.Windows.Controls.TextBox.TextWrapping%2A> атрибут **Wrap** вызовет введенного текста для переноса в новую строку при краем <xref:System.Windows.Controls.TextBox> достигнут элемент управления, автоматическое расширение <xref:System.Windows.Controls.TextBox> элемента управления, чтобы включить место для новой строки, если обязательно.</span><span class="sxs-lookup"><span data-stu-id="f333b-105">Setting the <xref:System.Windows.Controls.TextBox.TextWrapping%2A> attribute to **Wrap** will cause entered text to wrap to a new line when the edge of the <xref:System.Windows.Controls.TextBox> control is reached, automatically expanding the <xref:System.Windows.Controls.TextBox> control to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f333b-106">Установка <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибут **true** вызывает строки должен быть вставлен при нажатии клавиши ВВОД, автоматически расширяя <xref:System.Windows.Controls.TextBox> при необходимости включите место для новой строки.</span><span class="sxs-lookup"><span data-stu-id="f333b-106">Setting the <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> attribute to **true** causes a new line to be inserted when the RETURN key is pressed, once again automatically expanding the <xref:System.Windows.Controls.TextBox> to include room for a new line, if necessary.</span></span>  
  
 <span data-ttu-id="f333b-107"><xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Атрибут добавляет полосу прокрутки для <xref:System.Windows.Controls.TextBox>, после чего содержимое <xref:System.Windows.Controls.TextBox> прокручивать if <xref:System.Windows.Controls.TextBox> превышает размеры фрейма или окно, в котором он содержится.</span><span class="sxs-lookup"><span data-stu-id="f333b-107">The <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> attribute adds a scroll bar to the <xref:System.Windows.Controls.TextBox>, so that the contents of the <xref:System.Windows.Controls.TextBox> can be scrolled through if the <xref:System.Windows.Controls.TextBox> expands beyond the size of the frame or window that encloses it.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a><span data-ttu-id="f333b-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f333b-108">See Also</span></span>  
 <xref:System.Windows.TextWrapping>  
 [<span data-ttu-id="f333b-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="f333b-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="f333b-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="f333b-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
