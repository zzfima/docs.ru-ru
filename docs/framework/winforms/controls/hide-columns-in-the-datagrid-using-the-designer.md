---
title: Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], hiding
- DataGridView control [Windows Forms], column hiding
- data [Windows Forms], displaying
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
ms.openlocfilehash: d502a89913e108254848151e9058ac6ae83a9638
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039774"
---
# <a name="how-to-hide-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="76be9-102">Практическое руководство. Скрытие столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="76be9-102">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="76be9-103">Иногда требуется показать только некоторые из столбцов, доступных в элементе управления <xref:System.Windows.Forms.DataGridView> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="76be9-103">Sometimes you will want to display only some of the columns that are available in a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="76be9-104">Например, можно отобразить столбец заработной платы сотрудника для пользователей с учетными данными управления, скрывая их от других пользователей.</span><span class="sxs-lookup"><span data-stu-id="76be9-104">For example, you may want to show an employee salary column to users with management credentials while hiding it from other users.</span></span> <span data-ttu-id="76be9-105">Кроме того, может потребоваться привязать элемент управления к источнику данных, содержащему много столбцов, только некоторые из которых нужно отобразить.</span><span class="sxs-lookup"><span data-stu-id="76be9-105">Alternately, you may want to bind the control to a data source that contains many columns, only some of which you want to display.</span></span> <span data-ttu-id="76be9-106">В этом случае вы обычно удаляете столбцы, которые не нужны для отображения, а не скрывают их.</span><span class="sxs-lookup"><span data-stu-id="76be9-106">In this case, you will typically remove the columns you are not interested in displaying rather than hiding them.</span></span> <span data-ttu-id="76be9-107">Дополнительные сведения см. в разделе [Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="76be9-107">For more information, see [How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer](add-and-remove-columns-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="76be9-108">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="76be9-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="76be9-109">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="76be9-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-hide-a-column-using-the-designer"></a><span data-ttu-id="76be9-110">Скрытие столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="76be9-110">To hide a column using the designer</span></span>

1. <span data-ttu-id="76be9-111">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="76be9-111">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="76be9-112">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="76be9-112">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="76be9-113">В сетке **Свойства столбца** задайте <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> для `false`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="76be9-113">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> property to `false`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="76be9-114">Можно также скрыть столбец при его добавлении, сняв флажок Видимый в диалоговом окне **Добавление столбца** .</span><span class="sxs-lookup"><span data-stu-id="76be9-114">You can also hide a column when adding it by clearing the **Visible** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="76be9-115">См. также</span><span class="sxs-lookup"><span data-stu-id="76be9-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=nameWithType>
- [<span data-ttu-id="76be9-116">Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="76be9-116">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="76be9-117">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="76be9-117">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="76be9-118">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="76be9-118">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
