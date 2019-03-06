---
title: Создание сложной сетки
description: Пример использования элемента управления сетки для создания макета, который выглядит как календарь.
ms.date: 03/30/2017
helpviewer_keywords:
- calendar [WPF], creating
- monthly calendar [WPF], creating
- Grid control [WPF], creating [WPF], complex grid
ms.assetid: 4ce3040a-a156-4364-9596-98ca1eca5550
ms.openlocfilehash: dd17dfeea85e2b404f7a284f93faceec63145b1f
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355038"
---
# <a name="how-to-create-a-complex-grid"></a><span data-ttu-id="4fb80-103">Создание сложной сетки</span><span class="sxs-lookup"><span data-stu-id="4fb80-103">How to create a complex Grid</span></span>

<span data-ttu-id="4fb80-104">В этом примере показано, как использовать <xref:System.Windows.Controls.Grid> управления для создания макета, который выглядит как календарь.</span><span class="sxs-lookup"><span data-stu-id="4fb80-104">This example shows how to use a <xref:System.Windows.Controls.Grid> control to create a layout that looks like a monthly calendar.</span></span>

## <a name="example"></a><span data-ttu-id="4fb80-105">Пример</span><span class="sxs-lookup"><span data-stu-id="4fb80-105">Example</span></span>

<span data-ttu-id="4fb80-106">В следующем примере определяется восемь строк и восемь столбцов с помощью <xref:System.Windows.Controls.RowDefinition> и <xref:System.Windows.Controls.ColumnDefinition> классы.</span><span class="sxs-lookup"><span data-stu-id="4fb80-106">The following example defines eight rows and eight columns by using the <xref:System.Windows.Controls.RowDefinition> and <xref:System.Windows.Controls.ColumnDefinition> classes.</span></span> <span data-ttu-id="4fb80-107">Она использует <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> и <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> присоединенных свойств, вместе с <xref:System.Windows.Shapes.Rectangle> элементы, которые заполняют фон различных столбцов и строк.</span><span class="sxs-lookup"><span data-stu-id="4fb80-107">It uses the <xref:System.Windows.Controls.Grid.ColumnSpan%2A?displayProperty=nameWithType> and <xref:System.Windows.Controls.Grid.RowSpan%2A?displayProperty=nameWithType> attached properties, together with <xref:System.Windows.Shapes.Rectangle> elements, which fill the backgrounds of various columns and rows.</span></span> <span data-ttu-id="4fb80-108">Такой подход возможен, так как может существовать несколько элементов в каждой ячейке <xref:System.Windows.Controls.Grid>, принципиальное различие между <xref:System.Windows.Controls.Grid> и <xref:System.Windows.Documents.Table>.</span><span class="sxs-lookup"><span data-stu-id="4fb80-108">This design is possible because more than one element can exist in each cell in a <xref:System.Windows.Controls.Grid>, a principle difference between <xref:System.Windows.Controls.Grid> and <xref:System.Windows.Documents.Table>.</span></span>

<span data-ttu-id="4fb80-109">В примере используется вертикальные градиенты к <xref:System.Windows.Shapes.Shape.Fill%2A> столбцы и строки, чтобы улучшить визуальное представление и удобочитаемость календаря.</span><span class="sxs-lookup"><span data-stu-id="4fb80-109">The example uses vertical gradients to <xref:System.Windows.Shapes.Shape.Fill%2A> the columns and rows to improve the visual presentation and readability of the calendar.</span></span> <span data-ttu-id="4fb80-110">Стиль <xref:System.Windows.Controls.TextBlock> элементы представляют даты и дней недели.</span><span class="sxs-lookup"><span data-stu-id="4fb80-110">Styled <xref:System.Windows.Controls.TextBlock> elements represent the dates and days of the week.</span></span> <span data-ttu-id="4fb80-111"><xref:System.Windows.Controls.TextBlock> элементов абсолютного располагаются в пределах их ячеек с помощью <xref:System.Windows.FrameworkElement.Margin%2A> свойства и свойства выравнивания, которые определены в стиле для приложения.</span><span class="sxs-lookup"><span data-stu-id="4fb80-111"><xref:System.Windows.Controls.TextBlock> elements are absolutely positioned within their cells by using the <xref:System.Windows.FrameworkElement.Margin%2A> property and alignment properties that are defined within the style for the application.</span></span>

[!code-xaml[GridComplex#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridComplex/CS/default.xaml#1)]

<span data-ttu-id="4fb80-112">На следующем рисунке показана полученный элемент управления, настраиваемые календаря:</span><span class="sxs-lookup"><span data-stu-id="4fb80-112">The following image shows the resulting control, a customizable calendar:</span></span>

![Снимок экрана полученный элемент управления](././media/how-to-create-a-complex-grid/wpf-manual-calendar.png)

## <a name="see-also"></a><span data-ttu-id="4fb80-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4fb80-114">See also</span></span>

- <xref:System.Windows.Controls.Grid?displayProperty=nameWithType>
- <xref:System.Windows.Documents.TableCell?displayProperty=nameWithType>
- [<span data-ttu-id="4fb80-115">Общие сведения о закраске сплошным цветом и градиентом</span><span class="sxs-lookup"><span data-stu-id="4fb80-115">Painting with Solid Colors and Gradients Overview</span></span>](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="4fb80-116">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="4fb80-116">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="4fb80-117">Общие сведения о таблицах</span><span class="sxs-lookup"><span data-stu-id="4fb80-117">Table Overview</span></span>](../advanced/table-overview.md)