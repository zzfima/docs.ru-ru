---
title: Практическое руководство. Размещение дочерних элементов Grid
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 62508deee1b10b4a1287360f971b3699e57d4243
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="3cd34-102">Практическое руководство. Размещение дочерних элементов Grid</span><span class="sxs-lookup"><span data-stu-id="3cd34-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="3cd34-103">В этом примере показано, как использовать команду get и задать методы, определенные на <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="3cd34-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cd34-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3cd34-104">Example</span></span>  
 <span data-ttu-id="3cd34-105">В следующем примере определяется родительским <xref:System.Windows.Controls.Grid> элемент (`grid1`), содержит три столбца и три строки.</span><span class="sxs-lookup"><span data-stu-id="3cd34-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="3cd34-106">Дочерний элемент <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) добавляется <xref:System.Windows.Controls.Grid> в нулевой позиции столбца, строка нулевой позиции.</span><span class="sxs-lookup"><span data-stu-id="3cd34-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="3cd34-107"><xref:System.Windows.Controls.Button> элементы, которые представляют методы, которые могут быть вызваны для изменения положения <xref:System.Windows.Shapes.Rectangle> элемент в пределах <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="3cd34-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="3cd34-108">Когда пользователь нажимает кнопку, активируется связанный метод.</span><span class="sxs-lookup"><span data-stu-id="3cd34-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="3cd34-109">В следующем примере кода обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызова события.</span><span class="sxs-lookup"><span data-stu-id="3cd34-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="3cd34-110">Пример записывает эти вызовы методов в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.</span><span class="sxs-lookup"><span data-stu-id="3cd34-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="3cd34-111">См. также</span><span class="sxs-lookup"><span data-stu-id="3cd34-111">See Also</span></span>  
 <xref:System.Windows.Controls.Grid>  
 [<span data-ttu-id="3cd34-112">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="3cd34-112">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
