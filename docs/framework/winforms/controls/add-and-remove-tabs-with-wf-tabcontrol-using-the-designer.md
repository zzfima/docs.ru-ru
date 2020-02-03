---
title: Добавление и удаление вкладок с помощью элемента TabControl в конструкторе
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 445342ffb3b53c880ac38da52076e0c0cb0a9f23
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746283"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="a20c3-102">Практическое руководство. Добавление и удаление вкладок с использованием элемента управления TabControl в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="a20c3-102">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="a20c3-103">При помещении элемента управления <xref:System.Windows.Forms.TabControl> в форму он по умолчанию содержит две вкладки.</span><span class="sxs-lookup"><span data-stu-id="a20c3-103">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="a20c3-104">Можно добавлять или удалять вкладки с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="a20c3-104">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="a20c3-105">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей элемент управления <xref:System.Windows.Forms.TabControl>.</span><span class="sxs-lookup"><span data-stu-id="a20c3-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="a20c3-106">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="a20c3-106">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="a20c3-107">Добавление или удаление вкладки с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="a20c3-107">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="a20c3-108">На смарт-теге элемента управления щелкните **Добавить** вкладку или **Удалить вкладку** .</span><span class="sxs-lookup"><span data-stu-id="a20c3-108">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="a20c3-109">-или-</span><span class="sxs-lookup"><span data-stu-id="a20c3-109">-or-</span></span>

     <span data-ttu-id="a20c3-110">В окне **Свойства** нажмите кнопку **с многоточием** (![кнопку с многоточием (...) в окно свойств Visual Studio.](./media/visual-studio-ellipsis-button.png)) рядом со свойством <xref:System.Windows.Forms.TabControl.TabPages%2A>, чтобы открыть **Редактор коллекции TabPage**.</span><span class="sxs-lookup"><span data-stu-id="a20c3-110">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="a20c3-111">Нажмите кнопку **Добавить** или **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="a20c3-111">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="a20c3-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a20c3-112">See also</span></span>

- [<span data-ttu-id="a20c3-113">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="a20c3-113">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="a20c3-114">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="a20c3-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="a20c3-115">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="a20c3-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="a20c3-116">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="a20c3-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="a20c3-117">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a20c3-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
