---
title: Захват мыши в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: 30432c6978f60cc9ad47d5df5dafc7aa45229f3b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151649"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="09c71-102">Захват мыши в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09c71-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="09c71-103">*Захват мыши* называется элемент управления вводом все мыши.</span><span class="sxs-lookup"><span data-stu-id="09c71-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="09c71-104">Если мышь захвачена элементом управления, он получает ввод от мыши ли указатель мыши находится в границах.</span><span class="sxs-lookup"><span data-stu-id="09c71-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="09c71-105">Установка захвата мыши</span><span class="sxs-lookup"><span data-stu-id="09c71-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="09c71-106">В Windows Forms имеет захват мыши элементом управления при нажатии кнопки мыши на элемент управления, и который мышь выпускается элементом управления, когда пользователь отпускает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="09c71-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="09c71-107"><xref:System.Windows.Forms.Control.Capture%2A> Свойство <xref:System.Windows.Forms.Control> класса указывает ли мышь захвачена элементом.</span><span class="sxs-lookup"><span data-stu-id="09c71-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="09c71-108">Чтобы определить, когда элемент управления теряет захват мыши, обработайте <xref:System.Windows.Forms.Control.MouseCaptureChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="09c71-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="09c71-109">Только окна на передний план можно захватить мышь.</span><span class="sxs-lookup"><span data-stu-id="09c71-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="09c71-110">Если фоновое окно пытается захватить мышь, получит сообщения о событиях мыши, возникающие, когда указатель мыши находится в видимой части окна.</span><span class="sxs-lookup"><span data-stu-id="09c71-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="09c71-111">Кроме того даже если мышь захвачена окна на передний план, пользователь может по-прежнему щелкнуть другое окно выводило на передний план.</span><span class="sxs-lookup"><span data-stu-id="09c71-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="09c71-112">При захвате мыши сочетаний клавиш не работают.</span><span class="sxs-lookup"><span data-stu-id="09c71-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c71-113">См. также</span><span class="sxs-lookup"><span data-stu-id="09c71-113">See also</span></span>

- [<span data-ttu-id="09c71-114">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="09c71-114">Mouse Input in a Windows Forms Application</span></span>](mouse-input-in-a-windows-forms-application.md)
