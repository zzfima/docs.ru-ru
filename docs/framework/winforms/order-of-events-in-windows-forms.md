---
title: Порядок событий в формах Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- events [Windows Forms], order of
- focus event order
- application shutdown event order
- sequence [Windows Forms], of events
- validation events [Windows Forms], order of
- application startup event order
ms.assetid: e81db09b-4453-437f-b78a-62d7cd5c9829
ms.openlocfilehash: 24d48a9dfdf10601099333e52073bb7fa3579beb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800793"
---
# <a name="order-of-events-in-windows-forms"></a><span data-ttu-id="bc7d7-102">Порядок событий в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc7d7-102">Order of Events in Windows Forms</span></span>
<span data-ttu-id="bc7d7-103">Особый интерес для разработчиков представляет порядок, в котором вызываются события в приложениях Windows Forms, для обеспечения обработки каждого из этих событий в свою очередь.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-103">The order in which events are raised in Windows Forms applications is of particular interest to developers concerned with handling each of these events in turn.</span></span> <span data-ttu-id="bc7d7-104">Если ситуация требует аккуратной обработки событий, например когда производится перерисовка части формы, то необходимо знать точный порядок, в котором вызываются события во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-104">When a situation calls for meticulous handling of events, such as when you are redrawing parts of the form, an awareness of the precise order in which events are raised at run time is necessary.</span></span> <span data-ttu-id="bc7d7-105">В этом разделе приведены некоторые сведения о порядке событий, возникающих на нескольких важных этапах жизненного цикла приложений и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-105">This topic provides some details on the order of events during several important stages in the lifetime of applications and controls.</span></span> <span data-ttu-id="bc7d7-106">Конкретные сведения о порядке событий щелчков мыши см. в разделе [события мыши в Windows Forms](mouse-events-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d7-106">For specific details about the order of mouse input events, see [Mouse Events in Windows Forms](mouse-events-in-windows-forms.md).</span></span> <span data-ttu-id="bc7d7-107">Обзор событий в формах Windows Forms, см. в разделе [Общие сведения о событиях](events-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d7-107">For an overview of events in Windows Forms, see [Events Overview](events-overview-windows-forms.md).</span></span> <span data-ttu-id="bc7d7-108">Дополнительные сведения о создании обработчиков событий, см. в разделе [Обзор обработчиков событий](event-handlers-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="bc7d7-108">For details about the makeup of event handlers, see [Event Handlers Overview](event-handlers-overview-windows-forms.md).</span></span>  
  
## <a name="application-startup-and-shutdown-events"></a><span data-ttu-id="bc7d7-109">События запуска и завершения работы приложения</span><span class="sxs-lookup"><span data-stu-id="bc7d7-109">Application Startup and Shutdown Events</span></span>  
 <span data-ttu-id="bc7d7-110">Классы <xref:System.Windows.Forms.Form> и <xref:System.Windows.Forms.Control> предоставляют набор событий, связанных с запуском и завершением приложения.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-110">The <xref:System.Windows.Forms.Form> and <xref:System.Windows.Forms.Control> classes expose a set of events related to application startup and shutdown.</span></span> <span data-ttu-id="bc7d7-111">При запуске приложения Windows Forms события запуска главной формы вызываются в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="bc7d7-111">When a Windows Forms application starts, the startup events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 <span data-ttu-id="bc7d7-112">При закрытии приложения события запуска главной формы вызываются в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="bc7d7-112">When an application closes, the shutdown events of the main form are raised in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
- <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 <span data-ttu-id="bc7d7-113">Событие <xref:System.Windows.Forms.Application.ApplicationExit> класса <xref:System.Windows.Forms.Application> вызывается после событий завершения работы основной формы.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-113">The <xref:System.Windows.Forms.Application.ApplicationExit> event of the <xref:System.Windows.Forms.Application> class is raised after the shutdown events of the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc7d7-114">В Visual Basic 2005 содержатся дополнительные события приложений, такие как <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-114">Visual Basic 2005 includes additional application events, such as <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> and <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.</span></span>  
  
## <a name="focus-and-validation-events"></a><span data-ttu-id="bc7d7-115">События, связанные с фокусом и проверками</span><span class="sxs-lookup"><span data-stu-id="bc7d7-115">Focus and Validation Events</span></span>  
 <span data-ttu-id="bc7d7-116">При изменении фокуса с помощью клавиатуры (при нажатии клавиш TAB, SHIFT+TAB и так далее), путем вызова методов <xref:System.Windows.Forms.Control.Select%2A> или <xref:System.Windows.Forms.Control.SelectNextControl%2A>, либо присвоением свойства <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> текущей форме, события фокуса ввода класса <xref:System.Windows.Forms.Control> происходят в следующем порядке:</span><span class="sxs-lookup"><span data-stu-id="bc7d7-116">When you change the focus by using the keyboard (TAB, SHIFT+TAB, and so on), by calling the <xref:System.Windows.Forms.Control.Select%2A> or <xref:System.Windows.Forms.Control.SelectNextControl%2A> methods, or by setting the <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> property to the current form, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
 <span data-ttu-id="bc7d7-117">При изменении фокуса ввода с помощью мыши или путем вызова метода  <xref:System.Windows.Forms.Control.Focus%2A> события фокуса класса <xref:System.Windows.Forms.Control> происходят в следующем порядке.</span><span class="sxs-lookup"><span data-stu-id="bc7d7-117">When you change the focus by using the mouse or by calling the <xref:System.Windows.Forms.Control.Focus%2A> method, focus events of the <xref:System.Windows.Forms.Control> class occur in the following order:</span></span>  
  
- <xref:System.Windows.Forms.Control.Enter>  
  
- <xref:System.Windows.Forms.Control.GotFocus>  
  
- <xref:System.Windows.Forms.Control.LostFocus>  
  
- <xref:System.Windows.Forms.Control.Leave>  
  
- <xref:System.Windows.Forms.Control.Validating>  
  
- <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a><span data-ttu-id="bc7d7-118">См. также</span><span class="sxs-lookup"><span data-stu-id="bc7d7-118">See also</span></span>

- [<span data-ttu-id="bc7d7-119">Создание обработчиков событий в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc7d7-119">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
