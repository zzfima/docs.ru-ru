---
title: Практическое руководство. Создание пользовательского элемента Panel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Panel control [WPF]
- custom Panel elements [WPF]
ms.assetid: e0df4f1e-8c07-4e86-89a3-e22acfffdc2a
ms.openlocfilehash: 31edc75114c5dad613e5b65e7d8b051e2c3713af
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799142"
---
# <a name="how-to-create-a-custom-panel-element"></a><span data-ttu-id="d91e3-102">Практическое руководство. Создание пользовательского элемента Panel</span><span class="sxs-lookup"><span data-stu-id="d91e3-102">How to: Create a Custom Panel Element</span></span>
## <a name="example"></a><span data-ttu-id="d91e3-103">Пример</span><span class="sxs-lookup"><span data-stu-id="d91e3-103">Example</span></span>  
 <span data-ttu-id="d91e3-104">В этом примере показано, как переопределить поведение макета по умолчанию элемента <xref:System.Windows.Controls.Panel> и создать пользовательские элементы макета, которые являются производными от <xref:System.Windows.Controls.Panel>.</span><span class="sxs-lookup"><span data-stu-id="d91e3-104">This example shows how to override the default layout behavior of the <xref:System.Windows.Controls.Panel> element and create custom layout elements that are derived from <xref:System.Windows.Controls.Panel>.</span></span>  
  
 <span data-ttu-id="d91e3-105">В примере определяется простой настраиваемый элемент <xref:System.Windows.Controls.Panel> с именем `PlotPanel`, который позиционирует дочерние элементы в соответствии с двумя жестко заданными координатами x и y.</span><span class="sxs-lookup"><span data-stu-id="d91e3-105">The example defines a simple custom <xref:System.Windows.Controls.Panel> element called `PlotPanel`, which positions child elements according to two hard-coded x- and y-coordinates.</span></span> <span data-ttu-id="d91e3-106">В этом примере для свойств `x` и `y` задано значение `50`; Таким образом, все дочерние элементы располагаются в этом расположении по осям x и y.</span><span class="sxs-lookup"><span data-stu-id="d91e3-106">In this example, `x` and `y` are both set to `50`; therefore, all child elements are positioned at that location on the x and y axes.</span></span>  
  
 <span data-ttu-id="d91e3-107">Для реализации пользовательских поведений <xref:System.Windows.Controls.Panel> в примере используются методы <xref:System.Windows.FrameworkElement.MeasureOverride%2A> и <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>.</span><span class="sxs-lookup"><span data-stu-id="d91e3-107">To implement custom <xref:System.Windows.Controls.Panel> behaviors, the example uses the <xref:System.Windows.FrameworkElement.MeasureOverride%2A> and <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> methods.</span></span> <span data-ttu-id="d91e3-108">Каждый метод возвращает <xref:System.Windows.Size> данные, необходимые для позиционирования и отрисовки дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="d91e3-108">Each method returns the <xref:System.Windows.Size> data that is necessary to position and render child elements.</span></span>  
  
 [!code-cpp[PlotPanel#1](~/samples/snippets/cpp/VS_Snippets_Wpf/PlotPanel/CPP/PlotPanel.cpp#1)]
 [!code-csharp[PlotPanel#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PlotPanel/CSharp/PlotPanel.cs#1)]
 [!code-vb[PlotPanel#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PlotPanel/VisualBasic/PlotPanel.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d91e3-109">См. также</span><span class="sxs-lookup"><span data-stu-id="d91e3-109">See also</span></span>

- <xref:System.Windows.Controls.Panel>
- [<span data-ttu-id="d91e3-110">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="d91e3-110">Panels Overview</span></span>](panels-overview.md)
