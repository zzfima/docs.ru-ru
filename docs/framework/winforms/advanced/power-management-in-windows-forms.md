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
# <a name="power-management-in-windows-forms"></a>Управление питанием в Windows Forms
Приложения Windows Forms могут использовать возможности управления питанием в операционной системе Windows. Приложения могут отслеживать состояние питания компьютера и предпринимать действия при изменении состояния. Например, если приложение выполняется на переносном компьютере, может потребоваться отключить определенные функции в приложении, когда заряд батареи компьютера падает на определенный уровень.  
  
 .NET Framework предоставляет событие <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>, возникающее при каждом изменении состояния питания, например, когда пользователь приостанавливает или возобновляет работу операционной системы или меняется состояние электропитания или аккумулятора. Свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> класса <xref:System.Windows.Forms.SystemInformation> можно использовать для запроса текущего состояния, как показано в следующем примере кода.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Помимо перечислений <xref:System.Windows.Forms.BatteryChargeStatus>, свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> также содержит перечисления для определения емкости аккумулятора (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Можно использовать метод <xref:System.Windows.Forms.Application.SetSuspendState%2A> <xref:System.Windows.Forms.Application>, чтобы перевести компьютер в режим гибернации или приостановки. Если аргумент `force` имеет значение `false`, операционная система будет передавать событие всем приложениям, запрашивающим разрешение на приостановку. Если аргумент `disableWakeEvent` имеет значение `true`, операционная система отключает все события пробуждения.  
  
 В следующем примере кода показано, как перевести компьютер в режим гибернации.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>См. также:

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
