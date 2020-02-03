---
title: Отображение метки вставки в элементе управления ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ListView control [Windows Forms], drag operations
- graphics [Windows Forms], insertion marks
- drop and drag [Windows Forms], insertion marks
- insertion marks
ms.assetid: 88d0a15b-25fd-4dc3-a685-297351311940
ms.openlocfilehash: eeae51223a21baaf4d2412de2ce11d0c6cbcae27
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742219"
---
# <a name="how-to-display-an-insertion-mark-in-a-windows-forms-listview-control"></a><span data-ttu-id="40972-102">Практическое руководство. Индикация места вставки в элементе управления ListView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40972-102">How to: Display an Insertion Mark in a Windows Forms ListView Control</span></span>
<span data-ttu-id="40972-103">Метка вставки в элементе управления <xref:System.Windows.Forms.ListView> показывает пользователю, куда будут помещены перетаскиваемые элементы.</span><span class="sxs-lookup"><span data-stu-id="40972-103">The insertion mark in the <xref:System.Windows.Forms.ListView> control shows users the point where dragged items will be inserted.</span></span> <span data-ttu-id="40972-104">Когда пользователь перетаскивает элемент на точку между двумя другими элементами, метка вставки показывает ожидаемое новое расположение элемента.</span><span class="sxs-lookup"><span data-stu-id="40972-104">When a user drags an item to a point between two other items, the insertion mark shows the item's expected new location.</span></span>  
  
 <span data-ttu-id="40972-105">На рисунке ниже показана метка вставки.</span><span class="sxs-lookup"><span data-stu-id="40972-105">The following image shows an insertion mark:</span></span>  
  
 <span data-ttu-id="40972-106">![Снимок экрана, на котором показана метка вставки ListView.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "листвиевинсертион")</span><span class="sxs-lookup"><span data-stu-id="40972-106">![Screenshot that shows a ListView insertion mark.](./media/how-to-display-an-insertion-mark-in-a-windows-forms-listview-control/listview-insertion-mark.gif "ListViewInsertion")</span></span>  
  
 <span data-ttu-id="40972-107">В примере кода ниже показано, как использовать эту возможность.</span><span class="sxs-lookup"><span data-stu-id="40972-107">The following code example demonstrates how to use this feature.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40972-108">Пример</span><span class="sxs-lookup"><span data-stu-id="40972-108">Example</span></span>  
 [!code-cpp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CPP/listviewinsertionmarkexample.cpp#1)]
 [!code-csharp[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/CS/listviewinsertionmarkexample.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.InsertionMark#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.InsertionMark/VB/listviewinsertionmarkexample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40972-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="40972-109">Compiling the Code</span></span>  
 <span data-ttu-id="40972-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="40972-110">This example requires:</span></span>  
  
- <span data-ttu-id="40972-111">ссылки на сборки System и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="40972-111">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40972-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="40972-112">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.InsertionMark%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewInsertionMark>
- [<span data-ttu-id="40972-113">Элемент управления ListView</span><span class="sxs-lookup"><span data-stu-id="40972-113">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="40972-114">Общие сведения об элементе управления ListView</span><span class="sxs-lookup"><span data-stu-id="40972-114">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="40972-115">Пример. Выполнение операции перетаскивания в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="40972-115">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)
