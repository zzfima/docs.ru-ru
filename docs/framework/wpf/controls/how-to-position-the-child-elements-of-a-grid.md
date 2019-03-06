---
title: Практическое руководство. Размещение дочерних элементов сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: 90115bc6192a33f4c27eaa75ebfe6a7c9d1458e5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369179"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="277cb-102">Практическое руководство. Размещение дочерних элементов сетки</span><span class="sxs-lookup"><span data-stu-id="277cb-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="277cb-103">В этом примере показано, как использовать команду get и задайте методы, определенные на <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="277cb-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="277cb-104">Пример</span><span class="sxs-lookup"><span data-stu-id="277cb-104">Example</span></span>  
 <span data-ttu-id="277cb-105">В следующем примере определяется родительским <xref:System.Windows.Controls.Grid> элемент (`grid1`) с тремя столбцами и тремя строками.</span><span class="sxs-lookup"><span data-stu-id="277cb-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="277cb-106">Дочерний элемент <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) добавляется к <xref:System.Windows.Controls.Grid> в столбец номер 0, строку номер 0.</span><span class="sxs-lookup"><span data-stu-id="277cb-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <span data-ttu-id="277cb-107"><xref:System.Windows.Controls.Button> элементы представляют собой методы, которые могут быть вызваны для изменения положения <xref:System.Windows.Shapes.Rectangle> сервисном <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="277cb-107"><xref:System.Windows.Controls.Button> elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="277cb-108">Когда пользователь нажимает кнопку, активируется связанный метод.</span><span class="sxs-lookup"><span data-stu-id="277cb-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="277cb-109">В следующем примере кода программной части обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывают события.</span><span class="sxs-lookup"><span data-stu-id="277cb-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="277cb-110">Пример записывает эти вызовы методов в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.</span><span class="sxs-lookup"><span data-stu-id="277cb-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="277cb-111">Ниже приведен результат!</span><span class="sxs-lookup"><span data-stu-id="277cb-111">Here is the finished result!</span></span>
 
 ![Снимок экрана показан пользовательский интерфейс WPF с двумя столбцами, справа от оператора имеет 3 x 3 сетку и слева находятся кнопки для перемещения между столбцами и строками сетки цветным прямоугольником](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="277cb-113">См. также</span><span class="sxs-lookup"><span data-stu-id="277cb-113">See also</span></span>
- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="277cb-114">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="277cb-114">Panels Overview</span></span>](panels-overview.md)
