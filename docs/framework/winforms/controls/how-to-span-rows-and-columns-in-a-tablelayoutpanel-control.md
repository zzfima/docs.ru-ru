---
title: Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039698"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a><span data-ttu-id="73dd9-102">Практическое руководство. Объединение строк и столбцов в элементе управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="73dd9-102">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>
<span data-ttu-id="73dd9-103"><xref:System.Windows.Forms.TableLayoutPanel> Элементы управления могут охватывать смежные строки и столбцы.</span><span class="sxs-lookup"><span data-stu-id="73dd9-103">Controls in a <xref:System.Windows.Forms.TableLayoutPanel> control can span adjacent rows and columns.</span></span>

## <a name="to-span-columns-and-rows"></a><span data-ttu-id="73dd9-104">Охват столбцов и строк</span><span class="sxs-lookup"><span data-stu-id="73dd9-104">To span columns and rows</span></span>

1. <span data-ttu-id="73dd9-105">Перетащите элемент управления <xref:System.Windows.Forms.TableLayoutPanel> из **панели элементов** в свою форму.</span><span class="sxs-lookup"><span data-stu-id="73dd9-105">Drag a <xref:System.Windows.Forms.TableLayoutPanel> control from the **Toolbox** onto your form.</span></span>

2. <span data-ttu-id="73dd9-106">Перетащите элемент управления из **области элементов** в верхнюю <xref:System.Windows.Forms.TableLayoutPanel> левую ячейку элемента управления. <xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="73dd9-106">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** into the upper-left cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

3. <span data-ttu-id="73dd9-107">Задайте для свойства **ColumnSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 2.</span><span class="sxs-lookup"><span data-stu-id="73dd9-107">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **2**.</span></span> <span data-ttu-id="73dd9-108">Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления охватывает первый и второй столбцы.</span><span class="sxs-lookup"><span data-stu-id="73dd9-108">Note that the <xref:System.Windows.Forms.Button> control spans the first and second columns.</span></span>

4. <span data-ttu-id="73dd9-109">Присвойте свойству **RowSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 2.</span><span class="sxs-lookup"><span data-stu-id="73dd9-109">Set the <xref:System.Windows.Forms.Button> control's **RowSpan** property to **2**.</span></span> <span data-ttu-id="73dd9-110">Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления охватывает первую и вторую строки.</span><span class="sxs-lookup"><span data-stu-id="73dd9-110">Note that the <xref:System.Windows.Forms.Button> control spans the first and second rows.</span></span>

5. <span data-ttu-id="73dd9-111">Задайте для свойства **ColumnSpan** элементауправлениязначение<xref:System.Windows.Forms.Button> 1.</span><span class="sxs-lookup"><span data-stu-id="73dd9-111">Set the <xref:System.Windows.Forms.Button> control's **ColumnSpan** property to **1**.</span></span> <span data-ttu-id="73dd9-112">Обратите внимание <xref:System.Windows.Forms.Button> , что элемент управления перемещается в первый столбец и охватывает первую и вторую строки.</span><span class="sxs-lookup"><span data-stu-id="73dd9-112">Note that the <xref:System.Windows.Forms.Button> control moves into the first column and spans the first and second rows.</span></span>

## <a name="see-also"></a><span data-ttu-id="73dd9-113">См. также</span><span class="sxs-lookup"><span data-stu-id="73dd9-113">See also</span></span>

- [<span data-ttu-id="73dd9-114">Элемент управления TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="73dd9-114">TableLayoutPanel Control</span></span>](tablelayoutpanel-control-windows-forms.md)
