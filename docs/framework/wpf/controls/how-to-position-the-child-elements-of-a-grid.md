---
title: Практическое руководство. Размещение дочерних элементов Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 44268c32732a9409ea30f028adaa8a2631a06c5c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186723"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="1301f-102">Практическое руководство. Размещение дочерних элементов Grid</span><span class="sxs-lookup"><span data-stu-id="1301f-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="1301f-103">В этом примере показано, как использовать методы <xref:System.Windows.Controls.Grid> получения и набора, которые определяются для размещения элементов ребенка.</span><span class="sxs-lookup"><span data-stu-id="1301f-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1301f-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1301f-104">Example</span></span>  
 <span data-ttu-id="1301f-105">Следующий пример определяет <xref:System.Windows.Controls.Grid> родительский`grid1`элемент (), который имеет три столбца и три строки.</span><span class="sxs-lookup"><span data-stu-id="1301f-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="1301f-106">Элемент <xref:System.Windows.Shapes.Rectangle> ребенка`rect1`() добавляется к нулю <xref:System.Windows.Controls.Grid> положения столбца, положение строки ноль.</span><span class="sxs-lookup"><span data-stu-id="1301f-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="1301f-107"><xref:System.Windows.Controls.Button>элементы представляют методы, которые можно <xref:System.Windows.Shapes.Rectangle> назвать <xref:System.Windows.Controls.Grid>для переориентации элемента в пределах .</span><span class="sxs-lookup"><span data-stu-id="1301f-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="1301f-108">Когда пользователь нажимает кнопку, соответствующий метод активируется.</span><span class="sxs-lookup"><span data-stu-id="1301f-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="1301f-109">Следующий пример кода за рулем обрабатывает <xref:System.Windows.Controls.Primitives.ButtonBase.Click> методы, которые поднимают события кнопки.</span><span class="sxs-lookup"><span data-stu-id="1301f-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="1301f-110">Пример записывает вызовы <xref:System.Windows.Controls.TextBlock> этих методов к элементам, которые используют связанные методы получения для вывода новых значений свойств в виде строк.</span><span class="sxs-lookup"><span data-stu-id="1301f-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="1301f-111">Вот законченный результат!</span><span class="sxs-lookup"><span data-stu-id="1301f-111">Here is the finished result!</span></span>

 ![скриншот изображает пользовательский интерфейс WPF с двумя столбцами, правая сторона имеет сетку 3 x 3, а левая имеет кнопки для перемещения цветного прямоугольника между столбцами и рядами сетки](././media/grid-methods-sample.png)
  
## <a name="see-also"></a><span data-ttu-id="1301f-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1301f-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="1301f-114">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="1301f-114">Panels Overview</span></span>](panels-overview.md)
