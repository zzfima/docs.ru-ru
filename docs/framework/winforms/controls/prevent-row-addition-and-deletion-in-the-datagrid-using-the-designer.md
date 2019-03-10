---
title: Практическое руководство. Предотвращение добавления и удаления в элементе управления DataGridView формы Windows с помощью конструктора строк
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: 52514c07313a60bac8e2c7142b66099dbcd779e5
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714743"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="4937b-102">Практическое руководство. Предотвращение добавления и удаления в элементе управления DataGridView формы Windows с помощью конструктора строк</span><span class="sxs-lookup"><span data-stu-id="4937b-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="4937b-103">Иногда необходимо запретить пользователям вставлять новые строки данных или удалять существующие из элемента управления <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="4937b-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4937b-104">Новые строки добавляются в специальную строку для новых записей в нижней части элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4937b-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="4937b-105">При отключении функции добавления, не отображается строка для новых записей.</span><span class="sxs-lookup"><span data-stu-id="4937b-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="4937b-106">Вы можете затем сделать элемент управления доступным только для чтения, отключив удаления строк и редактирования ячейки.</span><span class="sxs-lookup"><span data-stu-id="4937b-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="4937b-107">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.DataGridView> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="4937b-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="4937b-108">Сведения о настройке такого проекта см. в разделе [как: Создайте проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как: Добавление элементов управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4937b-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4937b-109">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="4937b-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4937b-110">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="4937b-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4937b-111">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="4937b-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="4937b-112">Чтобы избежать добавления и удаления строк</span><span class="sxs-lookup"><span data-stu-id="4937b-112">To prevent row addition and deletion</span></span>  
  
-   <span data-ttu-id="4937b-113">Щелкните глиф смарт-тега (![глиф смарт-тега](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) в правом верхнем углу <xref:System.Windows.Forms.DataGridView> управления, а затем снимите **разрешить добавление** и **Разрешить удаление** флажки.</span><span class="sxs-lookup"><span data-stu-id="4937b-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4937b-114">Чтобы сделать элемент управления доступным только для чтения, снимите **Разрешить изменение** также флажок.</span><span class="sxs-lookup"><span data-stu-id="4937b-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4937b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="4937b-115">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- <span data-ttu-id="4937b-116">[Практическое руководство. Создание проекта приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project).</span><span class="sxs-lookup"><span data-stu-id="4937b-116">[How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project)</span></span>
- [<span data-ttu-id="4937b-117">Практическое руководство. Добавление элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4937b-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
