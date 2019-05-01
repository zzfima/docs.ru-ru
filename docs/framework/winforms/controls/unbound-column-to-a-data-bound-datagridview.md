---
title: Практическое руководство. Добавление столбца, не связанного с данными, в связанный с данными элемент управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
ms.openlocfilehash: 40308f7e8cc12dcff5b7d4393645f6a9007cc2b7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009205"
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a><span data-ttu-id="a8332-102">Практическое руководство. Добавление столбца, не связанного с данными, в связанный с данными элемент управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8332-102">How to: Add an Unbound Column to a Data-Bound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="a8332-103">Данные, отображаемые в элементе управления <xref:System.Windows.Forms.DataGridView>, обычно берутся из какого-либо источника данных, однако может потребоваться отобразить столбец данных, которые получены не из источника данных.</span><span class="sxs-lookup"><span data-stu-id="a8332-103">The data you display in the <xref:System.Windows.Forms.DataGridView> control will normally come from a data source of some kind, but you might want to display a column of data that does not come from the data source.</span></span> <span data-ttu-id="a8332-104">Такой столбец называется непривязанным.</span><span class="sxs-lookup"><span data-stu-id="a8332-104">This kind of column is called an unbound column.</span></span> <span data-ttu-id="a8332-105">Непривязанные столбцы могут принимать различные формы.</span><span class="sxs-lookup"><span data-stu-id="a8332-105">Unbound columns can take many forms.</span></span> <span data-ttu-id="a8332-106">Как правило, они используются для предоставления доступа к сведениям о строке данных.</span><span class="sxs-lookup"><span data-stu-id="a8332-106">Frequently, they are used to provide access to the details of a data row.</span></span>  
  
 <span data-ttu-id="a8332-107">В следующем примере кода демонстрируется создание несвязанного столбца **сведения** кнопки для отображения дочерней таблицы, связанные с определенной строкой в родительской таблице, при реализации сценария «основной/подробности».</span><span class="sxs-lookup"><span data-stu-id="a8332-107">The following code example demonstrates how to create an unbound column of **Details** buttons to display a child table related to a particular row in a parent table when you implement a master/detail scenario.</span></span> <span data-ttu-id="a8332-108">Для реакции на нажатия кнопок реализован обработчик событий <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>, который отображает форму, содержащую дочернюю таблицу.</span><span class="sxs-lookup"><span data-stu-id="a8332-108">To respond to button clicks, implement a <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> event handler that displays a form containing the child table.</span></span>  
  
 <span data-ttu-id="a8332-109">Эта задача поддерживается в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a8332-109">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="a8332-110">Также см. раздел [Как Добавление и удаление столбцов в Windows Forms с помощью конструктора элемента управления DataGridView](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="a8332-110">Also see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8332-111">Пример</span><span class="sxs-lookup"><span data-stu-id="a8332-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a8332-112">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="a8332-112">Compiling the Code</span></span>  
 <span data-ttu-id="a8332-113">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="a8332-113">This example requires:</span></span>  
  
- <span data-ttu-id="a8332-114">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="a8332-114">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="a8332-115">ссылки на сборки <xref:System?displayProperty=nameWithType> и <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a8332-115">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8332-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a8332-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a8332-117">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8332-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="a8332-118">Режимы отображения данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a8332-118">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
