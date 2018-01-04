---
title: "Практическое руководство. Установка фокуса в элементе управления TextBox"
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
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe07633e41986e383d5f40dc66c0689a91e33116
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-focus-in-a-textbox-control"></a>Практическое руководство. Установка фокуса в элементе управления TextBox
В этом примере показано, как использовать <xref:System.Windows.UIElement.Focus%2A> метод, чтобы установить фокус на <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примере описывается простой <xref:System.Windows.Controls.TextBox> управления с именем *tbFocusMe*  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a>Пример  
 В следующем примере вызывается <xref:System.Windows.UIElement.Focus%2A> метод, чтобы установить фокус на <xref:System.Windows.Controls.TextBox> управления с именем *tbFocusMe*.  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.UIElement.Focusable%2A>  
 <xref:System.Windows.UIElement.IsFocused%2A>  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
