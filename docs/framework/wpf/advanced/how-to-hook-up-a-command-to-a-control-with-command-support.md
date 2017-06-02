---
title: "Практическое руководство. Подключение команды к элементу управления с поддержкой команды | Microsoft Docs"
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
  - "Присоединение RoutedCommand класса элементов управления"
  - "классы управления, присоединение RoutedCommand"
  - "Класс RoutedCommand, присоединение к элементу управления"
  - "классы, RoutedCommand, присоединение к элементу управления"
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Практическое руководство. Подключение команды к элементу управления с поддержкой команды
В следующем примере показано, как подключить <xref:System.Windows.Input.RoutedCommand> для <xref:System.Windows.Controls.Control> со встроенной поддержкой команд.  Полный пример, в котором команды присоединяются к нескольким источникам, см. [создать образец пользовательского типа RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980) образца.  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет библиотеку общих команд, которые регулярно используются при программировании приложений.  Классы, составляющие библиотеку команд являются: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, и <xref:System.Windows.Documents.EditingCommands>.  
  
 Статический <xref:System.Windows.Input.RoutedCommand> объекты, составляющие эти классы не предоставляют логику команд.  Логика команды связан с командой <xref:System.Windows.Input.CommandBinding>.  Некоторые элементы управления обладают встроенной поддержкой CommandBinding для некоторых команд.  Этот механизм позволяет семантику остаются теми же, хотя фактическую реализацию команды можно изменить.  Объект <xref:System.Windows.Controls.TextBox>, например, обрабатывает <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды по-другому, чем элемент управления, предназначенный для поддержки изображений, но основная идея вставки чего-либо это означает останется прежним.  Логика команды не могут задаваться с помощью команды, но вместо этого должны быть определены в элемент управления или приложения.  
  
 Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] есть встроенная поддержка некоторых команд из библиотеки команд.  <xref:System.Windows.Controls.TextBox>, например, такие как поддерживает многие команды редактирования приложения <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Разработчик приложения не имеет никаких действий, чтобы получить эти команды для работы с этими элементами управления.  Если <xref:System.Windows.Controls.TextBox> является целью команды при выполнении команды, он будет обрабатывать команду с помощью <xref:System.Windows.Input.CommandBinding> , встроенные в элемент управления.  
  
 Ниже показано, как использовать <xref:System.Windows.Controls.MenuItem> в качестве источника команды для <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команду, где <xref:System.Windows.Controls.TextBox> является целью команды.  Вся логика, которая определяет как <xref:System.Windows.Controls.TextBox> выполняет вставку, встроена в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
 Объект <xref:System.Windows.Controls.MenuItem> создается и <xref:System.Windows.Controls.MenuItem.Command%2A> свойству <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды.  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не задано явно <xref:System.Windows.Controls.TextBox> объекта.  Когда <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не задано, целевой объект команды является элемент, на котором установлен фокус клавиатуры.  Если элемент, на котором установлен фокус клавиатуры не поддерживает <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды или не удается выполнить команду вставки (буфер обмена пуст, например) в настоящее время то <xref:System.Windows.Controls.MenuItem> будет неактивен.  
  
 [!code-xml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о командах](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Подключение команды к элементу управления без поддержки команд](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)