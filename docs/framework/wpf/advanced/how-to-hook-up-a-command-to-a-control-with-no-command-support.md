---
title: "Практическое руководство. Подключение команды к элементу управления, не поддерживающему команды | Microsoft Docs"
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
  - "классы, Control, присоединение RoutedCommand"
  - "классы, RoutedCommand, присоединение к Control"
  - "Control - класс, присоединение RoutedCommand"
  - "RoutedCommand - класс, присоединение к Control"
ms.assetid: dad08f64-700b-46fb-ad3f-fbfee95f0dfe
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Практическое руководство. Подключение команды к элементу управления, не поддерживающему команды
В следующем примере показано, как подключить команду <xref:System.Windows.Input.RoutedCommand> к элементу управления <xref:System.Windows.Controls.Control>, в котором отсутствует встроенная поддержка команд.  Полный пример, в котором команды присоединяются к нескольким источникам, см. в разделе [Пример создания пользовательской команды RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет библиотеку общих команд, которые регулярно используются при программировании приложений.  Классы, составляющие библиотеку команд: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands> и <xref:System.Windows.Documents.EditingCommands>.  
  
 Статические объекты <xref:System.Windows.Input.RoutedCommand>, составляющие эти классы, не предоставляют логику команд.  Логика команд связывается с командой с помощью привязки <xref:System.Windows.Input.CommandBinding>.  Во многих элементах управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] есть встроенная поддержка некоторых команд из библиотеки команд.  Например, элемент управления <xref:System.Windows.Controls.TextBox> поддерживает многие команды редактирования приложения, такие как <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A> и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Разработчику приложения не нужно предпринимать специальных действий для обеспечения совместимости этих команд с этими элементами управления.  Если при выполнении команды элемент <xref:System.Windows.Controls.TextBox> является целью команды, он будет обрабатывать команду с помощью привязки <xref:System.Windows.Input.CommandBinding>, встроенной в элемент управления.  
  
 Ниже показано, как использовать элемент управления <xref:System.Windows.Controls.Button> в качестве источника команды для команды <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  Создается привязка <xref:System.Windows.Input.CommandBinding>, которая связывает указанные обработчики событий <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> с командой <xref:System.Windows.Input.RoutedCommand>.  
  
 Сначала создается источник команды.  Элемент <xref:System.Windows.Controls.Button> используется в качестве источника команды.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 Далее создаются обработчики <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  Обработчик <xref:System.Windows.Input.ExecutedRoutedEventHandler> просто открывает поле <xref:System.Windows.MessageBox>, тем самым сообщая, что команда выполнена.  Обработчик <xref:System.Windows.Input.CanExecuteRoutedEventHandler> задает свойству <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> значение `true`.  Обычно, обработчик событий CanExecute выполняет более надежные проверки для определения возможности выполнения команды для текущей цели команды.  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 Наконец, привязка <xref:System.Windows.Input.CommandBinding> создается в корневом окне <xref:System.Windows.Window> приложения, которое связывает обработчик маршрутизируемых событий с командой <xref:System.Windows.Input.ApplicationCommands.Open%2A>.  
  
 [!code-xml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## См. также  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Подключение команды к элементу управления с поддержкой команд](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)