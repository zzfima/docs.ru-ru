---
title: Общие сведения о базовых элементах
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 6f8542be5a84a4b8b4cabf594c32d6fdfd3757d2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453766"
---
# <a name="base-elements-overview"></a>Общие сведения о базовых элементах
Большое количество классов в [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] являются производными от четырех классов, которые обычно называются в документации по [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] базовыми классами элементов. Этими классами являются <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>и <xref:System.Windows.FrameworkContentElement>. Класс <xref:System.Windows.DependencyObject> также связан, так как он является общим базовым классом как для <xref:System.Windows.UIElement>, так и для <xref:System.Windows.ContentElement>  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>Интерфейсы API базовых элементов в классах WPF  
 И <xref:System.Windows.UIElement>, и <xref:System.Windows.ContentElement> являются производными от <xref:System.Windows.DependencyObject>, через несколько разных путей. Разбиение на этом уровне работает с тем, как <xref:System.Windows.UIElement> или <xref:System.Windows.ContentElement> используются в пользовательском интерфейсе и какие цели они обслуживают в приложении. <xref:System.Windows.UIElement> также имеет <xref:System.Windows.Media.Visual> в своей иерархии классов, которая представляет собой класс, предоставляющий поддержку графики нижнего уровня, которая является базовой для [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> предоставляет платформу отрисовки, определяя независимые прямоугольные области экрана. На практике <xref:System.Windows.UIElement> для элементов, которые будут поддерживать более крупную объектную модель, предназначены для отрисовки и разметки в регионах, которые можно описать как прямоугольные области экрана, и где модель содержимого намеренно более открыта, чтобы разрешить различные сочетания элементов. <xref:System.Windows.ContentElement> не является производным от <xref:System.Windows.Media.Visual>; его модель заключается в том, что <xref:System.Windows.ContentElement> будет использоваться каким-либо другим, таким как читатель или средство просмотра, которое затем будет интерпретировать элементы и создать полную <xref:System.Windows.Media.Visual> для использования [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. Некоторые <xref:System.Windows.UIElement> классы предназначены для размещения содержимого: они предоставляют размещение и отрисовку для одного или нескольких классов <xref:System.Windows.ContentElement> (<xref:System.Windows.Controls.DocumentViewer> является примером такого класса). <xref:System.Windows.ContentElement> используется в качестве базового класса для элементов с небольшими объектными моделями и позволяет более подробно обращаться к тексту, информации или содержимому документа, которое может размещаться в <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Уровень платформы и уровень ядра  
 <xref:System.Windows.UIElement> выступает в качестве базового класса для <xref:System.Windows.FrameworkElement>, а <xref:System.Windows.ContentElement> выступает в качестве базового класса для <xref:System.Windows.FrameworkContentElement>. Причиной следующего уровня классов является поддержка уровня ядра WPF, отделенного от уровня платформы WPF. Кроме того, это разделение также существует в том, как интерфейсы API делятся между сборками PresentationCore и PresentationFramework. Уровень платформы WPF предоставляет более полное удовлетворение потребностей основного приложения, включая реализацию диспетчера макетов для представления. Уровень ядра WPF позволяет использовать по максимуму возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], не прибегая к затратам на дополнительные сборки. Различие между этими уровнями очень редко имеет значение для большинства типичных сценариев разработки приложений, и в целом следует рассматривать [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] API как единое целое, не заботясь о различиях между уровнями платформы WPF и уровня ядра WPF. Различия в уровнях следует учитывать в том случае, если при разработке приложения решено заменить значительное количество функций уровня платформы WPF, например если общее решение уже имеет свои собственные реализации композиции и макета [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Выбор элемента для наследования  
 Наиболее удобным способом создания другого класса, расширяющего возможности [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], является наследование от одного из классов [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Тогда вы получаете максимально возможное количество наследуемых функций благодаря существующей иерархии классов. В этом разделе перечислены возможности, предоставляемые тремя наиболее важными классами элементов. Эти сведения помогут вам решить, какой класс использовать для наследования.  
  
 Если вы реализуете элемент управления, который на самом деле является одной из наиболее распространенных причин для наследования от класса [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], вероятно, вам потребуется создать производный класс от класса, который является практическим элементом управления, базовым классом семейства элементов управления или по крайней мере из базового класса <xref:System.Windows.Controls.Control>. Некоторые рекомендации и практические примеры см. в разделе [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md).  
  
 Если вы не создаете элемент управления, а хотите создать производный класс от класса, который находится выше по иерархии, в следующих разделах вы найдете рекомендации по определению характеристик для каждого базового класса элементов.  
  
 При создании класса, производного от <xref:System.Windows.DependencyObject>, вы наследуете следующие функциональные возможности:  
  
- Поддержка <xref:System.Windows.DependencyObject.GetValue%2A> и <xref:System.Windows.DependencyObject.SetValue%2A> и общая поддержка системы свойств.  
  
- Возможность использования свойств зависимостей и вложенных свойств, которые реализуются как свойства зависимостей.  
  
 При создании класса, производного от <xref:System.Windows.UIElement>, вы наследуете следующие функциональные возможности, помимо предоставляемых <xref:System.Windows.DependencyObject>:  
  
- Базовая поддержка для анимируемых значений свойств. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md).  
  
- Базовая поддержка событий ввода и поддержка команд. Дополнительные сведения см. в разделе [Общие сведения о вводе данных](input-overview.md) и [Общие сведения о системе команд](commanding-overview.md).  
  
- Виртуальные методы, которые можно переопределить для передачи данных в систему макета.  
  
 При создании класса, производного от <xref:System.Windows.FrameworkElement>, вы наследуете следующие функциональные возможности, помимо предоставляемых <xref:System.Windows.UIElement>:  
  
- Поддержка стилей и раскадровок. Дополнительные сведения см. в разделе Обзор <xref:System.Windows.Style> и [раскадровок](../graphics-multimedia/storyboards-overview.md).  
  
- Поддержка привязки данных. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../data/data-binding-overview.md).  
  
- Поддержка ссылок на динамические ресурсы. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Поддержка наследования значений свойств и других флагов в метаданных, которые помогают передавать сведения о состоянии свойств в службы платформы, такие как привязка данных, управление стилями и реализация структуры макета. Дополнительные сведения см. в разделе [Метаданные свойств платформы](framework-property-metadata.md).  
  
- Понятие логического дерева. Дополнительные сведения см. в разделе [Деревья в WPF](trees-in-wpf.md).  
  
- Поддержка практической реализации системы макета на уровне платформы WPF, включая переопределение <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>, которое может обнаруживать изменения свойств, влияющих на макет.  
  
 При создании класса, производного от <xref:System.Windows.ContentElement>, вы наследуете следующие функциональные возможности, помимо предоставляемых <xref:System.Windows.DependencyObject>:  
  
- Поддержка анимации. Более подробную информацию см. в разделе [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md).  
  
- Базовая поддержка событий ввода и поддержка команд. Дополнительные сведения см. в разделе [Общие сведения о вводе данных](input-overview.md) и [Общие сведения о системе команд](commanding-overview.md).  
  
 При создании класса, производного от <xref:System.Windows.FrameworkContentElement>, вы получаете следующие функциональные возможности, помимо предоставляемых <xref:System.Windows.ContentElement>:  
  
- Поддержка стилей и раскадровок. Дополнительные сведения см. в разделе Обзор <xref:System.Windows.Style> и [анимации](../graphics-multimedia/animation-overview.md).  
  
- Поддержка привязки данных. Более подробную информацию см. в разделе [Общие сведения о связывании данных](../data/data-binding-overview.md).  
  
- Поддержка ссылок на динамические ресурсы. Дополнительные сведения см. в разделе [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Поддержка наследования значений свойств и других флагов в метаданных, которые помогают передавать сведения о состоянии свойств в службы платформы, такие как привязка данных, управление стилями и реализация структуры макета. Дополнительные сведения см. в разделе [Метаданные свойств платформы](framework-property-metadata.md).  
  
- Вы не наследуете доступ к изменениям системы макета (например, <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Реализации системы макета доступны только в <xref:System.Windows.FrameworkElement>. Однако вы наследуете переопределение <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A>, которое может обнаруживать изменения свойств, влияющих на макет, и передавать их на любые узлы содержимого.  
  
 Модели содержимого описаны в документации для различных классов. Модель содержимого, принятая для класса, возможно, является тем фактором, который следует рассмотреть при выборе подходящего класса для наследования. Дополнительные сведения см. в разделе [Модель содержимого WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Другие базовые классы  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> обеспечивает поддержку потоковой модели [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] и позволяет связывать все объекты, созданные для [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] приложений, с <xref:System.Windows.Threading.Dispatcher>. Даже если вы не наследуете от <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>или <xref:System.Windows.Media.Visual>, следует рассмотреть возможность наследования от <xref:System.Windows.Threading.DispatcherObject>, чтобы обеспечить поддержку этой потоковой модели. Дополнительные сведения см. в разделе [Модель потоков](threading-model.md).  
  
### <a name="visual"></a>Визуальный элемент  
 <xref:System.Windows.Media.Visual> реализует концепцию 2D-объекта, который обычно требует визуального представления в примерно прямоугольной области. Фактическая визуализация <xref:System.Windows.Media.Visual> происходит в других классах (он не является автономным), но класс <xref:System.Windows.Media.Visual> предоставляет известный тип, используемый процессами отрисовки на различных уровнях. <xref:System.Windows.Media.Visual> реализует проверку попадания, но не предоставляет события, которые сообщают о положительных проверках на попадание (они находятся в <xref:System.Windows.UIElement>). Дополнительные сведения см. в разделе [Программирование визуального слоя](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Freezable  
 <xref:System.Windows.Freezable> имитирует неизменность в изменяемом объекте, предоставляя средства для создания копий объекта, если Неизменяемый объект является обязательным или требуется для повышения производительности. Тип <xref:System.Windows.Freezable> предоставляет общую базу для определенных графических элементов, таких как геометрические объекты и кисти, а также анимации. Особенно, <xref:System.Windows.Freezable> не является <xref:System.Windows.Media.Visual>; Он может содержать свойства, которые становятся подсвойствами, когда <xref:System.Windows.Freezable> применяется для заполнения значения свойства другого объекта, и эти подсвойства могут повлиять на отрисовку. Дополнительные сведения см. в разделе [Общие сведения об объектах класса Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> — это <xref:System.Windows.Freezable> производный класс, который специально добавляет слой управления анимацией и некоторые служебные элементы, чтобы в настоящее время анимированные свойства можно было отличать от неанимированных свойств.  
  
### <a name="control"></a>Элемент управления  
 <xref:System.Windows.Controls.Control> является предполагаемым базовым классом для типа объекта, для которого в зависимости от технологии используется термин «элемент управления» или «компонент». Как правило, классы элементов управления [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] — это классы, которые либо непосредственно представляют элемент управления пользовательского интерфейса, либо близко участвуют в его композиции. Основные функциональные возможности, которые <xref:System.Windows.Controls.Control> позволяют, — это шаблоны элементов управления.  
  
## <a name="see-also"></a>См. также

- <xref:System.Windows.Controls.Control>
- [Общие сведения о свойствах зависимости](dependency-properties-overview.md)
- [Общие сведения о разработке элементов управления](../controls/control-authoring-overview.md)
- [Архитектура WPF](wpf-architecture.md)
