---
title: Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 31c597a0e2cbf41484f19c8d4179823e9fb929ba
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317679"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="3fd16-102">Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3fd16-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="3fd16-103">Скрытие пунктов меню — это способ управления пользовательским интерфейсом (UI) приложения и ограничить команды пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fd16-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="3fd16-104">Часто требуется скрыть меню целиком, когда все элементы меню на нем будут недоступны.</span><span class="sxs-lookup"><span data-stu-id="3fd16-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="3fd16-105">Это меньше отвлекаться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3fd16-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="3fd16-106">Кроме того можно скрыть и отключить меню или пункта меню, как скрытие не запрещает пользователю доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="3fd16-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="3fd16-107">Дополнительные сведения об отключении пунктов меню см. в разделе [как: Отключение объектов ToolStripMenuItem с помощью конструктора](how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="3fd16-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd16-108">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="3fd16-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3fd16-109">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="3fd16-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3fd16-110">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="3fd16-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="3fd16-111">Чтобы скрыть меню верхнего уровня и пунктов подменю</span><span class="sxs-lookup"><span data-stu-id="3fd16-111">To hide a top-level menu and its submenu items</span></span>  
  
1. <span data-ttu-id="3fd16-112">Выберите пункт меню верхнего уровня и задайте его <xref:System.Windows.Forms.ToolStripItem.Visible%2A> или <xref:System.Windows.Forms.ToolStripItem.Available%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="3fd16-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="3fd16-113">Если скрыть элемент меню верхнего уровня, все пункты меню внутри этого меню также скрыты.</span><span class="sxs-lookup"><span data-stu-id="3fd16-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="3fd16-114">Если щелкнуть в любом месте за пределами <xref:System.Windows.Forms.MenuStrip> после задания <xref:System.Windows.Forms.ToolStripItem.Visible%2A> для `false`, элемент целиком меню верхнего уровня и пунктов подменю исчезнут из формы, поэтому отображается результат выполнения этого действия.</span><span class="sxs-lookup"><span data-stu-id="3fd16-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="3fd16-115">Для отображения скрытых меню верхнего уровня элемента во время разработки, щелкните <xref:System.Windows.Forms.MenuStrip> в **область компонентов**в **Структура документа**, или в верхней части сетки свойств.</span><span class="sxs-lookup"><span data-stu-id="3fd16-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fd16-116">Редко предстоит скрыть меню целиком за исключением нескольких меню дочерние интерфейса (MDI) документа в сценарии слияния.</span><span class="sxs-lookup"><span data-stu-id="3fd16-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="3fd16-117">Чтобы скрыть элемент вложенного меню</span><span class="sxs-lookup"><span data-stu-id="3fd16-117">To hide a submenu item</span></span>  
  
1. <span data-ttu-id="3fd16-118">Выберите элемент и задайте его <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="3fd16-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="3fd16-119">Если скрыть пункт подменю, он остается видимым в форме во время разработки, то можно легко выделить для дальнейшей работы.</span><span class="sxs-lookup"><span data-stu-id="3fd16-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="3fd16-120">Он будет скрыт во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="3fd16-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd16-121">См. также</span><span class="sxs-lookup"><span data-stu-id="3fd16-121">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="3fd16-122">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3fd16-122">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="3fd16-123">Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="3fd16-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
