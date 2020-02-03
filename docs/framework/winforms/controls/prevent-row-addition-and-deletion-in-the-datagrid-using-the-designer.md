---
title: Предотвращение добавления и удаления строк в элементе управления DataGridView с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cc9aff0f15d1bd6de5c469ee7069a99f3360837a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728710"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="000c2-102">Практическое руководство. Запрет добавления и удаления строк элемента управления DataGridView в Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="000c2-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="000c2-103">Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="000c2-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="000c2-104">Новые строки будут введены в специальную строку для новых записей в нижней части элемента управления.</span><span class="sxs-lookup"><span data-stu-id="000c2-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="000c2-105">При отключении добавления строк строка для новых записей не отображается.</span><span class="sxs-lookup"><span data-stu-id="000c2-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="000c2-106">После этого элемент управления можно сделать доступным только для чтения, отключив удаление строк и изменение ячеек.</span><span class="sxs-lookup"><span data-stu-id="000c2-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="000c2-107">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="000c2-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="000c2-108">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="000c2-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="000c2-109">Предотвращение добавления и удаления строк</span><span class="sxs-lookup"><span data-stu-id="000c2-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="000c2-110">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу элемента управления <xref:System.Windows.Forms.DataGridView>, а затем снимите флажки **включить добавление** и **включить удаление** .</span><span class="sxs-lookup"><span data-stu-id="000c2-110">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="000c2-111">Чтобы сделать элемент управления доступным только для чтения, снимите флажок **включить редактирование** .</span><span class="sxs-lookup"><span data-stu-id="000c2-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="000c2-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="000c2-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="000c2-113">Как создать проект приложения Windows Forms</span><span class="sxs-lookup"><span data-stu-id="000c2-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="000c2-114">Практическое руководство. Добавление элементов управления в формы Windows Forms</span><span class="sxs-lookup"><span data-stu-id="000c2-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
