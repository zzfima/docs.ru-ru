---
title: "Общие сведения о системе команд | Microsoft Docs"
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
  - "классы, CommandBinding"
  - "библиотека команд"
  - "CommandBinding"
  - "управление"
  - "CommandManager"
  - "команды, определение"
  - "ICommandSource - интерфейсы"
  - "интерфейсы, ICommandSource"
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Общие сведения о системе команд
<a name="introduction"></a> Команды представляют собой механизм ввода в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], обеспечивающий обработку ввода на более семантическом уровне по сравнению с устройствами ввода.  Примерами команд являются операции **Копировать**, **Вырезать** и **Вставить**, доступные во многих приложениях.  
  
 В этом разделе представлены общие сведения о командах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], классах, входящих в состав модели команд, а также о порядке использования и создания команд в приложениях.  
  
 В этом разделе содержатся следующие подразделы.  
  
-   [Что представляют собой команды?](#commands_at_10000_feet)  
  
-   [Простой пример команды в WPF](#simple_command)  
  
-   [Четыре основных понятия в системе команд WPF](#Four_main_Concepts)  
  
-   [Библиотека команд](#Command_Library)  
  
-   [Создание пользовательских команд](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## Что представляют собой команды?  
 Команды применяются в различных целях.  Первой задачей является отделение семантики и объекта, вызывающего команду, от логики, которая выполняет команду.  Это позволяет вызывать для нескольких разнородных источников одну и ту же логику команды, а также настраивать логику команды для различных целевых объектов.  Например, операции редактирования **Копировать**, **Вырезать** и **Вставить**, которые поддерживаются во многих приложениях, можно вызывать посредством различных действий пользователя, если операции реализованы с помощью команд.  Приложение может поддерживать вырезание выделенных объектов или текста путем нажатия определенной кнопки, выбора пункта в меню или нажатия сочетания клавиш, например CTRL\+X.  С помощью команд можно привязать различные типы действий пользователя к одному набору логики.  
  
 Другой целью применения команд является указание на доступность действия.  Продолжая пример с вырезанием объекта или текста, отметим, что это действие имеет смысл только тогда, когда объект или текст выделены.  Если пользователь попытается выполнить вырезание, не выделив объект или текст, то ничего не должно происходить.  Чтобы указать пользователю на недоступность операции, во многих приложениях кнопки и пункты меню делаются недоступными, и пользователь знает, когда можно выполнить то или иное действие.  В команде можно реализовать метод <xref:System.Windows.Input.ICommand.CanExecute%2A>, чтобы указать на возможность выполнения действия.  Для кнопки можно оформить подписку на событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> и отключать кнопку, если <xref:System.Windows.Input.ICommand.CanExecute%2A> возвращает значение `false` или включать, если <xref:System.Windows.Input.ICommand.CanExecute%2A> возвращает значение `true`.  
  
 Семантика команды может быть одинаковой для различных приложений и классов, однако логика действия меняется в зависимости от конкретного объекта.  Сочетание клавиш CTRL\+X вызывает команду **Вырезать** в классах текста, классах изображения и браузерах. Однако фактическая логика выполнения операции **Вырезать** определяется приложением, которое выполняет операцию.  Класс <xref:System.Windows.Input.RoutedCommand> позволяет клиентам реализовать логику.  Текстовый объект может вырезать в буфер обмена выделенный текст, а объект изображения — выделенное изображение.  Во время обработки события <xref:System.Windows.Input.CommandManager.Executed> приложение получает доступ к назначению команды и может выполнять действие в зависимости от типа целевого объекта.  
  
<a name="simple_command"></a>   
## Простой пример команды в WPF  
 К самым простым способам использования команды в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно отнести применение предопределенного класса <xref:System.Windows.Input.RoutedCommand> одного из классов библиотеки команд; использование элемента управления с собственной поддержкой обработки команд; а также использование элемента управления с собственной поддержкой вызова команд.  Команда <xref:System.Windows.Input.ApplicationCommands.Paste%2A> представляет собой одну из предопределенных команд класса <xref:System.Windows.Input.ApplicationCommands>.  Элемент управления <xref:System.Windows.Controls.TextBox> содержит встроенную логику обработки команды <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  В классе <xref:System.Windows.Controls.MenuItem> реализована встроенная поддержка вызова команд.  
  
 В следующем примере описывается порядок настройки объекта <xref:System.Windows.Controls.MenuItem> таким образом, что при его выборе вызывается команда <xref:System.Windows.Input.ApplicationCommands.Paste%2A> для объекта <xref:System.Windows.Controls.TextBox> \(если в объекте <xref:System.Windows.Controls.TextBox> установлен фокус клавиатуры\).  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## Четыре основных понятия в системе команд WPF  
 В модели маршрутизации команд в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно выделить четыре основных понятия: команда, источник команды, цель команды и привязка команды.  
  
-   *Команда* — выполняемое действие.  
  
-   *Источник команды* — объект, которым вызывается команда.  
  
-   *Цель команды* — объект, для которого выполняется команда.  
  
-   *Привязка команды* — объект, используемый для сопоставления логики команды самой команде.  
  
 В предыдущем примере <xref:System.Windows.Input.ApplicationCommands.Paste%2A> — это команда, <xref:System.Windows.Controls.MenuItem> — источник команды, <xref:System.Windows.Controls.TextBox> — цель команды. Привязка команды предоставляется элементом управления <xref:System.Windows.Controls.TextBox>.  Необходимо отметить, что привязка <xref:System.Windows.Input.CommandBinding> не всегда предоставляется элементом управления, который принадлежит классу цели команды.  Довольно часто объект <xref:System.Windows.Input.CommandBinding> создается разработчиком приложения. Также объект <xref:System.Windows.Input.CommandBinding> может быть присоединен к предку цели команды.  
  
<a name="Commands"></a>   
### Команды  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] команды создаются путем реализации интерфейса <xref:System.Windows.Input.ICommand>.  Интерфейс <xref:System.Windows.Input.ICommand> предоставляет доступ к двум методам — <xref:System.Windows.Input.ICommand.Execute%2A> и <xref:System.Windows.Input.ICommand.CanExecute%2A>, а также событию <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  <xref:System.Windows.Input.ICommand.Execute%2A> выполняется действия, связанные с командой. <xref:System.Windows.Input.ICommand.CanExecute%2A> определяет, можно ли выполнить команду для текущего целевого объекта команды.  Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> вызывается, если диспетчер команд, в котором централизованно выполняются командные операции, обнаруживает в источнике команды изменения, которые могут сделать недействительной команду, вызванную, но еще не выполненную привязкой команды.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] реализация интерфейса <xref:System.Windows.Input.ICommand> принадлежит классу <xref:System.Windows.Input.RoutedCommand> и является основной темой данного раздела.  
  
 Основными источниками входных данных в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] являются мышь, клавиатура, рукописный ввод и перенаправленные команды.  При аппаратно\-ориентированном вводе уведомление объектов на странице приложения о возникновении события ввода осуществляется с помощью объекта <xref:System.Windows.RoutedEvent>.  То же относится и к объектам <xref:System.Windows.Input.RoutedCommand>.  Методы <xref:System.Windows.Input.RoutedCommand.Execute%2A> и <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> класса <xref:System.Windows.Input.RoutedCommand> не содержат логику приложения для команды. Вместо этого они используются для вызова перенаправленных событий, которые проходят и поднимаются по дереву до тех пор, пока не будет найден объект с привязкой <xref:System.Windows.Input.CommandBinding>.  В классе <xref:System.Windows.Input.CommandBinding> представлены обработчики для этих событий, а также обработчики, предназначенные для выполнения команды.  Дополнительные сведения о маршрутизации событий в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] см. в разделе [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Метод <xref:System.Windows.Input.RoutedCommand.Execute%2A> объекта <xref:System.Windows.Input.RoutedCommand> используется для вызова событий <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed> для цели команды.  Метод <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> объекта <xref:System.Windows.Input.RoutedCommand> используется для вызова событий <xref:System.Windows.Input.CommandManager.CanExecute> и <xref:System.Windows.Input.CommandManager.PreviewCanExecute> для цели команды.  Эти события проходят и поднимаются по дереву элементов до тех пор, пока не будет найден объект с привязкой <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.  
  
 В следующих классах [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представлен набор общих перенаправленных команд: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> и <xref:System.Windows.Documents.EditingCommands>.  Эти классы состоят только из объектов <xref:System.Windows.Input.RoutedCommand> и не включают в себя реализацию логики команды.  Реализация логики осуществляется в объекте, для которого выполняется команда.  
  
<a name="Command_Sources"></a>   
### Источники команд  
 Источником команды является объект, который вызывает команду.  Примерами источников команды являются объекты <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> и <xref:System.Windows.Input.KeyGesture>.  
  
 Источники команд в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] обычно реализуют интерфейс <xref:System.Windows.Input.ICommandSource>.  
  
 В интерфейсе <xref:System.Windows.Input.ICommandSource> предоставляются три свойства: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> и <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> — команда, которая выполняется при вызове источника команды.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> — объект, для которого выполняется команда.  Необходимо отметить, что в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойство <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> интерфейса <xref:System.Windows.Input.ICommandSource> применимо только в том случае, если интерфейс <xref:System.Windows.Input.ICommand> принадлежит классу <xref:System.Windows.Input.RoutedCommand>.  Если для свойства <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> установлено значение <xref:System.Windows.Input.ICommandSource>, а соответствующая команда не принадлежит классу <xref:System.Windows.Input.RoutedCommand>, цель команды игнорируется.  Если значение свойства <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> не задано, в качестве цели команды используется элемент, в котором установлен фокус клавиатуры.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> — тип данных, определяемый пользователем, который используется для передачи информации обработчикам, реализующим команду.  
  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представлены следующие классы, реализующие интерфейс <xref:System.Windows.Input.ICommandSource>: <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> и <xref:System.Windows.Input.InputBinding>.  При щелчке объектов <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> и <xref:System.Windows.Documents.Hyperlink> вызывается соответствующая команда. Объект <xref:System.Windows.Input.InputBinding> вызывает команду при выполнении связанного с ним объекта <xref:System.Windows.Input.InputGesture>.  
  
 В следующем примере описывается порядок использования объекта <xref:System.Windows.Controls.MenuItem> в <xref:System.Windows.Controls.ContextMenu> в качестве источника для команды <xref:System.Windows.Input.ApplicationCommands.Properties%2A>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Как правило, источник команды будет осуществлять прослушивание события <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>.  Это событие служит для оповещения источника команды о том, что изменена возможность выполнения команды для текущей цели команды.  Источник команды может запрашивать текущее состояние объекта <xref:System.Windows.Input.RoutedCommand> с помощью метода <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>.  Затем источник команды может отключить сам себя, если команда не может быть выполнена.  Примером этого является выделение объекта <xref:System.Windows.Controls.MenuItem> серым цветом, если команда не может быть выполнена.  
  
 Объект <xref:System.Windows.Input.InputGesture> может использоваться в качестве источника команды.  В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] существует два типа входных жестов: <xref:System.Windows.Input.KeyGesture> и <xref:System.Windows.Input.MouseGesture>.  Объект <xref:System.Windows.Input.KeyGesture> можно сравнить с сочетанием клавиш, например CTRL\+C.  Объект <xref:System.Windows.Input.KeyGesture> включает в себя объект <xref:System.Windows.Input.Key> и набор объектов <xref:System.Windows.Input.ModifierKeys>.  Объект <xref:System.Windows.Input.MouseGesture> включает в себя объект <xref:System.Windows.Input.MouseAction> и набор необязательных объектов <xref:System.Windows.Input.ModifierKeys>.  
  
 Для выполнения объекта <xref:System.Windows.Input.InputGesture> в качестве источника команды следует связать его с командой.  Для этого предусмотрено несколько способов.  Одним из способов является использование объекта <xref:System.Windows.Input.InputBinding>.  
  
 В следующем примере описывается порядок создания привязки <xref:System.Windows.Input.KeyBinding> между объектами <xref:System.Windows.Input.KeyGesture> и <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Другим способом связывания объектов <xref:System.Windows.Input.InputGesture> и <xref:System.Windows.Input.RoutedCommand> является добавление объекта <xref:System.Windows.Input.InputGesture> в коллекцию <xref:System.Windows.Input.InputGestureCollection> объекта <xref:System.Windows.Input.RoutedCommand>.  
  
 В следующем примере описывается порядок добавления объекта <xref:System.Windows.Input.KeyGesture> в коллекцию <xref:System.Windows.Input.InputGestureCollection> объекта <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### Класс CommandBinding  
 Объект <xref:System.Windows.Input.CommandBinding> предназначен для связывания команды с обработчиками событий, которые реализуют ее.  
  
 Класс <xref:System.Windows.Input.CommandBinding> содержит свойство <xref:System.Windows.Input.CommandBinding.Command%2A>, а также события <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed> <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> и <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 Свойство <xref:System.Windows.Input.CommandBinding.Command%2A> представляет собой команду, с которой связывается объект <xref:System.Windows.Input.CommandBinding>.  Логика команды реализуется с помощью обработчиков событий, которые присоединены к событиям <xref:System.Windows.Input.CommandBinding.PreviewExecuted> и <xref:System.Windows.Input.CommandBinding.Executed>.  Обработчики событий, присоединенные к событиям <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> и <xref:System.Windows.Input.CommandBinding.CanExecute>, определяют возможность выполнения команды для текущей цели команды.  
  
 В следующем примере описывается порядок создания привязки <xref:System.Windows.Input.CommandBinding> в корневом объекте <xref:System.Windows.Window> приложения.  Объект <xref:System.Windows.Input.CommandBinding> связывает команду <xref:System.Windows.Input.ApplicationCommands.Open%2A> с обработчиками событий <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 [!code-xml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Далее создаются обработчики событий <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  Обработчик <xref:System.Windows.Input.ExecutedRoutedEventHandler> открывает объект <xref:System.Windows.MessageBox>, в котором отображаются сведения о выполнении команды.  Обработчик <xref:System.Windows.Input.CanExecuteRoutedEventHandler> задает свойству <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> значение `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Объект <xref:System.Windows.Input.CommandBinding> присоединяется к определенному объекту, например корневому объекту <xref:System.Windows.Window> приложения или элементу управления.  Объект, к которому присоединен объект <xref:System.Windows.Input.CommandBinding>, определяет область привязки.  Например, объект <xref:System.Windows.Input.CommandBinding>, присоединенный к предку цели команды, доступен с помощью события <xref:System.Windows.Input.CommandBinding.Executed>. Однако объект <xref:System.Windows.Input.CommandBinding>, присоединенный к потомку цели команды, в этом случае недоступен.  Это напрямую связано с методами восходящей и нисходящей маршрутизации объекта <xref:System.Windows.RoutedEvent>, используемыми по отношению к объекту, который вызывает событие.  
  
 В некоторых случаях к цели команды присоединяется сам объект <xref:System.Windows.Input.CommandBinding>, как например в случае с классом <xref:System.Windows.Controls.TextBox> и командами <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> и <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  Однако во многих случаях рекомендуется присоединять объект <xref:System.Windows.Input.CommandBinding> к предку цели команды, например главному объекту <xref:System.Windows.Window> или объекту Application, особенно в тех случаях, когда один и тот же объект <xref:System.Windows.Input.CommandBinding> может использоваться для нескольких целей команды.  Эти решения принимаются на стадии разработки во время создания инфраструктуры команд.  
  
<a name="Commane_Target"></a>   
### Цель команды  
 Целью команды является элемент, для которого она выполняется.  В отношении <xref:System.Windows.Input.RoutedCommand> целью команды является элемент, с которого начинается маршрутизация событий <xref:System.Windows.Input.CommandManager.Executed> и <xref:System.Windows.Input.CommandManager.CanExecute>.  Как было отмечено ранее, в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] свойство <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> интерфейса <xref:System.Windows.Input.ICommandSource> применяется только в тех случаях, когда интерфейс <xref:System.Windows.Input.ICommand> принадлежит классу <xref:System.Windows.Input.RoutedCommand>.  Если для свойства <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> установлено значение <xref:System.Windows.Input.ICommandSource>, а соответствующая команда не принадлежит классу <xref:System.Windows.Input.RoutedCommand>, цель команды игнорируется.  
  
 Цель команды может быть явно задана в источнике команды.  Если цель команды не определена, в этом качестве используется элемент, в котором установлен фокус клавиатуры.  Одним из преимуществ использования в качестве цели команды элемента, в котором установлен фокус клавиатуры, является возможность использования одного источника команды для вызова команд для нескольких целей \(в этом случае не требуется отслеживать цель команды\).  Например, если объект <xref:System.Windows.Controls.MenuItem> вызывает команду **Вставить** в приложении, в котором содержатся элементы управления <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox>, в качестве цели могут выступать объекты <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.PasswordBox> \(в зависимости от того, в каком из них установлен фокус клавиатуры\).  
  
 В следующем примере описывается порядок явного определения цели команды в разметке и коде программной части.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### Класс CommandManager  
 В классе <xref:System.Windows.Input.CommandManager> представлен ряд связанных с командами функций.  В нем представлен набор статических методов для добавления и удаления обработчиков событий <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> и <xref:System.Windows.Input.CommandManager.CanExecute> для определенного элемента.  Также в нем представлены средства для регистрации объектов <xref:System.Windows.Input.CommandBinding> и <xref:System.Windows.Input.InputBinding> в определенном классе.  Также в классе <xref:System.Windows.Input.CommandManager> представлены средства, в которых используется событие <xref:System.Windows.Input.CommandManager.RequerySuggested> для уведомления команды о необходимости вызова события <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  
  
 Метод <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> используется для принудительного вызова объектом <xref:System.Windows.Input.CommandManager> события <xref:System.Windows.Input.CommandManager.RequerySuggested>.  Это используется в тех случаях, когда необходимо отключить или включить команду, если такие случаи не учитываются объектом <xref:System.Windows.Input.CommandManager>.  
  
<a name="Command_Library"></a>   
## Библиотека команд  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] представлен набор предопределенных команд.  Библиотека команд включает следующие классы: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> и <xref:System.Windows.Input.ComponentCommands>.  В этих классах представлены такие команды, как <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> и <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> и <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Большинство из этих команд включает в себя набор используемых по умолчанию привязок ввода.  Например, при обработке в приложении команды копирования автоматически используется привязка сочетания клавиш "CTRL\+C". Также можно получить привязки для других устройств ввода, например жестов пера [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] или голосовых команд.  
  
 При ссылке на команды в различных библиотеках команд с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] обычно можно опустить имя класса библиотеки классов, которое предоставляет статическое свойство команды.  Обычно имена команд задаются однозначно в виде строк. Собственные типы используются для логической группировки команд, но не являются обязательными для устранения неоднозначности.  Например, можно использовать сокращенную форму команды `Command="Cut"` вместо `Command="ApplicationCommands.Cut"`.  Этот удобный механизм встроен в обработчик команд [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \(более точно, это поведение преобразователя типа <xref:System.Windows.Input.ICommand>\), на который во время загрузки ссылается обработчик [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
<a name="creating_commands"></a>   
## Создание пользовательских команд  
 При необходимости можно создать собственные команды, расширяющие возможности, представленные в классах библиотеки команд.  Существует два способа создания пользовательской команды.  Написание команды с нуля с реализацией интерфейса <xref:System.Windows.Input.ICommand>.  Однако чаще применяется создание объекта <xref:System.Windows.Input.RoutedCommand> или <xref:System.Windows.Input.RoutedUICommand>.  
  
 Пример создания пользовательской команды <xref:System.Windows.Input.RoutedCommand> см. в файле [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## См. также  
 <xref:System.Windows.Input.RoutedCommand>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Input.InputBinding>   
 <xref:System.Windows.Input.CommandManager>   
 [Общие сведения о входных данных](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Общие сведения о перенаправленных событиях](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Реализация ICommandSource](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/ru-ru/013d68a0-5373-4a68-bd91-5de574307370)   
 [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980)