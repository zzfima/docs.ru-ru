---
title: Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: a185fe4421b5b5d7846c7d8cacbfc1cae5f805eb
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2019
ms.locfileid: "57704446"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="e43cd-102">Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="e43cd-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="e43cd-103">Можно ограничить или расширить набор команд, которые может выполнять пользователь, включение и отключение элементов меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="e43cd-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="e43cd-104">Пункты меню включены по умолчанию, когда они создаются, но его можно настроить через <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="e43cd-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="e43cd-105">Можно изменить значение этого свойства во время разработки в **свойства** окна или программным способом, задав его в код.</span><span class="sxs-lookup"><span data-stu-id="e43cd-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="e43cd-106">Дополнительные сведения см. в разделе [Как Отключение объектов ToolStripMenuItem](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="e43cd-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e43cd-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="e43cd-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e43cd-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="e43cd-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e43cd-109">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="e43cd-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="e43cd-110">Чтобы отключить пункт меню во время разработки</span><span class="sxs-lookup"><span data-stu-id="e43cd-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="e43cd-111">Выберите элемент меню в форме, установите <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="e43cd-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="e43cd-112">При отключении элемента меню первый или верхнего уровня в меню отключаются все пункты меню, содержащихся в меню.</span><span class="sxs-lookup"><span data-stu-id="e43cd-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="e43cd-113">Аналогичным образом отключение элемента меню, который имеет вложенное отключает элементы вложенного меню.</span><span class="sxs-lookup"><span data-stu-id="e43cd-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="e43cd-114">Если все команды конкретного меню недоступны для пользователя, он считается хорошим стилем программирования, как скрыть и отключить всего меню, как это представляет собой интерфейс пользователя.</span><span class="sxs-lookup"><span data-stu-id="e43cd-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="e43cd-115">Как следует скрыть и отключить меню, как скрытие не запрещает доступ к командам меню с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="e43cd-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="e43cd-116">Задайте <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойство пункта меню верхнего уровня к `false` скрыть меню целиком.</span><span class="sxs-lookup"><span data-stu-id="e43cd-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43cd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="e43cd-117">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="e43cd-118">Практическое руководство. Скрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="e43cd-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="e43cd-119">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="e43cd-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
