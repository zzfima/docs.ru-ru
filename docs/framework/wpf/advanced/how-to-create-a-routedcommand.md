---
title: Практическое руководство. Создание маршрутизируемой команды RoutedCommand
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- RoutedCommand class [WPF], creating
ms.assetid: aaf6979f-69ab-406f-979f-5766daa85fa0
ms.openlocfilehash: d433658a3039c262d2f682eff09df646d978018c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109048"
---
# <a name="how-to-create-a-routedcommand"></a><span data-ttu-id="27d67-102">Практическое руководство. Создание маршрутизируемой команды RoutedCommand</span><span class="sxs-lookup"><span data-stu-id="27d67-102">How to: Create a RoutedCommand</span></span>
<span data-ttu-id="27d67-103">В этом примере показано, как можно создавать пользовательские <xref:System.Windows.Input.RoutedCommand> и способ реализации пользовательской команды путем создания <xref:System.Windows.Input.ExecutedRoutedEventHandler> и <xref:System.Windows.Input.CanExecuteRoutedEventHandler> и присоединения их <xref:System.Windows.Input.CommandBinding>.</span><span class="sxs-lookup"><span data-stu-id="27d67-103">This example shows how to create a custom <xref:System.Windows.Input.RoutedCommand> and how to implement the custom command by creating a <xref:System.Windows.Input.ExecutedRoutedEventHandler> and a <xref:System.Windows.Input.CanExecuteRoutedEventHandler> and attaching them to a <xref:System.Windows.Input.CommandBinding>.</span></span>  <span data-ttu-id="27d67-104">Дополнительные сведения о системе команд см. в разделе [сведения о системе команд](commanding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="27d67-104">For more information on commanding, see the [Commanding Overview](commanding-overview.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27d67-105">Пример</span><span class="sxs-lookup"><span data-stu-id="27d67-105">Example</span></span>  
 <span data-ttu-id="27d67-106">Первым шагом в создании <xref:System.Windows.Input.RoutedCommand> является определение команды и создание его экземпляра.</span><span class="sxs-lookup"><span data-stu-id="27d67-106">The first step in creating a <xref:System.Windows.Input.RoutedCommand> is defining the command and instantiating it.</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommanddefinition)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommanddefinition)]  
  
 <span data-ttu-id="27d67-107">Чтобы использовать команду в приложении, необходимо создать обработчики событий, которые определяют, что делает команда</span><span class="sxs-lookup"><span data-stu-id="27d67-107">In order to use the command in an application, event handlers which define what the command does must be created</span></span>  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewexecuted)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewExecuted](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewexecuted)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcanexecute)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCanExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcanexecute)]  
  
 <span data-ttu-id="27d67-108">Далее, <xref:System.Windows.Input.CommandBinding> создается, который связывает команду с обработчиками событий.</span><span class="sxs-lookup"><span data-stu-id="27d67-108">Next, a  <xref:System.Windows.Input.CommandBinding> is created which associates the command with the event handlers.</span></span> <span data-ttu-id="27d67-109"><xref:System.Windows.Input.CommandBinding> Создается с определенным объектом.</span><span class="sxs-lookup"><span data-stu-id="27d67-109">The <xref:System.Windows.Input.CommandBinding> is created on a specific object.</span></span>  <span data-ttu-id="27d67-110">Этот объект определяет область <xref:System.Windows.Input.CommandBinding> в дереве элементов</span><span class="sxs-lookup"><span data-stu-id="27d67-110">This object defines the scope of the <xref:System.Windows.Input.CommandBinding> in the element tree</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewWindowCommandBindingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewwindowcommandbindingxaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandbindingcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandBindingCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandbindingcodebehind)]  
  
 <span data-ttu-id="27d67-111">Последним шагом является вызов команды.</span><span class="sxs-lookup"><span data-stu-id="27d67-111">The final step is invoking the command.</span></span>  <span data-ttu-id="27d67-112">Один из способов вызова команды — связать ее с <xref:System.Windows.Input.ICommandSource>, такие как <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="27d67-112">One way to invoke a command is to associate it with a <xref:System.Windows.Input.ICommandSource>, such as a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcustomcommandsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcustomcommandsourcecodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCustomCommandSourceCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcustomcommandsourcecodebehind)]  
  
 <span data-ttu-id="27d67-113">При нажатии кнопки, <xref:System.Windows.Input.RoutedCommand.Execute%2A> метод пользовательского <xref:System.Windows.Input.RoutedCommand> вызывается.</span><span class="sxs-lookup"><span data-stu-id="27d67-113">When the Button is clicked, the <xref:System.Windows.Input.RoutedCommand.Execute%2A> method on the custom <xref:System.Windows.Input.RoutedCommand> is called.</span></span>  <span data-ttu-id="27d67-114"><xref:System.Windows.Input.RoutedCommand> Вызывает <xref:System.Windows.Input.CommandManager.PreviewExecuted> и <xref:System.Windows.Input.CommandManager.Executed> перенаправленных событий.</span><span class="sxs-lookup"><span data-stu-id="27d67-114">The <xref:System.Windows.Input.RoutedCommand> raises the <xref:System.Windows.Input.CommandManager.PreviewExecuted> and <xref:System.Windows.Input.CommandManager.Executed> routed events.</span></span>  <span data-ttu-id="27d67-115">Эти события проходят по дереву элементов, ищете <xref:System.Windows.Input.CommandBinding> для этой конкретной команды.</span><span class="sxs-lookup"><span data-stu-id="27d67-115">These events traverse the element tree looking for a <xref:System.Windows.Input.CommandBinding> for this particular command.</span></span>  <span data-ttu-id="27d67-116">Если <xref:System.Windows.Input.CommandBinding> найден, <xref:System.Windows.Input.ExecutedRoutedEventHandler> связанные с <xref:System.Windows.Input.CommandBinding> вызывается.</span><span class="sxs-lookup"><span data-stu-id="27d67-116">If a <xref:System.Windows.Input.CommandBinding> is found, the <xref:System.Windows.Input.ExecutedRoutedEventHandler> associated with <xref:System.Windows.Input.CommandBinding> is called.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27d67-117">См. также</span><span class="sxs-lookup"><span data-stu-id="27d67-117">See also</span></span>

- <xref:System.Windows.Input.RoutedCommand>
- [<span data-ttu-id="27d67-118">Общие сведения о системе команд</span><span class="sxs-lookup"><span data-stu-id="27d67-118">Commanding Overview</span></span>](commanding-overview.md)
