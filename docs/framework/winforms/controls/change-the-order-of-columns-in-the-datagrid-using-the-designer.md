---
title: Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: bf77cf3705a470bbe00be383f6a5cb2d28bda34d
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039635"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ff1b4-102">Практическое руководство. Изменение порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ff1b4-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>

<span data-ttu-id="ff1b4-103">При привязке Windows Forms <xref:System.Windows.Forms.DataGridView> элемента управления к источнику данных порядок вывода автоматически создаваемых столбцов определяется источником данных.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="ff1b4-104">Если этот порядок не является предпочтительным, можно изменить порядок столбцов с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="ff1b4-105">Кроме того, может потребоваться добавить в элемент управления несвязанные столбцы и изменить их порядок их вывода.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="ff1b4-106">Дополнительные сведения об изменении порядка столбцов программным способом см. в [разделе как Изменение порядка столбцов в элементе управления](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)Windows Forms DataGridView.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>

<span data-ttu-id="ff1b4-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ff1b4-108">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="ff1b4-109">Изменение порядка столбцов с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ff1b4-109">To change the column order using the designer</span></span>

1. <span data-ttu-id="ff1b4-110">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="ff1b4-111">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="ff1b4-111">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="ff1b4-112">Щелкните стрелку вверх или вниз справа от списка **Выбранные столбцы** , пока выбранный столбец не будет расположен в нужном месте.</span><span class="sxs-lookup"><span data-stu-id="ff1b4-112">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff1b4-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ff1b4-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ff1b4-114">Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="ff1b4-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="ff1b4-115">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="ff1b4-115">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="ff1b4-116">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ff1b4-116">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
