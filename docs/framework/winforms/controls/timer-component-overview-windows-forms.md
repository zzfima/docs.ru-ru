---
title: "Общие сведения о компоненте Timer (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea78cadae6e033bc54274e5428ba5e8c6410259d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="timer-component-overview-windows-forms"></a>Общие сведения о компоненте Timer (Windows Forms)
Компонент Windows Forms <xref:System.Windows.Forms.Timer> вызывает событие через определенные интервалы времени. Этот компонент предназначен для работы в среде Windows Forms. Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="key-properties-methods-and-events"></a>Ключевые свойства, методы и события  
 Длина интервалов определяется <xref:System.Windows.Forms.Timer.Interval%2A> свойства, значение которого указывается в миллисекундах. При включении компонента <xref:System.Windows.Forms.Timer.Tick> события во время каждого интервала. Это, где можно добавить код для выполнения. Дополнительные сведения см. в разделе [как: запуска процедуры интервалы задать с помощью компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md). Основные методы <xref:System.Windows.Forms.Timer> , компонент <xref:System.Windows.Forms.Timer.Start%2A> и <xref:System.Windows.Forms.Timer.Stop%2A>, который включения таймера и отключения. При выключении таймера сбрасывает; Невозможно приостановить <xref:System.Windows.Forms.Timer> компонента.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Forms.Timer>  
 [Компонент Timer](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Ограничения свойства Interval компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
