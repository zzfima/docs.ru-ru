---
title: Добавление и удаление столбцов элемента управления DataGridView с помощью конструктора
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 8843b1d30f3e5f31a060e27b41b0105e6584f155
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628609"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="d2455-102">Практическое руководство. Добавление и удаление столбцов элемента управления DataGridView в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d2455-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="d2455-103">Для вывода данных элемент управления <xref:System.Windows.Forms.DataGridView> Windows Forms должен содержать столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2455-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="d2455-104">Если планируется Ручное заполнение элемента управления, необходимо вручную добавить столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2455-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="d2455-105">Кроме того, можно привязать элемент управления к источнику данных, который автоматически создает и заполняет столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2455-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="d2455-106">Если источник данных содержит больше столбцов, чем требуется отобразить, можно удалить ненужные столбцы.</span><span class="sxs-lookup"><span data-stu-id="d2455-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="d2455-107">Для следующих процедур требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="d2455-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d2455-108">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d2455-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="d2455-109">Добавление столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d2455-109">To add a column using the designer</span></span>

1. <span data-ttu-id="d2455-110">Щелкните глиф действия конструктора (![маленькая черная стрелка](./media/designer-actions-glyph.gif)) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем выберите **Добавить столбец**.</span><span class="sxs-lookup"><span data-stu-id="d2455-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="d2455-111">В диалоговом окне **Добавление столбца** выберите параметр **столбец с привязкой** к данным и выберите столбец из источника данных или выберите параметр **несвязанный столбец** и определите столбец с помощью предоставленных полей.</span><span class="sxs-lookup"><span data-stu-id="d2455-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="d2455-112">Нажмите кнопку **Добавить** , чтобы добавить столбец, в результате чего он появится в конструкторе, если существующие столбцы еще не заполнили область отображения элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d2455-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2455-113">Свойства столбцов можно изменить в диалоговом окне **Изменение столбцов** , доступ к которому можно получить из смарт-тега элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d2455-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="d2455-114">Удаление столбца с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="d2455-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="d2455-115">Выберите **изменить столбцы** из смарт-тега элемента управления.</span><span class="sxs-lookup"><span data-stu-id="d2455-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="d2455-116">Выберите столбец из списка **Выбранные столбцы** .</span><span class="sxs-lookup"><span data-stu-id="d2455-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="d2455-117">Нажмите кнопку **Удалить** , чтобы удалить столбец, что приведет к исчезновению его из конструктора.</span><span class="sxs-lookup"><span data-stu-id="d2455-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="d2455-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d2455-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d2455-119">Как создать проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2455-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="d2455-120">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d2455-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
