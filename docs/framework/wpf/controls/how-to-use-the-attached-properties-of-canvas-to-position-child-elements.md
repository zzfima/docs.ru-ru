---
title: Практическое руководство. Использование вложенных свойств холста для расположения дочерних элементов
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- attached properties [WPF Designer]
- Canvas control [WPF], attached properties
ms.assetid: 48f1d25d-3820-4107-a4cc-d6c1e5664a44
ms.openlocfilehash: 347c8502bd4c5fafcde7a142327f85bfb75b9954
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159631"
---
# <a name="how-to-use-the-attached-properties-of-canvas-to-position-child-elements"></a><span data-ttu-id="f2dc0-102">Практическое руководство. Использование вложенных свойств холста для расположения дочерних элементов</span><span class="sxs-lookup"><span data-stu-id="f2dc0-102">How to: Use the Attached Properties of Canvas to Position Child Elements</span></span>
<span data-ttu-id="f2dc0-103">В этом примере показано использование вложенных свойств <xref:System.Windows.Controls.Canvas> для размещения дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="f2dc0-103">This example shows how to use the attached properties of <xref:System.Windows.Controls.Canvas> to position child elements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2dc0-104">Пример</span><span class="sxs-lookup"><span data-stu-id="f2dc0-104">Example</span></span>  
 <span data-ttu-id="f2dc0-105">В следующем примере добавляется четыре <xref:System.Windows.Controls.Button> элементы как дочерние элементы родительского элемента <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="f2dc0-105">The following example adds four <xref:System.Windows.Controls.Button> elements as child elements of a parent <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="f2dc0-106">Каждый элемент представлен <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, и <xref:System.Windows.Controls.Canvas.Top%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2dc0-106">Each element is represented by a <xref:System.Windows.Controls.Canvas.Bottom%2A>, <xref:System.Windows.Controls.Canvas.Left%2A>, <xref:System.Windows.Controls.Canvas.Right%2A>, and <xref:System.Windows.Controls.Canvas.Top%2A>.</span></span>
<span data-ttu-id="f2dc0-107">Каждый <xref:System.Windows.Controls.Button> располагается относительно родительского элемента <xref:System.Windows.Controls.Canvas> и в соответствии с назначенным значением свойства.</span><span class="sxs-lookup"><span data-stu-id="f2dc0-107">Each <xref:System.Windows.Controls.Button> is positioned relative to the parent <xref:System.Windows.Controls.Canvas> and according to its assigned property value.</span></span>  
  
 [!code-cpp[CanvasAttachedProperties#1](~/samples/snippets/cpp/VS_Snippets_Wpf/CanvasAttachedProperties/CPP/CanvasAttachedProps.cpp#1)]
 [!code-csharp[CanvasAttachedProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasAttachedProperties/CSharp/CanvasAttachedProps.cs#1)]
 [!code-vb[CanvasAttachedProperties#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasAttachedProperties/VisualBasic/CanvasAttachedProps.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="f2dc0-108">См. также</span><span class="sxs-lookup"><span data-stu-id="f2dc0-108">See also</span></span>

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.Canvas.Bottom%2A>
- <xref:System.Windows.Controls.Canvas.Left%2A>
- <xref:System.Windows.Controls.Canvas.Right%2A>
- <xref:System.Windows.Controls.Canvas.Top%2A>
- <xref:System.Windows.Controls.Button>
- [<span data-ttu-id="f2dc0-109">Общие сведения о панелях</span><span class="sxs-lookup"><span data-stu-id="f2dc0-109">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="f2dc0-110">Разделы практического руководства</span><span class="sxs-lookup"><span data-stu-id="f2dc0-110">How-to Topics</span></span>](canvas-how-to-topics.md)
- [<span data-ttu-id="f2dc0-111">Общие сведения о присоединенных свойствах</span><span class="sxs-lookup"><span data-stu-id="f2dc0-111">Attached Properties Overview</span></span>](../advanced/attached-properties-overview.md)
