---
title: "Практическое руководство. Перевод элемента управления TextBox в режим только для чтения"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 36116346b389dac7e9783e69d9bcd79573b4bf75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="8d287-102">Практическое руководство. Перевод элемента управления TextBox в режим только для чтения</span><span class="sxs-lookup"><span data-stu-id="8d287-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="8d287-103">В этом примере показано, как настроить <xref:System.Windows.Controls.TextBox> допускает ввод данных пользователем или изменение элемента управления.</span><span class="sxs-lookup"><span data-stu-id="8d287-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8d287-104">Пример</span><span class="sxs-lookup"><span data-stu-id="8d287-104">Example</span></span>  
 <span data-ttu-id="8d287-105">Чтобы запретить пользователям изменять содержимое <xref:System.Windows.Controls.TextBox> установите <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> атрибут **true**.</span><span class="sxs-lookup"><span data-stu-id="8d287-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="8d287-106"><xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> Атрибут влияет только ввод данных пользователем, не влияет на значение текст [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] описание <xref:System.Windows.Controls.TextBox> управления или текст, задайте программным путем с помощью <xref:System.Windows.Controls.TextBox.Text%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="8d287-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="8d287-107">Значение по умолчанию <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> — **false**.</span><span class="sxs-lookup"><span data-stu-id="8d287-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d287-108">См. также</span><span class="sxs-lookup"><span data-stu-id="8d287-108">See Also</span></span>  
 [<span data-ttu-id="8d287-109">Общие сведения о TextBox</span><span class="sxs-lookup"><span data-stu-id="8d287-109">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [<span data-ttu-id="8d287-110">Общие сведения о RichTextBox</span><span class="sxs-lookup"><span data-stu-id="8d287-110">RichTextBox Overview</span></span>](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
