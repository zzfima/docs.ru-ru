---
title: Как выполнить Установка свойств высоты элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: be3235d4bf7b5e108420b5ed030157067cacdb8a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637057"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="d6d01-102">Как выполнить Установка свойств высоты элемента</span><span class="sxs-lookup"><span data-stu-id="d6d01-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="d6d01-103">Пример</span><span class="sxs-lookup"><span data-stu-id="d6d01-103">Example</span></span>  
 <span data-ttu-id="d6d01-104">В этом примере визуально показаны различия в поведении между четырьмя свойствами, связанных с высотой в отрисовки [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d6d01-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="d6d01-105"><xref:System.Windows.FrameworkElement> Класс предоставляет четыре свойства, описывающие характеристики высоты элемента.</span><span class="sxs-lookup"><span data-stu-id="d6d01-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="d6d01-106">Эти четыре свойства могут конфликтовать и когда это значение, которое имеет более высокий приоритет определяется следующим образом: <xref:System.Windows.FrameworkElement.MinHeight%2A> значение имеет приоритет над <xref:System.Windows.FrameworkElement.MaxHeight%2A> значение, которое в свою очередь имеет приоритет над <xref:System.Windows.FrameworkElement.Height%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="d6d01-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="d6d01-107">Четвертое свойство <xref:System.Windows.FrameworkElement.ActualHeight%2A>, доступен только для чтения и сообщает о фактической высоте, определенной при взаимодействии с процессом макета.</span><span class="sxs-lookup"><span data-stu-id="d6d01-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="d6d01-108">Следующие [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) как дочерний <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="d6d01-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="d6d01-109">Можно изменить свойства высоты <xref:System.Windows.Shapes.Rectangle> с помощью ряда <xref:System.Windows.Controls.ListBox> элементы, представляющие значения свойств <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6d01-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="d6d01-110">Таким образом визуально отображается приоритет каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="d6d01-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="d6d01-111">В следующих примерах кода обработки событий, <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="d6d01-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="d6d01-112">Каждый обработчик принимает входные данные из <xref:System.Windows.Controls.ListBox>, анализирует его как <xref:System.Double>и применяет значение к указанному свойству высоты.</span><span class="sxs-lookup"><span data-stu-id="d6d01-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="d6d01-113">Значения высоты также преобразуются в строку и записываются в различные <xref:System.Windows.Controls.TextBlock> элементы (определение этих элементов не представлено в выбранной XAML).</span><span class="sxs-lookup"><span data-stu-id="d6d01-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="d6d01-114">Полный пример см. в разделе [пример свойств высоты](https://go.microsoft.com/fwlink/?LinkID=159993).</span><span class="sxs-lookup"><span data-stu-id="d6d01-114">For the complete sample, see [Height Properties Sample](https://go.microsoft.com/fwlink/?LinkID=159993).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6d01-115">См. также</span><span class="sxs-lookup"><span data-stu-id="d6d01-115">See also</span></span>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="d6d01-116">Определение свойств ширины элемента</span><span class="sxs-lookup"><span data-stu-id="d6d01-116">Set the Width Properties of an Element</span></span>](../../../../docs/framework/wpf/controls/how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="d6d01-117">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="d6d01-117">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
- [<span data-ttu-id="d6d01-118">Пример свойств высоты</span><span class="sxs-lookup"><span data-stu-id="d6d01-118">Height Properties Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=159993)
