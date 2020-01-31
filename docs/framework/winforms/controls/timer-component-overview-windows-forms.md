---
title: Общие сведения о компоненте Timer
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742780"
---
# <a name="timer-component-overview-windows-forms"></a>Общие сведения о компоненте Timer (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.Timer> вызывает событие через определенные интервалы времени. Этот компонент предназначен для работы в среде Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).  
  
## <a name="key-properties-methods-and-events"></a>Ключевые свойства, методы и события  
 Длина интервалов определяется свойством <xref:System.Windows.Forms.Timer.Interval%2A>, значение которого указывается в миллисекундах. Когда компонент включен, событие <xref:System.Windows.Forms.Timer.Tick> возникает каждый интервал. Здесь нужно добавить код для выполнения. Дополнительные сведения см. в разделе [инструкции. выполнение процедур через заданные интервалы с помощью компонента таймера Windows Forms](run-procedures-at-set-intervals-with-wf-timer-component.md). Ключевыми методами компонента <xref:System.Windows.Forms.Timer> являются <xref:System.Windows.Forms.Timer.Start%2A> и <xref:System.Windows.Forms.Timer.Stop%2A>, которые включают и выключает таймер. Когда таймер отключается, он сбрасывается; невозможно приостановить <xref:System.Windows.Forms.Timer> компонент.  
  
## <a name="see-also"></a>См. также:

- <xref:System.Windows.Forms.Timer>
- [Компонент Timer](timer-component-windows-forms.md)
- [Ограничения свойства Interval компонента Timer в Windows Forms](limitations-of-the-timer-component-interval-property.md)
