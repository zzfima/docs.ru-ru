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
ms.openlocfilehash: 10a6451827a16605ba738cf74b7f684b69adb5dc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="order-of-events-in-windows-forms"></a>Порядок событий в формах Windows Forms
Особый интерес для разработчиков представляет порядок, в котором вызываются события в приложениях Windows Forms, для обеспечения обработки каждого из этих событий в свою очередь. Если ситуация требует аккуратной обработки событий, например когда производится перерисовка части формы, то необходимо знать точный порядок, в котором вызываются события во время выполнения. В этом разделе приведены некоторые сведения о порядке событий, возникающих на нескольких важных этапах жизненного цикла приложений и элементов управления. Подробные сведения о порядке событий щелчков мыши см [события мыши в формах Windows Forms](../../../docs/framework/winforms/mouse-events-in-windows-forms.md). Обзор событий в Windows Forms см. в разделе [Общие сведения о событиях](../../../docs/framework/winforms/events-overview-windows-forms.md). Дополнительные сведения о создании обработчиков событий см. в разделе [Обзор обработчиков событий](../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).  
  
## <a name="application-startup-and-shutdown-events"></a>События запуска и завершения работы приложения  
 Классы <xref:System.Windows.Forms.Form> и <xref:System.Windows.Forms.Control> предоставляют набор событий, связанных с запуском и завершением приложения. При запуске приложения Windows Forms события запуска главной формы вызываются в следующем порядке:  
  
-   <xref:System.Windows.Forms.Control.HandleCreated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.BindingContextChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Control.VisibleChanged?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Activated?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Shown?displayProperty=nameWithType>  
  
 При закрытии приложения события запуска главной формы вызываются в следующем порядке:  
  
-   <xref:System.Windows.Forms.Form.Closing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosing?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Closed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.FormClosed?displayProperty=nameWithType>  
  
-   <xref:System.Windows.Forms.Form.Deactivate?displayProperty=nameWithType>  
  
 Событие <xref:System.Windows.Forms.Application.ApplicationExit> класса <xref:System.Windows.Forms.Application> вызывается после событий завершения работы основной формы.  
  
> [!NOTE]
>  В Visual Basic 2005 содержатся дополнительные события приложений, такие как <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup?displayProperty=nameWithType> и <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown?displayProperty=nameWithType>.  
  
## <a name="focus-and-validation-events"></a>События, связанные с фокусом и проверками  
 При изменении фокуса с помощью клавиатуры (при нажатии клавиш TAB, SHIFT+TAB и так далее), путем вызова методов <xref:System.Windows.Forms.Control.Select%2A> или <xref:System.Windows.Forms.Control.SelectNextControl%2A>, либо присвоением свойства <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> текущей форме, события фокуса ввода класса <xref:System.Windows.Forms.Control> происходят в следующем порядке:  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
 При изменении фокуса ввода с помощью мыши или путем вызова метода  <xref:System.Windows.Forms.Control.Focus%2A> события фокуса класса <xref:System.Windows.Forms.Control> происходят в следующем порядке.  
  
-   <xref:System.Windows.Forms.Control.Enter>  
  
-   <xref:System.Windows.Forms.Control.GotFocus>  
  
-   <xref:System.Windows.Forms.Control.LostFocus>  
  
-   <xref:System.Windows.Forms.Control.Leave>  
  
-   <xref:System.Windows.Forms.Control.Validating>  
  
-   <xref:System.Windows.Forms.Control.Validated>  
  
## <a name="see-also"></a>См. также  
 [Создание обработчиков событий в Windows Forms](../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
