---
title: "Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms"
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
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4898ed7ddff6ca1800ba9380707ad989cbec1125
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="3ac71-102">Практическое руководство. Применение шаблонов строк для настройки отображения строк элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ac71-102">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="3ac71-103"><xref:System.Windows.Forms.DataGridView> Управления использует шаблон строки в качестве основы для всех строк, добавляемых к элементу управления через привязку данных или при вызове <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> метода без указания существующей строки для использования.</span><span class="sxs-lookup"><span data-stu-id="3ac71-103">The <xref:System.Windows.Forms.DataGridView> control uses the row template as a basis for all rows that it adds to the control either through data binding or when you call the <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> method without specifying an existing row to use.</span></span>  
  
 <span data-ttu-id="3ac71-104">Шаблон строк обеспечивает больший контроль над внешний вид и поведение строк, чем <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> предоставляет свойство.</span><span class="sxs-lookup"><span data-stu-id="3ac71-104">The row template gives you greater control over the appearance and behavior of rows than the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property provides.</span></span> <span data-ttu-id="3ac71-105">С помощью строки шаблона, можно задать любое <xref:System.Windows.Forms.DataGridViewRow> свойства, включая <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="3ac71-105">With the row template, you can set any <xref:System.Windows.Forms.DataGridViewRow> properties, including <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>.</span></span>  
  
 <span data-ttu-id="3ac71-106">Существуют ситуации, где необходимо использовать шаблон строки для достижения определенного эффекта.</span><span class="sxs-lookup"><span data-stu-id="3ac71-106">There are some situations where you must use the row template to achieve a particular effect.</span></span> <span data-ttu-id="3ac71-107">Например, информацию о высоте строк не могут храниться в <xref:System.Windows.Forms.DataGridViewCellStyle>, поэтому необходимо использовать шаблон строки для изменения высоты по умолчанию, используемые во всех строках.</span><span class="sxs-lookup"><span data-stu-id="3ac71-107">For example, row height information cannot be stored in a <xref:System.Windows.Forms.DataGridViewCellStyle>, so you must use a row template to change the default height used by all rows.</span></span> <span data-ttu-id="3ac71-108">Шаблон строки вариант также полезен при создании собственных классов, производных от <xref:System.Windows.Forms.DataGridViewRow> и пользовательского типа используется при добавлении новых строк в элемент управления.</span><span class="sxs-lookup"><span data-stu-id="3ac71-108">The row template is also useful when you create your own classes derived from <xref:System.Windows.Forms.DataGridViewRow> and you want your custom type used when new rows are added to the control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3ac71-109">Шаблон строки используется только в том случае, если добавляются строки.</span><span class="sxs-lookup"><span data-stu-id="3ac71-109">The row template is used only when rows are added.</span></span> <span data-ttu-id="3ac71-110">Существующие строки невозможно изменить, изменив шаблон строки.</span><span class="sxs-lookup"><span data-stu-id="3ac71-110">You cannot change existing rows by changing the row template.</span></span>  
  
### <a name="to-use-the-row-template"></a><span data-ttu-id="3ac71-111">Чтобы использовать шаблон строки</span><span class="sxs-lookup"><span data-stu-id="3ac71-111">To use the row template</span></span>  
  
-   <span data-ttu-id="3ac71-112">Задать свойства объекта, полученного из <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> свойство.</span><span class="sxs-lookup"><span data-stu-id="3ac71-112">Set properties on the object retrieved from the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3ac71-113">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="3ac71-113">Compiling the Code</span></span>  
 <span data-ttu-id="3ac71-114">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="3ac71-114">This example requires:</span></span>  
  
-   <span data-ttu-id="3ac71-115">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="3ac71-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="3ac71-116">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3ac71-116">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType>, and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ac71-117">См. также</span><span class="sxs-lookup"><span data-stu-id="3ac71-117">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="3ac71-118">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ac71-118">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="3ac71-119">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="3ac71-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)
