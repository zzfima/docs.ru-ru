---
title: Как выполнить Подключение команды к элементу управления без поддержки команд
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
ms.openlocfilehash: 5f963c871ed9b600586c32403a288eadd6e9daec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725380"
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Как выполнить Подключение команды к элементу управления без поддержки команд
В следующем примере показано, как подключить <xref:System.Windows.Input.RoutedCommand> к <xref:System.Windows.Controls.Control> без встроенной поддержки команды.  Полный пример подключения команд к нескольким источникам см. в примере [Создание примера настраиваемой команды RoutedCommand](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand).  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет библиотеку стандартных команд, с которыми регулярно работают при программировании приложений.  Классы, составляющие библиотеку команд : <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> и <xref:System.Windows.Documents.EditingCommands>.  
  
 Статические объекты <xref:System.Windows.Input.RoutedCommand>, формирующие эти классы, не поддерживают командную логику.  Логика команды связана с командой с <xref:System.Windows.Input.CommandBinding>.  Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют встроенную поддержку определенных команд в библиотеке команд.  <xref:System.Windows.Controls.TextBox>, например, поддерживает многие команды редактирования приложения, такие как <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Разработчику приложения не нужно выполнять никаких особых действий, чтобы эти команды заработали с этими элементами управления.  Если <xref:System.Windows.Controls.TextBox> является целевым объектом команды при выполнении команды, он будет обрабатывать команду с помощью класса <xref:System.Windows.Input.CommandBinding>, встроенного в элемент управления.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.Button> в качестве источника команды для команды <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  Создается класс <xref:System.Windows.Input.CommandBinding>, который связывает указанный <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> с <xref:System.Windows.Input.RoutedCommand>.  
  
 Сначала создается источник команды.  В качестве источника команды используется <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Затем создаются объекты <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> просто открывает <xref:System.Windows.MessageBox>, чтобы подтвердить выполнение команды.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> задает для свойства <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> значение `true`.  Как правило, обработчик CanExecute проводит более строгую проверку возможности выполнения команды с текущим целевым объектом команды.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Наконец, создается класс <xref:System.Windows.Input.CommandBinding> в корневом каталоге <xref:System.Windows.Window> приложения, который связывает обработчик перенаправленных событий с командой <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>См. также
- [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)
- [Подключение команды к элементу управления с поддержкой команд](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
