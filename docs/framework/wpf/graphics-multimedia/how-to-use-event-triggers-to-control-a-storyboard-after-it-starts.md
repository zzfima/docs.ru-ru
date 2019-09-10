---
title: Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: 32591edd065a8122b84ff14102f672ccf6001d67
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855851"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a>Практическое руководство. Использование триггеров событий для управления раскадровкой после ее запуска

В этом примере показано, <xref:System.Windows.Media.Animation.Storyboard> как управлять после запуска. Чтобы запустить <xref:System.Windows.Media.Animation.Storyboard> с помощью [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], используйте <xref:System.Windows.Media.Animation.BeginStoryboard>, который распространяет анимации на объекты и свойства, которые они анимированы, а затем запускает раскадровку. Если вы придаете <xref:System.Windows.Media.Animation.BeginStoryboard> имя, указав <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> его свойство, вы сделаете его управляемой раскадровкой. Затем можно интерактивно управлять раскадровкой после ее запуска.

Используйте следующие действия раскадровки вместе <xref:System.Windows.EventTrigger> с объектами для управления раскадровкой.

- <xref:System.Windows.Media.Animation.PauseStoryboard>: Приостанавливает раскадровку.

- <xref:System.Windows.Media.Animation.ResumeStoryboard>: Возобновляет приостановленную раскадровку.

- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Изменяет скорость раскадровки.

- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Перемещает раскадровку в конец периода заполнения, если он имеет значение.

- <xref:System.Windows.Media.Animation.StopStoryboard>: Останавливает раскадровку.

- <xref:System.Windows.Media.Animation.RemoveStoryboard>: Удаляет раскадровку, освобождая ресурсы.

## <a name="example"></a>Пример

В следующем примере используются управляемые действия раскадровки для интерактивного управления раскадровкой.

> [!NOTE]
> Пример управления раскадровкой с помощью кода см. в разделе [Управление раскадровкой после ее запуска с помощью интерактивных методов](how-to-control-a-storyboard-after-it-starts.md).

[!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]

Дополнительные примеры см. в разделе [Коллекция примеров анимации](https://go.microsoft.com/fwlink/?LinkID=159969).

## <a name="see-also"></a>См. также

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [Управление раскадровкой после ее запуска с помощью интерактивных методов](how-to-control-a-storyboard-after-it-starts.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о раскадровке](storyboards-overview.md)
