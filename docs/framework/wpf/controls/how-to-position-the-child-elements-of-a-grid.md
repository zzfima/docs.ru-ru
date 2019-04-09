---
title: Практическое руководство. Размещение дочерних элементов сетки
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Grid control [WPF], positioning child elements
ms.assetid: 27b3ba9b-ad32-44e2-bcab-a79d573a463c
ms.openlocfilehash: c508f45c1ea3d0925503d6fe5600498a0558d5ad
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202993"
---
# <a name="how-to-position-the-child-elements-of-a-grid"></a><span data-ttu-id="93ac4-102">Практическое руководство. Размещение дочерних элементов сетки</span><span class="sxs-lookup"><span data-stu-id="93ac4-102">How to: Position the Child Elements of a Grid</span></span>
<span data-ttu-id="93ac4-103">В этом примере показано, как использовать команду get и задайте методы, определенные на <xref:System.Windows.Controls.Grid> для размещения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="93ac4-103">This example shows how to use the get and set methods that are defined on <xref:System.Windows.Controls.Grid> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93ac4-104">Пример</span><span class="sxs-lookup"><span data-stu-id="93ac4-104">Example</span></span>  
 <span data-ttu-id="93ac4-105">В следующем примере определяется родительским <xref:System.Windows.Controls.Grid> элемент (`grid1`) с тремя столбцами и тремя строками.</span><span class="sxs-lookup"><span data-stu-id="93ac4-105">The following example defines a parent <xref:System.Windows.Controls.Grid> element (`grid1`) that has three columns and three rows.</span></span> <span data-ttu-id="93ac4-106">Дочерний элемент <xref:System.Windows.Shapes.Rectangle> элемент (`rect1`) добавляется к <xref:System.Windows.Controls.Grid> в столбец номер 0, строку номер 0.</span><span class="sxs-lookup"><span data-stu-id="93ac4-106">A child <xref:System.Windows.Shapes.Rectangle> element (`rect1`) is added to the <xref:System.Windows.Controls.Grid> in column position zero, row position zero.</span></span> <xref:System.Windows.Controls.Button> <span data-ttu-id="93ac4-107">элементы представляют собой методы, которые могут быть вызваны для изменения положения <xref:System.Windows.Shapes.Rectangle> сервисном <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="93ac4-107">elements represent methods that can be called to reposition the <xref:System.Windows.Shapes.Rectangle> element within the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="93ac4-108">Когда пользователь нажимает кнопку, активируется связанный метод.</span><span class="sxs-lookup"><span data-stu-id="93ac4-108">When a user clicks a button, the related method is activated.</span></span>  
  
 [!code-xaml[gridGetSetMethods](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml)]  
  
 <span data-ttu-id="93ac4-109">В следующем примере кода программной части обрабатывает методы, кнопки <xref:System.Windows.Controls.Primitives.ButtonBase.Click> вызывают события.</span><span class="sxs-lookup"><span data-stu-id="93ac4-109">The following code-behind example handles the methods that the button <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events raise.</span></span> <span data-ttu-id="93ac4-110">Пример записывает эти вызовы методов в <xref:System.Windows.Controls.TextBlock> элементы, которые используют связанные методы получения для вывода новых значений свойств в виде строк.</span><span class="sxs-lookup"><span data-stu-id="93ac4-110">The example writes these method calls to <xref:System.Windows.Controls.TextBlock> elements that use related get methods to output the new property values as strings.</span></span>  
  
 [!code-csharp[gridGetSetMethods#2](~/samples/snippets/csharp/VS_Snippets_Wpf/gridGetSetMethods/CSharp/Window1.xaml.cs#2)]
 [!code-vb[gridGetSetMethods#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gridGetSetMethods/VisualBasic/Window1.xaml.vb#2)]  
 <span data-ttu-id="93ac4-111">Ниже приведен результат!</span><span class="sxs-lookup"><span data-stu-id="93ac4-111">Here is the finished result!</span></span>
 
 ![Снимок экрана показан пользовательский интерфейс WPF с двумя столбцами, справа от оператора имеет 3 x 3 сетку и слева находятся кнопки для перемещения между столбцами и строками сетки цветным прямоугольником](././media/grid-methods-sample.png) 
  
## <a name="see-also"></a><span data-ttu-id="93ac4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="93ac4-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- [<span data-ttu-id="93ac4-114">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="93ac4-114">Panels Overview</span></span>](panels-overview.md)
