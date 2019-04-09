---
title: Практическое руководство. Копирование объектов ToolStripMenuItems
ms.date: 03/30/2017
helpviewer_keywords:
- menu items [Windows Forms], copying and pasting
- MenuStrip control [Windows Forms], arranging items
- ToolStripMenuItems [Windows Forms], copying and pasting
ms.assetid: 17ef4207-e92e-4db2-b648-27246e6517ad
ms.openlocfilehash: 94dc1271468661801d07b341214b03bc31bb3099
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116354"
---
# <a name="how-to-copy-toolstripmenuitems"></a><span data-ttu-id="80b96-102">Практическое руководство. Копирование объектов ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="80b96-102">How to: Copy ToolStripMenuItems</span></span>
<span data-ttu-id="80b96-103">Во время разработки вы можете копировать целиком меню верхнего уровня и пункты их подменю в другое место в <xref:System.Windows.Forms.MenuStrip>.</span><span class="sxs-lookup"><span data-stu-id="80b96-103">At design time, you can copy entire top-level menus and their submenu items to a different place on the <xref:System.Windows.Forms.MenuStrip>.</span></span> <span data-ttu-id="80b96-104">Вы также можете копировать отдельные пункты меню верхнего уровня или переупорядочивать пункты меню.</span><span class="sxs-lookup"><span data-stu-id="80b96-104">You can also copy individual menu items between top-level menus or change the position of menu items within a menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-another-top-level-location"></a><span data-ttu-id="80b96-105">Копирование меню верхнего уровня и его подменю в другое расположение верхнего уровня</span><span class="sxs-lookup"><span data-stu-id="80b96-105">To copy a top-level menu and its submenu items to another top-level location</span></span>  
  
1.  <span data-ttu-id="80b96-106">Щелкните левой кнопкой мыши меню, которое вы хотите скопировать, нажмите клавиши CTRL+C или щелкните меню правой кнопкой мыши и выберите в списке команду **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="80b96-106">Left-click the menu that you want to copy and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="80b96-107">Щелкните правой кнопкой мыши меню верхнего уровня, которое находится за новым предполагаемым расположением, и нажмите клавиши CTRL+V или щелкните правой кнопкой мыши пункт меню верхнего уровня, который находится перед новым предполагаемым расположением, и выберите команду **Вставить** в контекстном меню.</span><span class="sxs-lookup"><span data-stu-id="80b96-107">Left-click the top-level menu that is after the intended new location and press CTRL+V, or right-click the top-level menu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="80b96-108">Скопированное меню вставляется перед выбранным меню верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="80b96-108">The menu that you copied is inserted before the selected top-level menu.</span></span>  
  
### <a name="to-copy-a-top-level-menu-and-its-submenu-items-to-a-drop-down-location"></a><span data-ttu-id="80b96-109">Копирование меню верхнего уровня и пунктов подменю в расположение раскрывающегося списка</span><span class="sxs-lookup"><span data-stu-id="80b96-109">To copy a top-level menu and its submenu items to a drop-down location</span></span>  
  
1.  <span data-ttu-id="80b96-110">Щелкните левой кнопкой мыши меню, которое хотите переместить, и нажмите клавиши CTRL+C или щелкните меню правой кнопкой мыши и выберите в контекстном меню команду **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="80b96-110">Left-click the menu that you want to move and press CTRL+C, or right-click the menu and select **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="80b96-111">В целевом меню верхнего уровня щелкните левой кнопкой мыши пункт подменю, который находится над предполагаемым новым расположением, и нажмите клавиши CTRL+V или щелкните правой кнопкой мыши пункт подменю над предполагаемым новым расположением и выберите в контекстном меню команду **Вставить** .</span><span class="sxs-lookup"><span data-stu-id="80b96-111">In the destination top-level menu, left-click the submenu item that is above the intended new location and press CTRL+V, or right-click the submenu item that is above the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="80b96-112">Скопированное меню вставляется перед выбранным пунктом подменю.</span><span class="sxs-lookup"><span data-stu-id="80b96-112">The menu that you copied is inserted before the selected submenu item.</span></span>  
  
### <a name="to-copy-a-submenu-item-to-another-menu"></a><span data-ttu-id="80b96-113">Копирование пункта подменю в другое меню</span><span class="sxs-lookup"><span data-stu-id="80b96-113">To copy a submenu item to another menu</span></span>  
  
1.  <span data-ttu-id="80b96-114">Щелкните левой кнопкой пункт подменю, который вы хотите скопировать, и нажмите клавиши CTRL+C или щелкните правой кнопкой мыши пункт подменю и выберите в контекстном меню команду **Копировать** .</span><span class="sxs-lookup"><span data-stu-id="80b96-114">Left-click the submenu item that you want to copy and press CTRL+C, or right-click the submenu item and choose **Copy** from the shortcut menu.</span></span>  
  
2.  <span data-ttu-id="80b96-115">Щелкните левой кнопкой мыши меню, которое будет содержать вырезанный пункт подменю.</span><span class="sxs-lookup"><span data-stu-id="80b96-115">Left-click the menu that will contain the submenu item that you cut.</span></span>  
  
3.  <span data-ttu-id="80b96-116">Щелкните левой кнопкой мыши пункт подменю, который находится перед новым предполагаемым расположением, и нажмите клавиши CTRL+V или щелкните правой кнопкой мыши пункт подменю, предшествующий предполагаемому новому расположению, и выберите в контекстном меню команду **Вставить** .</span><span class="sxs-lookup"><span data-stu-id="80b96-116">Left-click the submenu item that is before the intended new location and press CTRL+V, or right-click the submenu item that is before the intended new location and select **Paste** from the shortcut menu.</span></span>  
  
     <span data-ttu-id="80b96-117">Скопированный пункт подменю вставляется перед выбранным пунктом подменю.</span><span class="sxs-lookup"><span data-stu-id="80b96-117">The submenu item that you copied is inserted before the selected submenu item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80b96-118">См. также</span><span class="sxs-lookup"><span data-stu-id="80b96-118">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="80b96-119">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="80b96-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
