---
title: Общие сведения о временных событиях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- timelines [WPF]
- timing events [WPF]
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
ms.openlocfilehash: ee45441e9ad09c60d8b61ecce4ef08b0027ce29e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145414"
---
# <a name="timing-events-overview"></a>Общие сведения о временных событиях
В этой теме описывается, как <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> использовать пять событий синхронизации, доступных на и объектов.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела вы должны знать, как создавать и использовать анимации. Чтобы начать работу с анимацией, смотрите [обзор анимации](animation-overview.md).  
  
 Есть несколько способов оживить [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]свойства в:  
  
- **Используя объекты раскадровки** (разметка и код): Вы можете использовать <xref:System.Windows.Media.Animation.Storyboard> объекты для организации и распространения анимации на один или несколько объектов. Например, см. [Animate a Property с помощью раскадровки.](how-to-animate-a-property-by-using-a-storyboard.md)  
  
- **Используя локальные анимации** (только <xref:System.Windows.Media.Animation.AnimationTimeline> код): Вы можете применять объекты непосредственно к свойствам, которые они анимируют. Например, [см. Animate a Property без использования раскадровки.](how-to-animate-a-property-without-using-a-storyboard.md)  
  
- **Использование часов** (только в коде): вы можете явно управлять созданием часов и самостоятельно распределять часы для анимации.  Например, см. [Animate свойства с помощью AnimationClock](how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Поскольку их можно использовать в разметке и <xref:System.Windows.Media.Animation.Storyboard> коде, примеры в этом обзоре используют объекты. Тем не менее описанные здесь идеи также применяются к другим методам анимирования свойств.  
  
### <a name="what-is-a-clock"></a>Что такое часы?  
 Временная шкала сама по себе просто описывает сегмент времени. Это <xref:System.Windows.Media.Animation.Clock> объект временной шкалы, который выполняет реальную работу: он поддерживает состояние времени выполнения для временной шкалы. В большинстве случаев, например при использовании раскадровок, часы для временной шкалы создаются автоматически. Вы также можете <xref:System.Windows.Media.Animation.Clock> создать явно <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> с помощью метода. Для получения <xref:System.Windows.Media.Animation.Clock> дополнительной информации об объектах, см. [Animation and Timing System Overview](animation-and-timing-system-overview.md)  
  
## <a name="why-use-events"></a>Зачем использовать события?  
 Все интерактивные временные операции являются асинхронными. Исключение составляет лишь поиск, который выравнивается по последнему такту. Точно определить, когда будут выполнены операции, невозможно. При наличии другого кода, который зависит от вашей операции, это может вызвать проблемы. Предположим, что вы хотите остановить временную шкалу, которая анимировала прямоугольник. После остановки временной шкалы вы изменяете цвет прямоугольника.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 В предыдущем примере вторая строка кода может быть выполнена до того, как раскадровка будет остановлена. Это вызвано тем, что остановка является асинхронной операцией. При отправке команды на остановку временной шкалы или часов создается своего рода "запрос на остановку". Этот запрос обрабатывается только на следующем такте системы управления временем.  
  
 Для выполнения команд после завершения временной шкалы используйте временные события. В следующем примере для изменения цвета прямоугольника после окончания воспроизведения раскадровки используется обработчик событий.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Для более полного [примера см. Получение уведомления при изменении состояния часов.](how-to-receive-notification-when-clock-state-changes.md)  
  
## <a name="public-events"></a>Открытые события  
 И <xref:System.Windows.Media.Animation.Timeline> <xref:System.Windows.Media.Animation.Clock> классы предоставляют пять событий синхронизации. В следующей таблице перечислены эти события и условия, которые их вызывают.  
  
|Событие|Интерактивная операция, вызывающая событие|Другие условия|  
|-----------|--------------------------------------|--------------------|  
|**Завершена**|Переход к заполнению|Часы останавливаются.|  
|**CurrentGlobalSpeedInvalidated**|Пауза, возобновление, поиск, установка соотношения скорости, переход к заполнению|Часы запускаются в обратном направлении, ускоряются, запускаются в обычном направлении или останавливаются.|  
|**CurrentStateInvalidated**|Начало, переход к заполнению, остановка|Часы запускаются, останавливаются, или выполняется заполнение.|  
|**CurrentTimeInvalidated**|Начало, поиск, переход к заполнению, остановка|Часы работают.|  
|**RemoveRequested**|Удалить||  
  
## <a name="ticking-and-event-consolidation"></a>Такты и объединение событий  
 Когда вы оживляют [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]объекты в, это механизм синхронизации, который управляет анимацией. Система управления временем отслеживает ход времени и вычисляет состояние каждой анимации. Она выполняет эти действия несколько раз в секунду. Такие вычислительные проходы называются "тактами".  
  
 Хотя такты меняются часто, между ними может возникать множество событий. Например, временная шкала может быть остановлена, запущена и снова остановлена, в этом случае ее состояние будет изменено три раза. Теоретически событие может вызываться несколько раз в одном такте. Однако система управления временем объединяет события, чтобы каждое событие могло происходить не более одного раза за такт.  
  
## <a name="registering-for-events"></a>Регистрация в событиях  
 Существует два способа регистрации временных событий: их можно зарегистрировать на временной шкале и на часах, созданных на основе временной шкалы. Регистрация события непосредственно на часах достаточно проста, но ее можно выполнить только в коде. Зарегистрировать события на временной шкале можно как в коде, так и в разметке. В следующем разделе описано, как зарегистрировать события часов на временной шкале.  
  
<a name="registeringforclockeventswithatimeline"></a>
## <a name="registering-for-clock-events-with-a-timeline"></a>Регистрация событий часов на временной шкале  
 Хотя <xref:System.Windows.Media.Animation.Timeline.Completed>шкала времени, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated> <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated> <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>и <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> события, как представляется, связаны с временной шкалой, регистрация <xref:System.Windows.Media.Animation.Clock> для этих событий фактически связывает обработчик событий с созданным для временной шкалы.  
  
 Например, при <xref:System.Windows.Media.Animation.Timeline.Completed> регистрации события в Хронике вы фактически говорите системе зарегистрироваться для <xref:System.Windows.Media.Animation.Clock.Completed> события каждого часа, созданного для временной шкалы. В коде необходимо зарегистрироваться для <xref:System.Windows.Media.Animation.Clock> этого события до создания для этой временной шкалы; в противном случае вы не получите уведомления. Это происходит [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]автоматически в ; парсер автоматически регистрируется для события <xref:System.Windows.Media.Animation.Clock> до создания.  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения об анимации и системе управления временем](animation-and-timing-system-overview.md)
- [Общие сведения об эффектах анимации](animation-overview.md)
- [Общие сведения о характере поведения во времени](timing-behaviors-overview.md)
