---
title: "Практическое руководство. Создание маршрутизируемой команды RoutedCommand | Microsoft Docs"
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
  - "классы, RoutedCommand, создание"
  - "создание, RoutedCommand - класс"
  - "RoutedCommand - класс, создание"
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# Практическое руководство. Создание маршрутизируемой команды RoutedCommand
В этом примере показано, как создать пользовательскую маршрутизируемую команду <xref:System.Windows.Input.RoutedCommand> и способ реализации пользовательской команды путем создания <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и присоединения их к <xref:System.Windows.Input.CommandBinding>.  Дополнительные сведения о работе с командами см. в разделе [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
## Пример  
 Первым шагом для создания маршрутизируемой команды <xref:System.Windows.Input.RoutedCommand> является определение команды и создание ее экземпляра.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 Чтобы использовать команды в приложении, не нужно создавать обработчики событий, которые определяют эти команды.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 Далее создается <xref:System.Windows.Input.CommandBinding>, который связывает команду с обработчиками событий.  Создается <xref:System.Windows.Input.CommandBinding> на определенном объекте.  Этот объект определяет область <xref:System.Windows.Input.CommandBinding> в дереве элементов  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 Последним шагом является вызов команды.  Одним из способов вызова команды является связывание ее с <xref:System.Windows.Input.ICommandSource>, например <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 При нажатии кнопки вызывается метод <xref:System.Windows.Input.RoutedCommand.Execute%2A> для пользовательской маршрутизируемой команде <xref:System.Windows.Input.RoutedCommand>.  <xref:System.Windows.Input.RoutedCommand> создает маршрутизируемые события <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed>.  Эти события проходят по дереву элементов в поисках <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.  Если найден <xref:System.Windows.Input.CommandBinding>, то вызывается обработчик <xref:System.Windows.Input.ExecutedRoutedEventHandler>, связанный с <xref:System.Windows.Input.CommandBinding>.  
  
## См. также  
 <xref:System.Windows.Input.RoutedCommand>   
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)