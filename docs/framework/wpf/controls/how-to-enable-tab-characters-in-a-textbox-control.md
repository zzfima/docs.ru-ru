---
title: Практическое руководство. Включение знаков табуляции в элементе управления TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: 6d134757c3c08e92e608a7ff868b2f3d28a69b27
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356550"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>Практическое руководство. Включение знаков табуляции в элементе управления TextBox
В этом примере показано, как включить принятие знаков табуляции в качестве обычных входных данных в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Включение принятия знаков табуляции в качестве входных данных в <xref:System.Windows.Controls.TextBox> , назначьте <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> атрибут **true**.  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
