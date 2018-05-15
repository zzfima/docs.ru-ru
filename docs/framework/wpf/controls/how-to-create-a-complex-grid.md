---
title: Практическое руководство. Создание сложной сетки
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: 49bf9781d56b93fd4529f3c9b62deb171e69155f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="45051-102">Практическое руководство. Создание сложной сетки</span><span class="sxs-lookup"><span data-stu-id="45051-102">How to: Create a Complex Grid</span></span>
<span data-ttu-id="45051-103">В этом примере показано, как использовать <xref:System.Windows.Controls.Grid> для создания макета, который выглядит как календарь.</span><span class="sxs-lookup"><span data-stu-id="45051-103">This example shows how to use a <xref:System.Windows.Controls.Grid> to create layout that looks like a monthly calendar.</span></span>  
  
## <a name="example"></a><span data-ttu-id="45051-104">Пример</span><span class="sxs-lookup"><span data-stu-id="45051-104">Example</span></span>  
 <span data-ttu-id="45051-105">В следующем примере определяется восемь строк и восемь столбцов с помощью <xref:System.Windows.Controls.RowDefinition> и <xref:System.Windows.Controls.ColumnDefinition> классы.</span><span class="sxs-lookup"><span data-stu-id="45051-105">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="45051-106">Она использует <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> вложенные свойства, вместе с <xref:System.Windows.Shapes.Rectangle> элементы, которые заполняют фон различных столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="45051-106">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="45051-107">Такой подход возможен, поскольку может существовать более одного элемента в каждой ячейке <xref:System.Windows.Controls.Grid>, принципиальное различие между <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="45051-107">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>  
  
 <span data-ttu-id="45051-108">В примере используется вертикальная градиентов <xref:System.Windows.Shapes.Shape.Fill%2A> столбцы и строки, чтобы улучшить визуальное представление и удобочитаемость календаря.</span><span class="sxs-lookup"><span data-stu-id="45051-108">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows in order to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="45051-109">Стиль <xref:System.Windows.Controls.TextBlock> элементы, которые представляют даты и дни недели.</span><span class="sxs-lookup"><span data-stu-id="45051-109">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="45051-110"><xref:System.Windows.Controls.TextBlock> элементы абсолютно располагаются в пределах их ячеек с помощью <xref:System.Windows.FrameworkElement.Margin%2A> свойств и свойств выравнивания, определенные в стиле для приложения.</span><span class="sxs-lookup"><span data-stu-id="45051-110"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>  
  
 [!code-xaml[GridComplex#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="45051-111">См. также</span><span class="sxs-lookup"><span data-stu-id="45051-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 <xref:System.Windows.Documents.TableCell>  
 [<span data-ttu-id="45051-112">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="45051-112">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)  
 [<span data-ttu-id="45051-113">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="45051-113">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)  
 [<span data-ttu-id="45051-114">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="45051-114">Table Overview</span></span>](../../../../docs/framework/wpf/advanced/table-overview.md)
