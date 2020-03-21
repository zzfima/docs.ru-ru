---
title: Общие сведения о базовых элементах
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 7d52d951d4fa4df83bbcca6b4cb479e18e532d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141632"
---
# <a name="base-elements-overview"></a>Общие сведения о базовых элементах
Высокий процент классов [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] в являются производными от четырех классов, которые обычно называются в документации SDK в качестве базовых классов элементов. Эти <xref:System.Windows.UIElement>классы, <xref:System.Windows.FrameworkElement> <xref:System.Windows.ContentElement>и <xref:System.Windows.FrameworkContentElement>. Класс <xref:System.Windows.DependencyObject> также связан, потому что это общий базовый класс как, <xref:System.Windows.UIElement> так и<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>Интерфейсы API базовых элементов в классах WPF  
 Оба <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> и являются <xref:System.Windows.DependencyObject>производными от , через несколько различных путей. Раскол на этом уровне посвящен <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> тому, как или используются в пользовательском интерфейсе и какую цель они служат в приложении. <xref:System.Windows.UIElement>также <xref:System.Windows.Media.Visual> имеет в своем классовой иерархии, которая является классом, который [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]предоставляет более низкого уровня графической поддержки, лежащей в основе . <xref:System.Windows.Media.Visual>обеспечивает платформу рендеринга, определяя независимые прямоугольные области экрана. На практике <xref:System.Windows.UIElement> для элементов, которые будут поддерживать более крупную модель объекта, предназначены для визуализации и компоновки в регионах, которые могут быть описаны как прямоугольные области экрана, и где модель содержимого намеренно более открыта, чтобы позволить различные комбинации элементов. <xref:System.Windows.ContentElement>не вытекает <xref:System.Windows.Media.Visual>из ; его модель заключается в том, что будет <xref:System.Windows.ContentElement> потребляться что-то другое, например, читатель или зритель, который затем интерпретировать элементы и производить полный <xref:System.Windows.Media.Visual> для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] потребления. Некоторые <xref:System.Windows.UIElement> классы предназначены для размещения содержимого: они предоставляют <xref:System.Windows.ContentElement> хостинг<xref:System.Windows.Controls.DocumentViewer> и рендеринг для одного или нескольких классов (является примером такого класса). <xref:System.Windows.ContentElement>используется в качестве базового класса для элементов с несколько меньшими моделями объектов <xref:System.Windows.UIElement>и что больше адрес текста, информации или содержимого документа, которые могут быть размещены в пределах .  
  
### <a name="framework-level-and-core-level"></a>Уровень платформы и уровень ядра  
 <xref:System.Windows.UIElement>служит базовым классом <xref:System.Windows.FrameworkElement> <xref:System.Windows.ContentElement> для, и служит <xref:System.Windows.FrameworkContentElement>базовым классом для . Причина этого следующего уровня классов заключается в поддержке базового уровня WPF, который отделен от рамочного уровня WPF, при этом разделение также существует в том, как AI делятся между сборками PresentationCore и PresentationFramework. Уровень платформы WPF предоставляет более полное удовлетворение потребностей основного приложения, включая реализацию диспетчера макетов для представления. Уровень ядра WPF позволяет использовать по максимуму возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], не прибегая к затратам на дополнительные сборки. Различие между этими уровнями очень редко имеет значение для большинства типичных [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] сценариев разработки приложений, и в целом следует думать об AA в целом и не касаться разницы между уровнем рамок WPF и базовым уровнем WPF. Различия в уровнях следует учитывать в том случае, если при разработке приложения решено заменить значительное количество функций уровня платформы WPF, например если общее решение уже имеет свои собственные реализации композиции и макета [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>Выбор элемента для наследования  
 Наиболее удобным способом создания другого класса, расширяющего возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является наследование от одного из классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Тогда вы получаете максимально возможное количество наследуемых функций благодаря существующей иерархии классов. В этом разделе перечислены возможности, предоставляемые тремя наиболее важными классами элементов. Эти сведения помогут вам решить, какой класс использовать для наследования.  
  
 Если вы внедряете элемент управления, который на самом деле [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] является одной из наиболее распространенных причин получения из класса, вы, вероятно, хотите извлечь из класса, который является практическим контролем, базовым классом управления, или, по крайней мере, из базового <xref:System.Windows.Controls.Control> класса. Некоторые рекомендации и практические примеры см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).  
  
 Если вы не создаете элемент управления, а хотите создать производный класс от класса, который находится выше по иерархии, в следующих разделах вы найдете рекомендации по определению характеристик для каждого базового класса элементов.  
  
 Если вы создаете класс, <xref:System.Windows.DependencyObject>который вытекает из, вы наследуете следующую функциональность:  
  
- <xref:System.Windows.DependencyObject.GetValue%2A>и <xref:System.Windows.DependencyObject.SetValue%2A> поддержку, и общую поддержку системы собственности.  
  
- Возможность использования свойств зависимостей и вложенных свойств, которые реализуются как свойства зависимостей.  
  
 Если вы создаете класс, <xref:System.Windows.UIElement>который вытекает из, вы наследуете следующие функциональные возможности в дополнение к этому, предоставляемые: <xref:System.Windows.DependencyObject>  
  
- Базовая поддержка для анимируемых значений свойств. Для получения дополнительной информации [см.](../graphics-multimedia/animation-overview.md)  
  
- Базовая поддержка событий ввода и поддержка команд. Дополнительные сведения см. в разделе [Общие сведения о вводе данных](input-overview.md) и [Общие сведения о системе команд](commanding-overview.md).  
  
