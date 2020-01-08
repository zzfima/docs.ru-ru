---
title: Практическое руководство. Реализация ICommandSource
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345094"
---
# <a name="how-to-implement-icommandsource"></a>Практическое руководство. Реализация ICommandSource

В этом примере показано, как создать источник команды путем реализации <xref:System.Windows.Input.ICommandSource>. Источник команды — это объект, который знает, как вызывать команду. Интерфейс <xref:System.Windows.Input.ICommandSource> предоставляет три члена:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: команда, которая будет вызываться.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: определяемый пользователем тип данных, который передается из источника команды в метод, обрабатывающий команду.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: объект, для которого выполняется команда.

В этом примере создается класс, наследующий от элемента управления <xref:System.Windows.Controls.Slider> и реализующий интерфейс <xref:System.Windows.Input.ICommandSource>.
  
## <a name="example"></a>Пример

WPF предоставляет ряд классов, реализующих <xref:System.Windows.Input.ICommandSource>, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>и <xref:System.Windows.Documents.Hyperlink>. Источник команды определяет, как он вызывает команду. Эти классы вызывают команду при их щелчке и становятся источником команды, только если задано их свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.

В этом примере команда вызывается при перемещении ползунка или точно точнее при изменении свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.

Ниже приведено определение класса.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

Следующим шагом является реализация элементов <xref:System.Windows.Input.ICommandSource>. В этом примере свойства реализуются как объекты <xref:System.Windows.DependencyProperty>. Это позволяет свойствам использовать привязку данных. Дополнительные сведения о классе <xref:System.Windows.DependencyProperty> см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md). Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).

Здесь показано только свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
Ниже приведен <xref:System.Windows.DependencyProperty> обратный вызов изменения:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

Следующим шагом является добавление и удаление команды, связанной с источником команды. Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> не может быть просто перезаписано при добавлении новой команды, так как обработчики событий, связанные с предыдущей командой (если таковой имеется), должны быть удалены первыми.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

Следующим шагом является создание логики для обработчика <xref:System.Windows.Input.ICommand.CanExecuteChanged>.

Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> уведомляет источник команды о том, что возможность выполнения команды в текущем целевом объекте команды могла измениться. Когда источник команды получает это событие, обычно он вызывает метод <xref:System.Windows.Input.ICommand.CanExecute%2A> для команды. Если команда не может выполняться на текущем целевом объекте команды, источник команды обычно отключается. Если команда может выполняться на текущем целевом объекте команды, источник команды обычно включает себя.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

Последним шагом является метод <xref:System.Windows.Input.ICommand.Execute%2A>. Если команда является <xref:System.Windows.Input.RoutedCommand>, вызывается метод <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A>. в противном случае вызывается метод <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>См. также:

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Общие сведения о системе команд](commanding-overview.md)
