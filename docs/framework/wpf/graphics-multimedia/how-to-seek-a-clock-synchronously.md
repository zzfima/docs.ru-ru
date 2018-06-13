---
title: Практическое руководство. Установка часов в синхронном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- clocks [WPF], seeking synchronously
- seeking clocks synchronously [WPF]
ms.assetid: e5b7529b-b7d0-40d2-9e1d-fa4b5e736e96
ms.openlocfilehash: d8e7b0f4bfa3a59814d87bfb6d7e8b40bd80f6e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559860"
---
# <a name="how-to-seek-a-clock-synchronously"></a>Практическое руководство. Установка часов в синхронном режиме
Используйте <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> метод для часов на определенный момент в синхронном. В следующем примере показано, как <xref:System.Windows.Media.Animation.ClockController.Seek%2A> и <xref:System.Windows.Media.Animation.ClockController.SeekAlignedToLastTick%2A> методы <xref:System.Windows.Media.Animation.ClockController>.  
  
 В этом примере показано, как осуществлять поиск <xref:System.Windows.Media.Animation.Clock>; пример, демонстрирующий установку раскадровки см. в разделе [поиска раскадровки синхронно](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md) .  
  
## <a name="example"></a>Пример  
 [!code-csharp[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClockController_procedural_snip/CSharp/SeekAlignedToLastTickExample.cs#clockcontrollerseekexample)]
 [!code-vb[ClockController_procedural_snip#ClockControllerSeekExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClockController_procedural_snip/visualbasic/seekalignedtolasttickexample.vb#clockcontrollerseekexample)]
