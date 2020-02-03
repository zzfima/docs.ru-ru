---
title: Захват мыши
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 10583f074831b16dce3c713b4ac9a76c7005c9f5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741018"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="31e58-102">Захват мыши в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31e58-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="31e58-103">*Захват мыши* означает, что элемент управления принимает в качестве команды все входные данные мыши.</span><span class="sxs-lookup"><span data-stu-id="31e58-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="31e58-104">Когда элемент управления захватывает мышь, он получает ввод с клавиатуры независимо от того, находится ли указатель внутри его границ.</span><span class="sxs-lookup"><span data-stu-id="31e58-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="31e58-105">Настройка захвата мыши</span><span class="sxs-lookup"><span data-stu-id="31e58-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="31e58-106">В Windows Forms мышь захватывается элементом управления, когда пользователь нажимает кнопку мыши на элементе управления, и мышь освобождается элементом управления, когда пользователь отпускает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="31e58-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="31e58-107">Свойство <xref:System.Windows.Forms.Control.Capture%2A> класса <xref:System.Windows.Forms.Control> указывает, захватывает ли элемент управления мышь.</span><span class="sxs-lookup"><span data-stu-id="31e58-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="31e58-108">Чтобы определить, когда элемент управления теряет захват мыши, обработайте событие <xref:System.Windows.Forms.Control.MouseCaptureChanged>.</span><span class="sxs-lookup"><span data-stu-id="31e58-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="31e58-109">Захват мыши может осуществляться только в окне переднего плана.</span><span class="sxs-lookup"><span data-stu-id="31e58-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="31e58-110">Когда окно в фоновом режиме пытается захватить мышь, окно получает сообщения только для событий мыши, происходящих, когда указатель мыши находится в пределах видимой части окна.</span><span class="sxs-lookup"><span data-stu-id="31e58-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="31e58-111">Кроме того, даже если окно переднего плана захватило мышь, пользователь по-прежнему может щелкнуть другое окно, переведя его на передний план.</span><span class="sxs-lookup"><span data-stu-id="31e58-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="31e58-112">При захвате мыши сочетания клавиш не работают.</span><span class="sxs-lookup"><span data-stu-id="31e58-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31e58-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="31e58-113">See also</span></span>

- [<span data-ttu-id="31e58-114">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31e58-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
