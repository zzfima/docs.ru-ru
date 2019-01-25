---
title: Как выполнить Включение знаков табуляции в элементе управления TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], enabling tab characters
- tab characters [WPF], enabling
ms.assetid: 14b1b064-61f7-4958-be63-88d85b868d03
ms.openlocfilehash: de3336838ba35a70575ec2549c79faf04be2e7a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743612"
---
# <a name="how-to-enable-tab-characters-in-a-textbox-control"></a>Как выполнить Включение знаков табуляции в элементе управления TextBox
В этом примере показано, как включить принятие знаков табуляции в качестве обычных входных данных в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
## <a name="example"></a>Пример  
 Включение принятия знаков табуляции в качестве входных данных в <xref:System.Windows.Controls.TextBox> , назначьте <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsTab%2A> атрибут **true**.  
  
 [!code-xaml[TextBox_EnablingTab#_AcceptsTab](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_EnablingTab/CS/Window1.xaml#_acceptstab)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [Общие сведения о RichTextBox](../../../../docs/framework/wpf/controls/richtextbox-overview.md)
