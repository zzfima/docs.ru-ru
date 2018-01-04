---
title: "Общие сведения о системе команд"
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
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: "35"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1af7d9dba986c3775dc3625d1e7a874f6b26c97d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="commanding-overview"></a>Общие сведения о системе команд
Система команд <a name="introduction"></a> представляет собой механизм ввода в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], обеспечивающий обработку входных данных на более семантическом уровне по сравнению с вводом устройств. Примеры команд включают операции **Копировать**, **Вырезать** и **Вставить**, доступные во многих приложениях.  
  
 В этом обзоре определяется понятие команд в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], классы, входящие в модель команд, и способы использования и создания команд в приложениях.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Что представляют собой команды?](#commands_at_10000_feet)  
  
-   [Пример простой команды в WPF](#simple_command)  
  
-   [Четыре основных понятия в системе команд WPF](#Four_main_Concepts)  
  
-   [Библиотека команд](#Command_Library)  
  
-   [Создание настраиваемых команд](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>Что представляют собой команды?  
 Команды применяются в различных целях. Первой задачей является отделение семантики и объекта, вызывающего команду, от логики, которая выполняет команду. Это позволяет нескольким и разнородным источникам вызывать одну логику команды, а также настраивать логику команды для различных целевых объектов. Например, операции редактирования **Копировать**, **Вырезать** и **Вставить**, которые встречаются во многих приложениях, могут вызываться с помощью разных действий пользователя, если они реализованы с помощью команд. Приложение может поддерживать вырезание выделенных объектов или текста путем нажатия определенной кнопки, выбора пункта меню или сочетания клавиш, например CTRL+X. С помощью команд можно привязать разные типы действий пользователя к одной логике.  
  
 Другой целью применения команд является указание того, доступно ли действие. Продолжая пример вырезания объекта или текста, действие имеет смысл, только если что-либо выбрано. Если пользователь попытается вырезать объект или текст, не выбрав его, ничего не произойдет. Чтобы уведомить пользователя об этом, во многих приложениях кнопки и пункты меню отключаются, чтобы пользователь понял, что это действие выполнить невозможно. Можно указать команды, возможна ли действие путем реализации <xref:System.Windows.Input.ICommand.CanExecute%2A> метод. Кнопки можно подписаться на <xref:System.Windows.Input.ICommand.CanExecuteChanged> событий и отключен, если <xref:System.Windows.Input.ICommand.CanExecute%2A> возвращает `false` или включать, если <xref:System.Windows.Input.ICommand.CanExecute%2A> возвращает `true`.  
  
 Семантика команды может быть согласованной в разных приложениях и классах, однако логика действия зависит от конкретного объекта, к которому она применяется. Сочетание клавиш CTRL+X вызывает команду **Вырезать** в классах текста, классах изображений и веб-браузерах, однако фактическая логика для выполнения операции **Вырезать** определяется приложением, которое ее выполняет. Объект <xref:System.Windows.Input.RoutedCommand> позволяет клиентам реализовать логику. Текстовый объект может вырезать выделенный текст в буфер обмена, а объект изображения может вырезать выбранное изображение. Когда приложение обрабатывает <xref:System.Windows.Input.CommandManager.Executed> событие, он имеет доступ к целевому команды и предпринять соответствующие действия в зависимости от типа целевого объекта.  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>Пример простой команды в WPF  
 Самый простой способ использования команды в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] заключается в использовании предопределенного <xref:System.Windows.Input.RoutedCommand> из одного из классов библиотеки команд; используйте элемент управления с собственной поддержкой обработки команд; и использование элемента управления с собственной поддержкой вызова команд.  <xref:System.Windows.Input.ApplicationCommands.Paste%2A> Команда является одной из предопределенных команд в <xref:System.Windows.Input.ApplicationCommands> класса.  <xref:System.Windows.Controls.TextBox> Управления содержит встроенную логику для обработки <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды.  И <xref:System.Windows.Controls.MenuItem> класс имеет собственную поддержку для вызова команд.  
  
 В следующем примере показано, как настроить <xref:System.Windows.Controls.MenuItem> так, что при его выборе вызывается <xref:System.Windows.Input.ApplicationCommands.Paste%2A> на <xref:System.Windows.Controls.TextBox>, исходя из <xref:System.Windows.Controls.TextBox> фокус клавиатуры.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>Четыре основных понятия в системе команд WPF  
 Модель перенаправляемых команд [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно разбить на четыре основных понятия: команда, источник команды, цель команды и привязка команды.  
  
-   *Команда* — это выполняемое действие.  
  
-   *Источник команды* — это объект, который вызывает команду.  
  
-   *Цель команды* — это объект, для которого выполняется команда.  
  
-   *Привязка команды* — это объект, сопоставляющий логику команды с командой.  
  
 В предыдущем примере <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команду, <xref:System.Windows.Controls.MenuItem> — источник команды <xref:System.Windows.Controls.TextBox> — цель команды и привязка команды предоставляется свойством <xref:System.Windows.Controls.TextBox> элемента управления.  Стоит отметить, что это не всегда так, <xref:System.Windows.Input.CommandBinding> предоставляется элементом управления, который является целевой класс команд.  Довольно часто <xref:System.Windows.Input.CommandBinding> должны создаваться разработчиком приложения, или <xref:System.Windows.Input.CommandBinding> могут быть присоединены к предку целевого объекта команды.  
  
<a name="Commands"></a>   
### <a name="commands"></a>Команды  
 Команды в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] создаются путем реализации <xref:System.Windows.Input.ICommand> интерфейса.  <xref:System.Windows.Input.ICommand>предоставляет два метода, <xref:System.Windows.Input.ICommand.Execute%2A>, и <xref:System.Windows.Input.ICommand.CanExecute%2A>и для события <xref:System.Windows.Input.ICommand.CanExecuteChanged>. <xref:System.Windows.Input.ICommand.Execute%2A>выполняет действия, связанные с командой. <xref:System.Windows.Input.ICommand.CanExecute%2A>Определяет, может ли команда выполняться на текущей цели команды. <xref:System.Windows.Input.ICommand.CanExecuteChanged>возникает, если диспетчер команд, команд, обнаруживает изменения в источнике команды, может сделать недействительным команду, которая возникает, но еще не выполнена с помощью привязки команды.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Реализация <xref:System.Windows.Input.ICommand> — <xref:System.Windows.Input.RoutedCommand> класса и рассматривается в этом обзоре.  
  
 Основными источниками входных данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются мышь, клавиатура, рукописный ввод и перенаправленные команды.  Использовать входные данные аппаратно ориентированном <xref:System.Windows.RoutedEvent> уведомление объектов на странице приложения произошедшего события ввода.  Объект <xref:System.Windows.Input.RoutedCommand> ничем не отличается.  <xref:System.Windows.Input.RoutedCommand.Execute%2A> И <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> методы <xref:System.Windows.Input.RoutedCommand> не содержат логику приложения для команды, но вместо вызовет этот туннель перенаправленные события и растут по дереву элементов, пока они обнаружить объект с <xref:System.Windows.Input.CommandBinding>.  <xref:System.Windows.Input.CommandBinding> Содержит обработчики для этих событий, а также обработчики, предназначенные для выполнения команды.  Дополнительные сведения о маршрутизации событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.RoutedCommand.Execute%2A> Метод <xref:System.Windows.Input.RoutedCommand> вызывает <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed> событий для целевого объекта команды.  <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> Метод <xref:System.Windows.Input.RoutedCommand> вызывает <xref:System.Windows.Input.CommandManager.CanExecute> и <xref:System.Windows.Input.CommandManager.PreviewCanExecute> событий для целевого объекта команды.  Эти события проходят и поднимаются по дереву элементов, пока они обнаружить объект с <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет набор общих команд перенаправленное распределены между несколькими классами: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, и <xref:System.Windows.Documents.EditingCommands>.  Эти классы состоят только из <xref:System.Windows.Input.RoutedCommand> объекты и не логика реализации команды.  За реализацию логики команды отвечает объект, для которого выполняется команда.  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>Источники команд  
 Источник команды — это объект, который вызывает команду.  Примерами источников команды являются <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button>, и <xref:System.Windows.Input.KeyGesture>.  
  
 Источники команд в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обычно реализуют <xref:System.Windows.Input.ICommandSource> интерфейса.  
  
 <xref:System.Windows.Input.ICommandSource>предоставляет три свойства: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, и <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A>является команда, которая выполняется при вызове источника команды.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>— Это объект, на котором выполняется команда.  Следует отметить, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> свойство <xref:System.Windows.Input.ICommandSource> применимо, только когда <xref:System.Windows.Input.ICommand> — <xref:System.Windows.Input.RoutedCommand>.  Если <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> устанавливается на <xref:System.Windows.Input.ICommandSource> и соответствующей команды не <xref:System.Windows.Input.RoutedCommand>, целевой объект команды учитывается. Если <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> не задано, элемент с фокусом клавиатуры будет целевой объект команды.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>команда реализует тип пользовательских данных, используется для передачи данных в обработчик.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Классы, реализующие <xref:System.Windows.Input.ICommandSource> , <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink>, и <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, и <xref:System.Windows.Documents.Hyperlink> вызова команды при щелчке и <xref:System.Windows.Input.InputBinding> вызывает команду при <xref:System.Windows.Input.InputGesture> связанных с она выполняется.  
  
 В следующем примере показано, как использовать <xref:System.Windows.Controls.MenuItem> в <xref:System.Windows.Controls.ContextMenu> в качестве источника команды для <xref:System.Windows.Input.ApplicationCommands.Properties%2A> команды.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Как правило, источник команды будет осуществлять прослушивание <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> событий.  Это событие сообщает источнику команды о том, что возможность выполнения команды для текущего целевого объекта команды может быть изменена.  Источник команды может запрашивать текущее состояние <xref:System.Windows.Input.RoutedCommand> с помощью <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> метод.  Источник команды может затем отключаться, если не удается выполнить команду.  Примером этого является <xref:System.Windows.Controls.MenuItem> серым цветом когда невозможно выполнить команду.  
  
 <xref:System.Windows.Input.InputGesture> Можно использовать в качестве источника команды.  Два типа входных жестов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , <xref:System.Windows.Input.KeyGesture> и <xref:System.Windows.Input.MouseGesture>.  Можно представить <xref:System.Windows.Input.KeyGesture> как сочетания клавиш, например CTRL + C.  Объект <xref:System.Windows.Input.KeyGesture> состоит из <xref:System.Windows.Input.Key> и набор <xref:System.Windows.Input.ModifierKeys>.  Объект <xref:System.Windows.Input.MouseGesture> состоит из <xref:System.Windows.Input.MouseAction> и необязательный набор <xref:System.Windows.Input.ModifierKeys>.  
  
 Чтобы <xref:System.Windows.Input.InputGesture> в качестве источника команды, она должна быть связана с помощью команды. Это можно настроить несколькими способами.  Один способ — использовать <xref:System.Windows.Input.InputBinding>.  
  
 В следующем примере показано, как создать <xref:System.Windows.Input.KeyBinding> между <xref:System.Windows.Input.KeyGesture> и <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Другой способ связать <xref:System.Windows.Input.InputGesture> для <xref:System.Windows.Input.RoutedCommand> заключается в добавлении <xref:System.Windows.Input.InputGesture> для <xref:System.Windows.Input.InputGestureCollection> на <xref:System.Windows.Input.RoutedCommand>.  
  
 Следующий пример демонстрирует добавление <xref:System.Windows.Input.KeyGesture> для <xref:System.Windows.Input.InputGestureCollection> из <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 Объект <xref:System.Windows.Input.CommandBinding> связывает команду с обработчиками событий, которые реализуют команду.  
  
 <xref:System.Windows.Input.CommandBinding> Класс содержит <xref:System.Windows.Input.CommandBinding.Command%2A> свойство, и <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>, и <xref:System.Windows.Input.CommandBinding.CanExecute> события.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A>команда, <xref:System.Windows.Input.CommandBinding> , связанного с.  Обработчики событий, которые привязываются к <xref:System.Windows.Input.CommandBinding.PreviewExecuted> и <xref:System.Windows.Input.CommandBinding.Executed> события реализовывать логику команды.  Обработчики событий, присоединенные к <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> и <xref:System.Windows.Input.CommandBinding.CanExecute> события определяют, если данная команда выполняться на текущей цели команды.  
  
 В следующем примере показано, как создать <xref:System.Windows.Input.CommandBinding> в корне <xref:System.Windows.Window> приложения.  <xref:System.Windows.Input.CommandBinding> Связывает <xref:System.Windows.Input.ApplicationCommands.Open%2A> с <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandBinding.CanExecute> обработчиков.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Далее, <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> создаются.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> Открывает <xref:System.Windows.MessageBox> котором отображаются сведения о том, выполнена команда.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> Задает <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> свойства `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Объект <xref:System.Windows.Input.CommandBinding> присоединяется к конкретному объекту, например корневой <xref:System.Windows.Window> приложения или элемента управления.  Объект, <xref:System.Windows.Input.CommandBinding> присоединяется к определяет область привязки.  Например <xref:System.Windows.Input.CommandBinding> присоединенного к предку команды целевой можно осуществлять путем <xref:System.Windows.Input.CommandBinding.Executed> событий, но <xref:System.Windows.Input.CommandBinding> присоединенного потомку команды не могут использоваться целевой.  Это напрямую связано способ <xref:System.Windows.RoutedEvent> туннели и может передаваться из объекта, который вызывает событие.  
  
 В некоторых случаях <xref:System.Windows.Input.CommandBinding> присоединяется к целевой объект команды, такие как с <xref:System.Windows.Controls.TextBox> класса и <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, и <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команд. Довольно часто менее, он является более удобным для присоединения <xref:System.Windows.Input.CommandBinding> к предку целевого объекта команды, например main <xref:System.Windows.Window> или объекта приложения, особенно в том случае, если же <xref:System.Windows.Input.CommandBinding> может использоваться для нескольких целей команды.  Это необходимо учитывать при создании инфраструктуры системы команд.  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>Цель команды  
 Целью команды является элемент, для которого выполняется команда.  По отношении к <xref:System.Windows.Input.RoutedCommand>, цель команды — элемент, расположенный какие маршрутизацию <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandManager.CanExecute> запускает.  Как было отмечено ранее, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> свойство <xref:System.Windows.Input.ICommandSource> применимо, только когда <xref:System.Windows.Input.ICommand> — <xref:System.Windows.Input.RoutedCommand>.  Если <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> устанавливается на <xref:System.Windows.Input.ICommandSource> и соответствующей команды не <xref:System.Windows.Input.RoutedCommand>, целевой объект команды учитывается.  
  
 Источник команды может явно задавать целевой объект команды.  Если цель команды не определена, в качестве целевого объекта будет использоваться элемент с фокусом клавиатуры.  Одно из преимуществ использования элемента с фокусом клавиатуры в качестве цели команды является то, что это позволяет разработчику приложения использовать один источник команды для вызова команд для нескольких целей без необходимости отслеживания целевого объекта команды.  Например если <xref:System.Windows.Controls.MenuItem> вызывает **вставить** команду в приложении, которое имеет <xref:System.Windows.Controls.TextBox> управления и <xref:System.Windows.Controls.PasswordBox> элемент управления, целевой объект может быть либо <xref:System.Windows.Controls.TextBox> или <xref:System.Windows.Controls.PasswordBox> в зависимости от того, что элемент управления имеет фокус клавиатуры.  
  
 В следующем примере показано явное задание цели команды в разметке и в коде программной части.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>Диспетчер команд CommandManager  
 <xref:System.Windows.Input.CommandManager> Представлен ряд команд, связанных с ними функциях.  Она предоставляет набор статических методов для добавления и удаления <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute>, и <xref:System.Windows.Input.CommandManager.CanExecute> обработчики событий в и из конкретного элемента.  Она предоставляет средства для регистрации <xref:System.Windows.Input.CommandBinding> и <xref:System.Windows.Input.InputBinding> объектов определенного класса.  <xref:System.Windows.Input.CommandManager> Также предоставляет средства, с помощью <xref:System.Windows.Input.CommandManager.RequerySuggested> событий для уведомления команды о необходимости вызова <xref:System.Windows.Input.ICommand.CanExecuteChanged> событий.  
  
 <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> Заставляет метод <xref:System.Windows.Input.CommandManager> для вызова <xref:System.Windows.Input.CommandManager.RequerySuggested> событий.  Это полезно для условий, которые следует включить или отключить команду, но это не условия, которые <xref:System.Windows.Input.CommandManager> известно.  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>Библиотека команд  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] предоставляет набор стандартных команд.  Библиотека команд включает следующие классы: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>и <xref:System.Windows.Input.ComponentCommands>.  Эти классы предоставляют команд, таких как <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> и <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, и <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Многие из этих команд содержат набор привязок ввода по умолчанию.  Например, если вы задаете обработку приложением команды копирования, вы автоматически получаете привязку CTRL+C. Кроме того, вы получаете привязки для других устройств ввода, таких как ввод с помощью пера и голосовых данных [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)].  
  
 При ссылке на команды в различных библиотеках команд с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], обычно можно опустить имя класса библиотеки, который предоставляет статическое свойство команды. Как правило, имена команд задаются однозначно в виде строк и существуют типы владельца, которые обеспечивает логическую группировку команд, однако они не являются необходимыми для устранения неоднозначности. Например, можно указать `Command="Cut"` вместо более подробной команды `Command="ApplicationCommands.Cut"`. Это удобный механизм встроен в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обработчик команд (точнее, это поведение преобразователя типа <xref:System.Windows.Input.ICommand>, который [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] процессора ссылки во время загрузки).  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>Создание настраиваемых команд  
 Если команды в классах библиотеки команд не соответствуют вашим потребностям, вы можете создать собственные команды.  Настраиваемые команды можно создать двумя способами.  Первый — для запуска с нуля и реализовать <xref:System.Windows.Input.ICommand> интерфейса.  Другим способом, а также наиболее распространенный подход — создание <xref:System.Windows.Input.RoutedCommand> или <xref:System.Windows.Input.RoutedUICommand>.  
  
 Пример создания пользовательской <xref:System.Windows.Input.RoutedCommand>, в разделе [создать пользовательский образец RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Реализация ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [Практическое руководство. Добавление команды в объект MenuItem](http://msdn.microsoft.com/en-us/013d68a0-5373-4a68-bd91-5de574307370)  
 [Создание примера настраиваемой команды RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980)
