---
title: "Практическое руководство. Включение команды | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CommandBinding"
  - "управление"
ms.assetid: d8016266-58d9-48f7-8298-a86b7ed49fbd
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Практическое руководство. Включение команды
В следующем примере демонстрируется использование команд в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  В примере показано, как связать команду <xref:System.Windows.Input.RoutedCommand> с элементом <xref:System.Windows.Controls.Button>, создать привязку <xref:System.Windows.Input.CommandBinding> и обработчики событий, в которых реализована <xref:System.Windows.Input.RoutedCommand>.  Дополнительные сведения о работе с командами см. в разделе [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Пример  
 В первой части кода создается [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)], состоящий из кнопки <xref:System.Windows.Controls.Button> и панели <xref:System.Windows.Controls.StackPanel>, и создается привязка <xref:System.Windows.Input.CommandBinding>, связывающая обработчик команды с <xref:System.Windows.Input.RoutedCommand>.  
  
 Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> элемента <xref:System.Windows.Controls.Button> связано с командой <xref:System.Windows.Input.ApplicationCommands.Close%2A>.  
  
 Привязка <xref:System.Windows.Input.CommandBinding> добавляется в коллекцию <xref:System.Windows.Input.CommandBindingCollection> корневого окна <xref:System.Windows.Window>.  Обработчики событий <xref:System.Windows.Input.CommandBinding.Executed> и <xref:System.Windows.Input.CommandBinding.CanExecute> присоединены к этой привязке и связаны с командой <xref:System.Windows.Input.ApplicationCommands.Close%2A>.  
  
 При отсутствии привязки <xref:System.Windows.Input.CommandBinding> отсутствует логика команды, есть только механизм для вызова команды.  При нажатии кнопки <xref:System.Windows.Controls.Button> вызывается событие <xref:System.Windows.RoutedEvent> <xref:System.Windows.Input.CommandManager.PreviewExecuted> для цели команды, за которым следует событие <xref:System.Windows.RoutedEvent> <xref:System.Windows.Input.CommandManager.Executed>.  Эти события проходят по дереву элементов в поисках привязки <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.  Стоит отметить, что поскольку событие <xref:System.Windows.RoutedEvent> проходит дерево элементов и передается вверх по иерархии объектов, необходимо соблюдать осторожность при выборе места установки привязки <xref:System.Windows.Input.CommandBinding>.  Если привязка <xref:System.Windows.Input.CommandBinding> относится к тому же уровню, что и цель команды или другой узел, который не расположен на маршруте события <xref:System.Windows.RoutedEvent>, привязка <xref:System.Windows.Input.CommandBinding> не осуществляется.  
  
 [!code-xml[EnableCloseCommand#CloseCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml#closecommandbinding)]  
  
 [!code-csharp[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandbindingcodebehind)]
 [!code-vb[EnableCloseCommand#CloseCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandbindingcodebehind)]  
  
 В следующей части кода реализуются обработчики событий <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 Обработчик <xref:System.Windows.Input.CommandManager.Executed> вызывает метод закрытия открытых файлов.  Обработчик <xref:System.Windows.Input.CommandBinding.CanExecute> вызывает метод для определения того, является ли файл открытым.  Если файл открыт, для метода <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> устанавливается значение `true`; в противном случае ему присваивается значение `false`.  
  
 [!code-csharp[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnableCloseCommand/CSharp/Window1.xaml.cs#closecommandhandler)]
 [!code-vb[EnableCloseCommand#CloseCommandHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnableCloseCommand/VisualBasic/Window1.xaml.vb#closecommandhandler)]  
  
## См. также  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)