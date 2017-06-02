---
title: "Практическое руководство. Реализация ICommandSource | Microsoft Docs"
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
  - "ICommandSource - интерфейсы, реализация"
  - "интерфейсы, ICommandSource, реализация"
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Практическое руководство. Реализация ICommandSource
В этом примере демонстрируется создание источника команды путем реализации <xref:System.Windows.Input.ICommandSource>.  Источник команды представляет собой объект, который знает, как вызвать команду.  Интерфейс <xref:System.Windows.Input.ICommandSource> предоставляет три члена: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> и <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> − это команда, которая будет вызвана.  <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> — определенный пользователем тип данных, передаваемый из источника команды методу, обрабатывающему команду.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> — объект, над которым выполняется команда.  
  
 В этом примере создается класс, который является базовым классом для элемента управления <xref:System.Windows.Controls.Slider> и реализует <xref:System.Windows.Input.ICommandSource>.  
  
## Пример  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет несколько классов, которые реализуют <xref:System.Windows.Input.ICommandSource>, такие как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem> и <xref:System.Windows.Controls.ListBoxItem>.  Источник команды определяет, как вызывается команда.  <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.MenuItem> вызывают команду нажатием.  <xref:System.Windows.Controls.ListBoxItem> вызывает команду при выполнении на нем двойного щелчка.  Эти классы становятся источниками команды, только когда установлено их свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 В данном примере команда будет вызываться при перемещении ползунка, или, точнее, при изменении свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.  
  
 Ниже приведено определение класса.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Следующим шагом является реализация элементов <xref:System.Windows.Input.ICommandSource>.  В этом примере свойства реализуются как объекты <xref:System.Windows.DependencyProperty>.  Это позволяет свойствам использовать привязку к данным.  Дополнительные сведения о классе <xref:System.Windows.DependencyProperty> см. в разделе [Общие сведения о свойствах зависимости](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Дополнительные сведения о привязке данных см. в разделе [Общие сведения о связывании данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Здесь показано только свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Ниже показан код обратного вызова изменения <xref:System.Windows.DependencyProperty>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Следующим шагом является добавление и удаление команды, связанной с источником команды.  Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> не может быть просто перезаписано при добавлении новой команды, поскольку сначала необходимо удалить обработчики событий, связанные с предыдущей командой, если таковая была.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 Последним шагом является создание логики для обработчика <xref:System.Windows.Input.ICommand.CanExecuteChanged> и метода <xref:System.Windows.Input.ICommand.Execute%2A>.  
  
 Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> сообщает источнику команды о возможном изменении способности выполнения команды для текущей цели команды.  При получении этого события источник команды обычно вызывает метод <xref:System.Windows.Input.ICommand.CanExecute%2A> для команды.  Если выполнение команды для текущей цели команды невозможно, источник команды обычно отключает себя.  Если выполнение команды для текущей цели команды возможно, источник команды обычно включает себя.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 Последним шагом является метод <xref:System.Windows.Input.ICommand.Execute%2A>.  Если команда представляет собой <xref:System.Windows.Input.RoutedCommand>, вызывается метод <xref:System.Windows.Input.RoutedCommand.Execute%2A> у <xref:System.Windows.Input.RoutedCommand>; в противном случае вызывается метод <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## См. также  
 <xref:System.Windows.Input.ICommandSource>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.Input.RoutedCommand>   
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)