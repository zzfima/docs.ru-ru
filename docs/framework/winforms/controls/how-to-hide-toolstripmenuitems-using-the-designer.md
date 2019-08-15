---
title: Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 968d34a5f79d469ef62beaa8ac96742d73391b22
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039745"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="8b487-102">Практическое руководство. Скрытие объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="8b487-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="8b487-103">Скрытие пунктов меню — это способ управления пользовательским интерфейсом приложения и ограничения пользовательских команд.</span><span class="sxs-lookup"><span data-stu-id="8b487-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="8b487-104">Часто требуется скрыть все меню, если все пункты меню на нем недоступны.</span><span class="sxs-lookup"><span data-stu-id="8b487-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="8b487-105">Это приводит к уменьшению числа отсчетов пользователя.</span><span class="sxs-lookup"><span data-stu-id="8b487-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="8b487-106">Кроме того, может потребоваться скрыть и отключить меню или пункт меню, так как скрытие одного из них не мешает пользователю получить доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="8b487-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="8b487-107">Дополнительные сведения об отключении пунктов меню см. [в разделе как Отключите объектов ToolStripMenuItem с помощью конструктора](how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="8b487-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="8b487-108">Скрытие меню верхнего уровня и его пунктов подменю</span><span class="sxs-lookup"><span data-stu-id="8b487-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="8b487-109">Выберите пункт меню верхнего уровня и задайте для <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`его свойства или <xref:System.Windows.Forms.ToolStripItem.Available%2A> значение.</span><span class="sxs-lookup"><span data-stu-id="8b487-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="8b487-110">При скрытии пункта меню верхнего уровня все пункты меню в этом меню также скрываются.</span><span class="sxs-lookup"><span data-stu-id="8b487-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="8b487-111">Если щелкнуть в любом месте <xref:System.Windows.Forms.MenuStrip> `false`, отличном от параметра <xref:System.Windows.Forms.ToolStripItem.Visible%2A> после установки значения, весь элемент меню верхнего уровня и его пункты подменю исчезают из формы, что показывает результат выполнения действия.</span><span class="sxs-lookup"><span data-stu-id="8b487-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="8b487-112">Чтобы отобразить скрытый элемент меню верхнего уровня во время разработки, щелкните <xref:System.Windows.Forms.MenuStrip> в **области компонентов**, в **структуре документа**или в верхней части сетки свойств.</span><span class="sxs-lookup"><span data-stu-id="8b487-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
>  <span data-ttu-id="8b487-113">Вы редко скрываете все меню, за исключением дочерних меню многодокументного интерфейса (MDI) в сценарии слияния.</span><span class="sxs-lookup"><span data-stu-id="8b487-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="8b487-114">Скрытие пункта подменю</span><span class="sxs-lookup"><span data-stu-id="8b487-114">To hide a submenu item</span></span>

1. <span data-ttu-id="8b487-115">Выберите элемент подменю и задайте для <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`его свойства значение.</span><span class="sxs-lookup"><span data-stu-id="8b487-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="8b487-116">При скрытии элемента вложенного меню он остается видимым в форме во время разработки, чтобы его можно было легко выбрать для дальнейшей работы.</span><span class="sxs-lookup"><span data-stu-id="8b487-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="8b487-117">В действительности он будет скрыт во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="8b487-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="8b487-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8b487-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="8b487-119">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="8b487-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="8b487-120">Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="8b487-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
