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
ms.openlocfilehash: 5ce43054130db88792acab852b1e886285ff34d7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116055"
---
# <a name="how-to-customize-data-formatting-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cefe9-102">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cefe9-102">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cefe9-103">В следующем примере кода показано, как реализовать обработчик для события <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>, которое изменяет способ отображения ячеек в зависимости от их столбцов и значений.</span><span class="sxs-lookup"><span data-stu-id="cefe9-103">The following code example demonstrates how to implement a handler for the <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> event that changes how cells are displayed depending on their columns and values.</span></span>  
  
 <span data-ttu-id="cefe9-104">Ячейки в столбце `Balance`, которые содержат отрицательные числа, имеют красный фон.</span><span class="sxs-lookup"><span data-stu-id="cefe9-104">Cells in the `Balance` column that contain negative numbers are given a red background.</span></span> <span data-ttu-id="cefe9-105">Также можно отформатировать эти ячейки в денежном формате для отображения отрицательных значений в круглых скобках.</span><span class="sxs-lookup"><span data-stu-id="cefe9-105">You can also format these cells as currency to display parentheses around negative values.</span></span> <span data-ttu-id="cefe9-106">Дополнительные сведения см. в разделе [Как Форматирование данных в Windows Forms элемента управления DataGridView](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="cefe9-106">For more information, see [How to: Format Data in the Windows Forms DataGridView Control](how-to-format-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="cefe9-107">В ячейках столбца `Priority` отображаются изображения вместо соответствующих текстовых значений.</span><span class="sxs-lookup"><span data-stu-id="cefe9-107">Cells in the `Priority` column display images in place of corresponding textual cell values.</span></span> <span data-ttu-id="cefe9-108">Свойство <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> объекта <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> используется для получения значения текстовой ячейки и задания соответствующего значения отображаемого изображения.</span><span class="sxs-lookup"><span data-stu-id="cefe9-108">The <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> property of the <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> is used both to get the textual cell value and to set the corresponding image display value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cefe9-109">Пример</span><span class="sxs-lookup"><span data-stu-id="cefe9-109">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/cs/customFormatting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewCustomizeDataFormatting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCustomizeDataFormatting/vb/customFormatting.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cefe9-110">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="cefe9-110">Compiling the Code</span></span>  
 <span data-ttu-id="cefe9-111">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="cefe9-111">This example requires:</span></span>  
  
-   <span data-ttu-id="cefe9-112">ссылки на сборки System, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="cefe9-112">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
-   <xref:System.Drawing.Bitmap> <span data-ttu-id="cefe9-113">изображения с именем `highPri.bmp`, `mediumPri.bmp`, и `lowPri.bmp` находящихся в том же каталоге, что и исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="cefe9-113">images named `highPri.bmp`, `mediumPri.bmp`, and `lowPri.bmp` residing in the same directory as the executable file.</span></span>  
  
 <span data-ttu-id="cefe9-114">Сведения о выполнении сборки этого примера из командной строки для Visual Basic или Visual C#, см. в разделе [построение из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) или [командной строки создания с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="cefe9-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cefe9-115">Можно также сборке этого примера в Visual Studio путем вставки кода в новый проект.</span><span class="sxs-lookup"><span data-stu-id="cefe9-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefe9-116">См. также</span><span class="sxs-lookup"><span data-stu-id="cefe9-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Drawing.Bitmap>
- [<span data-ttu-id="cefe9-117">Отображение данных с помощью элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cefe9-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cefe9-118">Практическое руководство. Форматирование данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cefe9-118">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cefe9-119">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cefe9-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="cefe9-120">Форматирование данных в элементе управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cefe9-120">Data Formatting in the Windows Forms DataGridView Control</span></span>](data-formatting-in-the-windows-forms-datagridview-control.md)
