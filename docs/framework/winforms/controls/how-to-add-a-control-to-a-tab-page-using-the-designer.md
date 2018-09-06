---
title: Практическое руководство. Добавление элемента управления на вкладку с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: 7ee734e1-e31e-4ed0-bbc0-a7e8a1f20fef
ms.openlocfilehash: 07326156fabbb8b991538a7e3bbaff7d807a1e94
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43740863"
---
# <a name="how-to-add-a-control-to-a-tab-page-using-the-designer"></a><span data-ttu-id="5f8e7-102">Практическое руководство. Добавление элемента управления на вкладку с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5f8e7-102">How to: Add a Control to a Tab Page Using the Designer</span></span>
<span data-ttu-id="5f8e7-103">Использование Windows Forms <xref:System.Windows.Forms.TabControl> является отображение других элементов управления в структуру предприятия.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-103">The use of the Windows Forms <xref:System.Windows.Forms.TabControl> is to display other controls in an organized fashion.</span></span> <span data-ttu-id="5f8e7-104">Эти инструкции можно использовать для отображения рисунка в основной части вкладки.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-104">You can use these instructions to display a picture on the main part of a tab page.</span></span> <span data-ttu-id="5f8e7-105">Сведения о добавлении значка в часть метки страницы вкладки, см. в разделе [как: изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="5f8e7-105">For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
 <span data-ttu-id="5f8e7-106">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.TabControl> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="5f8e7-107">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="5f8e7-107">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f8e7-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5f8e7-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="5f8e7-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5f8e7-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="5f8e7-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-control-using-the-designer"></a><span data-ttu-id="5f8e7-111">Добавление элемента управления с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="5f8e7-111">To add a control using the designer</span></span>  
  
1.  <span data-ttu-id="5f8e7-112">Щелкните соответствующую вкладку, чтобы он отображался в верхней части.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-112">Click the appropriate tab page so that it appears on top.</span></span>  
  
2.  <span data-ttu-id="5f8e7-113">Нарисуйте элемент управления на странице вкладки.</span><span class="sxs-lookup"><span data-stu-id="5f8e7-113">Draw the control on the tab page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f8e7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5f8e7-114">See Also</span></span>  
 [<span data-ttu-id="5f8e7-115">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="5f8e7-115">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="5f8e7-116">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="5f8e7-116">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="5f8e7-117">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f8e7-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="5f8e7-118">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="5f8e7-118">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="5f8e7-119">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f8e7-119">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
