---
title: Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 1f6312f9ac8520b2131e1d2d7a7fb996aee6060e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651592"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="80c38-102">Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c38-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="80c38-103"><xref:System.Windows.Forms.DataGridView> Элемент управления использует шаблон строки в качестве основы для всех строк, которые он добавляет в элемент управления путем привязки данных или при вызове <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> метода без указания существующей строки для использования.</span><span class="sxs-lookup"><span data-stu-id="80c38-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="80c38-104">Шаблон строк обеспечивает больший контроль над внешний вид и поведение строк, чем <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> предоставляет свойство.</span><span class="sxs-lookup"><span data-stu-id="80c38-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="80c38-105">С помощью шаблонов строк, можно задать любой <xref:System.Windows.Forms.DataGridViewRow> свойств, включая <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="80c38-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="80c38-106">Существуют ситуации, когда необходимо использовать шаблон строки для получения определенного результата.</span><span class="sxs-lookup"><span data-stu-id="80c38-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="80c38-107">Например, информацию о высоте строки не могут храниться в <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому необходимо использовать шаблон строки для изменения высоты по умолчанию, используемые во всех строках.</span><span class="sxs-lookup"><span data-stu-id="80c38-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="80c38-108">Шаблон строки удобно использовать при создании собственных классов, производным от <xref:System.Windows.Forms.DataGridViewRow> и нужно, чтобы пользовательского типа используется при добавлении новых строк к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="80c38-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c38-109">Шаблон строки используется только в том случае, если добавляются строки.</span><span class="sxs-lookup"><span data-stu-id="80c38-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="80c38-110">Существующие строки невозможно изменить, изменив шаблон строки.</span><span class="sxs-lookup"><span data-stu-id="80c38-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="80c38-111">Использование шаблонов строк</span><span class="sxs-lookup"><span data-stu-id="80c38-111">To use the row template</span></span>  
  
- <span data-ttu-id="80c38-112">Задать свойства объекта, полученного из <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="80c38-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80c38-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="80c38-113">Compiling the Code</span></span>  
 <span data-ttu-id="80c38-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="80c38-114">This example requires:</span></span>  
  
- <span data-ttu-id="80c38-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="80c38-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="80c38-116">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="80c38-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c38-117">См. также</span><span class="sxs-lookup"><span data-stu-id="80c38-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="80c38-118">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c38-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="80c38-119">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="80c38-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
