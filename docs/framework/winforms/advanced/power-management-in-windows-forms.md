---
title: "Power Management in Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "battery states"
  - "power states"
ms.assetid: ad04a801-5682-4d88-92c5-26eb9cdb209a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Power Management in Windows Forms
Приложения Windows Forms могут использовать функции управления питанием операционной системы Windows.  Приложения могут отслеживать состояние питания компьютера и принимать соответсвующие меры при изменении этого состояния.  Например, если приложение выполняется на переносном компьютере, можно отключить определенные функции приложения, когда заряд батареи падает ниже определенного уровня.  
  
 В среде [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] предусмотрено событие <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>, происходящее при изменении состояния питания, например при приостановке или возобновлении пользователем работы операционной системы, а также при изменении состояния питания от сети или уровня заряда батареи.  Для запроса текущего состояния может использоваться свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> класса <xref:System.Windows.Forms.SystemInformation>, как показано в следующем примере.  
  
 [!code-csharp[PowerMode#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#1)]
 [!code-vb[PowerMode#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#1)]  
  
 Помимо перечислений <xref:System.Windows.Forms.BatteryChargeStatus> свойство <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A> также содержит перечисления для определения заряда батареи \(<xref:System.Windows.Forms.PowerStatus.BatteryFullLifetime%2A>\) и процента заряда батареи \(<xref:System.Windows.Forms.PowerStatus.BatteryLifePercent%2A>, <xref:System.Windows.Forms.PowerStatus.BatteryLifeRemaining%2A>\).  
  
 Для перевода компьютера в спящий или ждущий режим можно использовать метод <xref:System.Windows.Forms.Application.SetSuspendState%2A> класса <xref:System.Windows.Forms.Application>.  Если для аргумента `force` установлено значение `false`, операционная система будет рассылать событие всем приложениям, запрашивая разрешение на приостановку.  Если для аргумента `disableWakeEvent` установлено значение `true`, операционная система отключает все события пробуждения.  
  
 В следующем примере кода демонстрируется перевод компьютера в спящий режим.  
  
 [!code-csharp[PowerMode#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/powermode/cs/form1.cs#2)]
 [!code-vb[PowerMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/powermode/vb/form1.vb#2)]  
  
## См. также  
 <xref:Microsoft.Win32.SystemEvents.PowerModeChanged>   
 <xref:System.Windows.Forms.SystemInformation.PowerStatus%2A>   
 <xref:System.Windows.Forms.Application.SetSuspendState%2A>   
 <xref:Microsoft.Win32.SystemEvents.SessionSwitch>