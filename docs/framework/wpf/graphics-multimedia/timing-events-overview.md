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
ms.openlocfilehash: a48d1621e5568d556a1177578cc662813d70a283
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565491"
---
# <a name="timing-events-overview"></a>Общие сведения о временных событиях
В этом разделе описывается использование пять временных событий, доступных на <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> объектов.  
  
## <a name="prerequisites"></a>Предварительные требования  
 Для понимания этого раздела вы должны знать, как создавать и использовать анимации. Чтобы начать работу с анимацией, см. [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Существует несколько способов для анимации свойства в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Использование объектов раскадровки** (разметка и код): можно использовать <xref:System.Windows.Media.Animation.Storyboard> объектов упорядочить и распространять анимации на один или несколько объектов. Пример см. в разделе [анимации свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Использование локальных анимаций** (только код): можно применить <xref:System.Windows.Media.Animation.AnimationTimeline> объекты напрямую к свойствам, их которого должна начаться анимация. Пример см. в разделе [Анимация свойства без использования раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **Использование часов** (только в коде): вы можете явно управлять созданием часов и самостоятельно распределять часы для анимации.  Пример см. в разделе [анимировать свойство с помощью AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Так как их можно использовать в разметку и код, в примерах в этом обзоре используется <xref:System.Windows.Media.Animation.Storyboard> объектов. Тем не менее описанные здесь идеи также применяются к другим методам анимирования свойств.  
  
### <a name="what-is-a-clock"></a>Что такое часы?  
 Временная шкала сама по себе просто описывает сегмент времени. Он является временной шкалы <xref:System.Windows.Media.Animation.Clock> объект, который не работает: он обеспечивает состояние синхронизации для временной шкалы во время выполнения. В большинстве случаев, например при использовании раскадровок, часы для временной шкалы создаются автоматически. Можно также создать <xref:System.Windows.Media.Animation.Clock> явным образом с помощью <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> метод. Дополнительные сведения о <xref:System.Windows.Media.Animation.Clock> объектов, в разделе [анимации и общие сведения о синхронизации системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Зачем использовать события?  
 Все интерактивные временные операции являются асинхронными. Исключение составляет лишь поиск, который выравнивается по последнему такту. Точно определить, когда будут выполнены операции, невозможно. При наличии другого кода, который зависит от вашей операции, это может вызвать проблемы. Предположим, что вы хотите остановить временную шкалу, которая анимировала прямоугольник. После остановки временной шкалы вы изменяете цвет прямоугольника.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 В предыдущем примере вторая строка кода может быть выполнена до того, как раскадровка будет остановлена. Это вызвано тем, что остановка является асинхронной операцией. При отправке команды на остановку временной шкалы или часов создается своего рода "запрос на остановку". Этот запрос обрабатывается только на следующем такте системы управления временем.  
  
 Для выполнения команд после завершения временной шкалы используйте временные события. В следующем примере для изменения цвета прямоугольника после окончания воспроизведения раскадровки используется обработчик событий.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Более полный пример см. в разделе [изменения состояния получать уведомления при часов](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Открытые события  
 <xref:System.Windows.Media.Animation.Timeline> И <xref:System.Windows.Media.Animation.Clock> классы предоставляют пять временных событий. В следующей таблице перечислены эти события и условия, которые их вызывают.  
  
|событие|Интерактивная операция, вызывающая событие|Другие условия|  
|-----------|--------------------------------------|--------------------|  
|**Completed**|Переход к заполнению|Часы останавливаются.|  
|**CurrentGlobalSpeedInvalidated**|Пауза, возобновление, поиск, установка соотношения скорости, переход к заполнению|Часы запускаются в обратном направлении, ускоряются, запускаются в обычном направлении или останавливаются.|  
|**CurrentStateInvalidated**|Начало, переход к заполнению, остановка|Часы запускаются, останавливаются, или выполняется заполнение.|  
|**CurrentTimeInvalidated**|Начало, поиск, переход к заполнению, остановка|Часы работают.|  
|**RemoveRequested**|Удалить||  
  
## <a name="ticking-and-event-consolidation"></a>Такты и объединение событий  
 При анимации объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обработчик синхронизации управляет анимациями. Система управления временем отслеживает ход времени и вычисляет состояние каждой анимации. Она выполняет эти действия несколько раз в секунду. Такие вычислительные проходы называются "тактами".  
  
 Хотя такты меняются часто, между ними может возникать множество событий. Например, временная шкала может быть остановлена, запущена и снова остановлена, в этом случае ее состояние будет изменено три раза. Теоретически событие может вызываться несколько раз в одном такте. Однако система управления временем объединяет события, чтобы каждое событие могло происходить не более одного раза за такт.  
  
## <a name="registering-for-events"></a>Регистрация в событиях  
 Существует два способа регистрации временных событий: их можно зарегистрировать на временной шкале и на часах, созданных на основе временной шкалы. Регистрация события непосредственно на часах достаточно проста, но ее можно выполнить только в коде. Зарегистрировать события на временной шкале можно как в коде, так и в разметке. В следующем разделе описано, как зарегистрировать события часов на временной шкале.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Регистрация событий часов на временной шкале  
 Несмотря на то что временной шкалы <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, и <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> отображаются события, связываемое со шкалой, регистрация этих событий фактически связывает обработчик событий с <xref:System.Windows.Media.Animation.Clock> создать для временной шкалы.  
  
 При регистрации для <xref:System.Windows.Media.Animation.Timeline.Completed> события на временной шкале, например, фактически дается системы для регистрации <xref:System.Windows.Media.Animation.Clock.Completed> событий всех часов, созданный для временной шкалы. В коде, необходимо зарегистрировать для этого события перед <xref:System.Windows.Media.Animation.Clock> создается для этой шкалы времени; в противном случае не будет получено уведомление. Это происходит автоматически в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; средство синтаксического анализа автоматически регистрирует события, прежде чем <xref:System.Windows.Media.Animation.Clock> создается.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об анимации и системе управления временем](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)  
 [Общие сведения об эффектах анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Общие сведения о характере поведения во времени](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)
