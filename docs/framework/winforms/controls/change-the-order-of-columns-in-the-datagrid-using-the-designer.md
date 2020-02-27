---
title: Изменение порядка столбцов в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 7540203fb1c0465caeb045275734d1a7c6f25ee8
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628752"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="aeba5-102">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="aeba5-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="aeba5-103">При привязке элемента управления Windows Forms <xref:System.Windows.Forms.DataGridView> к источнику данных порядок вывода автоматически создаваемых столбцов определяется источником данных.</span><span class="sxs-lookup"><span data-stu-id="aeba5-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="aeba5-104">Если этот порядок не является предпочтительным, можно изменить порядок столбцов с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="aeba5-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="aeba5-105">Кроме того, может потребоваться добавить в элемент управления несвязанные столбцы и изменить их порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="aeba5-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="aeba5-106">Дополнительные сведения об изменении порядка столбцов программным способом см. в разделе [как изменить порядок столбцов в элементе управления Windows Forms DataGridView](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="aeba5-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="aeba5-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="aeba5-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="aeba5-108">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="aeba5-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="aeba5-109">Изменение порядка столбцов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="aeba5-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="aeba5-110">Щелкните глиф действия конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="aeba5-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="aeba5-111">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="aeba5-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="aeba5-112">Щелкните стрелку вверх или вниз справа от списка **Выбранные столбцы** , пока выбранный столбец не будет расположен в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="aeba5-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="aeba5-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="aeba5-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="aeba5-114">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="aeba5-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="aeba5-115">Как создать проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aeba5-115">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="aeba5-116">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aeba5-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
