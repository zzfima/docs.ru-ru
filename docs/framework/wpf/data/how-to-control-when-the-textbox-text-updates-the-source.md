---
title: Практическое руководство. Управление обновлением источника из поля TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
ms.openlocfilehash: b211eb67e3bac95f74255935a39cc0d6aec61531
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73974785"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Практическое руководство. Управление обновлением источника из поля TextBox
В этом разделе описывается использование свойства <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для управления временем обновления источника привязки. В этом разделе в качестве примера используется элемент управления <xref:System.Windows.Controls.TextBox>.

## <a name="example"></a>Пример
 Свойство <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType> имеет <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение по умолчанию <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>. Это означает, что если приложение имеет <xref:System.Windows.Controls.TextBox> с привязанным к данным свойством <xref:System.Windows.Controls.TextBox.Text%2A?displayProperty=nameWithType>, то текст, введенный в <xref:System.Windows.Controls.TextBox>, не обновляет источник до тех пор, пока <xref:System.Windows.Controls.TextBox> не теряет фокус (например, если щелкнуть вне <xref:System.Windows.Controls.TextBox>).

 Если вы хотите, чтобы источник обновлялся по мере ввода, задайте для <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. В следующем примере выделенные строки кода показывают, что `Text` свойства <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.TextBlock> привязаны к одному и тому же свойству источника. Свойству <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> привязки <xref:System.Windows.Controls.TextBox> присвоено значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>.

 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]

 В результате <xref:System.Windows.Controls.TextBlock> отображает один и тот же текст (из-за изменения источника) по мере ввода пользователем текста в <xref:System.Windows.Controls.TextBox>, как показано на следующем снимке экрана примера:

 ![Снимок экрана, на котором показана простая привязка данных.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)

 Если у вас есть диалоговое окно или пользовательская форма, и вы хотите отложить обновления источника до тех пор, пока пользователь не закончит редактирование полей и не нажмет кнопку "ОК", можно задать <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значения привязок <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, как показано в следующем примере:

 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]

 Если значение <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> устанавливается равным <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, исходное значение изменяется только тогда, когда приложение вызывает метод <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>. В следующем примере показано, как вызвать <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> для `itemNameTextBox`:

 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]

> [!NOTE]
> Эту же методику можно использовать для свойств других элементов управления, но помните, что большинство других свойств имеют <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> значение по умолчанию <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. Дополнительные сведения см. на странице свойств <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.

> [!NOTE]
> Свойство <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> относится к обновлениям источника, поэтому оно применимо только для привязок <xref:System.Windows.Data.BindingMode.TwoWay> или <xref:System.Windows.Data.BindingMode.OneWayToSource>. Для работы привязок <xref:System.Windows.Data.BindingMode.TwoWay> и <xref:System.Windows.Data.BindingMode.OneWayToSource> исходный объект должен предоставлять уведомления об изменении свойств. Можно изучить примеры, приведенные в этом разделе, для получения дополнительной информации. Кроме того, см. раздел [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md).

## <a name="see-also"></a>См. также

- [Разделы практического руководства](data-binding-how-to-topics.md)
