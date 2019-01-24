---
title: Как выполнить Перемещение объектов ToolStripMenuItem
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], moving
- menus [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], dragging and dropping
- menu items [Windows Forms], moving
- menu items [Windows Forms], cutting and pasting
- menu items [Windows Forms], dragging and dropping
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], cutting and pasting
ms.assetid: cab9e03e-4edd-4c25-b3e3-bd1edc602bd9
ms.openlocfilehash: 12554ee2225dbb186392b910ddfd7c2f69695e7e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660220"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="7f0e4-102">Как выполнить Перемещение объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="7f0e4-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="7f0e4-103">Во время разработки, можно переместить все меню верхнего уровня и их пункты меню в другое место на <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="7f0e4-104">Можно также перемещать отдельные элементы между меню верхнего уровня или изменение положения элементов в меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7f0e4-105">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7f0e4-106">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="7f0e4-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7f0e4-107">Дополнительные сведения см. в разделе [Персонализация интегрированной среды разработки Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7f0e4-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="7f0e4-108">Чтобы переместить меню верхнего уровня и элементами меню в другое расположение верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="7f0e4-108">To move a top-level menu and its menu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="7f0e4-109">Щелкните и удерживайте нажатой левую кнопку мыши в меню, которое требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-109">Click and hold down the left mouse button on the menu that you want to move.</span></span>  
  
2.  <span data-ttu-id="7f0e4-110">Перетащите курсор в меню верхнего уровня, который находится перед новым предполагаемым расположением и отпустите левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-110">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>  
  
     <span data-ttu-id="7f0e4-111">Выбранное меню перемещается справа от курсора.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-111">The selected menu moves to the right of the insertion point.</span></span>  
  
### <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="7f0e4-112">Чтобы переместить в расположение раскрывающегося меню верхнего уровня и элементами меню</span><span class="sxs-lookup"><span data-stu-id="7f0e4-112">To move a top-level menu and its menu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="7f0e4-113">Щелкните меню, которое вы хотите переместить и нажмите клавиши CTRL + X, или щелкните меню правой кнопкой мыши и выберите **Вырезать** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-113">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="7f0e4-114">В целевом меню верхнего уровня щелкните левой кнопкой мыши элемент меню над предполагаемым новым расположением и нажмите клавиши CTRL + V, или щелкните правой кнопкой мыши элемент меню над предполагаемым новым расположением и выберите **вставить** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-114">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="7f0e4-115">Вырезанное меню вставляется после выбранного пункта меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-115">The menu that you cut is inserted after the selected menu item.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="7f0e4-116">Чтобы переместить элемент меню в меню, используя редактор коллекции элементов</span><span class="sxs-lookup"><span data-stu-id="7f0e4-116">To move a menu item within a menu using the Items Collection Editor</span></span>  
  
1.  <span data-ttu-id="7f0e4-117">Щелкните правой кнопкой мыши меню, содержащее элемент меню, который требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-117">Right-click the menu that contains the menu item you want to move.</span></span>  
  
2.  <span data-ttu-id="7f0e4-118">В контекстном меню выберите **редактировать элементы раскрывающегося меню**.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-118">From the shortcut menu, choose **Edit DropDownItems**.</span></span>  
  
3.  <span data-ttu-id="7f0e4-119">В **редактор коллекции элементов**, щелкните элемент меню, которую требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-119">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>  
  
4.  <span data-ttu-id="7f0e4-120">Щелкните кнопки со стрелками вверх и вниз для перемещения элемента меню в меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-120">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>  
  
5.  <span data-ttu-id="7f0e4-121">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-121">Click **OK**.</span></span>  
  
### <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="7f0e4-122">Чтобы переместить элемент меню в меню с помощью клавиатуры</span><span class="sxs-lookup"><span data-stu-id="7f0e4-122">To move a menu item within a menu using the keyboard</span></span>  
  
1.  <span data-ttu-id="7f0e4-123">Нажмите и удерживайте нажатой клавишу ALT.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-123">Press and hold down the ALT key.</span></span>  
  
2.  <span data-ttu-id="7f0e4-124">Нажмите и удерживайте левую кнопку мыши на пункт меню, который требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-124">Click and hold the left mouse button on the menu item that you want to move.</span></span>  
  
3.  <span data-ttu-id="7f0e4-125">Перетащите элемент меню в новое место и отпустите левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-125">Drag the menu item to the new location and release the left mouse button.</span></span>  
  
### <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="7f0e4-126">Чтобы переместить элемент меню в другое меню</span><span class="sxs-lookup"><span data-stu-id="7f0e4-126">To move a menu item to another menu</span></span>  
  
1.  <span data-ttu-id="7f0e4-127">Щелкните левой кнопкой мыши пункт меню, который вы хотите переместить и нажмите клавиши CTRL + X, или щелкните правой кнопкой мыши пункт меню и выберите пункт **Вырезать** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-127">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="7f0e4-128">Щелкните меню, которое будет содержать вырезанный элемент меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-128">Left-click the menu that will contain the menu item that you cut.</span></span>  
  
3.  <span data-ttu-id="7f0e4-129">Щелкните левой кнопкой мыши пункт меню, который находится перед новым предполагаемым расположением и нажмите клавиши CTRL + V или щелкните правой кнопкой мыши пункт меню, который находится перед новым предполагаемым расположением и выберите **вставить** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-129">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="7f0e4-130">Элемент меню, вырезанный вставляется после выбранного пункта меню.</span><span class="sxs-lookup"><span data-stu-id="7f0e4-130">The menu item that you cut is inserted after the selected menu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f0e4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="7f0e4-131">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="7f0e4-132">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="7f0e4-132">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
