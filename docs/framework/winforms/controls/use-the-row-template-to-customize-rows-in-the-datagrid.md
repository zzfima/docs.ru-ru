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
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966495"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="a5e67-102">Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5e67-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a5e67-103">Элемент управления использует шаблон строк в качестве основания для всех строк, добавляемых в элемент управления с помощью привязки данных, или при <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> вызове метода без указания существующей строки для использования. <xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="a5e67-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="a5e67-104">Шаблон строки обеспечивает больший контроль над внешним видом и поведением строк, чем <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> предоставляет свойство.</span><span class="sxs-lookup"><span data-stu-id="a5e67-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="a5e67-105">С помощью шаблона строки можно задать любые <xref:System.Windows.Forms.DataGridViewRow> свойства, включая. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A></span><span class="sxs-lookup"><span data-stu-id="a5e67-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="a5e67-106">Существует несколько ситуаций, в которых для достижения определенного результата необходимо использовать шаблон строки.</span><span class="sxs-lookup"><span data-stu-id="a5e67-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="a5e67-107">Например, сведения о высоте строки не могут храниться в <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому для изменения высоты по умолчанию, используемой всеми строками, необходимо использовать шаблон строк.</span><span class="sxs-lookup"><span data-stu-id="a5e67-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="a5e67-108">Шаблон строки также полезен при создании собственных классов, производных от <xref:System.Windows.Forms.DataGridViewRow> , и необходимости использовать пользовательский тип при добавлении новых строк к элементу управления.</span><span class="sxs-lookup"><span data-stu-id="a5e67-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5e67-109">Шаблон строки используется только при добавлении строк.</span><span class="sxs-lookup"><span data-stu-id="a5e67-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="a5e67-110">Нельзя изменить существующие строки, изменив шаблон строки.</span><span class="sxs-lookup"><span data-stu-id="a5e67-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="a5e67-111">Использование шаблона строки</span><span class="sxs-lookup"><span data-stu-id="a5e67-111">To use the row template</span></span>  
  
- <span data-ttu-id="a5e67-112">Задайте свойства объекта, полученного из <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> свойства.</span><span class="sxs-lookup"><span data-stu-id="a5e67-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a5e67-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a5e67-113">Compiling the Code</span></span>  
 <span data-ttu-id="a5e67-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a5e67-114">This example requires:</span></span>  
  
- <span data-ttu-id="a5e67-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="a5e67-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="a5e67-116">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a5e67-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5e67-117">См. также</span><span class="sxs-lookup"><span data-stu-id="a5e67-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [<span data-ttu-id="a5e67-118">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5e67-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a5e67-119">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a5e67-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
