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
ms.openlocfilehash: 36c152a9e388fe61b1c82a8783bf74bbe6c8f123
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592522"
---
# <a name="power-management-in-windows-forms"></a><span data-ttu-id="e5a2b-102">Управление питанием в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e5a2b-102">Power Management in Windows Forms</span></span>
<span data-ttu-id="e5a2b-103">Приложения Windows Forms можно воспользоваться преимуществами функций управления питанием в операционной системе Windows.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-103">Your Windows Forms applications can take advantage of the power management features in the Windows operating system.</span></span> <span data-ttu-id="e5a2b-104">Приложения можно отслеживать состояние питания компьютера и предпринимать действия при изменении состояния.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-104">Your applications can monitor the power status of a computer and take action when a status change occurs.</span></span> <span data-ttu-id="e5a2b-105">Например если приложение выполняется на портативном компьютере, может потребоваться отключить некоторые функции в приложении, когда заряд батареи падает ниже определенного уровня.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-105">For example, if your application is running on a portable computer, you might want to disable certain features in your application when the computer's battery charge falls under a certain level.</span></span>  
  
 <span data-ttu-id="e5a2b-106">Платформа .NET Framework предоставляет <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> событие, возникающее при каждом изменении состояния питания, например когда пользователь приостанавливает или возобновляет работу операционной системы, или при изменении состояния питания от сети или состояние батареи.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-106">The .NET Framework provides a <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> event that occurs whenever there is a change in power status, such as when a user suspends or resumes the operating system, or when the AC power status or battery status changes.</span></span> <span data-ttu-id="e5a2b-107"><xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Свойство <xref:System.Windows.Forms.SystemInformation> класс может быть используется для запроса его текущего состояния, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-107">The <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property of the <xref:System.Windows.Forms.SystemInformation> class can be used to query for the current status, as shown in the following code example.</span></span>  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 <span data-ttu-id="e5a2b-108">Помимо <xref:System.Windows.Forms.BatteryChargeStatus> перечислений, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> свойство также содержит перечисления для определения заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span><span class="sxs-lookup"><span data-stu-id="e5a2b-108">Besides the <xref:System.Windows.Forms.BatteryChargeStatus> enumerations, the <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> property also contains enumerations for determining battery capacity (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) and battery charge percentage (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).</span></span>  
  
 <span data-ttu-id="e5a2b-109">Можно использовать <xref:System.Windows.Forms.Application.SetSuspendState%2A> метод <xref:System.Windows.Forms.Application> перевести компьютер в режим гибернации или спящий режим.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-109">You can use the <xref:System.Windows.Forms.Application.SetSuspendState%2A> method of the <xref:System.Windows.Forms.Application> to put a computer into hibernation or suspend mode.</span></span> <span data-ttu-id="e5a2b-110">Если `force` аргумент имеет значение `false`, операционная система передает полученное событие ко всем приложениям, запрашивая разрешение на приостановку.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-110">If the `force` argument is set to `false`, the operating system will broadcast an event to all applications requesting permission to suspend.</span></span> <span data-ttu-id="e5a2b-111">Если `disableWakeEvent` аргумент имеет значение `true`, операционная система отключает все события пробуждения.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-111">If the `disableWakeEvent` argument is set to `true`, the operating system disables all wake events.</span></span>  
  
 <span data-ttu-id="e5a2b-112">В следующем примере кода показано, как перевести компьютер в спящий режим.</span><span class="sxs-lookup"><span data-stu-id="e5a2b-112">The following code example demonstrates how to put a computer into hibernation.</span></span>  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="e5a2b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="e5a2b-113">See also</span></span>

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
