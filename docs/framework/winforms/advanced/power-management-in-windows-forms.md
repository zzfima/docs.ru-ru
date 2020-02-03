---
title: Управление питанием
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 9ac39df43a08f62e50116c61c4bdeda4cd1c8281
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746864"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="c1b85-102">Управление питанием в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c1b85-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="c1b85-103">Приложения Windows Forms могут использовать возможности управления питанием в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="c1b85-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="c1b85-104">Приложения могут отслеживать состояние питания компьютера и предпринимать действия при изменении состояния.</span><span class="sxs-lookup"><span data-stu-id="c1b85-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="c1b85-105">Например, если приложение выполняется на переносном компьютере, может потребоваться отключить определенные функции в приложении, когда заряд батареи компьютера падает на определенный уровень.</span><span class="sxs-lookup"><span data-stu-id="c1b85-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="c1b85-106">.NET Framework предоставляет событие <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>, возникающее при каждом изменении состояния питания, например, когда пользователь приостанавливает или возобновляет работу операционной системы или меняется состояние электропитания или аккумулятора.</span><span class="sxs-lookup"><span data-stu-id="c1b85-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="c1b85-107">Свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> класса <xref:System.Windows.Forms.SystemInformation> можно использовать для запроса текущего состояния, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="c1b85-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="c1b85-108">Помимо перечислений <xref:System.Windows.Forms.BatteryChargeStatus>, свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> также содержит перечисления для определения емкости аккумулятора (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="c1b85-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="c1b85-109">Можно использовать метод <xref:System.Windows.Forms.Application.SetSuspendState%2A> <xref:System.Windows.Forms.Application>, чтобы перевести компьютер в режим гибернации или приостановки.</span><span class="sxs-lookup"><span data-stu-id="c1b85-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="c1b85-110">Если аргумент `force` имеет значение `false`, операционная система будет передавать событие всем приложениям, запрашивающим разрешение на приостановку.</span><span class="sxs-lookup"><span data-stu-id="c1b85-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="c1b85-111">Если аргумент `disableWakeEvent` имеет значение `true`, операционная система отключает все события пробуждения.</span><span class="sxs-lookup"><span data-stu-id="c1b85-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="c1b85-112">В следующем примере кода показано, как перевести компьютер в режим гибернации.</span><span class="sxs-lookup"><span data-stu-id="c1b85-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c1b85-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c1b85-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
