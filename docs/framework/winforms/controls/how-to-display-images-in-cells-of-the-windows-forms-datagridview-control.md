---
title: Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 90aaff419ecc2c890a8b3802f3aaf12092febb73
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083001"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="0fd29-102">Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fd29-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="0fd29-103">Рисунок или изображение — одно из значений, которые можно отобразить в строку данных.</span><span class="sxs-lookup"><span data-stu-id="0fd29-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="0fd29-104">Часто эти графики принимать форму фотографию сотрудника или логотип компании.</span><span class="sxs-lookup"><span data-stu-id="0fd29-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="0fd29-105">Применение рисунков очень просто при отображении данных в пределах <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0fd29-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="0fd29-106"><xref:System.Windows.Forms.DataGridView> В собственном коде обработки любого формата изображений, поддерживаемых элементом управления <xref:System.Drawing.Image> класса, а также OLE рисунка формат, используемый в некоторых базах данных.</span><span class="sxs-lookup"><span data-stu-id="0fd29-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="0fd29-107">Если <xref:System.Windows.Forms.DataGridView> элемента управления источника данных со столбцом изображений, они будут отображаться автоматически <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="0fd29-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="0fd29-108">В следующем примере кода показано, как извлекать значок из внедренного ресурса и преобразовать его в растровое изображение для отображения во всех ячейках столбец типа image.</span><span class="sxs-lookup"><span data-stu-id="0fd29-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="0fd29-109">Еще один пример, который заменяет соответствующие образы текстовые значения ячеек, см. в разделе [как: Настройка форматирования данных в элементе управления DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0fd29-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fd29-110">Пример</span><span class="sxs-lookup"><span data-stu-id="0fd29-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0fd29-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="0fd29-111">Compiling the Code</span></span>  
 <span data-ttu-id="0fd29-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="0fd29-112">This example requires:</span></span>  
  
-   <span data-ttu-id="0fd29-113">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="0fd29-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="0fd29-114">Ресурс со встроенным значком с именем `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="0fd29-114">An embedded icon resource named `tree.ico`.</span></span>  
  
-   <span data-ttu-id="0fd29-115">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0fd29-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fd29-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0fd29-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="0fd29-117">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fd29-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="0fd29-118">Практическое руководство. Настройка форматирования данных в элементе управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0fd29-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
