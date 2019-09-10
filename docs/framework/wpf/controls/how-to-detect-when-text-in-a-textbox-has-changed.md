---
title: Практическое руководство. Определение изменения текста в TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TextBox control [WPF], detecting text change
- text change [WPF], detecting
- detecting text change [WPF]
ms.assetid: 1c39ee14-e37f-49fb-a0d1-a9824ca13584
ms.openlocfilehash: 8c7744e9e61b8ba796802e54435c0bf9fdbee50e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855618"
---
# <a name="how-to-detect-when-text-in-a-textbox-has-changed"></a>Практическое руководство. Определение изменения текста в TextBox

В этом примере показан один из способов использования <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> события для выполнения метода при изменении текста <xref:System.Windows.Controls.TextBox> в элементе управления.

В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , <xref:System.Windows.Controls.TextBox> содержащего элемент управления, для которого необходимо отслеживать изменения, вставьте <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> метод, который будет вызываться при каждом срабатывании события.  Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.

Обработчик событий вызывается при каждом изменении содержимого <xref:System.Windows.Controls.TextBox> элемента управления либо пользователем, либо программным способом.

> [!NOTE]
> Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.

## <a name="example"></a>Пример

В, определяющем элемент управления, укажите <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> атрибут со значением, соответствующим имени метода обработчика событий. <xref:System.Windows.Controls.TextBox> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]

[!code-xaml[TextBox_MiscCode#_TextChangedXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textchangedxaml)]

## <a name="example"></a>Пример

В классе кода программной части для [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , <xref:System.Windows.Controls.TextBox> содержащего элемент управления, для которого необходимо отслеживать изменения, вставьте <xref:System.Windows.Controls.Primitives.TextBoxBase.TextChanged> метод, который будет вызываться при каждом срабатывании события.  Этот метод должен иметь сигнатуру, которая соответствует тому, что ожидается <xref:System.Windows.Controls.TextChangedEventHandler> делегатом.

[!code-csharp[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textchangedeventhandler)]
[!code-vb[TextBox_MiscCode#_TextChangedEventHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textchangedeventhandler)]

Обработчик событий вызывается при каждом изменении содержимого <xref:System.Windows.Controls.TextBox> элемента управления либо пользователем, либо программным способом.

> [!NOTE]
> Это событие срабатывает при <xref:System.Windows.Controls.TextBox> создании элемента управления и его первоначальном заполнении текстом.

Комментарии

## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.TextChangedEventArgs>
- [Общие сведения о TextBox](textbox-overview.md)
- [Общие сведения о RichTextBox](richtextbox-overview.md)
