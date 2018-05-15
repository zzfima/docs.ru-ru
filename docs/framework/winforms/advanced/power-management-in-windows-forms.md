---
title: Управление питанием в Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- battery states
- power states
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
ms.openlocfilehash: 845cc9c910d63dfc7460bba0d5368b5b1e63efcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="bb446-102">Управление питанием в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bb446-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="bb446-103">Приложения Windows Forms можно воспользоваться преимуществами функций управления питанием в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="bb446-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="bb446-104">Ваши приложения могут отслеживать состояние питания компьютера и предпринять действия, когда происходит изменение состояния.</span><span class="sxs-lookup"><span data-stu-id="bb446-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="bb446-105">Например если приложение выполняется на портативном компьютере, может потребоваться отключить определенные функции приложения, когда заряд батареи падает ниже определенного уровня.</span><span class="sxs-lookup"><span data-stu-id="bb446-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="bb446-106">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Предоставляет <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> событие, возникающее при изменении состояния питания, например, когда пользователь приостанавливает или возобновляет работу операционной системы или при изменении состояния питания от сети или уровня заряда батареи.</span><span class="sxs-lookup"><span data-stu-id="bb446-106">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="bb446-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Свойство <xref:System.Windows.Forms.SystemInformation> класс можно использовать запрос для текущего состояния, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="bb446-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="bb446-108">Помимо <xref:System.Windows.Forms.BatteryChargeStatus> перечислений, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> свойства также содержит перечисления для определения заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="bb446-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="bb446-109">Можно использовать <xref:System.Windows.Forms.Application.SetSuspendState%2A> метод <xref:System.Windows.Forms.Application> перевести компьютер в спящий режим или режим приостановки.</span><span class="sxs-lookup"><span data-stu-id="bb446-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="bb446-110">Если `force` аргумента равно `false`, операционная система будет рассылать событие ко всем приложениям, запрашивая разрешение на приостановку.</span><span class="sxs-lookup"><span data-stu-id="bb446-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="bb446-111">Если `disableWakeEvent` аргумента равно `true`, операционная система отключает все события пробуждения.</span><span class="sxs-lookup"><span data-stu-id="bb446-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="bb446-112">В следующем примере кода показано, как перевод компьютера в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="bb446-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="bb446-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bb446-113">See Also</span></span>  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>  
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>  
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>  
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
