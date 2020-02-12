---
title: Практическое руководство. Установка свойств высоты элемента
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124290"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a><span data-ttu-id="614f4-102">Практическое руководство. Установка свойств высоты элемента</span><span class="sxs-lookup"><span data-stu-id="614f4-102">How to: Set the Height Properties of an Element</span></span>
## <a name="example"></a><span data-ttu-id="614f4-103">Пример</span><span class="sxs-lookup"><span data-stu-id="614f4-103">Example</span></span>  
 <span data-ttu-id="614f4-104">В этом примере визуально отображаются различия в поведении отрисовки четырех свойств, связанных с высотой, в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="614f4-104">This example visually shows the differences in rendering behavior among the four height-related properties in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="614f4-105">Класс <xref:System.Windows.FrameworkElement> предоставляет четыре свойства, описывающие характеристики высоты элемента.</span><span class="sxs-lookup"><span data-stu-id="614f4-105">The <xref:System.Windows.FrameworkElement> class exposes four properties that describe the height characteristics of an element.</span></span> <span data-ttu-id="614f4-106">Эти четыре свойства могут конфликтовать, и, когда это происходит, значение, которое имеет приоритет, определяется следующим образом: значение <xref:System.Windows.FrameworkElement.MinHeight%2A> имеет приоритет над значением <xref:System.Windows.FrameworkElement.MaxHeight%2A>, которое, в свою очередь, имеет приоритет над значением <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="614f4-106">These four properties can conflict, and when they do, the value that takes precedence is determined as follows: the <xref:System.Windows.FrameworkElement.MinHeight%2A> value takes precedence over the <xref:System.Windows.FrameworkElement.MaxHeight%2A> value, which in turn takes precedence over the <xref:System.Windows.FrameworkElement.Height%2A> value.</span></span> <span data-ttu-id="614f4-107">Четвертое свойство, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, доступно только для чтения и сообщает фактическую высоту, определенную взаимодействием с процессом макета.</span><span class="sxs-lookup"><span data-stu-id="614f4-107">A fourth property, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, is read-only, and reports the actual height as determined by interactions with the layout process.</span></span>  
  
 <span data-ttu-id="614f4-108">В следующих [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] примерах элемент <xref:System.Windows.Shapes.Rectangle> (`rect1`) рисуется в качестве дочернего элемента для <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="614f4-108">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] examples draw a <xref:System.Windows.Shapes.Rectangle> element (`rect1`) as a child of <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="614f4-109">Свойства высоты <xref:System.Windows.Shapes.Rectangle> можно изменить с помощью ряда элементов <xref:System.Windows.Controls.ListBox>, представляющих значения свойств <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>и <xref:System.Windows.FrameworkElement.Height%2A>.</span><span class="sxs-lookup"><span data-stu-id="614f4-109">You can change the height properties of a <xref:System.Windows.Shapes.Rectangle> by using a series of <xref:System.Windows.Controls.ListBox> elements that represent the property values of <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>, and <xref:System.Windows.FrameworkElement.Height%2A>.</span></span> <span data-ttu-id="614f4-110">Таким образом, для каждого свойства отображается визуальный порядок.</span><span class="sxs-lookup"><span data-stu-id="614f4-110">In this manner, the precedence of each property is visually displayed.</span></span>  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 <span data-ttu-id="614f4-111">В следующих примерах кода программной части обработаны события, которые вызывает событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>.</span><span class="sxs-lookup"><span data-stu-id="614f4-111">The following code-behind examples handle the events that the <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event raises.</span></span> <span data-ttu-id="614f4-112">Каждый обработчик принимает входные данные из <xref:System.Windows.Controls.ListBox>, анализирует значение как <xref:System.Double>и применяет это значение к указанному свойству, связанному с высотой.</span><span class="sxs-lookup"><span data-stu-id="614f4-112">Each handler takes the input from the <xref:System.Windows.Controls.ListBox>, parses the value as a <xref:System.Double>, and applies the value to the specified height-related property.</span></span> <span data-ttu-id="614f4-113">Значения высоты также преобразуются в строку и записываются в различные элементы <xref:System.Windows.Controls.TextBlock> (определение этих элементов не отображается в выбранном коде XAML).</span><span class="sxs-lookup"><span data-stu-id="614f4-113">The height values are also converted to a string and written to various <xref:System.Windows.Controls.TextBlock> elements (definition of those elements is not shown in the selected XAML).</span></span>  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 <span data-ttu-id="614f4-114">Полный пример см. в разделе [образец свойств Height](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span><span class="sxs-lookup"><span data-stu-id="614f4-114">For the complete sample, see [Height Properties Sample](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="614f4-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="614f4-115">See also</span></span>

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [<span data-ttu-id="614f4-116">Определение свойств ширины элемента</span><span class="sxs-lookup"><span data-stu-id="614f4-116">Set the Width Properties of an Element</span></span>](how-to-set-the-width-properties-of-an-element.md)
- [<span data-ttu-id="614f4-117">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="614f4-117">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="614f4-118">Пример свойств высоты</span><span class="sxs-lookup"><span data-stu-id="614f4-118">Height Properties Sample</span></span>](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
