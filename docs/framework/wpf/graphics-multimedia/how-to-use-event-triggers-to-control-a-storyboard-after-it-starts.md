---
title: Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 518f5d7ea0b5dc00677489f1383814563c565145
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186699"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Инструкция по Использованию Триггеров Событий для Управления Раскадровкой после ее Запуска

В этом примере <xref:System.Windows.Media.Animation.Storyboard> показано, как управлять запуском после его запуска. Для начала <xref:System.Windows.Media.Animation.Storyboard> с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]помощью, использование <xref:System.Windows.Media.Animation.BeginStoryboard>, который распределяет анимации на объекты и свойства, которые они анимировать, а затем запускает раскадровку. Если вы <xref:System.Windows.Media.Animation.BeginStoryboard> даете имя, <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> указывая его свойство, вы делаете его управляемым раскадровкой. Затем можно интерактивно управлять раскадровки после его запуска.

Используйте следующие действия <xref:System.Windows.EventTrigger> раскадровки вместе с объектами для управления раскадровкой.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Паузы раскадровки.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Продвигает раскадровку до конца периода заполнения, если он имеет один.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождая ресурсы.

## <a name="example"></a>Пример

В следующем примере используются управляемые действия раскадровки для интерактивного управления раскадровкой.

> [!NOTE]
> Чтобы увидеть пример управления раскадровкой с помощью кода, [см. Управление раскадровкой после того, как он начинает использовать свои интерактивные методы.](how-to-control-a-storyboard-after-it-starts.md)

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Дополнительные примеры можно найти в [галерее «Пример анимации».](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/AnimationExamples)

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Управление раскадровкой после ее запуска с помощью интерактивных методов](how-to-control-a-storyboard-after-it-starts.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
