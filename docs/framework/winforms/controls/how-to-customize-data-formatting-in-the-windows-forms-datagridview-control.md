---
title: Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting data
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], changing colors in DataGridView control [Windows Forms]
- colors [Windows Forms], changing in DataGridView control [Windows Forms]
- data [Windows Forms], formatting in DataGridView control
- DataGridView control [Windows Forms], cell customization
- DataGridView control [Windows Forms], changing cell colors
- Windows Forms, changing colors of DataGridView cells
- DataGridView control [Windows Forms], substituting cell values for display
- data grids [Windows Forms], formatting data
ms.assetid: a6e72c70-ce18-425f-828d-d57be6f96ab6
ms.openlocfilehash: 948e9bf485b42b445491a4da9f8de7ae7974075c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592824"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="21681-102">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21681-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="21681-103">В следующем примере кода показано, как реализовать обработчик для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>, которое изменяет способ отображения ячеек в зависимости от их столбцов и значений.</span><span class="sxs-lookup"><span data-stu-id="21681-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="21681-104">Ячейки в столбце `Balance`, которые содержат отрицательные числа, имеют красный фон.</span><span class="sxs-lookup"><span data-stu-id="21681-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="21681-105">Также можно отформатировать эти ячейки в денежном формате для отображения отрицательных значений в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="21681-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="21681-106">Дополнительные сведения см. в разделе [Практическое руководство. Форматирование данных в Windows Forms элемента управления DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="21681-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="21681-107">В ячейках столбца `Priority` отображаются изображения вместо соответствующих текстовых значений.</span><span class="sxs-lookup"><span data-stu-id="21681-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="21681-108">Свойство <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> объекта <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> используется для получения значения текстовой ячейки и задания соответствующего значения отображаемого изображения.</span><span class="sxs-lookup"><span data-stu-id="21681-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21681-109">Пример</span><span class="sxs-lookup"><span data-stu-id="21681-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="21681-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="21681-110">Compiling the Code</span></span>  
 <span data-ttu-id="21681-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="21681-111">This example requires:</span></span>  
  
- <span data-ttu-id="21681-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="21681-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
- <span data-ttu-id="21681-113">Изображения <xref:System.Drawing.Bitmap> с именами `highPri.bmp`, `mediumPri.bmp` и `lowPri.bmp` находятся в том же каталоге, что и исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="21681-113"><xref:System.Drawing.Bitmap> images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21681-114">См. также</span><span class="sxs-lookup"><span data-stu-id="21681-114">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="21681-115">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21681-115">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="21681-116">Практическое руководство. Форматирование данных в Windows Forms элемента управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="21681-116">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="21681-117">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21681-117">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="21681-118">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="21681-118">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
