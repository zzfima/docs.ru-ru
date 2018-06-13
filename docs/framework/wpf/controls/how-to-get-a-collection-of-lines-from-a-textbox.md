---
title: Практическое руководство. Получение коллекции строк из элемента TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- lines [WPF], getting collection of
- TextBox control [WPF], getting collection of lines
ms.assetid: a12f529d-b926-47f6-92bf-cad5f17b532a
ms.openlocfilehash: 64187527da3cfb97343e2036338822d479dd997a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552744"
---
# <a name="how-to-get-a-collection-of-lines-from-a-textbox"></a>Практическое руководство. Получение коллекции строк из элемента TextBox
В этом примере показано, как получить коллекцию строк текста из <xref:System.Windows.Controls.TextBox>.  
  
## <a name="example"></a>Пример  
 В следующем примере показано простой метод, который принимает <xref:System.Windows.Controls.TextBox> как аргумент и возвращает <xref:System.Collections.Specialized.StringCollection> содержащих строки текста в **TextBox**.  <xref:System.Windows.Controls.TextBox.LineCount%2A> Свойство позволяет определить, сколько строк в настоящее время **TextBox**и <xref:System.Windows.Controls.TextBox.GetLineText%2A> метод затем используется для извлечения каждой строки и добавить его в коллекцию строк.  
  
 [!code-csharp[TextBox_MiscCode#_TextBox_GetLines](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textbox_getlines)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
