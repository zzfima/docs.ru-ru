---
title: Установка чередующихся стилей строк для элемента управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ledger-like formats
- DataGridView control [Windows Forms], row style alternation
- Windows Forms, rows
- rows [Windows Forms], alternating
- data [Windows Forms], displaying
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
ms.openlocfilehash: 74f65d03a359136de943f8a2937ed5e5f1e62519
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743045"
---
# <a name="how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ff9dd-102">Практическое руководство. Установка стилей для чередующихся строк в элементе управления DataGridView формы Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ff9dd-102">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="ff9dd-103">Табличные данные часто представляются в формате, похожем на формат книги, где чередующиеся строки имеют разные цвета фона.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-103">Tabular data is often presented in a ledger-like format where alternating rows have different background colors.</span></span> <span data-ttu-id="ff9dd-104">Такой формат позволяет проще определять, какие ячейки находятся в какой строке, что особенно удобно в широких таблицах со множеством столбцов.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-104">This format makes it easier for users to tell which cells are in each row, especially with wide tables that have many columns.</span></span>

<span data-ttu-id="ff9dd-105">С помощью элемента управления <xref:System.Windows.Forms.DataGridView> можно указать полные сведения о стиле для чередующихся строк.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-105">With the <xref:System.Windows.Forms.DataGridView> control, you can specify complete style information for alternating rows.</span></span> <span data-ttu-id="ff9dd-106">Для различения чередующихся строк можно использовать характеристики стиля, такие как цвет переднего плана и шрифт, а также цвет фона.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-106">You can use style characteristics like foreground color and font, in addition to background color, to differentiate alternating rows.</span></span> <span data-ttu-id="ff9dd-107">Дополнительные сведения см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="ff9dd-107">For more information, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="ff9dd-108">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ff9dd-109">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="ff9dd-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

### <a name="define-styles-for-alternating-rows"></a><span data-ttu-id="ff9dd-110">Определение стилей для чередующихся строк</span><span class="sxs-lookup"><span data-stu-id="ff9dd-110">Define styles for alternating rows</span></span>

1. <span data-ttu-id="ff9dd-111">Выберите элемент управления <xref:System.Windows.Forms.DataGridView> в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-111">Select the <xref:System.Windows.Forms.DataGridView> control in the designer.</span></span>

2. <span data-ttu-id="ff9dd-112">В окне **Свойства** нажмите кнопку с многоточием (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-112">In the **Properties** window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> property.</span></span>

3. <span data-ttu-id="ff9dd-113">В диалоговом окне **Построитель** стилей определите стиль, задав свойства, и используйте панель **предварительного просмотра** для подтверждения выбора.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-113">In the **CellStyle Builder** dialog box, define the style by setting the properties, and use the **Preview** pane to confirm your choices.</span></span> <span data-ttu-id="ff9dd-114">Указанные стили используются для каждой другой строки, отображаемой в элементе управления, начиная со второго.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-114">The styles you specify are used for every other row displayed in the control, starting with the second one.</span></span>

4. <span data-ttu-id="ff9dd-115">Чтобы определить стили для оставшихся строк, повторите шаги 2 и 3 с помощью свойства <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-115">To define styles for the remaining rows, repeat steps 2 and 3 using the <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> property.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ff9dd-116">Ячейки отображаются с использованием стилей, унаследованных от нескольких свойств.</span><span class="sxs-lookup"><span data-stu-id="ff9dd-116">Cells are displayed using styles inherited from multiple properties.</span></span> <span data-ttu-id="ff9dd-117">Дополнительные сведения о наследовании стилей см. [в разделе Стили ячеек в элементе управления Windows Forms DataGridView](cell-styles-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="ff9dd-117">For more information about style inheritance, see [Cell Styles in the Windows Forms DataGridView Control](cell-styles-in-the-windows-forms-datagridview-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ff9dd-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="ff9dd-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ff9dd-119">Стили ячеек элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff9dd-119">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ff9dd-120">Базовое форматирование и оформление элемента управления DataGridView в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff9dd-120">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ff9dd-121">Использование конструктора с элементом управления DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff9dd-121">Using the Designer with the Windows Forms DataGridView Control</span></span>](using-the-designer-with-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="ff9dd-122">Как создать проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff9dd-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ff9dd-123">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff9dd-123">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
