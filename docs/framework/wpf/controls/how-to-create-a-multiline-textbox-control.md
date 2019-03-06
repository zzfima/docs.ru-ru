---
title: Практическое руководство. Создание элемента управления для многострочных элементов TextBox
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [WPF], multiple lines of text
ms.assetid: 05914a93-d0ea-4a9a-b693-09df7d4e2ac2
ms.openlocfilehash: 75bbee806b2b7039656d6c8e7c9a64359e77d16f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352351"
---
# <a name="how-to-create-a-multiline-textbox-control"></a>Практическое руководство. Создание элемента управления для многострочных элементов TextBox
В этом примере показано, как использовать [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] для определения <xref:System.Windows.Controls.TextBox> элемент управления, который будет автоматически расширяться, чтобы вместить несколько строк текста.  
  
## <a name="example"></a>Пример  
 Параметр <xref:System.Windows.Controls.TextBox.TextWrapping%2A> атрибут **Wrap** вызовет введенного текста программы-оболочки в новую строку при границе <xref:System.Windows.Controls.TextBox> будет достигнут элемент управления, автоматически расширяя <xref:System.Windows.Controls.TextBox> элемента управления, чтобы появилось место для строки, в том случае, если обязательно.  
  
 Установка <xref:System.Windows.Controls.Primitives.TextBoxBase.AcceptsReturn%2A> атрибут **true** приводит к новой строке должен быть вставлен при нажатии клавиши ВВОД, автоматически расширяя <xref:System.Windows.Controls.TextBox> чтобы появилось место для новой строки, в том случае, при необходимости.  
  
 <xref:System.Windows.Controls.Primitives.TextBoxBase.VerticalScrollBarVisibility%2A> Атрибут добавляет полосу прокрутки для <xref:System.Windows.Controls.TextBox>, так что содержимое <xref:System.Windows.Controls.TextBox> может прокручиваться до, если <xref:System.Windows.Controls.TextBox> превышает размеры рамки или окна, который его окружает.  
  
 [!code-xaml[TextBox_MiscCode#_MultilineTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_multilinetextboxxaml)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Windows.TextWrapping>
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
