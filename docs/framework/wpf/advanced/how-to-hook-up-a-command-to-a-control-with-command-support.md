---
title: "Практическое руководство. Подключение команды к элементу управления с поддержкой команды"
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
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b190868b8718442966a22d7be14d976ec47f53b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-command-support"></a>Практическое руководство. Подключение команды к элементу управления с поддержкой команды
Следующий пример показывает, как подключить <xref:System.Windows.Input.RoutedCommand> для <xref:System.Windows.Controls.Control> со встроенной поддержкой команд.  Полный пример подключения команд к нескольким источникам см. в примере [Создание примера настраиваемой команды RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] предоставляет библиотеку стандартных команд, с которыми регулярно работают при программировании приложений.  Классы, составляющие библиотеку команд являются: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, и <xref:System.Windows.Documents.EditingCommands>.  
  
 Статический <xref:System.Windows.Input.RoutedCommand> объекты, составляющие эти классы не предоставляют логику команд.  Логика команды связан с командой <xref:System.Windows.Input.CommandBinding>.  Некоторые элементы управления обладают встроенными привязками CommandBinding для некоторых команд.  Этот механизм позволяет сохранять семантику команды даже при изменении ее фактической реализации.  Объект <xref:System.Windows.Controls.TextBox>, например, обрабатывает <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды по-разному, чем элемент управления, предназначенный для поддержки изображений, но основная идея действие вставки чего-либо остается неизменным.  Логика команд не может поставляться командой: ее должен поставлять элемент управления или приложение.  
  
 Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] имеют встроенную поддержку определенных команд в библиотеке команд.  <xref:System.Windows.Controls.TextBox>, например, такие как поддерживает многие команды редактирования приложения <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  Разработчику приложения не нужно выполнять никаких особых действий, чтобы эти команды заработали с этими элементами управления.  Если <xref:System.Windows.Controls.TextBox> является целевой объект команды при выполнении команды, он будет обрабатывать команду с помощью <xref:System.Windows.Input.CommandBinding> встраивается в элементе управления.  
  
 В следующем примере показано использование <xref:System.Windows.Controls.MenuItem> как источника команды для <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команду, где <xref:System.Windows.Controls.TextBox> является целевым объектом команды.  Всю логику, которая определяет как <xref:System.Windows.Controls.TextBox> выполняет вставку, встроена в <xref:System.Windows.Controls.TextBox> элемента управления.  
  
 Объект <xref:System.Windows.Controls.MenuItem> создается и <xref:System.Windows.Controls.MenuItem.Command%2A> свойству <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команды.  <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> Не задано явно <xref:System.Windows.Controls.TextBox> объекта.  Если <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> не задано, целевой объект команды является элемент, который имеет фокус клавиатуры.  Если элемент, который имеет фокус клавиатуры не поддерживает <xref:System.Windows.Input.ApplicationCommands.Paste%2A> команду или в настоящее время невозможно выполнить команду вставки (буфер обмена пуст, например) то <xref:System.Windows.Controls.MenuItem> будет неактивен.  
  
 [!code-xaml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Подключение команды к элементу управления без поддержки команд](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)
