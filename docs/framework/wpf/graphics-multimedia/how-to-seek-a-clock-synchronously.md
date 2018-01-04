---
title: "Практическое руководство. Установка часов в синхронном режиме"
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
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 90611e0b18e58e4c24b44e7c87cba56e4b0b01ad
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-seek-a-clock-synchronously"></a>Практическое руководство. Установка часов в синхронном режиме
Используйте <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> метод для часов на определенный момент в синхронном. В следующем примере показано, как <xref:System.Windows.Media.Animation.ClockController.Seek%2A> и <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> методы <xref:System.Windows.Media.Animation.ClockController>.  
  
 В этом примере показано, как осуществлять поиск <xref:System.Windows.Media.Animation.Clock>; пример, демонстрирующий установку раскадровки см. в разделе [поиска раскадровки синхронно](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Пример  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
