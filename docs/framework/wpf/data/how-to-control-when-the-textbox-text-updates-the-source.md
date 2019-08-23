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
ms.openlocfilehash: d1d624d7550a1135431b7fffc7450e3a510855a7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966451"
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>Практическое руководство. Управление обновлением источника из поля TextBox
В этом разделе описывается использование <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> свойства для управления временем обновления источника привязки. В разделе используется <xref:System.Windows.Controls.TextBox> элемент управления в качестве примера.  
  
## <a name="example"></a>Пример  
 Языковой элемент <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> свойство имеет <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>значение по умолчанию. Это означает, что приложение имеет объект <xref:System.Windows.Controls.TextBox> с привязкой <xref:System.Windows.Controls.TextBox>к данным.<xref:System.Windows.Controls.TextBox.Text%2A> , текст, введенный в, <xref:System.Windows.Controls.TextBox> не обновляет источник <xref:System.Windows.Controls.TextBox> до тех пор, пока фокус не будет утрачен (например, если щелкнуть вне <xref:System.Windows.Controls.TextBox>).  
  
 Если вы хотите, чтобы источник обновлялся по мере ввода, задайте <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> для <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>привязки значение. В следующем примере выделенные строки кода показывают, что `Text` свойства <xref:System.Windows.Controls.TextBox> и и привязаны к одному и <xref:System.Windows.Controls.TextBlock> тому же свойству источника. Свойству <xref:System.Windows.Controls.TextBox> привязки присвоено значение <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>  
  
 [!code-xaml[SimpleBinding#USTHowTo](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=33-39,41-42)]  
  
 В результате объект <xref:System.Windows.Controls.TextBlock> отображает тот же текст (так как источник изменяется) при вводе пользователем текста <xref:System.Windows.Controls.TextBox>в, как показано на следующем снимке экрана примера:  
  
 ![Снимок экрана, на котором показана простая привязка данных.](./media/how-to-control-when-the-textbox-text-updates-the-source/data-binding-simple-binding-sample.png)  
  
 Если у вас есть диалоговое окно или пользовательская форма, и вы хотите отложить обновления источника до тех пор, пока пользователь не закончит редактирование полей и не нажмет кнопку " <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> ОК", можно задать для <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>привязок значение, как показано в следующем примере:  
  
 [!code-xaml[UpdateSource#2](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Если <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> значение равно ,исходноезначениеизменяетсятолькотогда,когда<xref:System.Windows.Data.UpdateSourceTrigger.Explicit>приложение вызывает метод. В следующем примере показано, как вызвать <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> метод `itemNameTextBox`для:  
  
 [!code-csharp[UpdateSource#1](~/samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
> Эту же методику можно использовать для свойств других элементов управления, но помните, что большинство других свойств имеют <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>значение по умолчанию. Дополнительные сведения см. на <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> странице свойств.  
  
> [!NOTE]
> Свойство работает с обновлениями источника и, следовательно, относится только <xref:System.Windows.Data.BindingMode.TwoWay> к привязкам или <xref:System.Windows.Data.BindingMode.OneWayToSource>. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Чтобы привязки <xref:System.Windows.Data.BindingMode.OneWayToSource> и работали, исходный объект должен предоставлять уведомления об изменении свойств. <xref:System.Windows.Data.BindingMode.TwoWay> Можно изучить примеры, приведенные в этом разделе, для получения дополнительной информации. Кроме того, см. раздел [Реализация уведомления об изменении свойства](how-to-implement-property-change-notification.md).  
  
## <a name="see-also"></a>См. также

- [Разделы практического руководства](data-binding-how-to-topics.md)
