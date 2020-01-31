---
title: Отображение изображений в ячейках элемента управления DataGridView
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
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740286"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a><span data-ttu-id="980eb-102">Практическое руководство. Вывод изображений в ячейках элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="980eb-102">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="980eb-103">Изображение или рисунок — это одно из значений, которое можно отобразить в строке данных.</span><span class="sxs-lookup"><span data-stu-id="980eb-103">A picture or graphic is one of the values that you can display in a row of data.</span></span> <span data-ttu-id="980eb-104">Часто эти графические изображения имеют форму фотографии сотрудника или логотипа компании.</span><span class="sxs-lookup"><span data-stu-id="980eb-104">Frequently, these graphics take the form of an employee's photograph or a company logo.</span></span>  
  
 <span data-ttu-id="980eb-105">Внедрение рисунков выполняется просто при отображении данных в элементе управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="980eb-105">Incorporating pictures is simple when you display data within the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="980eb-106">Элемент управления <xref:System.Windows.Forms.DataGridView> изначально обрабатывает любой формат изображения, поддерживаемый классом <xref:System.Drawing.Image>, а также формат изображения OLE, используемый некоторыми базами данных.</span><span class="sxs-lookup"><span data-stu-id="980eb-106">The <xref:System.Windows.Forms.DataGridView> control natively handles any image format supported by the <xref:System.Drawing.Image> class, as well as the OLE picture format used by some databases.</span></span>  
  
 <span data-ttu-id="980eb-107">Если источник данных элемента управления <xref:System.Windows.Forms.DataGridView> имеет столбец изображений, они будут автоматически отображаться элементом управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="980eb-107">If the <xref:System.Windows.Forms.DataGridView> control's data source has a column of images, they will be displayed automatically by the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="980eb-108">В следующем примере кода показано, как извлечь значок из внедренного ресурса и преобразовать его в точечный рисунок для отображения в каждой ячейке столбца Image.</span><span class="sxs-lookup"><span data-stu-id="980eb-108">The following code example demonstrates how to extract an icon from an embedded resource and convert it to a bitmap for display in every cell of an image column.</span></span> <span data-ttu-id="980eb-109">Другой пример, в котором текстовые значения ячеек заменяются соответствующими изображениями, см. в разделе [как настроить форматирование данных в элементе управления Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="980eb-109">For another example that replaces textual cell values with corresponding images, see [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="980eb-110">Пример</span><span class="sxs-lookup"><span data-stu-id="980eb-110">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="980eb-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="980eb-111">Compiling the Code</span></span>  
 <span data-ttu-id="980eb-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="980eb-112">This example requires:</span></span>  
  
- <span data-ttu-id="980eb-113">элемент управления <xref:System.Windows.Forms.DataGridView> с именем `dataGridView1`;</span><span class="sxs-lookup"><span data-stu-id="980eb-113">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
- <span data-ttu-id="980eb-114">Внедренный ресурс значка с именем `tree.ico`.</span><span class="sxs-lookup"><span data-stu-id="980eb-114">An embedded icon resource named `tree.ico`.</span></span>  
  
- <span data-ttu-id="980eb-115">ссылки на сборки <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> и <xref:System.Drawing?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="980eb-115">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Drawing?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="980eb-116">См. также:</span><span class="sxs-lookup"><span data-stu-id="980eb-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="980eb-117">Базовые характеристики столбцов, строк и ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="980eb-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [<span data-ttu-id="980eb-118">Практическое руководство. Настройка форматирования данных элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="980eb-118">How to: Customize Data Formatting in the Windows Forms DataGridView Control</span></span>](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
