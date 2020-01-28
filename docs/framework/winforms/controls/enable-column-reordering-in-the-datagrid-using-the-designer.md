---
title: Включение изменения порядка столбцов в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: 823c0064b2710ab5dfd0f67edf95374590d4490b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745841"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="25e41-102">Практическое руководство. Разрешение изменения порядка столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="25e41-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="25e41-103">При просмотре данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, пользователям иногда требуется сравнить значения в конкретных столбцах.</span><span class="sxs-lookup"><span data-stu-id="25e41-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="25e41-104">Это может оказаться неудобным, если столбцы широко разделены в элементе управления, особенно если для просмотра всех интересующих вас столбцов пользователи должны прокручиваться по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="25e41-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="25e41-105">Можно упростить задачу сравнения значений столбцов, позволяя пользователям изменять порядок столбцов.</span><span class="sxs-lookup"><span data-stu-id="25e41-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="25e41-106">При включении переупорядочения столбцов пользователи могут перемещать столбец в новую точку, перетаскивая заголовок столбца с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="25e41-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>

 <span data-ttu-id="25e41-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="25e41-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="25e41-108">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="25e41-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-enable-column-reordering"></a><span data-ttu-id="25e41-109">Включение изменения порядка столбцов</span><span class="sxs-lookup"><span data-stu-id="25e41-109">To enable column reordering</span></span>

- <span data-ttu-id="25e41-110">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **включить изменение порядка столбцов**.</span><span class="sxs-lookup"><span data-stu-id="25e41-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>

## <a name="see-also"></a><span data-ttu-id="25e41-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="25e41-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="25e41-112">Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="25e41-112">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="25e41-113">Как создать проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25e41-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="25e41-114">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="25e41-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
