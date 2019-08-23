---
title: Практическое руководство. Управление часами в интерактивном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 2d18f395974750a6b85458f636a27f6101e7978f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69951339"
---
# <a name="how-to-interactively-control-a-clock"></a>Практическое руководство. Управление часами в интерактивном режиме
Свойство<xref:System.Windows.Media.Animation.ClockController>объектапозволяет интерактивно запускать, приостанавливать, возобновлять, искать, прерывать часы до периода заполнения и останавливать часы. <xref:System.Windows.Media.Animation.Clock> Только корневые часы дерева времени можно контролировать в интерактивном режиме.  
  
> [!NOTE]
> Существуют и другие способы интерактивного управления анимациями, которые не нуждаются в непосредственной работе с часами. можно также использовать раскадровки. Раскадровки поддерживаются как в разметке, так и в коде. Пример см. в разделе [анимация свойства с помощью](how-to-animate-a-property-by-using-a-storyboard.md) раскадровки или [обзора анимации](animation-overview.md).  
  
 В следующем примере несколько кнопок используются для интерактивного управления часами анимации.  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>См. также

- [Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
