---
title: События элементов управления Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
ms.openlocfilehash: 41ad95de7a65dbd0cb3a0d1af8f5c8cb00c1ccdd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61971988"
---
# <a name="events-in-windows-forms-controls"></a><span data-ttu-id="328da-102">События элементов управления Windows Forms</span><span class="sxs-lookup"><span data-stu-id="328da-102">Events in Windows Forms Controls</span></span>
<span data-ttu-id="328da-103">Элемент управления Windows Forms наследует более шестидесяти событий <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="328da-103">A Windows Forms control inherits more than sixty events from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span> <span data-ttu-id="328da-104">К ним относятся <xref:System.Windows.Forms.Control.Paint> событие, которое вызывает в элементе управления для отрисовки, события, связанные с отображением окна, такие как <xref:System.Windows.Forms.Control.Resize> и <xref:System.Windows.Forms.Control.Layout> события и низкоуровневые события мыши и клавиатуры.</span><span class="sxs-lookup"><span data-stu-id="328da-104">These include the <xref:System.Windows.Forms.Control.Paint> event, which causes a control to be drawn, events related to displaying a window, such as the <xref:System.Windows.Forms.Control.Resize> and <xref:System.Windows.Forms.Control.Layout> events, and low-level mouse and keyboard events.</span></span> <span data-ttu-id="328da-105">Некоторые низкоуровневые события синтезируются элементом <xref:System.Windows.Forms.Control> в семантические события, такие как <xref:System.Windows.Forms.Control.Click> и <xref:System.Windows.Forms.Control.DoubleClick>.</span><span class="sxs-lookup"><span data-stu-id="328da-105">Some low-level events are synthesized by <xref:System.Windows.Forms.Control> into semantic events such as <xref:System.Windows.Forms.Control.Click> and <xref:System.Windows.Forms.Control.DoubleClick>.</span></span> <span data-ttu-id="328da-106">Дополнительные сведения о наследуемых событиях см. в разделе <xref:System.Windows.Forms.Control>.</span><span class="sxs-lookup"><span data-stu-id="328da-106">For details about inherited events, see <xref:System.Windows.Forms.Control>.</span></span>  
  
 <span data-ttu-id="328da-107">Если для пользовательского элемента управления требуется переопределение функциональности наследуемых событий, переопределите наследуемый метод `On` *EventName*, а не присоединяйте делегат.</span><span class="sxs-lookup"><span data-stu-id="328da-107">If your custom control needs to override inherited event functionality, override the inherited `On`*EventName* method instead of attaching a delegate.</span></span> <span data-ttu-id="328da-108">Если вы не знакомы с моделью событий в .NET Framework, ознакомьтесь с разделом [Инициирование событий из компонента](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="328da-108">If you are not familiar with the event model in the .NET Framework, see [Raising Events from a Component](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/sh2e3k5z(v=vs.120)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="328da-109">См. также</span><span class="sxs-lookup"><span data-stu-id="328da-109">See also</span></span>

- [<span data-ttu-id="328da-110">Переопределение метода OnPaint</span><span class="sxs-lookup"><span data-stu-id="328da-110">Overriding the OnPaint Method</span></span>](overriding-the-onpaint-method.md)
- [<span data-ttu-id="328da-111">Обработка введенных пользователем данных</span><span class="sxs-lookup"><span data-stu-id="328da-111">Handling User Input</span></span>](handling-user-input.md)
- [<span data-ttu-id="328da-112">Определение событий</span><span class="sxs-lookup"><span data-stu-id="328da-112">Defining an Event</span></span>](defining-an-event-in-windows-forms-controls.md)
- [<span data-ttu-id="328da-113">События</span><span class="sxs-lookup"><span data-stu-id="328da-113">Events</span></span>](../../../standard/events/index.md)
