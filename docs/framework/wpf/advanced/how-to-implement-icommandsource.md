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
# <a name="how-to-implement-icommandsource"></a><span data-ttu-id="e21dd-102">Практическое руководство. Реализация ICommandSource</span><span class="sxs-lookup"><span data-stu-id="e21dd-102">How to: Implement ICommandSource</span></span>

<span data-ttu-id="e21dd-103">В этом примере показано, как <xref:System.Windows.Input.ICommandSource>создать источник команд путем реализации.</span><span class="sxs-lookup"><span data-stu-id="e21dd-103">This example shows how to create a command source by implementing <xref:System.Windows.Input.ICommandSource>.</span></span> <span data-ttu-id="e21dd-104">Источник команды — это объект, который знает, как вызвать команду.</span><span class="sxs-lookup"><span data-stu-id="e21dd-104">A command source is an object that knows how to invoke a command.</span></span> <span data-ttu-id="e21dd-105">Интерфейс <xref:System.Windows.Input.ICommandSource> предоставляет три члена:</span><span class="sxs-lookup"><span data-stu-id="e21dd-105">The <xref:System.Windows.Input.ICommandSource> interface exposes three members:</span></span>

- <span data-ttu-id="e21dd-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: команда, которая будет вызываться.</span><span class="sxs-lookup"><span data-stu-id="e21dd-106"><xref:System.Windows.Input.ICommandSource.Command%2A>: the command that will be invoked.</span></span>
- <span data-ttu-id="e21dd-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: тип данных, определяемый пользователем, который передается из источника команды в метод, обрабатывающий команду.</span><span class="sxs-lookup"><span data-stu-id="e21dd-107"><xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: a user-defined data type which is passed from the command source to the method that handles the command.</span></span>
- <span data-ttu-id="e21dd-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: объект, на который выполняется команда.</span><span class="sxs-lookup"><span data-stu-id="e21dd-108"><xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: the object that the command is being executed on.</span></span>

<span data-ttu-id="e21dd-109">В этом примере создается класс, <xref:System.Windows.Controls.Slider> который наследует <xref:System.Windows.Input.ICommandSource> от управления и реализует интерфейс.</span><span class="sxs-lookup"><span data-stu-id="e21dd-109">In this example, a class is created that inherits from the <xref:System.Windows.Controls.Slider> control and implements the  <xref:System.Windows.Input.ICommandSource> interface.</span></span>
  
## <a name="example"></a><span data-ttu-id="e21dd-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e21dd-110">Example</span></span>

<span data-ttu-id="e21dd-111">WPF предоставляет ряд классов, <xref:System.Windows.Input.ICommandSource>которые <xref:System.Windows.Controls.Button>реализуют, такие как, <xref:System.Windows.Controls.MenuItem> <xref:System.Windows.Documents.Hyperlink></span><span class="sxs-lookup"><span data-stu-id="e21dd-111">WPF provides a number of classes which implement <xref:System.Windows.Input.ICommandSource>, such as <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, and <xref:System.Windows.Documents.Hyperlink>.</span></span> <span data-ttu-id="e21dd-112">Источник команды определяет, как он вызывает команду.</span><span class="sxs-lookup"><span data-stu-id="e21dd-112">A command source defines how it invokes a command.</span></span> <span data-ttu-id="e21dd-113">Эти классы вызывают команду при нажатии кнопки, и они <xref:System.Windows.Input.ICommandSource.Command%2A> становятся источником команды только при установке их свойства.</span><span class="sxs-lookup"><span data-stu-id="e21dd-113">These classes invoke a command when they're clicked and they only become a command source when their <xref:System.Windows.Input.ICommandSource.Command%2A> property is set.</span></span>

<span data-ttu-id="e21dd-114">В этом примере вы будете вызывать команду при перемещении слайдера <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> или, точнее, при изменении свойства.</span><span class="sxs-lookup"><span data-stu-id="e21dd-114">In this example, you'll invoke the command when the slider is moved, or more accurately, when the <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> property is changed.</span></span>

<span data-ttu-id="e21dd-115">Ниже приводится определение класса:</span><span class="sxs-lookup"><span data-stu-id="e21dd-115">The following is the class definition:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

