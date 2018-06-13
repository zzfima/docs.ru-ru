---
title: Как управлять раскадровкой после ее запуска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2407de5029007748de691a3020078b1241b02fd4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561466"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Как управлять раскадровкой после ее запуска
В этом примере показано, как использовать код для управления <xref:System.Windows.Media.Animation.Storyboard> после его начала. Для управления раскадровки в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Trigger> и <xref:System.Windows.TriggerAction> объектов; например, в разделе [использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Чтобы запустить раскадровку, используйте его <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод, который распределяет анимации раскадровки со свойствами и запускает раскадровкой.  
  
 Чтобы сделать раскадровку управляемой, используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и укажите **true** качестве второго параметра. Затем можно использовать интерактивные методы раскадровки можно приостановить, возобновить, поиска, остановки, ускорения, или замедления раскадровки или перевести ее периода заполнения. Ниже приведен список интерактивных методов раскадровки:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Задает интерактивную скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Ищет указанное место раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Ищет раскадровку в указанном месте. В отличие от <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метод, эта операция обрабатывается до следующего такта.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Перемещает раскадровку до периода заполнения, если оно имеется.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Останавливает раскадровку.  
  
 В следующем примере несколько методов используются для интерактивного управления раскадровкой.  
  
 **Примечание:** пример раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], в разделе [использования триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>См. также  
 [Использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
