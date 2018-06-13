---
title: Захват мыши в Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- mouse [Windows Forms], capture
ms.assetid: 8911d4b0-a4f8-4f93-8246-371aebd27d0c
ms.openlocfilehash: dfe983b9e407eddb9bed3bcc1a767cdeff38f2ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33538412"
---
# <a name="mouse-capture-in-windows-forms"></a><span data-ttu-id="34940-102">Захват мыши в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34940-102">Mouse Capture in Windows Forms</span></span>
<span data-ttu-id="34940-103">*Захват мыши* называется элемента управления вводом все мыши.</span><span class="sxs-lookup"><span data-stu-id="34940-103">*Mouse capture* refers to when a control takes command of all mouse input.</span></span> <span data-ttu-id="34940-104">Элемент управления захватил мышь, получает ввод от мыши ли указатель мыши находится в пределах его границ.</span><span class="sxs-lookup"><span data-stu-id="34940-104">When a control has captured the mouse, it receives mouse input whether or not the pointer is within its borders.</span></span>  
  
## <a name="setting-mouse-capture"></a><span data-ttu-id="34940-105">Установка захвата мыши</span><span class="sxs-lookup"><span data-stu-id="34940-105">Setting Mouse Capture</span></span>  
 <span data-ttu-id="34940-106">В Windows Forms мышь захвачена элементом управления, когда пользователь нажимает кнопку мыши на элементе управления и кнопка мыши была отпущена элементом управления, когда пользователь отпускает кнопку мыши.</span><span class="sxs-lookup"><span data-stu-id="34940-106">In Windows Forms the mouse is captured by the control when the user presses a mouse button on a control, and the mouse is released by the control when the user releases the mouse button.</span></span>  
  
 <span data-ttu-id="34940-107"><xref:System.Windows.Forms.Control.Capture%2A> Свойство <xref:System.Windows.Forms.Control> класс указывает, является ли мышь захвачена элементом.</span><span class="sxs-lookup"><span data-stu-id="34940-107">The <xref:System.Windows.Forms.Control.Capture%2A> property of the <xref:System.Windows.Forms.Control> class specifies whether a control has captured the mouse.</span></span> <span data-ttu-id="34940-108">Чтобы определить, когда элемент управления теряет захват мыши, обработку <xref:System.Windows.Forms.Control.MouseCaptureChanged> событий.</span><span class="sxs-lookup"><span data-stu-id="34940-108">To determine when a control loses mouse capture, handle the <xref:System.Windows.Forms.Control.MouseCaptureChanged> event.</span></span>  
  
 <span data-ttu-id="34940-109">Захватить мышь может только окно переднего плана.</span><span class="sxs-lookup"><span data-stu-id="34940-109">Only the foreground window can capture the mouse.</span></span> <span data-ttu-id="34940-110">Если окна на задний план пытается захватить мышь, получит сообщения о событиях мыши, которые возникают, когда указатель мыши находится в видимой части окна.</span><span class="sxs-lookup"><span data-stu-id="34940-110">When a background window attempts to capture the mouse, the window receives messages only for mouse events that occur when the mouse pointer is within the visible portion of the window.</span></span> <span data-ttu-id="34940-111">Кроме того даже если мышь захвачена окно переднего плана, пользователь может по-прежнему щелкнуть другое окно, ее перевод на передний план.</span><span class="sxs-lookup"><span data-stu-id="34940-111">Also, even if the foreground window has captured the mouse, the user can still click another window, bringing it to the foreground.</span></span> <span data-ttu-id="34940-112">При захвате мыши сочетания клавиш не работают.</span><span class="sxs-lookup"><span data-stu-id="34940-112">When the mouse is captured, shortcut keys do not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34940-113">См. также</span><span class="sxs-lookup"><span data-stu-id="34940-113">See Also</span></span>  
 [<span data-ttu-id="34940-114">Ввод данных мышью в приложении Windows Forms</span><span class="sxs-lookup"><span data-stu-id="34940-114">Mouse Input in a Windows Forms Application</span></span>](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)
