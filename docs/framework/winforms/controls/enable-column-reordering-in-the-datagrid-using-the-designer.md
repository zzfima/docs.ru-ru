---
title: Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 3864ce70f058259b597df904311bd4a48218b151
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040348"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="9ce80-102">Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9ce80-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="9ce80-103">При просмотре данных, отображаемых <xref:System.Windows.Forms.DataGridView> в элементе управления Windows Forms, пользователям иногда требуется сравнить значения в конкретных столбцах.</span><span class="sxs-lookup"><span data-stu-id="9ce80-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="9ce80-104">Это может оказаться неудобным, если столбцы широко разделены в элементе управления, особенно если для просмотра всех интересующих вас столбцов пользователи должны прокручиваться по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="9ce80-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="9ce80-105">Можно упростить задачу сравнения значений столбцов, позволяя пользователям изменять порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="9ce80-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="9ce80-106">При включении переупорядочения столбцов пользователи могут перемещать столбец в новую точку, перетаскивая заголовок столбца с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="9ce80-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="9ce80-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="9ce80-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9ce80-108">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="9ce80-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="9ce80-109">Включение изменения порядка столбцов</span><span class="sxs-lookup"><span data-stu-id="9ce80-109">To enable column reordering</span></span>

- <span data-ttu-id="9ce80-110">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **включить изменение порядка столбцов**.</span><span class="sxs-lookup"><span data-stu-id="9ce80-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="9ce80-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9ce80-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9ce80-112">Практическое руководство. Закрепление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="9ce80-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="9ce80-113">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="9ce80-113">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="9ce80-114">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9ce80-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
