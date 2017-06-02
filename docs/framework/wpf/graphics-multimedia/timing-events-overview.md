---
title: "Общие сведения о временных событиях | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Clock - класс"
  - "классы, часы"
  - "Временные шкалы"
  - "временные события"
ms.assetid: 597e3280-0867-4359-a97b-5b2f4149e350
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# Общие сведения о временных событиях
В этом разделе описываются способы использования пяти временных событий, доступных на <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> объектов.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Чтобы разобраться в этом разделе, необходимо понять, как создание и использование анимации. Чтобы начать работу с анимацией, см. раздел [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Существует несколько способов анимации свойств в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   **Использование объектов раскадровки** (разметка и код): можно использовать <xref:System.Windows.Media.Animation.Storyboard> объектов для упорядочения и распространять анимации для одного или нескольких объектов. Например, в разделе [анимация свойства с помощью раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md).  
  
-   **Использование локальных анимаций** (только код): можно применить <xref:System.Windows.Media.Animation.AnimationTimeline> объектов напрямую для свойств, которые они анимируют. Например, в разделе [анимация свойства без раскадровки](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
-   **С помощью часами** (только код): можно явно управлять создания часов и самостоятельно распределить часы анимации.  Например, в разделе [анимация свойства с помощью AnimationClock](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-an-animationclock.md).  
  
 Так как их можно использовать в разметки и кода, используйте примеры в этом обзоре <xref:System.Windows.Media.Animation.Storyboard> объектов. Тем не менее основные понятия, описанные может применяться к другим методам свойств анимации.  
  
### <a name="what-is-a-clock"></a>Что такое часов?  
 Временная шкала сама по себе фактически ничего не делает кроме как описывает сегмент времени. Это временной шкалы <xref:System.Windows.Media.Animation.Clock> объект, который содержит реальной работы: он обеспечивает состояние синхронизации для временной шкалы во время выполнения. В большинстве случаев, например при использовании раскадровок часы создаются автоматически для шкалы времени. Можно также создать <xref:System.Windows.Media.Animation.Clock> явным образом с помощью <xref:System.Windows.Media.Animation.Timeline.CreateClock%2A> метод. Дополнительные сведения о <xref:System.Windows.Media.Animation.Clock> объектов, в разделе [анимации и обзор системы времени](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md).  
  
## <a name="why-use-events"></a>Зачем использовать события?  
 За одним исключением (поиск с выравниванием по последнему делению), все интерактивные временные операции являются асинхронными. Никоим образом не узнать, только если они будут выполняться. Что может быть проблемой при наличии другого кода, зависящего от конкретной временной операции. Предположим, что было необходимо остановить временную шкалу, которая выполняла анимацию прямоугольника. После остановки шкалы времени цвет прямоугольника.  
  
 [!code-csharp[events_procedural#NeedForEventsFragment](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#needforeventsfragment)]
 [!code-vb[events_procedural#NeedForEventsFragment](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#needforeventsfragment)]  
  
 В предыдущем примере вторая строка кода может выполняться до остановки раскадровки. Это потому, что остановка является асинхронной операцией. О шкале времени или часам остановиться создает «запрос остановки» сортировки, не обрабатывается до следующего деления обработчика времени.  
  
 Для выполнения команд после завершения временной шкалы, используйте временные события. В следующем примере обработчик событий используется для изменения цвета прямоугольника после остановки воспроизведения раскадровки.  
  
 [!code-csharp[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#registerforstoryboardcurrentstateinvalidatedevent)]
 [!code-vb[events_procedural#RegisterForStoryboardCurrentStateInvalidatedEvent](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#registerforstoryboardcurrentstateinvalidatedevent)]  
[!code-csharp[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/events_procedural/CSharp/EventExample.cs#storyboardcurrentstateinvalidatedevent2)]
[!code-vb[events_procedural#StoryboardCurrentStateInvalidatedEvent2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/events_procedural/VisualBasic/EventExample.vb#storyboardcurrentstateinvalidatedevent2)]  
  
 Более полный пример см. в разделе [получать уведомления при часов изменения состояния](../../../../docs/framework/wpf/graphics-multimedia/how-to-receive-notification-when-clock-state-changes.md).  
  
## <a name="public-events"></a>Открытые события  
 <xref:System.Windows.Media.Animation.Timeline> и <xref:System.Windows.Media.Animation.Clock> оба класса предоставляют пять временных событий. В следующей таблице перечислены эти события и условия, которые вызывают их.  
  
|Событие|Вызывающая интерактивная операция|Другие триггеры|  
|-----------|--------------------------------------|--------------------|  
|**Завершено**|Переход к заполнению|Время истекло.|  
|**CurrentGlobalSpeedInvalidated**|Приостановить, возобновить, поиск, задание отношения скоростей, переход к заполнению, остановка|Часы обращает, ускоряет, запускает или останавливает.|  
|**CurrentStateInvalidated**|Начало, переход к заполнению, остановка|Запуск, остановка или заполняет часов.|  
|**CurrentTimeInvalidated**|Начало, поиск, переход к заполнению, остановка|Продвижение часов вперед.|  
|**RemoveRequested**|Удалить||  
  
## <a name="ticking-and-event-consolidation"></a>Временные такты и объединение событий  
 При анимации объектов в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], обработчик синхронизации управляет анимациями. Обработчик времени отслеживает ход времени и вычисляет состояние каждой анимации. Он выполняет много таких проходов вычислений в секунду. Эти проходы вычислений называются «тактах».  
  
 Пока тактов происходят часто, возможно, много всего произошло между тактами. Например временной шкалы может быть остановлена, запущена и остановлена еще раз, в этом случае его состояние будет изменено, три раза. Теоретически событие может вызываться несколько раз в одном такте. Однако временной механизм объединяет события, чтобы каждое событие может быть более одного раза одному такту.  
  
## <a name="registering-for-events"></a>Регистрация событий  
 Существует два способа регистрации временных событий: можно зарегистрировать со шкалой времени или с помощью часов, созданных на временной шкале. Регистрация события непосредственно с помощью часов является достаточно простой, хотя он может быть выполнено только из кода. Можно регистрировать события с помощью временной шкалы из разметки или кода. Следующий раздел описывает регистрировать события часов с помощью временной шкалы.  
  
<a name="registeringforclockeventswithatimeline"></a>   
## <a name="registering-for-clock-events-with-a-timeline"></a>Регистрация событий часов с помощью временной шкалы  
 Несмотря на то что временной шкалы <xref:System.Windows.Media.Animation.Timeline.Completed>, <xref:System.Windows.Media.Animation.Timeline.CurrentGlobalSpeedInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentStateInvalidated>, <xref:System.Windows.Media.Animation.Timeline.CurrentTimeInvalidated>, и <xref:System.Windows.Media.Animation.Timeline.RemoveRequested> события отображаются связываемое со шкалой, регистрация этих событий фактически связывает обработчик событий с <xref:System.Windows.Media.Animation.Clock> создан для временной шкалы.  
  
 При регистрации для <xref:System.Windows.Media.Animation.Timeline.Completed> события на временной шкале, например, фактически дается системы для регистрации <xref:System.Windows.Media.Animation.Clock.Completed> событий всех часов, созданный для временной шкалы. В коде, необходимо зарегистрировать для этого события перед <xref:System.Windows.Media.Animation.Clock> создан для этой шкалы времени; в противном случае — не будет получено уведомление. Это происходит автоматически в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]; средство синтаксического анализа автоматически регистрирует событие до <xref:System.Windows.Media.Animation.Clock> создается.  
  
## <a name="see-also"></a>См. также  
 [Анимации и обзор системы](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Обзор анимации](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Свойствах](../../../../docs/framework/wpf/graphics-multimedia/timing-behaviors-overview.md)