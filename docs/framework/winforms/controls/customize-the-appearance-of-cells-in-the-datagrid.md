---
title: "Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 545a3bff5e810f9c0a995366e7f6460930f9e936
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3b7d0-102">Практическое руководство. Настройка внешнего вида ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b7d0-102">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3b7d0-103">Можно настроить внешний вид ячеек, обрабатывая <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.CellPainting> событий.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-103">You can customize the appearance of any cell by handling the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.CellPainting> event.</span></span> <span data-ttu-id="3b7d0-104">Можно извлечь <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Drawing.Graphics> из <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-104">You can extract the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Drawing.Graphics> from the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.</span></span> <span data-ttu-id="3b7d0-105">С этим <xref:System.Drawing.Graphics>, могут повлиять на внешний вид всего <xref:System.Windows.Forms.DataGridView> элемент управления, но обычно нужно повлияют на вид в настоящее время закрашиваемой ячейки.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-105">With this <xref:System.Drawing.Graphics>, you can affect the appearance of the entire <xref:System.Windows.Forms.DataGridView> control, but you will usually want to affect only the appearance of the cell that is currently being painted.</span></span> <span data-ttu-id="3b7d0-106"><xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> Свойство <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> позволяет ограничить применение операций рисования в в настоящее время, содержащей закрашиваемую ячейку.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-106">The <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> property of the <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> enables you to restrict your painting operations to the cell that is currently being painted.</span></span>  
  
 <span data-ttu-id="3b7d0-107">В следующем примере кода будет отрисовываться все ячейки в `ContactName` столбца с помощью <xref:System.Windows.Forms.DataGridView> цветовой схемы элемента управления.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-107">In the following code example, you will paint all the cells in a `ContactName` column using the <xref:System.Windows.Forms.DataGridView> control's color scheme.</span></span> <span data-ttu-id="3b7d0-108">Текстовое содержимое каждой ячейки, рисуется в <xref:System.Drawing.Color.Crimson%2A>, и в тот же цвет, что рисуется внутренняя рамка <xref:System.Windows.Forms.DataGridView> элемента управления <xref:System.Windows.Forms.DataGridView.GridColor%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-108">Each cell's text content is painted in <xref:System.Drawing.Color.Crimson%2A>, and an inset rectangle is drawn in the same color as the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.GridColor%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b7d0-109">Пример</span><span class="sxs-lookup"><span data-stu-id="3b7d0-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b7d0-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3b7d0-110">Compiling the Code</span></span>  
 <span data-ttu-id="3b7d0-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3b7d0-111">This example requires:</span></span>  
  
-   <span data-ttu-id="3b7d0-112">Объект <xref:System.Windows.Forms.DataGridView> управления с именем `dataGridView1` с `ContactName` столбца, подобное показанному в таблице Customers в учебной базе данных Northwind.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` with a `ContactName` column such as the one in the Customers table in the Northwind sample database.</span></span>  
  
-   <span data-ttu-id="3b7d0-113">ссылки на сборки System, System.Windows.Forms и System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="3b7d0-113">References to the System, System.Windows.Forms, and System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7d0-114">См. также</span><span class="sxs-lookup"><span data-stu-id="3b7d0-114">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [<span data-ttu-id="3b7d0-115">Настройка элементов управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3b7d0-115">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
