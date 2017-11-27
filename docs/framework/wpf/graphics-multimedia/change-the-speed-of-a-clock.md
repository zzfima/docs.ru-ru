---
title: "Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98cfa63eac4bc697c5412616de71395624408c63
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени
Объект <xref:System.Windows.Media.Animation.ClockController> объекта <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> свойства можно изменить скорость <xref:System.Windows.Media.Animation.Clock> без изменения <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> часов <xref:System.Windows.Media.Animation.Timeline>. В следующем примере <xref:System.Windows.Media.Animation.ClockController> используется для интерактивного изменения <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> часов. <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Событий и часов <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> свойства используются для отображения текущей глобальной скорости часов при каждом запуске интерактивного <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> изменяется.  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