<span data-ttu-id="e21dd-116">Следующим шагом является реализация <xref:System.Windows.Input.ICommandSource> членов.</span><span class="sxs-lookup"><span data-stu-id="e21dd-116">The next step is to implement the <xref:System.Windows.Input.ICommandSource> members.</span></span> <span data-ttu-id="e21dd-117">В этом примере свойства <xref:System.Windows.DependencyProperty> реализуются как объекты.</span><span class="sxs-lookup"><span data-stu-id="e21dd-117">In this example, the properties are implemented as <xref:System.Windows.DependencyProperty> objects.</span></span> <span data-ttu-id="e21dd-118">Это позволяет свойствам использовать привязку данных.</span><span class="sxs-lookup"><span data-stu-id="e21dd-118">This enables the properties to use data binding.</span></span> <span data-ttu-id="e21dd-119">Для получения дополнительной <xref:System.Windows.DependencyProperty> информации [Dependency Properties Overview](dependency-properties-overview.md)о классе см.</span><span class="sxs-lookup"><span data-stu-id="e21dd-119">For more information about the <xref:System.Windows.DependencyProperty> class, see the [Dependency Properties Overview](dependency-properties-overview.md).</span></span> <span data-ttu-id="e21dd-120">Для получения дополнительной информации [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md)о связывании данных см.</span><span class="sxs-lookup"><span data-stu-id="e21dd-120">For more information about data binding, see the [Data Binding Overview](../../../desktop-wpf/data/data-binding-overview.md).</span></span>

<span data-ttu-id="e21dd-121">Здесь <xref:System.Windows.Input.ICommandSource.Command%2A> отображается только свойство.</span><span class="sxs-lookup"><span data-stu-id="e21dd-121">Only the <xref:System.Windows.Input.ICommandSource.Command%2A> property is shown here.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
<span data-ttu-id="e21dd-122">Ниже приводится <xref:System.Windows.DependencyProperty> изменение обратного вызова:</span><span class="sxs-lookup"><span data-stu-id="e21dd-122">The following is the <xref:System.Windows.DependencyProperty> change callback:</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

<span data-ttu-id="e21dd-123">Следующим шагом является добавление и удаление команды, связанной с источником команды.</span><span class="sxs-lookup"><span data-stu-id="e21dd-123">The next step is to add and remove the command which is associated with the command source.</span></span> <span data-ttu-id="e21dd-124">Свойство <xref:System.Windows.Input.ICommandSource.Command%2A> не может быть просто перезаписано при добавлении новой команды, поскольку обработчики событий, связанные с предыдущей командой, если она была, должны быть удалены в первую очередь.</span><span class="sxs-lookup"><span data-stu-id="e21dd-124">The <xref:System.Windows.Input.ICommandSource.Command%2A> property cannot simply be overwritten when a new command is added, because the event handlers associated with the previous command, if there was one, must be removed first.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

<span data-ttu-id="e21dd-125">Следующим шагом является создание логики для обработчика. <xref:System.Windows.Input.ICommand.CanExecuteChanged></span><span class="sxs-lookup"><span data-stu-id="e21dd-125">The next step is to create logic for the <xref:System.Windows.Input.ICommand.CanExecuteChanged> handler.</span></span>

<span data-ttu-id="e21dd-126">Событие <xref:System.Windows.Input.ICommand.CanExecuteChanged> уведомляет источник команды о том, что способность команды выполнять сяпог текущей цели команды может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="e21dd-126">The <xref:System.Windows.Input.ICommand.CanExecuteChanged> event notifies the command source that the ability of the command to execute on the current command target may have changed.</span></span> <span data-ttu-id="e21dd-127">Когда источник команды получает это событие, <xref:System.Windows.Input.ICommand.CanExecute%2A> он обычно вызывает метод в команде.</span><span class="sxs-lookup"><span data-stu-id="e21dd-127">When a command source receives this event, it typically calls the <xref:System.Windows.Input.ICommand.CanExecute%2A> method on the command.</span></span> <span data-ttu-id="e21dd-128">Если команда не может выполнить в текущей цели команды, источник команды, как правило, отменяется.</span><span class="sxs-lookup"><span data-stu-id="e21dd-128">If the command cannot execute on the current command target, the command source will typically disable itself.</span></span> <span data-ttu-id="e21dd-129">Если команда может выполняться в текущей цели команды, источник команды, как правило, позволяет самому себе.</span><span class="sxs-lookup"><span data-stu-id="e21dd-129">If the command can execute on the current command target, the command source will typically enable itself.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

<span data-ttu-id="e21dd-130">Последним шагом является <xref:System.Windows.Input.ICommand.Execute%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e21dd-130">The last step is the <xref:System.Windows.Input.ICommand.Execute%2A> method.</span></span> <span data-ttu-id="e21dd-131">Если команда <xref:System.Windows.Input.RoutedCommand>является, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> метод называется; в противном случае называется <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> метод.</span><span class="sxs-lookup"><span data-stu-id="e21dd-131">If the command is a <xref:System.Windows.Input.RoutedCommand>, the <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> method is called; otherwise, the <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> method is called.</span></span>

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a><span data-ttu-id="e21dd-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e21dd-132">See also</span></span>

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="e21dd-133">Общие сведения о системе команд</span><span class="sxs-lookup"><span data-stu-id="e21dd-133">Commanding Overview</span></span>](commanding-overview.md)
