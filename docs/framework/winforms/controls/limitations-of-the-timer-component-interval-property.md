---
title: Ограничения свойства интервала компонента Timer
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745230"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a><span data-ttu-id="7e6b2-102">Ограничения свойства Interval компонента Timer в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7e6b2-102">Limitations of the Windows Forms Timer Component's Interval Property</span></span>
<span data-ttu-id="7e6b2-103">Компонент Windows Forms <xref:System.Windows.Forms.Timer> имеет свойство <xref:System.Windows.Forms.Timer.Interval%2A>, которое указывает количество миллисекунд, прошедших между одним событием таймера и следующим.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="7e6b2-104">Если компонент не отключен, таймер будет продолжать принимать <xref:System.Windows.Forms.Timer.Tick> событие с приблизительно равным интервалом времени.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="7e6b2-105">Этот компонент предназначен для работы в среде Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="7e6b2-106">Если вам требуется таймер, подходящий для серверной среды, см. раздел [Общие сведения о серверных таймерах](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="7e6b2-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="7e6b2-107">Свойство Interval</span><span class="sxs-lookup"><span data-stu-id="7e6b2-107">The Interval Property</span></span>  
 <span data-ttu-id="7e6b2-108">Свойство <xref:System.Windows.Forms.Timer.Interval%2A> имеет несколько ограничений, которые следует учитывать при программировании компонента <xref:System.Windows.Forms.Timer>.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
- <span data-ttu-id="7e6b2-109">Если приложение или другое приложение выполняет значительные требования к системе (например, длинные циклы, ресурсоемкие вычисления или доступ к диску, сети или портам), приложение может не получить события таймера так часто, как указано в свойстве <xref:System.Windows.Forms.Timer.Interval%2A>.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
- <span data-ttu-id="7e6b2-110">Не гарантируется, что интервал будет находиться в точном времени.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="7e6b2-111">Для обеспечения точности таймер должен проверять системные часы по мере необходимости, а не пытаться следить за накопленным временем на внутреннем уровне.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
- <span data-ttu-id="7e6b2-112">Точность свойства <xref:System.Windows.Forms.Timer.Interval%2A> задается в миллисекундах.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="7e6b2-113">Некоторые компьютеры предоставляют счетчик высокого разрешения с разрешением выше миллисекунд.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="7e6b2-114">Доступность такого счетчика зависит от аппаратного процессора компьютера.</span><span class="sxs-lookup"><span data-stu-id="7e6b2-114">The availability of such a counter depends on the processor hardware of your computer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7e6b2-115">См. также:</span><span class="sxs-lookup"><span data-stu-id="7e6b2-115">See also</span></span>

- <xref:System.Windows.Forms.Timer>
- [<span data-ttu-id="7e6b2-116">Компонент Timer</span><span class="sxs-lookup"><span data-stu-id="7e6b2-116">Timer Component</span></span>](timer-component-windows-forms.md)
- [<span data-ttu-id="7e6b2-117">Общие сведения о компоненте Timer</span><span class="sxs-lookup"><span data-stu-id="7e6b2-117">Timer Component Overview</span></span>](timer-component-overview-windows-forms.md)
