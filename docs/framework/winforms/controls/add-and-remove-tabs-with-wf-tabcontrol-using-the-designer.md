---
title: Практическое руководство. Добавление и удаление вкладок с использованием элемента управления TabControl в формах Windows Forms с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 51f84a1272749b92f8ef4a74771c84e01511a678
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521330"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="c64b2-102">Практическое руководство. Добавление и удаление вкладок с использованием элемента управления TabControl в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c64b2-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="c64b2-103">При размещении <xref:System.Windows.Forms.TabControl> элемента управления в форме, он содержит две вкладки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c64b2-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="c64b2-104">Можно добавить или удалить вкладки с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="c64b2-104">You can add or remove tabs using the designer.</span></span>  
  
 <span data-ttu-id="c64b2-105">Следующая процедура требуется **приложения Windows** проекта с формой, содержащей <xref:System.Windows.Forms.TabControl> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="c64b2-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="c64b2-106">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="c64b2-106">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c64b2-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="c64b2-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="c64b2-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="c64b2-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="c64b2-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="c64b2-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="c64b2-110">Чтобы добавить или удалить вкладку с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="c64b2-110">To add or remove a tab using the designer</span></span>  
  
-   <span data-ttu-id="c64b2-111">В смарт-теге элемента управления, нажмите кнопку **добавить вкладку** или **удалить вкладку**</span><span class="sxs-lookup"><span data-stu-id="c64b2-111">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>  
  
     <span data-ttu-id="c64b2-112">- или -</span><span class="sxs-lookup"><span data-stu-id="c64b2-112">-or-</span></span>  
  
     <span data-ttu-id="c64b2-113">В **свойства** окно, нажмите кнопку **кнопку с многоточием** кнопки (![экрана VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) рядом с полем <xref:System.Windows.Forms.TabControl.TabPages%2A> свойства, чтобы открыть **редактор коллекции TabPage**.</span><span class="sxs-lookup"><span data-stu-id="c64b2-113">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="c64b2-114">Нажмите кнопку **добавить** или **удалить** кнопки.</span><span class="sxs-lookup"><span data-stu-id="c64b2-114">Click the **Add** or **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64b2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="c64b2-115">See Also</span></span>  
 [<span data-ttu-id="c64b2-116">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="c64b2-116">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="c64b2-117">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="c64b2-117">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="c64b2-118">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="c64b2-118">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="c64b2-119">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="c64b2-119">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="c64b2-120">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c64b2-120">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
