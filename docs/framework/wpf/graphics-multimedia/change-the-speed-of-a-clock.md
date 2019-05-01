---
title: Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- speed of Clock [WPF], changing
- clocks [WPF], changing speed of
ms.assetid: 72f36dd0-f085-445d-8589-19a83fe74f5e
ms.openlocfilehash: 19e6874b9b472cb4a5f716677f99af03f2b73b10
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010193"
---
# <a name="how-to-change-the-speed-of-a-clock-without-changing-the-speed-of-its-timeline"></a>Практическое руководство. Изменение скорости часов без изменения скорости шкалы времени
Объект <xref:System.Windows.Media.Animation.ClockController> объекта <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> свойства можно изменить скорость <xref:System.Windows.Media.Animation.Clock> без изменения <xref:System.Windows.Media.Animation.Timeline.SpeedRatio%2A> часов <xref:System.Windows.Media.Animation.Timeline>. В следующем примере <xref:System.Windows.Media.Animation.ClockController> используется для интерактивного изменения <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> часов. <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeedInvalidated> Событий и часов <xref:System.Windows.Media.Animation.Clock.CurrentGlobalSpeed%2A> свойства используются для отображения Текущая глобальная скорость часов при каждом запуске интерактивного <xref:System.Windows.Media.Animation.ClockController.SpeedRatio%2A> изменяется.  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerSpeedRatioExample.cs#graphicsmmclockcontrollerspeedratioexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerSpeedRatioExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerspeedratioexample.vb#graphicsmmclockcontrollerspeedratioexample)]
