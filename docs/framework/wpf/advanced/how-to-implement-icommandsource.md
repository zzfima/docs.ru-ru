---
title: Практическое руководство. Реализация ICommandSource
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174697"
---
# <a name="how-to-implement-icommandsource"></a>Практическое руководство. Реализация ICommandSource

В этом примере показано, как <xref:System.Windows.Input.ICommandSource>создать источник команд путем реализации. Источник команды — это объект, который знает, как вызвать команду. Интерфейс <xref:System.Windows.Input.ICommandSource> предоставляет три члена:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: команда, которая будет вызываться.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: тип данных, определяемый пользователем, который передается из источника команды в метод, обрабатывающий команду.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: объект, на который выполняется команда.

В этом примере создается класс, <xref:System.Windows.Controls.Slider> который наследует <xref:System.Windows.Input.ICommandSource> от управления и реализует интерфейс.
  
## <a name="example"></a>Пример

WPF предоставляет ряд классов, <xref:System.Windows.Input.ICommandSource>которые <xref:System.Windows.Controls.Button>реализуют, такие как, <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Documents.Hyperlink> Источник команды определяет, как он вызывает команду. Эти классы вызывают команду при нажатии кнопки, и они <xref:System.Windows.Input.ICommandSource.Command%2A> становятся источником команды только при установке их свойства.

В этом примере вы будете вызывать команду при перемещении слайдера <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> или, точнее, при изменении свойства.

Ниже приводится определение класса:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Следующим шагом является реализация <xref:System.Windows.Input.ICommandSource> членов. В этом примере свойства <xref:System.Windows.DependencyProperty> реализуются как объекты. Это позволяет свойствам использовать привязку данных. Для получения дополнительной <xref:System.Windows.DependencyProperty> информации [Dependency Properties Overview](dependency-properties-overview.md)о классе см. Для получения дополнительной информации [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md)о связывании данных см.

Здесь <xref:System.Windows.Input.ICommandSource.Command%2A> отображается только свойство.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Ниже приводится <xref:System.Windows.DependencyProperty> изменение обратного вызова:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Следующим шагом является добавление и удаление команды, связанной с источником команды. Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> не может быть просто перезаписано при добавлении новой команды, поскольку обработчики событий, связанные с предыдущей командой, если она была, должны быть удалены в первую очередь.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Следующим шагом является создание логики для обработчика. <xref:System.Windows.Input.ICommand.CanExecuteChanged>

Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> уведомляет источник команды о том, что способность команды выполнять сяпог текущей цели команды может быть изменена. Когда источник команды получает это событие, <xref:System.Windows.Input.ICommand.CanExecute%2A> он обычно вызывает метод в команде. Если команда не может выполнить в текущей цели команды, источник команды, как правило, отменяется. Если команда может выполняться в текущей цели команды, источник команды, как правило, позволяет самому себе.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

Последним шагом является <xref:System.Windows.Input.ICommand.Execute%2A> метод. Если команда <xref:System.Windows.Input.RoutedCommand>является, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> метод называется; в противном случае называется <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> метод.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Общие сведения о системе команд](commanding-overview.md)
