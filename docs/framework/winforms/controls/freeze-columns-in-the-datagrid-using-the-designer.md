---
title: Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], column freezing
- data [Windows Forms], displaying
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
ms.openlocfilehash: 7ebdf7a1598ac3cd61005ae607e5bfbe7cb49059
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933715"
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="f1201-102">Практическое руководство. Замораживание столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f1201-102">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="f1201-103">При просмотре пользователями данных, отображаемых в элементе управления Windows Forms <xref:System.Windows.Forms.DataGridView>, им порой требуется часто обращаться к одному столбцу или набору столбцов.</span><span class="sxs-lookup"><span data-stu-id="f1201-103">When users view data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, they sometimes need to refer to a single column or set of columns frequently.</span></span> <span data-ttu-id="f1201-104">Например, при отображении таблицы с информацией о клиенте, содержащей много столбцов, полезно отображать имя клиента всегда, одновременно позволяя другим столбцам прокручиваться за пределами видимой области.</span><span class="sxs-lookup"><span data-stu-id="f1201-104">For example, when you display a table of customer information that contains many columns, it is useful for you to display the customer name at all times while enabling other columns to scroll outside the visible region.</span></span>

 <span data-ttu-id="f1201-105">Для этого необходимо закрепить столбцы в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="f1201-105">To achieve this behavior, you can freeze columns in the control.</span></span> <span data-ttu-id="f1201-106">При закреплении столбца все столбцы слева от него (или справа для языков с направлением письма справа налево) также закрепляются.</span><span class="sxs-lookup"><span data-stu-id="f1201-106">When you freeze a column, all the columns to its left (or to its right in right-to-left language scripts) are frozen as well.</span></span> <span data-ttu-id="f1201-107">Закрепленные столбцы остаются на месте в то время, как остальные столбцы можно прокручивать.</span><span class="sxs-lookup"><span data-stu-id="f1201-107">Frozen columns remain in place while all other columns can scroll.</span></span> <span data-ttu-id="f1201-108">Если разрешено переупорядочивание столбцов, закрепленные столбцы рассматриваются как группа, отличная от группы незакрепленных столбцов.</span><span class="sxs-lookup"><span data-stu-id="f1201-108">If column reordering is enabled, the frozen columns are treated as a group distinct from the unfrozen columns.</span></span> <span data-ttu-id="f1201-109">Пользователи могут переставлять местами столбцы в каждой из групп, но не могут перемещать столбцы из одной группы в другую.</span><span class="sxs-lookup"><span data-stu-id="f1201-109">Users can reposition columns in either group, but they cannot move a column from one group to the other.</span></span>

 <span data-ttu-id="f1201-110">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="f1201-110">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f1201-111">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f1201-111">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-freeze-a-column-using-the-designer"></a><span data-ttu-id="f1201-112">Закрепление столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f1201-112">To freeze a column using the designer</span></span>

1. <span data-ttu-id="f1201-113">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="f1201-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="f1201-114">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="f1201-114">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="f1201-115">В сетке **Свойства столбца** задайте <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> для `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="f1201-115">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f1201-116">Можно также закрепить столбец при его добавлении, выбрав зафиксированное поле в диалоговом окне **Добавление столбца** .</span><span class="sxs-lookup"><span data-stu-id="f1201-116">You can also freeze a column when adding it by selecting the **Frozen** box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1201-117">См. также</span><span class="sxs-lookup"><span data-stu-id="f1201-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>
- [<span data-ttu-id="f1201-118">Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f1201-118">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="f1201-119">Практическое руководство. Включение изменения порядка столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="f1201-119">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="f1201-120">[Практическое руководство. Отображение текста справа налево в Windows Forms для глобализации](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f1201-120">[How to: Display Right-to-Left Text in Windows Forms for Globalization](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/7d3337xw(v=vs.100))</span></span>
- <span data-ttu-id="f1201-121">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="f1201-121">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="f1201-122">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1201-122">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
