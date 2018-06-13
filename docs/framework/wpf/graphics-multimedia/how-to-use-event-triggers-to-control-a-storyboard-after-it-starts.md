---
title: Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: c864668026c4f8bb58a4d6c4c36f96fb07445a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561298"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска
В этом примере показано, как управлять <xref:System.Windows.Media.Animation.Storyboard> после ее запуска. Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard>, которая распределяет анимацию для объектов и свойств и затем запускает раскадровку. Если вы предоставите <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав его <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> свойства, можно упростить управляемой раскадровки. Затем можно интерактивно управлять раскадровкой после ее запуска.  
  
 Используйте следующие действия раскадровки вместе с <xref:System.Windows.EventTrigger> объекты для управления раскадровкой.  
  
-   <xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.  
  
-   <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.  
  
-   <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровки в конец периода заполнения, если он есть.  
  
-   <xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.  
  
-   <xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождает ресурсы.  
  
## <a name="example"></a>Пример  
 В следующем примере управляемые действия раскадровки для интерактивного управления раскадровки.  
  
 **Примечание:** пример управления раскадровки с помощью кода, см. в разделе [управления раскадровки после его запуске с помощью его интерактивных методов](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 Дополнительные примеры см. в разделе [Коллекция примеров анимации](http://go.microsoft.com/fwlink/?LinkID=159969).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [Управление раскадровкой после ее запуска с помощью интерактивных методов](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о раскадровке](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
