---
title: Общие сведения о вложенных событиях
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handling attached events [WPF]
- defining attached events as routed events [WPF]
- attached events [WPF], scenarios for
- attached events vs. routed events [WPF]
- backing attached events with routed events [WPF]
- attached events [WPF], definition
ms.assetid: 2c40eae3-80e4-4a45-ae09-df6c9ab4d91e
ms.openlocfilehash: a3a2f711840ad7f6e28443dac3c18501cd4400e0
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/23/2019
ms.locfileid: "68401399"
---
# <a name="attached-events-overview"></a>Общие сведения о вложенных событиях
[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] определяет компонент языка и тип события, называемый *присоединенным событием*. Концепция присоединенного события позволяет добавить обработчик для конкретного события в произвольный элемент, а не в элемент, который фактически определяет или наследует событие. В этом случае ни объект, потенциально вызывающий событие, ни конечный обрабатывающий экземпляр не определяет или иным образом не "владеет" событием.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Предварительные требования  
 Предполагается, что вы ознакомились с разделами [Общие сведения о перенаправленных событиях](routed-events-overview.md) и [Обзор XAML (WPF)](xaml-overview-wpf.md).  
  
<a name="Syntax"></a>   
## <a name="attached-event-syntax"></a>Синтаксис присоединенных событий  
 Присоединенные события имеют синтаксис [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и шаблон кодирования, который должен использоваться резервным кодом для поддержки использования присоединенных событий.  
  
 В синтаксисе [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] присоединенное событие указывается не только по имени события, но и по типу владельца и имени события, разделенным символом точки (.). Так как имя события квалифицируется с помощью имени типа, которому оно принадлежит, синтаксис присоединенных событий позволяет подключить любое присоединенное событие к любому элементу, для которого может быть создан экземпляр.  
  
 Например, ниже приведен синтаксис [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] для подключения обработчика для пользовательского присоединенного события `NeedsCleaning`.  
  
 [!code-xaml[WPFAquariumSln#AE](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquarium/Window1.xaml#ae)]  
  
 Обратите внимание на префикс `aqua:`. Префикс необходим в этом случае, поскольку присоединенное событие является пользовательским событием, которое поступает из пользовательского сопоставленного xmlns.  
  
<a name="WPFImplements"></a>   
## <a name="how-wpf-implements-attached-events"></a>Реализация присоединенных событий в WPF  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]вложенные события поддерживаются <xref:System.Windows.RoutedEvent> полем и направляются через дерево после их возникновения. Как правило, источником присоединенного события (объектом, вызывающим событие) является система или служба, и таким образом, объект, который выполняет код, порождающий это событие, не является непосредственной частью дерева элементов.  
  
<a name="Scenarios"></a>   
## <a name="scenarios-for-attached-events"></a>Сценарии для присоединенных событий  
 В [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]вложенные события присутствуют в определенных функциональных областях, где существует абстракция уровня службы, например для событий, включенных статическим <xref:System.Windows.Input.Mouse> классом или <xref:System.Windows.Controls.Validation> классом. Классы, которые взаимодействуют со службой или используют ее, могут использовать событие в синтаксисе присоединенных событий или предоставить присоединенное событие как перенаправленное событие, которое является частью процесса интеграции возможностей службы классом.  
  
 Хотя [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] определяет количество присоединенных событий, ситуации, в которых вы будете использовать или обрабатывать присоединенное событие напрямую, очень ограничены. Как правило, присоединенное событие служит целью архитектуры, но затем перенаправляется в неприсоединенное (с помощью оболочки события CLR) перенаправленное событие.  
  
 Например, базовое присоединенное событие <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> может быть проще обработано в любом <xref:System.Windows.UIElement> заданном <xref:System.Windows.UIElement.MouseDown> с помощью <xref:System.Windows.UIElement> , вместо того чтобы обрабатываться с помощью синтаксиса вложенных событий в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] коде или. Присоединенное событие выполняет определенную роль в архитектуре, поскольку оно обеспечивает будущее расширение типов устройств ввода. Гипотетическому устройству пришлось бы вызывать <xref:System.Windows.Input.Mouse.MouseDown?displayProperty=nameWithType> только для имитации ввода с <xref:System.Windows.Input.Mouse> помощью мыши, а не для этого. Однако этот сценарий включает обработку кода события, а обработка [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] присоединенного события не относится к этому сценарию.  
  
<a name="Handling"></a>   
## <a name="handling-an-attached-event-in-wpf"></a>Обработка присоединенного события в WPF  
 Процесс для обработки присоединенного события и код обработчика, который вы будете писать, по сути аналогичны перенаправленному событию.  
  
 Как правило, присоединенное событие [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не сильно отличается от перенаправленного события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Различие заключается в выборе источника события и его представления классом в качестве члена (что также влияет на синтаксис обработчика [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]).  
  
 Тем не менее, как было отмечено ранее, существующие присоединенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] не предназначены для обработки в [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Гораздо чаще целью событий является включение составного элемента для передачи состояния в родительский элемент при компоновке. В этом случае событие обычно вызывается в коде и зависит от обработки класса в соответствующем родительском классе. Например, элементы <xref:System.Windows.Controls.Primitives.Selector> внутри a должны вызывать вложенное <xref:System.Windows.Controls.Primitives.Selector.Selected> событие, которое <xref:System.Windows.Controls.Primitives.Selector> затем обрабатывается классом и может быть преобразовано <xref:System.Windows.Controls.Primitives.Selector> классом в другое перенаправленное событие <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> . . Дополнительные сведения о перенаправленных событиях и обработке классов см. в разделе [Маркировка перенаправленных событий как обработанных и обработка классов](marking-routed-events-as-handled-and-class-handling.md).  
  
<a name="Custom"></a>   
## <a name="defining-your-own-attached-events-as-routed-events"></a>Определение собственных присоединенных событий как перенаправленных событий  
 При наследовании от общих базовых классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] можно реализовать собственные присоединенные события, включив определенные методы шаблонов в собственный класс и используя вспомогательные методы, которые уже присутствуют в базовых классах.  
  
 Шаблон выглядит следующим образом.  
  
- Метод **добавляет обработчик*EventName*** с двумя параметрами. Первый параметр — это экземпляр, в который добавляется обработчик событий. Второй параметр — это добавляемый обработчик событий. Метод должен иметь `public` значение и `static`, без возвращаемого значения.  
  
- Метод **удаляет обработчик*EventName*** с двумя параметрами. Первый параметр — это экземпляр, из которого удаляется обработчик событий. Второй параметр — это обработчик событий, который необходимо удалить. Метод должен иметь `public` значение и `static`, без возвращаемого значения.  
  
 Метод доступа **Add*ИмяСобытия*Handler** [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] упрощает обработку при объявлении атрибутов обработчика вложенных событий в элементе. Методы обработчика **Add*EventName*** и Remove ***EventName*** также обеспечивают доступ кода к хранилищу обработчиков событий для присоединенного события.  
  
 Этот общий шаблон еще недостаточно точен для практической реализации в структуре, поскольку реализация любого заданного модуля чтения [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] может иметь разные схемы для идентификации базовых событий в поддерживающем языке и архитектуре. Это одна из причин, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] по которой присоединенные события реализуются как перенаправляемые события; идентификатор, используемый для события (<xref:System.Windows.RoutedEvent>), уже определен [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] системой событий. Кроме того, перенаправление события является естественным расширением реализации для концепции уровня языка [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] присоединенного события.  
  
 Реализация **обработчика добавления*EventName*** для <xref:System.Windows.UIElement.AddHandler%2A> присоединенногособытиясостоитизвызоваметодасперенаправленнымсобытиемиобработчиком[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в качестве аргументов.  
  
 Эта стратегия реализации и система перенаправленных событий в целом ограничивают обработку присоединенных событий <xref:System.Windows.UIElement> производными классами или <xref:System.Windows.ContentElement> производными классами, так как <xref:System.Windows.UIElement.AddHandler%2A> только эти классы имеют реализации.  
  
 Например, следующий код определяет присоединенное событие `NeedsCleaning` в классе владельца`Aquarium`, используя стратегию присоединенных событий [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] для объявления присоединенного события как перенаправленного события.  
  
 [!code-csharp[WPFAquariumSln#AECode](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#aecode)]
 [!code-vb[WPFAquariumSln#AECode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#aecode)]  
  
 Обратите внимание, что метод, используемый для установления поля идентификатора <xref:System.Windows.EventManager.RegisterRoutedEvent%2A>присоединенного события, фактически является тем же методом, который используется для регистрации неприсоединенного перенаправленного события. Все присоединенные события и перенаправленные события регистрируются в централизованном внутреннем хранилище. Эта реализация хранилища событий обеспечивает поддержку режима "события в качестве интерфейса", который рассматривается в разделе [Общие сведения о перенаправленных событиях](routed-events-overview.md).  
  
<a name="Raising"></a>   
## <a name="raising-a-wpf-attached-event"></a>Вызов присоединенного события WPF  
 Как правило, вам не требуется вызывать существующие определенные присоединенные события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] в коде. Эти события следуют общей концептуальной модели службы, а классы служб, такие как <xref:System.Windows.Input.InputManager> , отвечают за создание событий.  
  
 Однако при определении пользовательского присоединенного события [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.RoutedEvent>, основанного на модели для создания присоединенных событий, можно использовать <xref:System.Windows.UIElement.RaiseEvent%2A> для вызова вложенного события из любого <xref:System.Windows.UIElement> или <xref:System.Windows.ContentElement>. Для вызова перенаправленного события (присоединенного или нет) требуется объявить конкретный элемент в дереве элементов в качестве источника события. Этот источник сообщается в <xref:System.Windows.UIElement.RaiseEvent%2A> качестве вызывающего. За определение того, какой элемент передается как источник в дереве, отвечает служба.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о перенаправленных событиях](routed-events-overview.md)
- [Подробное описание синтаксиса XAML](xaml-syntax-in-detail.md)
- [Код XAML и пользовательские классы для WPF](xaml-and-custom-classes-for-wpf.md)
