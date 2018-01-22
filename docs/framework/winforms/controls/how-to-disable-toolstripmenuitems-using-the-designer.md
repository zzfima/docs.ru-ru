---
title: "Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f704e99622900d8c37c8ddd5054a3c5ad920bc6b
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="0e9e7-102">Практическое руководство. Отключение объектов ToolStripMenuItem с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="0e9e7-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="0e9e7-103">Можно ограничить или расширить набор команд, которые может выбрать пользователь, включение и отключение элементов меню в ответ на действия пользователя.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="0e9e7-104">Пункты меню включены по умолчанию, если они были созданы, но это можно изменить с помощью <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="0e9e7-105">Можно изменить значение этого свойства во время разработки в **свойства** окна или программным путем установки его в код.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="0e9e7-106">Дополнительные сведения см. в разделе [как: отключение объектов ToolStripMenuItem](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="0e9e7-106">For more information, see [How to: Disable ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e9e7-107">Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="0e9e7-108">Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** .</span><span class="sxs-lookup"><span data-stu-id="0e9e7-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="0e9e7-109">Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="0e9e7-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="0e9e7-110">Чтобы отключить пункт меню во время разработки</span><span class="sxs-lookup"><span data-stu-id="0e9e7-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="0e9e7-111">Выберите элемент меню в форме, установите <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="0e9e7-112">Отключение элемента меню первой или верхнего уровня в меню отключает всех пунктов меню.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="0e9e7-113">Аналогичным образом отключение пункта меню, который имеет вложенное отключает элементов вложенного меню.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="0e9e7-114">Если все команды конкретного меню недоступны пользователю, он считается хорошим стилем программирования, как скрыть и отключить всего меню, это представляет чистой пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="0e9e7-115">Как следует скрыть и отключить меню, как скрытие не запрещает доступ к командам меню с помощью сочетаний клавиш.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="0e9e7-116">Задать <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства элемента меню верхнего уровня для `false` скрыть меню целиком.</span><span class="sxs-lookup"><span data-stu-id="0e9e7-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9e7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="0e9e7-117">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="0e9e7-118">Практическое руководство. Скрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="0e9e7-118">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="0e9e7-119">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="0e9e7-119">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
