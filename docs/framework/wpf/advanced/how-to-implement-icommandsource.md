---
title: "Практическое руководство. Реализация ICommandSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d82a211f59fbdecdc932b7e57b242274e91cd5b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-icommandsource"></a>Практическое руководство. Реализация ICommandSource
В этом примере показано, как создать источник команды путем реализации <xref:System.Windows.Input.ICommandSource>.  Источник команды — это объект, который знает, как вызывать команду.  <xref:System.Windows.Input.ICommandSource> Интерфейс предоставляет три члена: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, и <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A>Представляет команду, которая будет вызываться. <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> Имеет тип данных, определяемых пользователем, передаваемый из источника команды методу, который обрабатывает команду. <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> — Объект, для которого выполняется команда.  
  
 В этом примере класс создается какие подклассов <xref:System.Windows.Controls.Slider> управления и реализует <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Пример  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]предоставляет несколько классов, которые реализуют <xref:System.Windows.Input.ICommandSource>, такие как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, и <xref:System.Windows.Controls.ListBoxItem>.  Источник команды определяет порядок вызова команды.   <xref:System.Windows.Controls.Button>и <xref:System.Windows.Controls.MenuItem> вызова команды при щелчке.  Объект <xref:System.Windows.Controls.ListBoxItem> вызывает команду при двойном щелчке. Эти классы становятся лишь команду источника при их <xref:System.Windows.Input.ICommandSource.Command%2A> свойству.  
  
 В этом примере команда будет вызываться при перемещении ползунка или, точнее, когда <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> изменить свойство.  
  
 Ниже приведено определение класса.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 Следующим шагом является реализация <xref:System.Windows.Input.ICommandSource> члены.  В этом примере свойства реализуются как <xref:System.Windows.DependencyProperty> объектов.  Это позволяет свойствам использовать привязку данных.  Дополнительные сведения о <xref:System.Windows.DependencyProperty> см. в описании [Общие сведения о свойствах зависимостей](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Только <xref:System.Windows.Input.ICommandSource.Command%2A> свойство приведен ниже.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Ниже приведен <xref:System.Windows.DependencyProperty> изменить обратного вызова.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 Следующим шагом является добавление и удаление команды, связанной с источника команды.  <xref:System.Windows.Input.ICommandSource.Command%2A> Свойство не может быть просто перезаписано при добавлении новой команды поскольку обработчики событий, связанные с предыдущей командой, если таковая была сначала необходимо удалить.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 Последним шагом является создание логики для <xref:System.Windows.Input.ICommand.CanExecuteChanged> обработчика и <xref:System.Windows.Input.ICommand.Execute%2A> метод.  
  
 <xref:System.Windows.Input.ICommand.CanExecuteChanged> Событие уведомляет источника команды, могла быть изменена возможность выполнения команды на текущей цели команды.  При получении этого события источник команды обычно вызывает <xref:System.Windows.Input.ICommand.CanExecute%2A> метод для команды.  Если команда не может выполнить на текущей цели команды, источник команды обычно отключается.  Если команда может выполняться на текущей цели команды, источник команды обычно включает себя.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 Последний шаг — <xref:System.Windows.Input.ICommand.Execute%2A> метод.  Если команда является <xref:System.Windows.Input.RoutedCommand>, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> метод вызван; в противном случае — <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> вызывается метод.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [Общие сведения о системе команд](../../../../docs/framework/wpf/advanced/commanding-overview.md)
