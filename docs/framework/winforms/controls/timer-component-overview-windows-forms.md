---
title: Общие сведения о компоненте Timer (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 6e453f6b7718c6c5be3109f51153a3f5e4b5b6f4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032232"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="4fa59-102">Общие сведения о компоненте Timer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4fa59-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="4fa59-103">Компонент Windows Forms <xref:System.Windows.Forms.Timer> вызывает событие через определенные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="4fa59-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="4fa59-104">Этот компонент предназначен для работы в среде Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="4fa59-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="4fa59-105">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="4fa59-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="4fa59-106">Ключевые свойства, методы и события</span><span class="sxs-lookup"><span data-stu-id="4fa59-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="4fa59-107">Длина в интервале, заданном параметром <xref:System.Windows.Forms.Timer.Interval%2A> свойство, значение которого указывается в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="4fa59-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="4fa59-108">При включении компонента <xref:System.Windows.Forms.Timer.Tick> события во время каждого интервала.</span><span class="sxs-lookup"><span data-stu-id="4fa59-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="4fa59-109">Это, где необходимо добавить код, который будет выполнен.</span><span class="sxs-lookup"><span data-stu-id="4fa59-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="4fa59-110">Дополнительные сведения см. в разделе [как: выполните процедуры периодичностью задать с помощью компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="4fa59-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="4fa59-111">Основные методы класса <xref:System.Windows.Forms.Timer> компонент <xref:System.Windows.Forms.Timer.Start%2A> и <xref:System.Windows.Forms.Timer.Stop%2A>, который включать таймер и отключать.</span><span class="sxs-lookup"><span data-stu-id="4fa59-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="4fa59-112">При выключении таймера, он сбрасывает; Невозможно приостановить <xref:System.Windows.Forms.Timer> компонента.</span><span class="sxs-lookup"><span data-stu-id="4fa59-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fa59-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4fa59-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="4fa59-114">Компонент Timer</span><span class="sxs-lookup"><span data-stu-id="4fa59-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="4fa59-115">Ограничения свойства Interval компонента Timer в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="4fa59-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
