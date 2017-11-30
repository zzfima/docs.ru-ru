---
title: "Практическое руководство. Подключение команды к элементу управления, не поддерживающему команды"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Control class [WPF], attaching a RoutedCommand
- classes [WPF], Control [WPF], attaching a RoutedCommand
- RoutedCommand class [WPF], attaching to a Control
- classes [WPF], RoutedCommand [WPF], attaching to a Control
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6f38a6f900ee2b253708da4b63bdc2f474fa3ab1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a>Практическое руководство. Подключение команды к элементу управления, не поддерживающему команды
Следующий пример показывает, как подключить <xref:System.Windows.Input.RoutedCommand> для <xref:System.Windows.Controls.Control> которого отсутствует встроенная поддержка команды.  Полный пример подключения команд к нескольким источникам см. в примере [Создание примера настраиваемой команды RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет библиотеку стандартных команд, с которыми регулярно работают при программировании приложений.  Классы, составляющие библиотеку команд являются: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, и <xref:System.Windows.Documents.EditingCommands>.  
  
 Статический <xref:System.Windows.Input.RoutedCommand> объекты, составляющие эти классы не предоставляют логику команд.  Логика команды связан с командой <xref:System.Windows.Input.CommandBinding>.  Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] есть встроенная поддержка некоторых команд из библиотеки команд.  <xref:System.Windows.Controls.TextBox>, например, такие как поддерживает многие команды редактирования приложения <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Разработчику приложения не нужно выполнять никаких особых действий, чтобы эти команды заработали с этими элементами управления.  Если <xref:System.Windows.Controls.TextBox> является целевой объект команды при выполнении команды, он будет обрабатывать команду с помощью <xref:System.Windows.Input.CommandBinding> встраивается в элементе управления.  
  
 В следующем примере показано использование <xref:System.Windows.Controls.Button> как источника команды для <xref:System.Windows.Input.ApplicationCommands.Open%2A> команды.  Объект <xref:System.Windows.Input.CommandBinding> создается, связывает указанный <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> с <xref:System.Windows.Input.RoutedCommand>.  
  
 Во-первых создается источника команды.  Объект <xref:System.Windows.Controls.Button> используется в качестве источника команды.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Далее, <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> создаются.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> Просто открывает <xref:System.Windows.MessageBox> для обозначения того, что выполнена команда.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> Задает <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> свойства `true`.  Как правило, оно может выполнять обработчик выполнит более надежными проверяет, если выполнить команды на текущей цели команды.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Наконец <xref:System.Windows.Input.CommandBinding> создается в корневом каталоге <xref:System.Windows.Window> приложения, которое связывает обработчик маршрутизируемых событий для <xref:System.Windows.Input.ApplicationCommands.Open%2A> команды.  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Подключение команды к элементу управления с поддержкой команд](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
