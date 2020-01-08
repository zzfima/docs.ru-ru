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
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="ad777-102">Практическое руководство. Реализация ICommandSource</span><span class="sxs-lookup"><span data-stu-id="ad777-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="ad777-103">В этом примере показано, как создать источник команды путем реализации <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="ad777-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="ad777-104">Источник команды — это объект, который знает, как вызывать команду.</span><span class="sxs-lookup"><span data-stu-id="ad777-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="ad777-105">Интерфейс <xref:System.Windows.Input.ICommandSource> предоставляет три члена:</span><span class="sxs-lookup"><span data-stu-id="ad777-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="ad777-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: команда, которая будет вызываться.</span><span class="sxs-lookup"><span data-stu-id="ad777-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="ad777-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: определяемый пользователем тип данных, который передается из источника команды в метод, обрабатывающий команду.</span><span class="sxs-lookup"><span data-stu-id="ad777-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="ad777-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: объект, для которого выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="ad777-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="ad777-109">В этом примере создается класс, наследующий от элемента управления <xref:System.Windows.Controls.Slider> и реализующий интерфейс <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="ad777-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="ad777-110">Пример</span><span class="sxs-lookup"><span data-stu-id="ad777-110">Example</span></span>

<span data-ttu-id="ad777-111">WPF предоставляет ряд классов, реализующих <xref:System.Windows.Input.ICommandSource>, таких как <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>и <xref:System.Windows.Documents.Hyperlink>.</span><span class="sxs-lookup"><span data-stu-id="ad777-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="ad777-112">Источник команды определяет, как он вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="ad777-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="ad777-113">Эти классы вызывают команду при их щелчке и становятся источником команды, только если задано их свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad777-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="ad777-114">В этом примере команда вызывается при перемещении ползунка или точно точнее при изменении свойства <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad777-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="ad777-115">Ниже приведено определение класса.</span><span class="sxs-lookup"><span data-stu-id="ad777-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="ad777-116">Следующим шагом является реализация элементов <xref:System.Windows.Input.ICommandSource>.</span><span class="sxs-lookup"><span data-stu-id="ad777-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="ad777-117">В этом примере свойства реализуются как объекты <xref:System.Windows.DependencyProperty>.</span><span class="sxs-lookup"><span data-stu-id="ad777-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="ad777-118">Это позволяет свойствам использовать привязку данных.</span><span class="sxs-lookup"><span data-stu-id="ad777-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="ad777-119">Дополнительные сведения о классе <xref:System.Windows.DependencyProperty> см. в разделе [Общие сведения о свойствах зависимостей](dependency-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ad777-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="ad777-120">Дополнительные сведения о привязке данных см. в разделе [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ad777-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="ad777-121">Здесь показано только свойство <xref:System.Windows.Input.ICommandSource.Command%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad777-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="ad777-122">Ниже приведен <xref:System.Windows.DependencyProperty> обратный вызов изменения:</span><span class="sxs-lookup"><span data-stu-id="ad777-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="ad777-123">Следующим шагом является добавление и удаление команды, связанной с источником команды.</span><span class="sxs-lookup"><span data-stu-id="ad777-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="ad777-124">Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> не может быть просто перезаписано при добавлении новой команды, так как обработчики событий, связанные с предыдущей командой (если таковой имеется), должны быть удалены первыми.</span><span class="sxs-lookup"><span data-stu-id="ad777-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="ad777-125">Следующим шагом является создание логики для обработчика <xref:System.Windows.Input.ICommand.CanExecuteChanged>.</span><span class="sxs-lookup"><span data-stu-id="ad777-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="ad777-126">Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> уведомляет источник команды о том, что возможность выполнения команды в текущем целевом объекте команды могла измениться.</span><span class="sxs-lookup"><span data-stu-id="ad777-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="ad777-127">Когда источник команды получает это событие, обычно он вызывает метод <xref:System.Windows.Input.ICommand.CanExecute%2A> для команды.</span><span class="sxs-lookup"><span data-stu-id="ad777-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="ad777-128">Если команда не может выполняться на текущем целевом объекте команды, источник команды обычно отключается.</span><span class="sxs-lookup"><span data-stu-id="ad777-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="ad777-129">Если команда может выполняться на текущем целевом объекте команды, источник команды обычно включает себя.</span><span class="sxs-lookup"><span data-stu-id="ad777-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="ad777-130">Последним шагом является метод <xref:System.Windows.Input.ICommand.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad777-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="ad777-131">Если команда является <xref:System.Windows.Input.RoutedCommand>, вызывается метод <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A>. в противном случае вызывается метод <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ad777-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="ad777-132">См. также:</span><span class="sxs-lookup"><span data-stu-id="ad777-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="ad777-133">Общие сведения о системе команд</span><span class="sxs-lookup"><span data-stu-id="ad777-133">Commanding Overview</span></span>](commanding-overview.md)