- Виртуальные методы, которые можно переопределить для передачи данных в систему макета.  
  
 Если вы создаете класс, <xref:System.Windows.FrameworkElement>который вытекает из, вы наследуете следующие функциональные возможности в дополнение к этому, предоставляемые: <xref:System.Windows.UIElement>  
  
- Поддержка стилей и раскадровок. Для получения дополнительной <xref:System.Windows.Style> информации, [см.](../graphics-multimedia/storyboards-overview.md)  
  
- Поддержка привязки данных. Для получения дополнительной информации [см.](../data/data-binding-overview.md)  
  
- Поддержка ссылок на динамические ресурсы. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Поддержка наследования значений свойств и других флагов в метаданных, которые помогают передавать сведения о состоянии свойств в службы платформы, такие как привязка данных, управление стилями и реализация структуры макета. Дополнительные сведения см. в разделе [Метаданные свойств платформы](framework-property-metadata.md).  
  
- Понятие логического дерева. Дополнительные сведения см. в разделе [Деревья в WPF](trees-in-wpf.md).  
  
- Поддержка практической реализации системы макета на рамочном уровне WPF, включая <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> переопределение, которое может обнаруживать изменения в свойствах, влияющих на расположение.  
  
 Если вы создаете класс, <xref:System.Windows.ContentElement>который вытекает из, вы наследуете следующие функциональные возможности в дополнение к этому, предоставляемые: <xref:System.Windows.DependencyObject>  
  
- Поддержка анимации. Для получения дополнительной информации [см.](../graphics-multimedia/animation-overview.md)  
  
- Базовая поддержка событий ввода и поддержка команд. Дополнительные сведения см. в разделе [Общие сведения о вводе данных](input-overview.md) и [Общие сведения о системе команд](commanding-overview.md).  
  
 Если вы создаете класс, <xref:System.Windows.FrameworkContentElement>который вытекает из, вы получаете <xref:System.Windows.ContentElement>следующую функциональность в дополнение к этому, предоставленному:  
  
- Поддержка стилей и раскадровок. Для получения дополнительной <xref:System.Windows.Style> информации, [см.](../graphics-multimedia/animation-overview.md)  
  
- Поддержка привязки данных. Для получения дополнительной информации [см.](../data/data-binding-overview.md)  
  
- Поддержка ссылок на динамические ресурсы. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Поддержка наследования значений свойств и других флагов в метаданных, которые помогают передавать сведения о состоянии свойств в службы платформы, такие как привязка данных, управление стилями и реализация структуры макета. Дополнительные сведения см. в разделе [Метаданные свойств платформы](framework-property-metadata.md).  
  
- Вы не наследуете доступ к изменениям <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>системы макета (например). Реализация системы планировки <xref:System.Windows.FrameworkElement>доступна только на . Тем не менее, вы наследуете <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> переопределение, которое может обнаружить изменения в свойствах, влияющих на макет, и сообщать о них любым хостам содержимого.  
  
 Модели содержимого описаны в документации для различных классов. Модель содержимого, принятая для класса, возможно, является тем фактором, который следует рассмотреть при выборе подходящего класса для наследования. Дополнительные сведения см. в разделе [Модель содержимого WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>Другие базовые классы  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>обеспечивает поддержку [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] модели потоков и позволяет [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] всем объектам, созданным для приложений, <xref:System.Windows.Threading.Dispatcher>ассоциироваться с . Даже если вы не <xref:System.Windows.UIElement> <xref:System.Windows.DependencyObject>вытекают <xref:System.Windows.Media.Visual>из , или , <xref:System.Windows.Threading.DispatcherObject> вы должны рассмотреть вывод из для того, чтобы получить эту поддержку модели потоков. Дополнительные сведения см. в разделе [Модель потоков](threading-model.md).  
  
### <a name="visual"></a>Визуальный элемент  
 <xref:System.Windows.Media.Visual>реализует концепцию 2D-объекта, который обычно требует визуального представления в примерно прямоугольной области. Фактическое рендеринг <xref:System.Windows.Media.Visual> происходит в других классах (он не <xref:System.Windows.Media.Visual> является автономным), но класс предоставляет известный тип, который используется при визуализации процессов на различных уровнях. <xref:System.Windows.Media.Visual>реализует тестирование хит, но он не разоблачает события, <xref:System.Windows.UIElement>которые сообщают хит-тестирования срабатываний (они находятся в ). Дополнительные сведения см. в разделе [Программирование визуального слоя](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable>имитирует неизменяемость в изменяемом объекте, предоставляя средства для генерации копий объекта, когда неизменяемый объект требуется или желаемого по причинам производительности. Тип <xref:System.Windows.Freezable> обеспечивает общую основу для некоторых графических элементов, таких как геометрии и кисти, а также анимации. Примечательно, что <xref:System.Windows.Freezable> a <xref:System.Windows.Media.Visual>не является; он может содержать свойства, которые <xref:System.Windows.Freezable> становятся субсвойствами при применении для заполнения значения свойства другого объекта, и эти субсвойства могут повлиять на визуализацию. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>— <xref:System.Windows.Freezable> это производный класс, который специально добавляет слой управления анимацией и некоторые элементы утилиты, чтобы в настоящее время анимированные свойства можно отличить от неанимированных свойств.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control>является базовым классом для типа объекта, который по-разному называется элементом управления или компонентом, в зависимости от технологии. Как правило, классы элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] — это классы, которые либо непосредственно представляют элемент управления пользовательского интерфейса, либо близко участвуют в его композиции. Основной функциональностью, которая <xref:System.Windows.Controls.Control> позволяет это контроль шаблонов.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Controls.Control>
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Архитектура WPF](wpf-architecture.md)
