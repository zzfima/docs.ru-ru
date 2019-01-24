---
title: Как выполнить Управление раскадровкой после ее запуска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: 2fd9f34cdd6aac56ee5a29d972f18979292c69e0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570152"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Как выполнить Управление раскадровкой после ее запуска
В этом примере показано, как использовать код для управления <xref:System.Windows.Media.Animation.Storyboard> после ее запуска. Управление раскадровкой в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], использовать <xref:System.Windows.Trigger> и <xref:System.Windows.TriggerAction> объектов; например, см. в разделе [использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
 Чтобы запустить раскадровку, используйте его <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод, который распределяет анимации раскадровки в свойства и запускает раскадровку.  
  
 Чтобы сделать раскадровку управляемой, используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и указать **true** качестве второго параметра. Затем можно использовать интерактивные методы раскадровки для приостановки, возобновления, поиска, остановить, ускорить работу, или снизить скорость раскадровки или перейти к периоду заполнения. Ниже приведен список интерактивных методов раскадровки:  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Задает интерактивную скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Ищет указанное место раскадровки.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Поиск раскадровки в указанное расположение. В отличие от <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> метод, эта операция обрабатывается до следующий такт.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Перемещает раскадровку к периоду заполнения, если он имеется.  
  
-   <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Останавливает раскадровку.  
  
 В следующем примере несколько методов используются для интерактивного управления раскадровкой.  
  
 **Примечание.** Чтобы ознакомиться с примером раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], см. в разделе [использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).  
  
## <a name="example"></a>Пример  
 [!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
 [!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]  
  
## <a name="see-also"></a>См. также
- [Использование триггеров событий для управления раскадровкой после ее запуска](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
