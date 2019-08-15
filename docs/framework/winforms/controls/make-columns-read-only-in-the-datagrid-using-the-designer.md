---
title: Практическое руководство. Включение режима "только для чтения" для столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- DataGridView control [Windows Forms], read-only columns
- data [Windows Forms], displaying
- columns [Windows Forms], read-only
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
ms.openlocfilehash: 6bdd561c863a461f43a5a7aac025fead1f971bb0
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039809"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="c1ca7-102">Практическое руководство. Включение режима "только для чтения" для столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c1ca7-102">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="c1ca7-103">По умолчанию пользователи могут изменять текст и числовые данные, отображаемые <xref:System.Windows.Forms.DataGridView> в элементе управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-103">By default, users can modify text and numerical data displayed in the Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c1ca7-104">Если требуется отобразить данные, не предназначенные для изменения, необходимо сделать столбцы, содержащие данные, только для чтения.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-104">If you want to display data that is not meant for modification, you must make the columns that contain the data read-only.</span></span> <span data-ttu-id="c1ca7-105">Сведения о том, как сделать элемент управления доступным только для чтения, см [. в разделе как Предотвращение добавления и удаления строк в элементе управления Windows Forms DataGridView с помощью конструктора](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="c1ca7-105">For information about how to make the control entirely read-only, see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).</span></span>

 <span data-ttu-id="c1ca7-106">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="c1ca7-107">Сведения о настройке такого проекта см. в разделе [как Создайте проект](/visualstudio/ide/step-1-create-a-windows-forms-application-project) приложения Windows Forms и [выполните следующие действия. Добавьте элементы управления в](how-to-add-controls-to-windows-forms.md)Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-make-a-column-read-only-by-using-the-designer"></a><span data-ttu-id="c1ca7-108">Создание столбца, доступного только для чтения, с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c1ca7-108">To make a column read-only by using the designer</span></span>

1. <span data-ttu-id="c1ca7-109">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем <xref:System.Windows.Forms.DataGridView> углу элемента управления, а затем выберите **изменить столбцы**.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-109">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>

2. <span data-ttu-id="c1ca7-110">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="c1ca7-110">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="c1ca7-111">В сетке **Свойства столбца** задайте <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> для `true`свойства значение.</span><span class="sxs-lookup"><span data-stu-id="c1ca7-111">In the **Column Properties** grid, set the <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> property to `true`.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c1ca7-112">Можно также сделать столбец только для чтения при его добавлении, установив флажок **только чтение** в диалоговом окне **Добавление столбца** .</span><span class="sxs-lookup"><span data-stu-id="c1ca7-112">You can also make a column read-only when you add it by selecting the **Read Only** check box in the **Add Column** dialog box.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1ca7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c1ca7-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c1ca7-114">Практическое руководство. Добавление и удаление столбцов в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c1ca7-114">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="c1ca7-115">Практическое руководство. Предотвращение добавления и удаления строк в элементе управления Windows Forms DataGridView с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c1ca7-115">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)
- <span data-ttu-id="c1ca7-116">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="c1ca7-116">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="c1ca7-117">Практическое руководство. Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1ca7-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
