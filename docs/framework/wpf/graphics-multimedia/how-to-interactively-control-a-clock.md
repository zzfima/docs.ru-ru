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
ms.openlocfilehash: 6d3dbc8c39e63b46871b0cc88fbe8d5d51b63463
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361659"
---
# <a name="how-to-interactively-control-a-clock"></a>Практическое руководство. Управление часами в интерактивном режиме
Объект <xref:System.Windows.Media.Animation.Clock> объекта <xref:System.Windows.Media.Animation.ClockController> свойства можно в интерактивном режиме запуск, приостановка, возобновление, поиска, перемещать значение к периоду заполнения и остановить часы. Можно интерактивно управлять только корневые часы дерево временной шкалы.  
  
> [!NOTE]
>  Существуют другие способы интерактивного управления анимации, которые не требуется работать непосредственно с часов: можно также использовать раскадровки. Раскадровки поддерживаются в разметке и коде. Например, см. в разделе [анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md) или [Общие сведения об анимации](animation-overview.md).  
  
 В следующем примере несколько кнопок используются для интерактивного управления таймера анимации.  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>См. также
- [Анимация свойства с помощью раскадровки](how-to-animate-a-property-by-using-a-storyboard.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
