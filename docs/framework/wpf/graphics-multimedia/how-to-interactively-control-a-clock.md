---
title: Как выполнить Управление часами в интерактивном режиме
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controlling clocks interactively [WPF]
- clocks [WPF], controlling interactively
ms.assetid: d0b520e0-2f18-4cef-977f-2909e709548a
ms.openlocfilehash: 93c2d754ec899c96a50fef3dcef680434f564276
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657549"
---
# <a name="how-to-interactively-control-a-clock"></a>Как выполнить Управление часами в интерактивном режиме
Объект <xref:System.Windows.Media.Animation.Clock> объекта <xref:System.Windows.Media.Animation.ClockController> свойства можно в интерактивном режиме запуск, приостановка, возобновление, поиска, перемещать значение к периоду заполнения и остановить часы. Можно интерактивно управлять только корневые часы дерево временной шкалы.  
  
> [!NOTE]
>  Существуют другие способы интерактивного управления анимации, которые не требуется работать непосредственно с часов: можно также использовать раскадровки. Раскадровки поддерживаются в разметке и коде. Например, см. в разделе [анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md) или [Общие сведения об анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 В следующем примере несколько кнопок используются для интерактивного управления таймера анимации.  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ClockControllerExample.cs#graphicsmmclockcontrollerexample)]
 [!code-vb[timingbehaviors_procedural_snip#GraphicsMMClockControllerExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/clockcontrollerexample.vb#graphicsmmclockcontrollerexample)]  
  
## <a name="see-also"></a>См. также
- [Анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)
- [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
