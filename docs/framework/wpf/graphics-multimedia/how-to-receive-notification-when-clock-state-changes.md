---
title: "Как: уведомить при часов &#39; s изменения состояния"
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
- clocks [WPF], notification of state changes
- notifications [WPF], clocks' state changes
ms.assetid: ecb10fc9-d0c2-45c3-b0a1-7b11baa733da
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f59fddb1add29d52ccba6fc8b8ce84938b53a1c2
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-receive-notification-when-a-clock39s-state-changes"></a>Как: уведомить при часов &#39; s изменения состояния
Часы <xref:System.Windows.Media.Animation.Clock.CurrentStateInvalidated> событие возникает при его <xref:System.Windows.Media.Animation.Clock.CurrentState%2A> становится недействительным, например при запуске или остановке часов. Можно зарегистрировать для этого события непосредственно с помощью <xref:System.Windows.Media.Animation.Clock>, или можно зарегистрировать с помощью <xref:System.Windows.Media.Animation.Timeline>.  
  
 В следующем примере <xref:System.Windows.Media.Animation.Storyboard> и два <xref:System.Windows.Media.Animation.DoubleAnimation> объекты используются для анимации ширины двух прямоугольников. <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> Событие используется для прослушивания изменений состояния часов.  
  
## <a name="example"></a>Пример  
 [!code-xaml[timingbehaviors_snip#_graphicsmm_StateExampleMarkupWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml#_graphicsmm_stateexamplemarkupwholepage)]  
  
 [!code-csharp[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/StateExample.xaml.cs#_graphicsmm_stateeventhandlers)]
 [!code-vb[timingbehaviors_snip#_graphicsmm_StateEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_snip/visualbasic/stateexample.xaml.vb#_graphicsmm_stateeventhandlers)]  
  
 На следующем рисунке показан различные состояния анимаций введите в качестве родительской временной шкалы (*раскадровки*) продвижения.  
  
 ![Синхронизация состояния для раскадровки с двумя анимациями](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-3timelines.png "graphicsmm_3timelines")  
  
 В следующей таблице показаны значения времени, по которому *Animation1* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> события:  
  
||||||||  
|-|-|-|-|-|-|-|  
|Время (в секундах)|1|10|19|21|30|39|  
|Регион|Активно|Активно|Остановлено|Активно|Активно|Остановлено|  
  
 В следующей таблице показаны значения времени, по которому *Animation2* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> события:  
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
|Время (в секундах)|1|9|11|19|21|29|31|39|  
|Регион|Активно|Заполнение|Активно|Остановлено|Активно|Заполнение|Активно|Остановлено|  
  
 Обратите внимание, что *Animation1* <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> событие запускается через 10 секунд, даже если его состояние остается <xref:System.Windows.Media.Animation.ClockState.Active>. Это, так как ее состояние изменилось на 10 секунд, но ее изменить <xref:System.Windows.Media.Animation.ClockState.Active> для <xref:System.Windows.Media.Animation.ClockState.Filling> и обратно <xref:System.Windows.Media.Animation.ClockState.Active> в же делений.
