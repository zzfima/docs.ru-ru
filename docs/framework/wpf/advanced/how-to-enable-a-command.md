---
title: Практическое руководство. Включение команды
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CommandBindings [WPF]
- commanding [WPF]
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
ms.openlocfilehash: 81ae2e46c4fdd8b46e2b72b9a1430437ebfe97b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enable-a-command"></a>Практическое руководство. Включение команды
Следующий пример демонстрирует использование команд в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В примере показано связывание <xref:System.Windows.Input.RoutedCommand> для <xref:System.Windows.Controls.Button>, создайте <xref:System.Windows.Input.CommandBinding>и создания обработчиков событий, которые реализуют <xref:System.Windows.Input.RoutedCommand>.  Дополнительные сведения о командах см. в разделе [Общие сведения о работе с командами](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## <a name="example"></a>Пример  
 В первой части кода создает [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], который состоит из <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.StackPanel>и создает <xref:System.Windows.Input.CommandBinding> , связывающая обработчик команды с <xref:System.Windows.Input.RoutedCommand>.  
  
 <xref:System.Windows.Input.ICommandSource.Command%2A> Свойство <xref:System.Windows.Controls.Button> связан с <xref:System.Windows.Input.ApplicationCommands.Close%2A> команды.  
  
 <xref:System.Windows.Input.CommandBinding> Добавляется <xref:System.Windows.Input.CommandBindingCollection> корневого <xref:System.Windows.Window>. <xref:System.Windows.Input.CommandBinding.Executed> И <xref:System.Windows.Input.CommandBinding.CanExecute> присоединенные к этой привязке обработчиков событий и связанные с <xref:System.Windows.Input.ApplicationCommands.Close%2A> команды.  
  
 Без <xref:System.Windows.Input.CommandBinding> отсутствует логика команды, механизм для вызова команды.  Когда <xref:System.Windows.Controls.Button> нажатии <xref:System.Windows.Input.CommandManager.PreviewExecuted> <xref:System.Windows.RoutedEvent> возникает на целевой объект команды, за которым следует <xref:System.Windows.Input.CommandManager.Executed> <xref:System.Windows.RoutedEvent>.  Эти события проходят по дереву элементов, поиск <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.  Стоит отметить, что поскольку <xref:System.Windows.RoutedEvent> проходят и поднимаются по дереву элементов, следует соблюдать осторожность в where <xref:System.Windows.Input.CommandBinding> помещается.   Если <xref:System.Windows.Input.CommandBinding> на одноуровневым элементом целевой объект команды или другой узел, который не является в маршруте <xref:System.Windows.RoutedEvent>, <xref:System.Windows.Input.CommandBinding> не будет осуществляться.  
  
 [!code-xaml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 В следующей части кода реализуются <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandBinding.CanExecute> обработчики событий.  
  
 <xref:System.Windows.Input.CommandManager.Executed> Обработчик вызывает метод для закрытия открытого файла.  <xref:System.Windows.Input.CommandBinding.CanExecute> Обработчик вызывает метод, чтобы определить, открыт ли файл.  Если файл был открыт, <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> задано значение `true`; в противном случае оно равно `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)
