---
title: "Общие сведения о компоненте Timer (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 90296d2741a96e8788bf7a9b18bf3ea303ad2bae
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="6f412-102">Общие сведения о компоненте Timer (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6f412-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="6f412-103">Компонент Windows Forms <xref:System.Windows.Forms.Timer> вызывает событие через определенные интервалы времени.</span><span class="sxs-lookup"><span data-stu-id="6f412-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="6f412-104">Этот компонент предназначен для работы в среде Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="6f412-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="6f412-105">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span><span class="sxs-lookup"><span data-stu-id="6f412-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="6f412-106">Ключевые свойства, методы и события</span><span class="sxs-lookup"><span data-stu-id="6f412-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="6f412-107">Длина интервалов определяется <xref:System.Windows.Forms.Timer.Interval%2A> свойства, значение которого указывается в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="6f412-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="6f412-108">При включении компонента <xref:System.Windows.Forms.Timer.Tick> события во время каждого интервала.</span><span class="sxs-lookup"><span data-stu-id="6f412-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="6f412-109">Это, где можно добавить код для выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f412-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="6f412-110">Дополнительные сведения см. в разделе [как: запуска процедуры интервалы задать с помощью компонента Timer в Windows Forms](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span><span class="sxs-lookup"><span data-stu-id="6f412-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="6f412-111">Основные методы <xref:System.Windows.Forms.Timer> , компонент <xref:System.Windows.Forms.Timer.Start%2A> и <xref:System.Windows.Forms.Timer.Stop%2A>, который включения таймера и отключения.</span><span class="sxs-lookup"><span data-stu-id="6f412-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="6f412-112">При выключении таймера сбрасывает; Невозможно приостановить <xref:System.Windows.Forms.Timer> компонента.</span><span class="sxs-lookup"><span data-stu-id="6f412-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f412-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6f412-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="6f412-114">Компонент Timer</span><span class="sxs-lookup"><span data-stu-id="6f412-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="6f412-115">Ограничения свойства Interval компонента Timer в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f412-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
