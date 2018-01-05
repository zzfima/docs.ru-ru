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
ms.workload: dotnet
ms.openlocfilehash: 804c4ffd54a0f8cc94e8849a223b1af8b27a58b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hook-up-a-command-to-a-control-with-no-command-support"></a><span data-ttu-id="e4931-102">Практическое руководство. Подключение команды к элементу управления, не поддерживающему команды</span><span class="sxs-lookup"><span data-stu-id="e4931-102">How to: Hook Up a Command to a Control with No Command Support</span></span>
<span data-ttu-id="e4931-103">Следующий пример показывает, как подключить <xref:System.Windows.Input.RoutedCommand> для <xref:System.Windows.Controls.Control> которого отсутствует встроенная поддержка команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-103">The following example shows how to hook up a <xref:System.Windows.Input.RoutedCommand> to a <xref:System.Windows.Controls.Control> which does not have built in support for the command.</span></span>  <span data-ttu-id="e4931-104">Полный пример подключения команд к нескольким источникам см. в примере [Создание примера настраиваемой команды RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).</span><span class="sxs-lookup"><span data-stu-id="e4931-104">For a complete sample which hooks up commands to multiple sources, see the [Create a Custom RoutedCommand Sample](http://go.microsoft.com/fwlink/?LinkID=159980) sample.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4931-105">Пример</span><span class="sxs-lookup"><span data-stu-id="e4931-105">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="e4931-106"> предоставляет библиотеку стандартных команд, с которыми регулярно работают при программировании приложений.</span><span class="sxs-lookup"><span data-stu-id="e4931-106"> provides a library of common commands which application programmers encounter regularly.</span></span>  <span data-ttu-id="e4931-107">Классы, составляющие библиотеку команд являются: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, и <xref:System.Windows.Documents.EditingCommands>.</span><span class="sxs-lookup"><span data-stu-id="e4931-107">The classes which comprise the command library are: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, and <xref:System.Windows.Documents.EditingCommands>.</span></span>  
  
 <span data-ttu-id="e4931-108">Статический <xref:System.Windows.Input.RoutedCommand> объекты, составляющие эти классы не предоставляют логику команд.</span><span class="sxs-lookup"><span data-stu-id="e4931-108">The static <xref:System.Windows.Input.RoutedCommand> objects which make up these classes do not supply command logic.</span></span>  <span data-ttu-id="e4931-109">Логика команды связан с командой <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="e4931-109">The logic for the command is associated with the command with a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="e4931-110">Многие элементы управления в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] есть встроенная поддержка некоторых команд из библиотеки команд.</span><span class="sxs-lookup"><span data-stu-id="e4931-110">Many controls in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] have built in support for some of the commands in the command library.</span></span>  <span data-ttu-id="e4931-111"><xref:System.Windows.Controls.TextBox>, например, такие как поддерживает многие команды редактирования приложения <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, и <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span><span class="sxs-lookup"><span data-stu-id="e4931-111"><xref:System.Windows.Controls.TextBox>, for example, supports many of the application edit commands such as <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, and <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.</span></span>  <span data-ttu-id="e4931-112">Разработчику приложения не нужно выполнять никаких особых действий, чтобы эти команды заработали с этими элементами управления.</span><span class="sxs-lookup"><span data-stu-id="e4931-112">The application developer does not have to do anything special to get these commands to work with these controls.</span></span>  <span data-ttu-id="e4931-113">Если <xref:System.Windows.Controls.TextBox> является целевой объект команды при выполнении команды, он будет обрабатывать команду с помощью <xref:System.Windows.Input.CommandBinding> встраивается в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="e4931-113">If the <xref:System.Windows.Controls.TextBox> is the command target when the command is executed, it will handle the command using the <xref:System.Windows.Input.CommandBinding> that is built into the control.</span></span>  
  
 <span data-ttu-id="e4931-114">В следующем примере показано использование <xref:System.Windows.Controls.Button> как источника команды для <xref:System.Windows.Input.ApplicationCommands.Open%2A> команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-114">The following shows how to use a <xref:System.Windows.Controls.Button> as the command source for the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  <span data-ttu-id="e4931-115">Объект <xref:System.Windows.Input.CommandBinding> создается, связывает указанный <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> с <xref:System.Windows.Input.RoutedCommand>.</span><span class="sxs-lookup"><span data-stu-id="e4931-115">A <xref:System.Windows.Input.CommandBinding> is created that associates the specified <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> with the <xref:System.Windows.Input.RoutedCommand>.</span></span>  
  
 <span data-ttu-id="e4931-116">Во-первых создается источника команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-116">First, the command source is created.</span></span>  <span data-ttu-id="e4931-117">Объект <xref:System.Windows.Controls.Button> используется в качестве источника команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-117">A <xref:System.Windows.Controls.Button> is used as the command source.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandsource)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbuttoncommandsource)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerButtonCommandSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbuttoncommandsource)]  
  
 <span data-ttu-id="e4931-118">Далее, <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> создаются.</span><span class="sxs-lookup"><span data-stu-id="e4931-118">Next, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> and the <xref:System.Windows.Input.CanExecuteRoutedEventHandler> are created.</span></span>  <span data-ttu-id="e4931-119"><xref:System.Windows.Input.ExecutedRoutedEventHandler> Просто открывает <xref:System.Windows.MessageBox> для обозначения того, что выполнена команда.</span><span class="sxs-lookup"><span data-stu-id="e4931-119">The <xref:System.Windows.Input.ExecutedRoutedEventHandler> simply opens a <xref:System.Windows.MessageBox> to signify that the command executed.</span></span>  <span data-ttu-id="e4931-120"><xref:System.Windows.Input.CanExecuteRoutedEventHandler> Задает <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> свойства `true`.</span><span class="sxs-lookup"><span data-stu-id="e4931-120">The <xref:System.Windows.Input.CanExecuteRoutedEventHandler> sets the <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> property to `true`.</span></span>  <span data-ttu-id="e4931-121">Как правило, оно может выполнять обработчик выполнит более надежными проверяет, если выполнить команды на текущей цели команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-121">Normally, the can execute handler would perform more robust checks to see if the command could execute on the current command target.</span></span>  
  
 [!code-csharp[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerbothhandlers)]
 [!code-vb[commandWithHandler#CommandHandlerBothHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerbothhandlers)]  
  
 <span data-ttu-id="e4931-122">Наконец <xref:System.Windows.Input.CommandBinding> создается в корневом каталоге <xref:System.Windows.Window> приложения, которое связывает обработчик маршрутизируемых событий для <xref:System.Windows.Input.ApplicationCommands.Open%2A> команды.</span><span class="sxs-lookup"><span data-stu-id="e4931-122">Finally, a <xref:System.Windows.Input.CommandBinding> is created on the root <xref:System.Windows.Window> of the application that associates the routed events handlers to the <xref:System.Windows.Input.ApplicationCommands.Open%2A> command.</span></span>  
  
 [!code-xaml[commandWithHandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
## <a name="see-also"></a><span data-ttu-id="e4931-123">См. также</span><span class="sxs-lookup"><span data-stu-id="e4931-123">See Also</span></span>  
 [<span data-ttu-id="e4931-124">Общие сведения о системе команд</span><span class="sxs-lookup"><span data-stu-id="e4931-124">Commanding Overview</span></span>](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [<span data-ttu-id="e4931-125">Подключение команды к элементу управления с поддержкой команд</span><span class="sxs-lookup"><span data-stu-id="e4931-125">Hook Up a Command to a Control with Command Support</span></span>](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-command-support.md)
