---
title: Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], setting sizing modes
- DataGridView control [Windows Forms], sizing modes
ms.assetid: e9ad15e6-b4bb-44aa-a767-3738e9db1651
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 457241bb213be24d87bc184499da1940c35a9553
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-set-the-sizing-modes-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="b3159-102">Практическое руководство. Режимы изменения размеров элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3159-102">How to: Set the Sizing Modes of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="b3159-103">Следующие процедуры демонстрируют некоторые распространенные сценарии для настройки или комбинирования параметров изменения размеров, доступных для элемента управления <xref:System.Windows.Forms.DataGridView> и для определенных столбцов в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="b3159-103">The following procedures demonstrate some common scenarios that customize or combine the sizing options available for the <xref:System.Windows.Forms.DataGridView> control and for specific columns in a control.</span></span>  
  
### <a name="to-create-a-fixed-width-column"></a><span data-ttu-id="b3159-104">Создание столбца с фиксированной шириной</span><span class="sxs-lookup"><span data-stu-id="b3159-104">To create a fixed-width column</span></span>  
  
-   <span data-ttu-id="b3159-105">Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, свойства <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> значение <xref:System.Windows.Forms.DataGridViewTriState.False>, свойства <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> значение `true` и свойства <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="b3159-105">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode.None>, the <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A> property to <xref:System.Windows.Forms.DataGridViewTriState.False>, the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`, and the <xref:System.Windows.Forms.DataGridViewColumn.Width%2A> property to an appropriate value.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#10)]  
  
### <a name="to-create-a-column-that-adjusts-its-size-to-fit-its-content"></a><span data-ttu-id="b3159-106">Создание столбца, который изменяет свой размер в соответствии с содержимым</span><span class="sxs-lookup"><span data-stu-id="b3159-106">To create a column that adjusts its size to fit its content</span></span>  
  
-   <span data-ttu-id="b3159-107">Задайте для свойства <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> значение режима изменения размера на основе содержимого.</span><span class="sxs-lookup"><span data-stu-id="b3159-107">Set the <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A> property to a content-based sizing mode.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#20)]  
  
### <a name="to-create-fill-mode-columns-for-values-of-varying-size-and-importance"></a><span data-ttu-id="b3159-108">Создание столбцов с заполнением для значений различного размера и важности</span><span class="sxs-lookup"><span data-stu-id="b3159-108">To create fill-mode columns for values of varying size and importance</span></span>  
  
-   <span data-ttu-id="b3159-109">Задайте для свойства <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> значение <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill>, чтобы указать режим изменения размера для всех столбцов, которые не переопределяют это значение.</span><span class="sxs-lookup"><span data-stu-id="b3159-109">Set the <xref:System.Windows.Forms.DataGridView.AutoSizeColumnsMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode.Fill> to set the sizing mode for all columns that do not override this value.</span></span> <span data-ttu-id="b3159-110">Задайте свойствам <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> столбцов значения, которые будут указывать средние пропорции их ширины.</span><span class="sxs-lookup"><span data-stu-id="b3159-110">Set the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> properties of the columns to values that are proportional to their average content widths.</span></span> <span data-ttu-id="b3159-111">Задайте свойства <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> для важных столбцов, чтобы обеспечить частичное отображение содержимого.</span><span class="sxs-lookup"><span data-stu-id="b3159-111">Set the <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> properties of important columns to ensure partial content display.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#30)]  
  
## <a name="example"></a><span data-ttu-id="b3159-112">Пример</span><span class="sxs-lookup"><span data-stu-id="b3159-112">Example</span></span>  
 <span data-ttu-id="b3159-113">Ниже приводится полный код демонстрационного приложения, которое поможет лучше разобраться с изменениями размеров, описанными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="b3159-113">The following complete code example provides a demonstration application that can help you understand the sizing options described in this topic.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/CS/sizingscenarios.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSizingScenarios#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSizingScenarios/vb/sizingscenarios.vb#00)]  
  
 <span data-ttu-id="b3159-114">Использование этого демонстрационного приложения.</span><span class="sxs-lookup"><span data-stu-id="b3159-114">To use this demonstration application:</span></span>  
  
-   <span data-ttu-id="b3159-115">Измените размер формы.</span><span class="sxs-lookup"><span data-stu-id="b3159-115">Change the size of the form.</span></span> <span data-ttu-id="b3159-116">Обратите внимание, как меняется ширина столбцов с заполнением при сохранении пропорций, указанных в свойстве <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A>.</span><span class="sxs-lookup"><span data-stu-id="b3159-116">Observe how the fill-mode columns change their widths while retaining the proportions indicated by the <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A> property values.</span></span> <span data-ttu-id="b3159-117">Обратите внимание, что столбец <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> не изменяется, если размер формы слишком мал.</span><span class="sxs-lookup"><span data-stu-id="b3159-117">Observe how a column's <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A> prevents it from changing when the form is too small.</span></span>  
  
-   <span data-ttu-id="b3159-118">Измените размеры столбцов, перетаскивая их разделители с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="b3159-118">Change the column sizes by dragging the column dividers with the mouse.</span></span> <span data-ttu-id="b3159-119">Обратите внимание, что некоторые столбцы не могут изменять размер, а столбцы с изменяемой шириной нельзя сделать уже, чем их минимальная ширина.</span><span class="sxs-lookup"><span data-stu-id="b3159-119">Observe how some columns cannot be resized, and how resizable columns cannot be made narrower than their minimum widths.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b3159-120">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b3159-120">Compiling the Code</span></span>  
 <span data-ttu-id="b3159-121">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b3159-121">This example requires:</span></span>  
  
-   <span data-ttu-id="b3159-122">ссылки на сборки System и System.Windows.Forms;</span><span class="sxs-lookup"><span data-stu-id="b3159-122">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="b3159-123">Сведения о построении этого примера из командной строки для Visual Basic или Visual C# см. в разделе [построение из командной строки](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [построение с командной строки csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="b3159-123">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="b3159-124">Чтобы выполнить сборку этого примера в [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] , можно также вставить код в новый проект.</span><span class="sxs-lookup"><span data-stu-id="b3159-124">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="b3159-125">См. также [Практическое руководство. Компиляция и выполнение откомпилированного примера кода формы Windows Forms с помощью Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="b3159-125">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3159-126">См. также</span><span class="sxs-lookup"><span data-stu-id="b3159-126">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.AutoSizeMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>  
 <xref:System.Windows.Forms.DataGridViewColumn.Resizable%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.Width%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.FillWeight%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.MinimumWidth%2A?displayProperty=nameWithType>
