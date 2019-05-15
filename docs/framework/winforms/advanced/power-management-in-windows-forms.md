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
# <a name="power-management-in-windows-forms"></a>Управление питанием в Windows Forms
Приложения Windows Forms можно воспользоваться преимуществами функций управления питанием в операционной системе Windows. Приложения можно отслеживать состояние питания компьютера и предпринимать действия при изменении состояния. Например если приложение выполняется на портативном компьютере, может потребоваться отключить некоторые функции в приложении, когда заряд батареи падает ниже определенного уровня.  
  
 Платформа .NET Framework предоставляет <xref:Microsoft.Win32.SystemEvents.PowerModeChanged> событие, возникающее при каждом изменении состояния питания, например когда пользователь приостанавливает или возобновляет работу операционной системы, или при изменении состояния питания от сети или состояние батареи. <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> Свойство <xref:System.Windows.Forms.SystemInformation> класс может быть используется для запроса его текущего состояния, как показано в следующем примере кода.  
  
 [!code-csharp[PowerMode#1](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Помимо <xref:System.Windows.Forms.BatteryChargeStatus> перечислений, <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> свойство также содержит перечисления для определения заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>) и процента заряда батареи (<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>).  
  
 Можно использовать <xref:System.Windows.Forms.Application.SetSuspendState%2A> метод <xref:System.Windows.Forms.Application> перевести компьютер в режим гибернации или спящий режим. Если `force` аргумент имеет значение `false`, операционная система передает полученное событие ко всем приложениям, запрашивая разрешение на приостановку. Если `disableWakeEvent` аргумент имеет значение `true`, операционная система отключает все события пробуждения.  
  
 В следующем примере кода показано, как перевести компьютер в спящий режим.  
  
 [!code-csharp[PowerMode#2](~/samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## <a name="see-also"></a>См. также

- <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>
- <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>
- <xref:System.Windows.Forms.Application.SetSuspendState%2A>
- <xref:Microsoft.Win32.SystemEvents.SessionSwitch>
