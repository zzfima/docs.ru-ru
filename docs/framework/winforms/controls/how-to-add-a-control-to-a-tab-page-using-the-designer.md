---
title: Практическое руководство. Добавление элемента управления на вкладку с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- TabPage control
- tab controls [Windows Forms], tab order
- tab pages [Windows Forms], adding controls
ms.assetid: 7ee734e1-e31e-4ed0-bbc0-a7e8a1f20fef
ms.openlocfilehash: 1bd6050287df288b41f944232d36d2e77c1309d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-add-a-control-to-a-tab-page-using-the-designer"></a><span data-ttu-id="b59c3-102">Практическое руководство. Добавление элемента управления на вкладку с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="b59c3-102">How to: Add a Control to a Tab Page Using the Designer</span></span>
<span data-ttu-id="b59c3-103">Использование Windows Forms <xref:System.Windows.Forms.TabControl> — отображение других элементов управления в структуру предприятия.</span><span class="sxs-lookup"><span data-stu-id="b59c3-103">The use of the Windows Forms <xref:System.Windows.Forms.TabControl> is to display other controls in an organized fashion.</span></span> <span data-ttu-id="b59c3-104">Эти инструкции можно использовать для отображения рисунков в основной части вкладки.</span><span class="sxs-lookup"><span data-stu-id="b59c3-104">You can use these instructions to display a picture on the main part of a tab page.</span></span> <span data-ttu-id="b59c3-105">Сведения о добавлении значка в часть метки страницу вкладки см [как: изменение внешнего вида элемента управления TabControl в Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span><span class="sxs-lookup"><span data-stu-id="b59c3-105">For information about adding an icon to the label part of a tab page, see [How to: Change the Appearance of the Windows Forms TabControl](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).</span></span>  
  
 <span data-ttu-id="b59c3-106">В следующей процедуре требуется **приложение Windows** проекта с формой, содержащей <xref:System.Windows.Forms.TabControl> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="b59c3-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="b59c3-107">Сведения о настройке такого проекта см. в разделе [как: Создание проекта приложения Windows](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) и [как: Добавление элементов управления в Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="b59c3-107">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b59c3-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="b59c3-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="b59c3-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="b59c3-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="b59c3-110">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="b59c3-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-control-using-the-designer"></a><span data-ttu-id="b59c3-111">Чтобы добавить элемент управления с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="b59c3-111">To add a control using the designer</span></span>  
  
1.  <span data-ttu-id="b59c3-112">Щелкните соответствующую вкладку, чтобы он отображался в верхней части страницы.</span><span class="sxs-lookup"><span data-stu-id="b59c3-112">Click the appropriate tab page so that it appears on top.</span></span>  
  
2.  <span data-ttu-id="b59c3-113">Разместите элемент управления на странице вкладки.</span><span class="sxs-lookup"><span data-stu-id="b59c3-113">Draw the control on the tab page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b59c3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="b59c3-114">See Also</span></span>  
 [<span data-ttu-id="b59c3-115">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="b59c3-115">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="b59c3-116">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="b59c3-116">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="b59c3-117">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b59c3-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)  
 [<span data-ttu-id="b59c3-118">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="b59c3-118">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="b59c3-119">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b59c3-119">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
