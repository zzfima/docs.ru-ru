---
title: Практическое руководство. Перемещение объектов ToolStripMenuItem
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
ms.openlocfilehash: adf25973fde790937461007bd0106cca02dd83be
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039801"
---
# <a name="how-to-move-toolstripmenuitems"></a><span data-ttu-id="96780-102">Практическое руководство. Перемещение объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="96780-102">How to: Move ToolStripMenuItems</span></span>
<span data-ttu-id="96780-103">Во время разработки можно перемещать целые меню верхнего уровня и их пункты меню в другое место <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="96780-103">At design time, you can move entire top-level menus and their menu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="96780-104">Можно также перемещать отдельные пункты меню между меню верхнего уровня или изменять положение пунктов меню в меню.</span><span class="sxs-lookup"><span data-stu-id="96780-104">You can also move individual menu items between top-level menus or change the position of menu items within a menu.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-another-top-level-location"></a><span data-ttu-id="96780-105">Перемещение меню верхнего уровня и его пунктов меню в другое расположение верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="96780-105">To move a top-level menu and its menu items to another top-level location</span></span>

1. <span data-ttu-id="96780-106">Щелкните и удерживайте левую кнопку мыши в меню, которое требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="96780-106">Click and hold down the left mouse button on the menu that you want to move.</span></span>

2. <span data-ttu-id="96780-107">Перетащите точку вставки в меню верхнего уровня, расположенное перед предполагаемым новым расположением, и отпустите левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="96780-107">Drag the insertion point to the top-level menu that is before the intended new location and release the left mouse button.</span></span>

     <span data-ttu-id="96780-108">Выбранное меню перемещается справа от точки вставки.</span><span class="sxs-lookup"><span data-stu-id="96780-108">The selected menu moves to the right of the insertion point.</span></span>

## <a name="to-move-a-top-level-menu-and-its-menu-items-to-a-drop-down-location"></a><span data-ttu-id="96780-109">Перемещение меню верхнего уровня и его пунктов меню в раскрывающийся список</span><span class="sxs-lookup"><span data-stu-id="96780-109">To move a top-level menu and its menu items to a drop-down location</span></span>

1. <span data-ttu-id="96780-110">Щелкните правой кнопкой мыши меню, которое нужно переместить, и нажмите клавиши CTRL + X, либо щелкните меню в контекстном меню и выберите команду **Вырезать** .</span><span class="sxs-lookup"><span data-stu-id="96780-110">Left-click the menu that you want to move and press CTRL+X, or right-click the menu and select **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="96780-111">В меню назначения верхнего уровня щелкните левой кнопкой мыши пункт меню над предполагаемым новым расположением и нажмите клавиши CTRL + V или щелкните правой кнопкой пункт меню над нужным новым расположением и выберите в контекстном меню команду **Вставить** .</span><span class="sxs-lookup"><span data-stu-id="96780-111">In the destination top-level menu, left-click the menu item above the intended new location and press CTRL+V, or right-click the menu item above the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="96780-112">Вырезанное меню вставляется после выбранного пункта меню.</span><span class="sxs-lookup"><span data-stu-id="96780-112">The menu that you cut is inserted after the selected menu item.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-items-collection-editor"></a><span data-ttu-id="96780-113">Перемещение пункта меню в меню с помощью редактора коллекции элементов</span><span class="sxs-lookup"><span data-stu-id="96780-113">To move a menu item within a menu using the Items Collection Editor</span></span>

1. <span data-ttu-id="96780-114">Щелкните правой кнопкой мыши меню, содержащее пункт меню, который требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="96780-114">Right-click the menu that contains the menu item you want to move.</span></span>

2. <span data-ttu-id="96780-115">В контекстном меню выберите **изменить дропдовнитемс**.</span><span class="sxs-lookup"><span data-stu-id="96780-115">From the shortcut menu, choose **Edit DropDownItems**.</span></span>

3. <span data-ttu-id="96780-116">В **редакторе коллекции элементов**щелкните элемент меню, который нужно переместить, левой кнопкой мыши.</span><span class="sxs-lookup"><span data-stu-id="96780-116">In the **Items Collection Editor**, left-click the menu item you want to move.</span></span>

4. <span data-ttu-id="96780-117">Нажмите клавиши со СТРЕЛКАми вверх и вниз, чтобы переместить пункт меню в меню.</span><span class="sxs-lookup"><span data-stu-id="96780-117">Click the UP and DOWN ARROW keys to move the menu item within the menu.</span></span>

5. <span data-ttu-id="96780-118">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96780-118">Click **OK**.</span></span>

## <a name="to-move-a-menu-item-within-a-menu-using-the-keyboard"></a><span data-ttu-id="96780-119">Перемещение пункта меню в меню с помощью клавиатуры</span><span class="sxs-lookup"><span data-stu-id="96780-119">To move a menu item within a menu using the keyboard</span></span>

1. <span data-ttu-id="96780-120">Нажмите и удерживайте клавишу ALT.</span><span class="sxs-lookup"><span data-stu-id="96780-120">Press and hold down the ALT key.</span></span>

2. <span data-ttu-id="96780-121">Щелкните и удерживайте левую кнопку мыши в пункте меню, которое требуется переместить.</span><span class="sxs-lookup"><span data-stu-id="96780-121">Click and hold the left mouse button on the menu item that you want to move.</span></span>

3. <span data-ttu-id="96780-122">Перетащите элемент меню в новое место и отпустите левую кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="96780-122">Drag the menu item to the new location and release the left mouse button.</span></span>

## <a name="to-move-a-menu-item-to-another-menu"></a><span data-ttu-id="96780-123">Перемещение пункта меню в другое меню</span><span class="sxs-lookup"><span data-stu-id="96780-123">To move a menu item to another menu</span></span>

1. <span data-ttu-id="96780-124">Щелкните правой кнопкой мыши пункт меню, который нужно переместить, и нажмите клавиши CTRL + X, либо щелкните элемент меню в контекстном меню и выберите **Вырезать** .</span><span class="sxs-lookup"><span data-stu-id="96780-124">Left-click the menu item that you want to move and press CTRL+X, or right-click the menu item and choose **Cut** from the shortcut menu.</span></span>

2. <span data-ttu-id="96780-125">Щелкните левой кнопкой мыши меню, в котором будет содержаться вырезанный пункт меню.</span><span class="sxs-lookup"><span data-stu-id="96780-125">Left-click the menu that will contain the menu item that you cut.</span></span>

3. <span data-ttu-id="96780-126">Щелкните левой кнопкой мыши пункт меню, который находится перед предполагаемым новым расположением, и нажмите клавиши CTRL + V или щелкните элемент меню, находящееся перед нужным новым расположением, и выберите в контекстном меню команду **Вставить** .</span><span class="sxs-lookup"><span data-stu-id="96780-126">Left-click the menu item that is before the intended new location and press CTRL+V, or right-click the menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>

     <span data-ttu-id="96780-127">Вырезанный пункт меню вставляется после выбранного пункта меню.</span><span class="sxs-lookup"><span data-stu-id="96780-127">The menu item that you cut is inserted after the selected menu item.</span></span>

## <a name="see-also"></a><span data-ttu-id="96780-128">См. также</span><span class="sxs-lookup"><span data-stu-id="96780-128">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="96780-129">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="96780-129">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
