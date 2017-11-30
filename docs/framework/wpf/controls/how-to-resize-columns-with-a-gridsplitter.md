---
title: "Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c8299a3f4885618601c8087a61c21dc5d989813
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a><span data-ttu-id="c2d94-102">Практическое руководство. Изменение размера столбцов с помощью разделителя GridSplitter</span><span class="sxs-lookup"><span data-stu-id="c2d94-102">How to: Resize Columns with a GridSplitter</span></span>
<span data-ttu-id="c2d94-103">В этом примере показано, как создать вертикальной <xref:System.Windows.Controls.GridSplitter> для увеличения пространства между двумя столбцами в <xref:System.Windows.Controls.Grid> без изменения размеров <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="c2d94-103">This example shows how to create a vertical <xref:System.Windows.Controls.GridSplitter> in order to redistribute the space between two columns in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c2d94-104">Пример</span><span class="sxs-lookup"><span data-stu-id="c2d94-104">Example</span></span>  
 <span data-ttu-id="c2d94-105">**Создание GridSplitter, который накладывается на границы столбца**</span><span class="sxs-lookup"><span data-stu-id="c2d94-105">**How to create a GridSplitter that overlays the edge of a column**</span></span>  
  
 <span data-ttu-id="c2d94-106">Чтобы указать <xref:System.Windows.Controls.GridSplitter> , изменяет размеры соседних столбцов в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Column%2A> подключен к одному из столбцов, которые вы хотите изменить свойство.</span><span class="sxs-lookup"><span data-stu-id="c2d94-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent columns in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="c2d94-107">Если вашей <xref:System.Windows.Controls.Grid> имеет более одной строки, задайте <xref:System.Windows.Controls.Grid.RowSpan%2A> вложенное свойство числом строк.</span><span class="sxs-lookup"><span data-stu-id="c2d94-107">If your <xref:System.Windows.Controls.Grid> has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="c2d94-108">Затем установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> свойства <xref:System.Windows.HorizontalAlignment.Left> или <xref:System.Windows.HorizontalAlignment.Right> (выравнивание, которое можно задать зависит от двух столбцы, которого необходимо изменить).</span><span class="sxs-lookup"><span data-stu-id="c2d94-108">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Left> or <xref:System.Windows.HorizontalAlignment.Right> (which alignment you set depends on which two columns you want to resize).</span></span> <span data-ttu-id="c2d94-109">Задайте <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.VerticalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="c2d94-109">Finally, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 <span data-ttu-id="c2d94-110">Объект <xref:System.Windows.Controls.GridSplitter> , не имеет свой собственный столбца может быть скрыт других элементов управления в <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="c2d94-110">A <xref:System.Windows.Controls.GridSplitter> that does not have its own column may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="c2d94-111">Дополнительные сведения о том, как предотвратить возникновение этой проблемы, см. в разделе [Проверка видимости GridSplitter](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="c2d94-111">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="c2d94-112">**Создание GridSplitter, который занимает столбец**</span><span class="sxs-lookup"><span data-stu-id="c2d94-112">**How to create a GridSplitter that occupies a column**</span></span>  
  
 <span data-ttu-id="c2d94-113">Чтобы указать <xref:System.Windows.Controls.GridSplitter> , занимает столбец в <xref:System.Windows.Controls.Grid>, задайте <xref:System.Windows.Controls.Grid.Column%2A> подключен к одному из столбцов, которые вы хотите изменить свойство.</span><span class="sxs-lookup"><span data-stu-id="c2d94-113">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a column in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Column%2A> attached property to one of the columns that you want to resize.</span></span> <span data-ttu-id="c2d94-114">Если ваш сетка имеет более одной строки, задайте <xref:System.Windows.Controls.Grid.RowSpan%2A> вложенное свойство числом строк.</span><span class="sxs-lookup"><span data-stu-id="c2d94-114">If your Grid has more than one row, set the <xref:System.Windows.Controls.Grid.RowSpan%2A> attached property to the number of rows.</span></span> <span data-ttu-id="c2d94-115">Затем установите <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> для <xref:System.Windows.HorizontalAlignment.Center>, задайте <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> свойства <xref:System.Windows.VerticalAlignment.Stretch>и задайте <xref:System.Windows.Controls.ColumnDefinition.Width%2A> столбца, который содержит <xref:System.Windows.Controls.GridSplitter> для <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="c2d94-115">Then set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> to <xref:System.Windows.HorizontalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> property to <xref:System.Windows.VerticalAlignment.Stretch>, and set the <xref:System.Windows.Controls.ColumnDefinition.Width%2A> of the column that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="c2d94-116">В следующем примере показан способ определения вертикальной <xref:System.Windows.Controls.GridSplitter> , занимает столбец и изменяет размеры столбцов на обеих сторонах.</span><span class="sxs-lookup"><span data-stu-id="c2d94-116">The following example shows how to define a vertical <xref:System.Windows.Controls.GridSplitter> that occupies a column and resizes the columns on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="c2d94-117">См. также</span><span class="sxs-lookup"><span data-stu-id="c2d94-117">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="c2d94-118">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="c2d94-118">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
