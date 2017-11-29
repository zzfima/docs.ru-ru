---
title: "Практическое руководство. Сокрытие объектов ToolStripMenuItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding
- MenuStrip control [Windows Forms], hiding menu items
- menus [Windows Forms], hiding menu items
- menu items [Windows Forms], hiding
- hiding menu items
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cb24fd36bdee76fa80a87d48f41b72f01c8f263
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-toolstripmenuitems"></a><span data-ttu-id="3c382-102">Практическое руководство. Сокрытие объектов ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="3c382-102">How to: Hide ToolStripMenuItems</span></span>
<span data-ttu-id="3c382-103">Скрытие пунктов меню служит для управления пользовательским интерфейсом приложения и ограничивать использование команд пользователями.</span><span class="sxs-lookup"><span data-stu-id="3c382-103">Hiding menu items is a way to control the user interface of your application and restrict user commands.</span></span> <span data-ttu-id="3c382-104">Часто необходимо скрыть меню целиком, когда все элементы меню недоступны.</span><span class="sxs-lookup"><span data-stu-id="3c382-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="3c382-105">Это меньше отвлекаться для пользователя.</span><span class="sxs-lookup"><span data-stu-id="3c382-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="3c382-106">Кроме того может потребоваться скрыть и отключить меню или пункта меню, как скрытие не запрещает пользователю доступ к команде меню с помощью сочетания клавиш.</span><span class="sxs-lookup"><span data-stu-id="3c382-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span>  
  
### <a name="to-hide-any-menu-item-programmatically"></a><span data-ttu-id="3c382-107">Чтобы скрыть любой элемент меню программными средствами</span><span class="sxs-lookup"><span data-stu-id="3c382-107">To hide any menu item programmatically</span></span>  
  
-   <span data-ttu-id="3c382-108">Внутри метода, в котором задаются свойства элемента меню, добавьте код для задания <xref:System.Windows.Forms.ToolStripItem.Visible%2A> свойства `false`.</span><span class="sxs-lookup"><span data-stu-id="3c382-108">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem3.Visible = False  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3c382-109">См. также</span><span class="sxs-lookup"><span data-stu-id="3c382-109">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 [<span data-ttu-id="3c382-110">Общие сведения об элементе управления MenuStrip</span><span class="sxs-lookup"><span data-stu-id="3c382-110">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="3c382-111">Практическое руководство. Блокирование доступа к элементам меню ToolStripMenuItem</span><span class="sxs-lookup"><span data-stu-id="3c382-111">How to: Disable ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)
