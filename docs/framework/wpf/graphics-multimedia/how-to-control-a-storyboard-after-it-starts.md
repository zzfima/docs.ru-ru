---
title: Практическое руководство. Управление раскадровкой после ее запуска
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Storyboards [WPF], controlling after start
ms.assetid: 040f13f0-69f9-4ab5-be2b-079f4f80c7c0
ms.openlocfilehash: de30cfdb49df721cb4d6845dc67464e8a5b61f93
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855861"
---
# <a name="how-to-control-a-storyboard-after-it-starts"></a>Практическое руководство. Управление раскадровкой после ее запуска

В этом примере показано, как использовать код для управления <xref:System.Windows.Media.Animation.Storyboard> после его запуска. Для управления раскадровкой [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]в используйте <xref:System.Windows.Trigger> объекты <xref:System.Windows.TriggerAction> и. пример см. в разделе [Использование триггеров событий для управления раскадровкой после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

Для запуска раскадровки используется <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод, который распределяет анимации раскадровки по свойствам, которые они анимированы, и запускает раскадровку.

Чтобы сделать раскадровку управляемой, используйте <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> метод и укажите **значение true** в качестве второго параметра. Затем можно использовать интерактивные методы раскадровки, чтобы приостанавливать, возобновлять, искать, останавливать, ускорить или замедлить раскадровку, а также переключаться на свой период заполнения. Ниже приведен список интерактивных методов раскадровки:

- <xref:System.Windows.Media.Animation.Storyboard.Pause%2A>: Приостанавливает раскадровку.

- <xref:System.Windows.Media.Animation.Storyboard.Resume%2A>: Возобновляет приостановленную раскадровку.

- <xref:System.Windows.Media.Animation.Storyboard.SetSpeedRatio%2A>: Задает интерактивную скорость раскадровки.

- <xref:System.Windows.Media.Animation.Storyboard.Seek%2A>: Выполняет поиск раскадровки в указанном расположении.

- <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A>: Выполняет поиск раскадровки в указанном расположении. В отличие <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> от метода, эта операция обрабатывается до следующего тика.

- <xref:System.Windows.Media.Animation.Storyboard.SkipToFill%2A>: Переносит раскадровку на ее период заполнения, если она есть.

- <xref:System.Windows.Media.Animation.Storyboard.Stop%2A>: Останавливает раскадровку.

В следующем примере для интерактивного управления раскадровкой используются несколько методов раскадровки.

> [!NOTE]
> Пример управления раскадровкой с помощью триггеров с [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]см. в разделе [Использование триггеров событий для контроля раскадровки после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md).

## <a name="example"></a>Пример

[!code-csharp[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_procedural_snip/CSharp/ControlStoryboardExample.cs#controlstoryboardexampleusingwholepage)]
[!code-vb[timingbehaviors_procedural_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/timingbehaviors_procedural_snip/visualbasic/controlstoryboardexample.vb#controlstoryboardexampleusingwholepage)]

## <a name="see-also"></a>См. также

- [Использование триггеров событий для управления раскадровкой после ее запуска](how-to-use-event-triggers-to-control-a-storyboard-after-it-starts.md)
